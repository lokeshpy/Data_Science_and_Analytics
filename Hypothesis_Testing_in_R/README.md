# Implementing R Hypothesis Testing
In this article I will use R’s IDE tool to perform hypothesis testing h the ideas present in the rest of your paper.
### R Hypothesis Tests
Hypothesis testing generally considers samples from two populations. For example, you could have a group of students with scores compared before and after tutoring. This would allow us to understand the possible impact of tutoring.
### Test Setup
The null hypothesis for a paired t-test is Ho: μd = Do.
A paired t-test is commonly a two-sided test which seeks to identify any difference where one sample is higher or lower than the other by for example Do. Differences can also be identified that are less than or greater than zero, or some other value. The three alternate hypotheses then can be written as:
μd > Do
μd < Do
μd ≠ Do
In this example, tutoring is being examined to determine its effect on students. Twelve students participate in the study. Each student’s score is measured both before and after the tutoring was administered. The example below will compute summary statistics, Unpaired Two Sample t-test, and Independent t-test.

### R Code:
```

# R Hypothesis Tests

install.packages("dplyr")

tScore_before <- c(40, 62, 74, 22, 64, 65, 49, 49, 49)

tScore_after <- c(68, 61, 64, 76, 90, 75, 66, 60, 63)

# Create a data frame

my_data <- data.frame(group = rep(c("Score Before", "Score After"), each = 9),
                      
                      scores = c(tScore_before,  tScore_after))


# Print all data

print(my_data)


#Compute summary statistics by groups

library(dplyr)

group_by(my_data, group) %>%
  
  summarise(count = n(), mean = mean(scores, na.rm = TRUE),
            sd = sd(scores, na.rm = TRUE))


# Compute Unpaired Two Sample t-test

res <- t.test(tScore_before, tScore_after, var.equal = TRUE)

res

plot(tScore_before, tScore_after)

# Compute independent t-test

res <- t.test(scores ~ group, data = my_data, var.equal = TRUE)

res

ggboxplot(my_data, x="group", y="scores",ylab = "Scores", xlab = "Group")


#test whether the average score before score is less than the average after score, type this:

t.test(scores ~ group, data = my_data,
       
       var.equal = TRUE, alternative = "less")
```


### R Output:
 
![R Code Output](https://github.com/lokeshpy/Data_Science_and_Analytics/blob/master/images/image13.JPG)
![Rcode Output1](https://github.com/lokeshpy/Data_Science_and_Analytics/blob/master/images/image14.JPG)
![R Code Output2](https://github.com/lokeshpy/Data_Science_and_Analytics/blob/master/images/image15.JPG)
![Rcode Output3](https://github.com/lokeshpy/Data_Science_and_Analytics/blob/master/images/image16.JPG)

 
Scattred and Box Plot Graph:
![R Graph](https://github.com/lokeshpy/Data_Science_and_Analytics/blob/master/images/image17.JPG) 

