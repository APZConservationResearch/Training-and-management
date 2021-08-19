# Coding Etiquette
We strive to make our code as readable and transferable as possible. Following these guidelines is the first step to ensuring every person collaborating on our projects, present and future, has the ability to easily understand our code and repeat our methods. These are not strict guidelines as some projects will have unique requirements; however, readable, transferable, and well annotated code is a must and is something to work towards at every step of the process.  

## Outline
1. [Organizing Projects](#section1)
2. [Organizing Scripts](#section2)
3. [Tidying Data](#section3)
4. [Coding Syntax](#section4)
5. [Adding to Our Etiquette](#section5)


## Organizing Projects <a name="section1"></a>
Most projects will consist of four primary components:

   1.  Raw data (to be stored on P: drive or on local device)
   2.  Script for wrangling data
   3.  Script for functions
   4.  Script for data analysis and visualization
    
By seperating scripts into various components, users looking to repeat your methods can ignore wrangling steps that may be unique to your raw data. Similarily, keeping the functions in a seperate script makes it easier to access functions which may be helpful for future projects.   

## Organizing Scripts <a name="section2"></a>

There are different ways you may choose to organize your script. For example, some users are more comfortable with R Markdown (.rmd) scripts while others prefer .R scripts. There are however key requirements which every script should include.

### Script sectioned into chunks
Whether using .rmd or .R, scripts should be in discrete and collapsible chunks, each of which has an informative description. To make collapsible chunks in .R scripts make a comment followed by "----" (e.g. `# Visualizing effect of this variable on that other variable ----`). Following input of this, a table of contents will be automatically generated that be accessed by clicking here in the top right corner of your script.

![image](https://user-images.githubusercontent.com/57048454/129761217-3aa31f83-ec31-469d-ba7e-6d8dfd870b59.png)

Each script should always include the following chunks:

1. Introduction that contains
   1. Desription of script
   2. Author information   
2. Libraries needed

### Annotations
Inline annotations are essential to readable code. These annotations should focus on the *why* rather than the *what*.

## Tidying Data <a name="section3"></a>

Wrangling data can be the most frustrating part of coding, but if done properly analysis can be quick and enjoyable. Before analysing data, it needs to be organized into a *tidy* data structure. This structure is the most flexible and commonly used among data scientists. If you are unfamiliar with *tidy* data, take some time to [learn about the structure](https://cran.r-project.org/web/packages/tidyr/vignettes/tidy-data.html).    

## Coding Syntax <a name="section4"></a>

### 1. Naming conventions
Good names for files and objects is an important but often overlooked aspect of coding. All file, object, variable, and function names should be short but informative and alphanumeric. Our naming conventions also follow these specific rules:  

**Script file names** 
* Underscore_to_seperate_words

**Object names**
* lowercase
* underscore_to_seperate_words

**Variable names**
* nouns
* lowercase
* underscore_to_seperate_words

**Function names**
* verbs
* lowercase
* period.to.seperate.words

### 2. Spacing conventions
* Place spaces around operators (e.g. `= +`), and assignments `x <- 5`
* A space should go after a comma but not before ` x <- c(1, 2)`
* Do not place spaces around parentheses unless there is a comma before it `x[1, ]` or a function call
 
```{r}
my.function <- function (x, y) {
x * y
}
```
* When making inline comments make two spaces after code, followed by one `#`, one space, then the comment  
`x <- 5  # This is a proper inline comment`

### 3. Line length and indent conventions
* Limit line length to 80 characters (in RStudio see `Tools/Global Options/Code/Display/Show Margin/80 characters`)
* Opening curly brackets should not go on a new line but should end a line. Closing curly brackets should go on their own line (see `my.function` example above).
* Start a new line after using a pipe operator
```{r}
new_object <- object %>%
   summarise(this_variable)
```
* Start a new line after a `+` when adding layers in `ggplot2`
```{r}
(new_plot <- ggplot(aes(x = predictor, y = response)) +
   geom_point())
```
* Use the indenting which is automatically applied by RStudio after pipe operators in `dplyR` and when adding layers after a `+` in `ggplot2`

## Adding to Our Etiquette <a name="section5"></a>
As our Github repositories continue to grow and new projects are added, we will add package specific code and etiquette. For example, if you want to use a mixed effects model, which package should you use? What syntax should you use? 
Any colloborators who believe code they are using will be helpful to collaborators in the future can make a pull request in the Functions-and-packages.md file.


This coding etiquette was developed using [Our Coding Club's etiquette](https://ourcodingclub.github.io/tutorials/etiquette/) and [Hadley Whickham’s R Style Guide](http://adv-r.had.co.nz/Style.html). 



