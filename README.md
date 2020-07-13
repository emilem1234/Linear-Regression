######summarizes key information about statistical objects in tidy tibbles. This makes it easy to report results, create plots and consistently work with large numbers of models at once. Broom provides three verbs that each provide different types of information about a model. tidy() summarizes information about model components such as coefficients of a regression. glance() reports information about an entire model, such as goodness of fit measures like AIC and BIC. augment() adds information about individual observations to a dataset, such as fitted values or influence measures.#####


# Linear-Regression
###BROOM PACKAGE  FOR GROUPING LINEAR REGRESSION

##installing packages#
install.packages ("tidyverse","modelr","broom")


#### importing libaries
Library(tidyverse)
Library(modelr)
Library(broom)

#### variable selection and coding

variable < - model %>% group_by (STATE,CITY) %>% summarise (Claims_total=sum(CLAIM))
data.frame(variable)


####Getting some results

Result<- variable %>% group_by(STATE,CITY) %>% do(tidy(Claim_total~Year)))-> tryitlinearregression
tryitlinearregression

####Getting extra results with the fitted value

Result<- variable %>% group_by(STATE,CITY) %>% do(augment(Claim_total~Year)))-> tryitfitted.value
tryitfitted.value



####Save the Excel  file 
write.csv(ryitlinearregression, file = "ryitlinearregression.csv")
write.csv(tryitfitted.value, file="tryitfitted.csv"
