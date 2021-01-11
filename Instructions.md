# First-Rmd-Git
First R markdown Assignment in Github

## Finding the assignment on GitHub

Git is a powerful tool for tracking the development of your code and working collaboratively with carefully controlled versioning.

We will be completing assignments in GitHub Classroom in order to easily provide feedback on code, work in teams, and eventually host our dashboard.

https://github.com/jfiksel/github-classroom-for-students 

To begin you will want to make sure you have a GitHub account and have successfully installed R and R Studio. When signing up, I'd prefer your username is similar to your name in Canvas so I can identify you.

Continue to follow the instructions and ask for help if you face difficulties accessing the terminal or website.

Next, access our assignments, click the following link to accept the assignment in GitHub.

[INSERT LINK TO ASSSIGNMENT ON GITHUB CLASSROOM HERE]

## Assignment

For this assignment, read Bookdown chapter 2 sections 2.1 - 2.11 and use the syntax of R markdown to complete the assignment by editing three sections of an R Markdown the YAML header, the text, and the chunk, while making a commit for each change.

### YAML header

- Change your name in the author's information. Save the file and then commit with the message "Updated author name."
- Change the title. Save the file and then commit with the message "Updated document title."

### Text level

- Remove the text about R Markdown to add a sentence that says something like "I have added text here to show I can write in an R Markdown. " Save the file and then commit with the message "Updated textual information."
- Change the text to a new sentence that says something like "Here are some of my favorite things: " then use the bullet points or numbers to list three things you love.  Save the file and then commit with the message "Added my favorite things."
- Change the header "## Including Plots" to "## Average MPG" and then save the file and then commit with the message "Updated headers"

### Chunk level

- Change the `setup` chunk to the code below, save the file, and then commit with the message "Added tidyverse package." You may need to install the package if the script does not do so. 

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
require('tidyverse')
```
- Change the `avgmpg` code chunk so it shows miles per gallon for city driving instead of the highway so it matches the code below, save the file, and then commit with the message "Converted the bar plot of mpg to city averages." 

```{r avgmpg}
avgmpgdata <- mpg %>% 
  group_by(manufacturer) %>% 
  summarize(hwy = mean(hwy), cty = mean(cty))

g <- ggplot(data = avgmpgdata)
g + geom_col(aes(x = cty, y = reorder(manufacturer, cty), fill = manufacturer)) +
  ggtitle("Average Miles per Gallon for City Driving by Manufacturer", subtitle = "Data on vehicles from 1999 to 2008 for 38 popular models of cars") +
  theme(legend.position="none") 
```

### Knit the document
Now that you have all the information you need to update the visualization, you are ready to turn the R Markdown file into an HTML webpage. 

- Press the Knit button so that an HTML file is made. After Knitting the document, commit with the message "Knitted the mpg figure to HTML document."

### Submit the assignment

You have complete the assignment and are ready to turn it in. To submit it for grading, push your commits to your repository using the "Push" button. Then use GitHub to submit a pull request. Here your professor can view your work and provide feedback.

## Additional resources for connecting with Git using R Studio

https://r-pkgs.org/git.html#git 

https://happygitwithr.com 
