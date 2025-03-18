# Install and load required packages
install.packages("rvest")
install.packages("dplyr")
install.packages("glmnet")
library(rvest)
library(dplyr)

#The file path
file_path <- "C:/Users/User/Downloads/2017.csv"

# Read the CSV file into R
data <- read.csv(file_path)

View(data)

#From Wikipedia
url <- "https://en.wikipedia.org/wiki/List_of_countries_by_income_equality"
webpage <- read_html(url)
# Inspect the structure of the webpage to identify the correct table
tables <- webpage %>% html_nodes("table")
length(tables)
# Extract the table we are interested in
table <- tables[[2]] %>% html_table(fill = TRUE)
head(table)
colnames(table)
colnames(table) <- make.unique(colnames(table))
colnames(table)
dim(table)
gini_data <- table %>%
  select( `Country`,  `World Bank Gini[5][6]`)

# We have downloaded the wikipedia table now we merge them into a single data
file_path <- "C:/Users/User/Downloads/2017.csv"
existing_data <- read.csv(file_path)
head(existing_data)
# Merge the existing data with the Gini data
merged_data <- merge(existing_data, gini_data, by.x = "Country", by.y = "Country", all.x = TRUE)
# Display the first few rows of the merged data
View(merged_data)

#Scatter plot
install.packages("ggplot2")
library(ggplot2)
ggplot(merged_data, aes(x = Economy..GDP.per.Capita., y = Happiness.Score)) +geom_point() +labs(title = "Scatter Plot of Score vs GDP", x = "GDP",
       y = "Score")

#linear model
library(dplyr)
merged_data <- merged_data %>%
  rename(
    gdp = Economy..GDP.per.Capita.,
    gini_index = `World Bank Gini[5][6]`,
    family = Family,
    happiness_score = Happiness.Score
  )
View(merged_data)
merged_data$gini_index <- as.numeric(merged_data$gini_index)
cat("Missing values in gini_index: ", sum(is.na(merged_data$gini_index)), "\n")
# Filter rows where gini_index is NA and select the Country column
countries_with_na_gini <- merged_data %>%
  filter(is.na(gini_index)) %>%
  select(Country)
print(countries_with_na_gini)
merged_data <- merged_data %>%
  mutate(gini_index = case_when(
 Country == "Afghanistan" ~ 41,Country == "Bahrain" ~ 44.3,
 Country == "Congo (Brazzaville)" ~ 48.9,    
 Country == "Congo (Kinshasa)" ~ 42,
 Country == "Hong Kong S.A.R., China" ~ 49.9,  
 Country == "Kuwait" ~ 47.1,  
 Country == "Libya" ~ 44.1,  
 Country == "Macedonia" ~ 68.2, 
 Country == "North Cyprus" ~ 68.5,  
 Country == "Palestinian Territories" ~ 33.7,  
 Country == "Taiwan Province of China" ~ 34.2,  
 TRUE ~ gini_index  # Retain the existing value for other countries
  ))
View(merged_data)
str(merged_data)

library(ggcorrplot)

# FIRST HEAT MAP
numeric_data <- merged_data[, sapply(merged_data, is.numeric)]

# Calculate correlation matrix
correlation_matrix <- cor(numeric_data)
ggcorrplot(
  correlation_matrix,
  type = "upper",
  colors = c("darkred", "white", "darkred"),  # Set the color to blue
  lab = TRUE,  # Show labels
  lab_size = 3,  # Set label size
  show.diag = FALSE, # Do not show values in the diagonal
) +
  theme(
    panel.grid = element_blank(),  # Remove the grid
    panel.border = element_blank()  # Remove the panel border if needed
  )


# Extracting numerical variables
numerical_vars <- sapply(merged_data, is.numeric)

# Selecting only numerical variables
numerical_data <- merged_data[, numerical_vars]
names(numeric_data)

par(mfrow = c(3, 2))
# Plotting each numerical variable against happiness score
for (var in names(numerical_data)) {
    plot(x = numerical_data[[var]], y = numerical_data$happiness_score,
         main = paste("Scatter plot of", var, "vs. happiness score"),
         xlab = var, ylab = "Happiness Score",
         pch = 19, col = "blue")
    abline(lm(numerical_data$happiness_score ~ numerical_data[[var]]), col = "red")
    # Optionally, you can add a regression line
  }





#Split the data into 80% for training and 20% for validation
set.seed(100)
split=sample(1:2, nrow(merged_data), replace = TRUE, prob=c(0.8, 0.2))
train=merged_data[split==1, ]
val=merged_data[split==2, ] 

acc_error<- function(actual,pred){
  mape <- mean(abs((actual - pred)/actual))*100
  mae=mean(abs(actual-pred))
  RMSE= sqrt(mean((actual-pred)^2))
  vec=c(mape,mae, RMSE) 
  names(vec)= c("MAPE", "MAE", "RMSE")
  return(vec)
}
summary(train$happiness_score)
summary(val$happiness_score)

#1- model
model1 <- lm(happiness_score ~ gdp + gini_index + family, data = train)
summary(model1)
#train evaluation
train_predictions1 <- predict(model1, newdata = train)
train_perform1=acc_error(train$happiness_score, train_predictions1)
train_perform1
#evaluation on the validation set 
val_predictions1 <- predict(model1, newdata = val)
perform1=acc_error(val$happiness_score, val_predictions1)
perform1


#2-Model with all the variables (except whisker low/high):
model2 <- lm(happiness_score ~ gdp +Health..Life.Expectancy.+ Freedom + Generosity + Trust..Government.Corruption.+ Dystopia.Residual+ gini_index + family, data = train)
summary(model2)
#train evaluation
train_predictions2 <- predict(model2, newdata = train)
train_perform2=acc_error(train$happiness_score, train_predictions2)
train_perform2
#evaluation on the validation set 
val_predictions2 <- predict(model2, newdata = val)
perform2=acc_error(val$happiness_score, val_predictions2)
perform2




#Highly correlated 
#3-Model with all the  correlated variables 
model3 <- lm(happiness_score ~ gdp +Health..Life.Expectancy.+ Freedom + family, data = train)
summary(model3)
#train evaluation
train_predictions3 <- predict(model3, newdata = train)
train_perform3=acc_error(train$happiness_score, train_predictions3)
train_perform3
#evaluation on the validation set 
val_predictions3 <- predict(model3, newdata = val)
perform3=acc_error(val$happiness_score, val_predictions3)
perform3

#4-New model adding to the previous one gini_index 
model4 <- lm(happiness_score ~ gdp +Health..Life.Expectancy. +Freedom
               +gini_index+ family, data = train)
summary(model4)
#train evaluation
train_predictions4 <- predict(model4, newdata = train)
train_perform4=acc_error(train$happiness_score, train_predictions4)
train_perform4
#evaluation on the validation set 
val_predictions4 <- predict(model4, newdata = val)
perform4=acc_error(val$happiness_score, val_predictions4)
perform4


summary_table1 <- data.frame(
  Model = c("Linear Model 1", "Linear Model 2", "Linear Model 3", "Linear Model 4"),
  Num_Variables = c(3, 8, 4, 5,),
  Train_RMSE = c(0.6010893, 0.0002825236, 0.5069923, 0.5060438),
  Val_RMSE = c(0.5023825 , 0.0002664727 , 0.4582873, 0.4577640 ),
  Adj_R_Squared = c(0.7082, 1.00, 0.7907, 0.7897 )
)
print(summary_table1)


#load necessary library
library(glmnet)
# 1-Extract the response variable and predictors
y <- train$happiness_score
x1 <- as.matrix(train[, c("gdp", "gini_index", "family")])

# Set up a grid for lambda
lambda_grid <- 10^seq(-3, 1, length = 100)

# Perform Lasso regression with 5-fold cross-validation
cv_fit1 <- cv.glmnet(x1, y, alpha = 1, lambda = lambda_grid, nfolds = 5)

# Function to calculate RMSE
calculate_rmse <- function(actual, predicted) {
  sqrt(mean((actual - predicted)^2))
}

# Store RMSE values
rmse_values1 <- numeric(length(cv_fit1$lambda))
# Calculate RMSE for each lambda
for (i in 1:length(cv_fit1$lambda)) {
  lasso_model1  <- glmnet(x1, y, alpha = 1, lambda = cv_fit1$lambda[i])
  predictions1 <- predict(lasso_model1, x1)
  rmse_values1[i] <- calculate_rmse(y, predictions1)
}

# Combine lambda and RMSE values in a data frame
results1 <- data.frame(lambda = cv_fit1$lambda, RMSE = rmse_values1)

# Display the results
print(results1)
#test the lambda 
lambda_best <- cv_fit1$lambda.min
lambda_best
library(caret)
library(glmnet)
# Specify the tuning grid
tuning_grid1 <- expand.grid(alpha = 1, lambda = lambda_best)
train_control <- trainControl(method = "cv", number = 5)
# Train Lasso regression model with specified lambda value
cv_model1 <- train(happiness_score ~ gdp + gini_index + family, 
                  data = train, 
                  method = "glmnet",
                  trControl = train_control,
                  tuneGrid = tuning_grid1)

# Print the model
print(cv_model1)
# Extract the glmnet model object from the train object on each fold 
lasso_model1 <- cv_model1$finalModel
# View coefficients(each fold)
coef(lasso_model1)

# 2- Extract the response variable and predictors
y <- train$happiness_score
x2 <- as.matrix(train[, c("gdp","family","Freedom","gini_index","Health..Life.Expectancy.")])

# Set up a grid for lambda
lambda_grid <- 10^seq(-3, 1, length = 100)

# Perform Lasso regression with 5-fold cross-validation
cv_fit2 <- cv.glmnet(x2, y, alpha = 1, lambda = lambda_grid, nfolds = 5)
# Function to calculate RMSE
calculate_rmse <- function(actual, predicted) {
  sqrt(mean((actual - predicted)^2))
}

# Store RMSE values
rmse_values2 <- numeric(length(cv_fit2$lambda))

# Calculate RMSE for each lambda
for (i in 1:length(cv_fit2$lambda)) {
  lasso_model2 <- glmnet(x2, y, alpha = 1, lambda = cv_fit2$lambda[i])
  predictions2 <- predict(lasso_model2, x2)
  rmse_values2[i] <- calculate_rmse(y, predictions2)
}

# Combine lambda and RMSE values in a data frame
results2 <- data.frame(lambda = cv_fit2$lambda, RMSE = rmse_values2)

# Display the results
print(results2)


#test the lambda 
lambda_bestt <- cv_fit2$lambda.min
lambda_bestt
library(caret)
library(glmnet)
# Specify the tuning grid
tuning_grid2 <- expand.grid(alpha = 1, lambda = lambda_bestt)
train_control <- trainControl(method = "cv", number = 5)
# Train Lasso regression model with specified lambda value
cv_model2 <- train(happiness_score ~ gdp +Health..Life.Expectancy.+  family+Freedom+gini_index, 
                   data = train, 
                   method = "glmnet",
                   trControl = train_control,
                   tuneGrid = tuning_grid2)

# Print the model
print(cv_model2)
# Extract the glmnet model object from the train object on each fold 
lasso_model2 <- cv_model2$finalModel
# View coefficients(each fold)
coef(lasso_model2)

#3- Extract the response variable and predictors
y <- train$happiness_score
x3 <- as.matrix(train[, c("gdp", "Freedom", "family","Health..Life.Expectancy.")])

# Set up a grid for lambda
lambda_grid <- 10^seq(-3, 1, length = 100)

# Perform Lasso regression with 5-fold cross-validation
cv_fit3 <- cv.glmnet(x3, y, alpha = 1, lambda = lambda_grid, nfolds = 5)

# Function to calculate RMSE
calculate_rmse <- function(actual, predicted) {
  sqrt(mean((actual - predicted)^2))
}

# Store RMSE values
rmse_values3 <- numeric(length(cv_fit3$lambda))

# Calculate RMSE for each lambda
for (i in 1:length(cv_fit3$lambda)) {
  lasso_model3 <- glmnet(x3, y, alpha = 1, lambda = cv_fit3$lambda[i])
  predictions3 <- predict(lasso_model3, x3)
  rmse_values3[i] <- calculate_rmse(y, predictions3)
}

# Combine lambda and RMSE values in a data frame
results3 <- data.frame(lambda = cv_fit3$lambda, RMSE = rmse_values3)

# Display the results
print(results3)
#test the lambda 
lambda_besttt <- cv_fit3$lambda.min
lambda_besttt
library(caret)
library(glmnet)
# Specify the tuning grid
tuning_grid3 <- expand.grid(alpha = 1, lambda = lambda_besttt)

# Train Lasso regression model with specified lambda value
cv_model3 <- train(happiness_score ~ gdp + Freedom + family+Health..Life.Expectancy., 
                  data = train, 
                  method = "glmnet",
                  trControl = train_control,
                  tuneGrid = tuning_grid3)

# Print the model
print(cv_model3)
# Extract the glmnet model object from the train object on each fold 
lasso_model3 <- cv_model3$finalModel
# View coefficients(each fold)
coef(lasso_model3)

#summarytable

summary_table2 <- data.frame(
  Model = c("Lasso Model 1", "Lasso Model 2", "Lasso Model 3"),
  Num_Variables = c(3, 5, 4),
  Train_RMSE = c(0.6113141, 0.5303394,0.5250623),
  Adj_R_Squared = c( 0.7208953,0.7781193 ,0.798708)
)
print(summary_table2)

#evaluation on the validation set for the best lasso model chosen 
val_predictionsCV3 <- predict(cv_model3, newdata = val)
performCV3=acc_error(val$happiness_score, val_predictionsCV3)
performCV3

