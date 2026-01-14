# First-Rmd-Git

First R markdown Assignment in Github

## Finding the assignment on GitHub

Git is a powerful tool for tracking the development of your code and working collaboratively with carefully controlled versioning.
We will complete assignments in GitHub Classroom to easily provide feedback on code, work in teams, and eventually host our dashboard.
I recommend setting up Git in your RStudio to familiarize you with protocols. 

A complete [guide for students using GitHub Classroom](https://github.com/jfiksel/github-classroom-for-students) is available. Please complete steps 1-6 before attempting to clone the assignment. Considering that you face challenges when using your personal computer, you may complete the assignment with JupyterHub without tracking in Git with the expectation you ask for help to resolve the issues.

Video orienting users to Happy Git for R [https://www.youtube.com/watch?v=dQw4w9WgXcQ](https://www.youtube.com/watch?v=ZjyR_dDMyLU)

First, please ensure you have a GitHub account and have successfully installed R and R Studio. When signing up, I'd prefer your username to be similar to your name in Canvas so I can identify you. You may run into security issues regarding HTTPS or SSH protocols. For this course, SSH is preferred. If you have any problems, please don't hesitate to contact the instructor for additional support since errors are common here. 
Please follow the instructions and ask for help if you have problems accessing the terminal or website.

Next, you can access our assignments and click the link to accept them in GitHub Classroom. To submit, Push your changes and paste the link to your repo in Canvas to indicate you have completed the assignment.

## Assignment

For this assignment, read [Bookdown chapter 2](https://bookdown.org/yihui/rmarkdown/basics.html) sections 2.1 - 2.11 and use the syntax of R Markdown to complete the assignment by editing three sections of an R Markdown the YAML header, the text, and the chunk, while making a commit for each change.  

### YAML header

- Change your name in the author's information. Save the file and then commit with the message "Updated author name."
- Change the title. Save the file and then commit with the message "Updated document title."
- Change the date. Save the file and then commit with the message "Updated date."

### Text level

- Remove the text about R Markdown to add a sentence that says something like "I have added text here to show I can write in an R Markdown document." Save the file and then commit with the message "Updated textual information."
- Change the text to a new sentence that says something like "Here are some of my favorite things: " then add a blank line and use the bullet points or numbers to list three things you love.  Save the file and then commit with the message "Added my favorite things."
- Change the header `## Including Plots` to `## Average MPG` and then save the file and then commit with the message "Updated headers"

### Chunk level

- Change the `setup` chunk to the code below, save the file, and then commit with the message "Added tidyverse package." You may need to install the package if the script does not do so. 

````
```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
require('tidyverse')
```
````

- Change the `avgmpg` code chunk so it shows miles per gallon for city driving instead of the highway so it matches the code below, save the file, and then commit with a message like "Converted the bar plot of mpg to city averages." 

```` 
```{r avgmpg}
avgmpgdata <- mpg %>% 
  group_by(manufacturer) %>% 
  summarize(hwy = mean(hwy), cty = mean(cty))

g <- ggplot(data = avgmpgdata)
g + geom_col(aes(x = cty, y = reorder(manufacturer, cty), fill = manufacturer)) +
  ggtitle("Average Miles per Gallon for City Driving by Manufacturer", subtitle = "Data on vehicles from 1999 to 2008 for 38 popular models of cars") +
  theme(legend.position="none") 
```
````  

### Knit the document
Now that you have all the information you need to update the visualization, you can turn the R Markdown file into an HTML webpage. 

- Press the Knit button so that an HTML file is made. After Knitting the document, commit with a message like "Knitted the mpg figure to HTML document."

### Submit the assignment

You have complete the assignment and are ready to turn it in. To submit it for grading, push your commits to your repository using the "Push" button. Then check GitHub that your commits are visible and your final HTML is upto date. Here your professor can view your work and provide feedback on the "Feedback" pull request. You do not need to merge the pull request. Finally, copy and paste the link to your repo in Canvas to indicate you have completed the assignment.

## Additional resources for connecting with Git using R Studio

- https://r-pkgs.org/git.html#git 
- https://happygitwithr.com 
