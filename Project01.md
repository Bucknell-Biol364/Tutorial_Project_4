Group Project 4
================
Abby, Irene, and Sam
9 Feb 2022

## Target Audience

Our target audience is Biol 202 class that is working with rats in a lab
collecting data. We want to help teach these students how to use R and
how to use R to help analyze their data.

This tutorial will provide you with a step by step approach to help you
utilize R studio in order to help you explore, visualize, and
statistically test your data. R Studio is a program build for these
kinds of task and works much better then programs like excel, especially
for larger data sets. This tutorial is tailored to people with limited
knowledge of R studio. Through the completion of this tutorial you
should gain basic R Studio skills that could be applied to other data
sets.

How to access this tutorial: First make sure you have RStudio downloaded
and ready to use. Open RStudio and make sure you have the updated
version. Next, open this github repo where this tutorial lives and click
the green code button located at the top of the window. Click on
“download zip”, which will load the documents into your download folder.
Then locate the files and move them to an accessible folder on your
computer. Then open R Studio again and find the file using the files tab
in the bottom left corner of R. Click on the file named Project01.Rmd to
load the tutorial. From there just follow the instructions on the file
and get ready to learn how to use R Studio .

#Introducing R

*What is R?* R is a programming language that is used to manipulate,
visualize, and interpret data. R is specifically designed to manipulate
large data set and to visualize those data sets in a way that can be
used to gather conclusions. It is free to download, making it very
accessible to anyone who wants to use it. Currently, R is the industry
standard for data science in biology.

*Introduction to R Studio * The display screen of R Studio is split into
4 different quadrants, each of which has a different purpose.

R Script: the upper left window. This is where you will spend the most
time in R as it’s where you will write your code.

R Consule: the bottom left window. This is where the program R is
actually running. You are also able to write code directly in the
console, but there is no way to edit the code you put there after you
run it. Generally it’s best to write any code in the script so then you
have the ability to change it later. The console is also where error
messages appear. These messages will be usable, in conjunction with
other sources as such as Google, in determining the mistakes you made in
your code.

R Environment: the upper right window. This shows a record of all of the
objects you currently have saved in R. So any variables, data frames, or
variables you have will be shown here.

R graphical output/files/packages: the bottom right screen. This window
has many different functions. Here, you can navigate through your
computer and locate files to load into R. The plots tab also allows you
to look at any graphs you created. Lastly, the package tab is one way
you’ll be able to load different packages into R.

*Writing commands in R* Writing code is how you’ll get anything done in
R, so it’s best to learn how to do so first.

The section above said that you write code in the R script window, but
the text you’re currently reading isn’t code. We are currently using a R
Markdown file, where the default text is not considered code.

To write a line of code that R will try to run, you must use a code
chunk. Anything that isn’t within a code chunk will just be considered
text and ignored by R, but R will try to run anything that is within a
code chunk.

Creating Code Chunks There are many wasy to create a code chunk.

1.  Use the create code chunk button on the top of the screen (a green C
    with a plus sign). This will automatically add a chunk wherever your
    mouse is currently in the script. When you use this, chose the
    default R option.

2.  creating one manually. You can type in the symbols that indicate a
    code chunk by yourself. The start of a chunk is is designated by
    three backticks (\`\`\`) followed by a set of curly brackes ({}). On
    the next time, add three additional bacticks to designate the end of
    a code chunk. The code you want to run should go in between.

You may also name your code chunks something more specific by adding
more wording following the r in the curly brackets. But be warned, if
you are going to name your code chunks, know that each code chunk must
have a unique name or else R may run into problems.

Adding Comments What if you want to add a line of text code within a
code chunk that isn’t code? You can add comments by prefacing them with
a # symbol. This tells R that the text following # is not meant to be
run.

Run the code below and see what output is given.

``` r
print("Hello World")
```

    ## [1] "Hello World"

``` r
#this code will return the phrase "Hello World" bock to you. 
```

Notice how the print command was the only thing that run in that code
chunk. The words following # are ignored.

*Packages in R* You can use R just by writing code into the console,
which will work just fine; however, it is much more useful to use
packages. Packages are collections of code, functions, and data sets
that make R easier to use.

Loading in packages There are many ways to load packages, but the
annoying thing is that a packages must be both installed in computer and
then loaded onto your specific document. Even if you already installed a
package, you will have to load the same package for every new R markdown
you create.

First is just by using the package tab in the bottom right screen.

The second method is by writing code that specifically loads the
package. This method is preferred; if you were to share your code with
anyone, they would be able to use the same packages you installed
because you added code to do that.

Let’s do any example of loading in some packages right now.

Here, we’re loading the package “cowplot”, which is used to create
neater, more uniform looking graphs.

This code looks complicated, but let’s break it down.
`if (!require("cowplot")) install.packages("cowplot")` tells R to see
see if “cowplot” is already installed in your computer. If it’s not
installed, then it tells R to do so. Next, `library(cowplot)` tells R to
load cowplot on your current work space.

To load different packages, type in the name of you package you want to
use. So, here, we’re loading in the package “tidyverse”, which contains
a whole host of useful packages used to help manipulate and visualize
data

Notice how you only have to replace the name of the package. So here,
the word tidyverse replaced every instance of the the word cowplot. Keep
the format the same - keep the quotation marks where they already are
but keep them off where they aren’t needed.

Try loading in the package “ggplot2”, which is used to help make graphs

In this tutorial, we’re going to be looking at

This is an updated and expanded version of the mammals sleep dataset.
Updated sleep times and weights were taken from V. M. Savage and G. B.
West. A quantitative, theoretical framework for understanding mammalian
sleep. Proceedings of the National Academy of Sciences, 104
(3):1051-1056, 2007. <http://www.pnas.org/content/104/3/1051.abstract>

#Data exploration

You can view the data in table form to see if it imported correctly
*Just type the name of the data set*

Then you can look at the summary of the whole datasheet. This can be
done with the summary command.

*summary(dataset) allows you to look at the summary of the data*

The summary command is very powerful in that it provides the basics of
the data. It tells you what each variable type (mode) is labled as
(character, numeric, integer, complex, or logical). It also provides you
with each variables name, number of data points, mean, median, min, max,
1st quartile, and 3rd quartile.

Sometimes the mode that R picks for the data needs to be changed.

*new name \<- as.character(dataset$variable)* *You can check it worked
with mode(new name)*

For this specific variable it would be useless to change the mode but
sometimes you will run into situations where it is necessary, so always
check the class and mode of your variables.

Now that the whole data set has been seen you can now begin to look at
different variables.

*table(dataset$variable)*

or you could view tables with 2 variables against each other

*table(dataset*v**a**r**i**b**l**e*1, *d**a**t**a**s**e**t*variable2)*

A hypothesis to test for this data is, total sleep depends on body
weight.

For the hypothesis we are looking at body weight so we can look at a box
plot of the data. Type the command below.

*qqnorm(msleep*b**o**d**y**w**t*, *m**a**i**n* = ′*N**o**r**m**a**l**Q* − *Q**P**l**o**t**f**o**r**B**o**d**y**W**e**i**g**h**t*′)*q**q**l**i**n**e*(*m**s**l**e**e**p*bodywt)*

From this QQ-plot we can see the normality of the data. It is important
that the data be distributed normally because for statistical tests you
will see later many assume the data is normal.

We can see here that the data is not distrusted normally, so we can try
and transform the to become normally distrusted.

Try making a histogram of body weight but this time try doing a log
transformation.

*Type the same command as before but this time for x type log(bodywt)*

The data was made more normal from a log10 transformation. Sometimes the
data cannot be transformed to become normal and that is okay. Just make
a note when doing a statistical test that the data was not distributed
normally.

If you had a more specific hypothesis and wanted to look at a more
specific range within the variable you could do that. Maybe you wanted
to only look at the brain weights were the body weight was below 100.

*new name \<- filter(msleep, (bodywt \<= 100))* *ggplot(new name) +
aes(x = log(brainwt)) + geom_histogram() + theme_cowplot()*

If you needed, you could do multiple data filters for different variable
at the same time. Just make sure to give the filtered data a good name.
Sometimes you can end up with a lot of different names, so stay
organized. Also you never want to name something the same as the name of
the data set because R will overwrite the data with your filtered data.

When you explore the data enough you can then move onto truly
visualizing it.

#Data visulization

Though you’ve already seen some graphs displayed, here we’ll show you
how to create graphs in some more depth. Specifically, we will use the
package ggplot2 to do so. We’ll at the distribution of some of the key
variables we’re looking at, such as body weight and and sleep total.

*One variable graphs* \* Let’s first start with the histogram you
already saw in the previous section exploring the distribution of body
weight.

``` r
ggplot(msleep) +
  aes(x=bodywt) +
  geom_histogram()
```

    ## `stat_bin()` using `bins = 30`. Pick better value with `binwidth`.

![](Project01_files/figure-gfm/histogram%20for%20body%20weight-1.png)<!-- -->
Let’s break this down a bit. The function ggplot is very diverse and can
be used to create many,many plots, but it has some specific parameters
that you must use for it to work. The above code shows the bare minimum
you need to use ggplot. Many more additional parameters can be called to
change the graph.

(Note that there are many different format you can use to utilize
ggplot, and this tutorial will only show you one method)

*Basic Elements of ggplot:* 1) ggplot(), this calls the function ggplot.
Within the parenthesis is where you should call the dataframe you are
using. This tells R to use that dataframe when creating the graph.

2.  aes(), this controls the “aesthetics” of the graph, or which
    variables in the data should be used where. So here, you would tell
    R which x and y variable you’re using ( and possibly which variable
    you cant to group by if that’s your analysis). In the example above,
    only the x variable is specified as the variable bodywt. The y
    variable is left unspecified in this case, which means R will use
    count ( or the total number of individual) as the y variable. (Note
    that you don’t need to use parenthesis here, “bodywt”, since you
    already specified msleep as the dataframe. So R will look within the
    dataframe msleep for a variable called bodywt.)

3.  geom_historgram(), this tell R which specific graph you want to
    create. Because we’re looking at a distribution of only one
    variable, we’re using a histogram. You can, however, use serval
    other graphs - geom_boxplot, geom_point (for a scatterplot), and
    more. (A list of some of the different plots you can make are listed
    here: <https://ggplot2.tidyverse.org/reference/>)

But we can add some additonal features/change some features of our
graph. Let’s redo this same histogram, but this time 1) clean up the
histogram, 2) clean it up the background, and 3)change the axes labels,
and 4) transformed the data to log

``` r
ggplot(msleep) +
  aes(x=log(bodywt))+
  geom_histogram(bins=50, color="black",fill="grey")+
  labs(x="Body Mass (kg)",y="Number of Individuals")+
  theme_cowplot()
```

![](Project01_files/figure-gfm/improved%20histogram%20for%20body%20weight-1.png)<!-- -->
1) Cleaning up the graph: Here, three things were changed: the outline
of the bars, the color of the bars, and the size of each bar. -
`bins=50` changed the size of each bar. To be more technical, this code
changed the number of bins used. A bin is a a group of data. The default
is bin=30, but by changing that to a large number we are able to see a
bit of the graph as a whole. You will not always have to change the bin
number, but the previous graph gave a suggestion to change the bin
number. - `color="black"` changed the outline of the histogram to the
color black. You can specify the name of basic colors within quotations.
- `fill="grey"`, this changed the color the histogram.

2.  Cleaning up the Background The grey and white grid mas removed and
    axis lines were added. This is all courtesy of the command
    `theme_cowplot()` which applies all these changes in one command.

3.  Changing the Axes Names A new section `labs()` was added. This
    stands for labels, and you can change the label names of anything
    you specify. So to change the x axis label, you would use
    `x="New Name"`. The same logic would apply to the y axis label.
    Here, you will need to specify the name is quotation marks.

4.  Log transforming the Data As we noted in the last section, the
    distribution of body weight isn’t normal. One way to remedy this is
    to tell R to use the log of body weight when creating the graph.
    Instead of just calling `x=bodywt`, add log() before the quantity
    you want to log. So `x=log(bodywt)`

So the general format for
`ggplot(Dataframe) + aes(x=xvariable,y=yvariable)+ geom_histogram(bins=#, color="color",fill="color") + labs(x="X Label",y="Y Label")+ theme_cowplot()`

Create a histogram showing the distribution for the total amount of REM
sleep. The base code is provided, but you’ll have to add the specifics.
Keep in mind that you may also have to transform the variable.

``` r
ggplot() +
  aes()+
  geom_histogram()
```

![](Project01_files/figure-gfm/your%20histogram%20for%20rem%20sleep-1.png)<!-- -->

*Looking at more than one variable*

*Quantitative vs quantitative variable* To look at the distribution of
two quantitative variables, use a scatter plot.

``` r
ggplot(msleep) +
  aes(x=log(bodywt),y=sleep_total)+
  geom_smooth()+
  geom_point()+
  labs(x="Log Body Mass (kg)",y="Total Sleep (hrs)")+
  theme_cowplot()
```

    ## `geom_smooth()` using method = 'loess' and formula 'y ~ x'

![](Project01_files/figure-gfm/boxplot%20of%20vore%20and%20sleep_total-1.png)<!-- -->

As you can see, the same basic elements of ggplot are still used:
calling ggplot(), aes(), and some geom function. Now, though we’re
creating a scatterplot instead of a histogram so the exact geom function
has changed from geom_histogram() to geom_point().

To use a scatter plot, use `geom_point`, which plots points on the
graph. The additional code `geom_smooth` will add a regression line on
the point as well as a 95% confidence interval.

Create a scatter plot that plots the total body weight to the amount of
REM sleep.

``` r
ggplot()+
  aes()+
  geom_point()
```

![](Project01_files/figure-gfm/your%20scatterplot%20for%20REM%20sleep%20and%20body%20weight-1.png)<!-- -->

*Creating a New Variable* Since we’re looking looking at both the total
hours of sleep and the amount of REM sleep, we should look at the
relationship between the ratio REM/sleep total and body weight.

Looking at the variable in the data frame, however, we see that there is
not a variable for the ratio of REM sleep to total sleep. So we should
will need to create a new variable for this.

Creating a new variable involves the an arrow symbol `<-` or `->`. The
arrow should point to the new variable and start at what that new
variable will contain. You can call your new variable anything, but it’s
best to keep your name short, relevant to what it holds, and avoid
spaces within. Format for creation of new variable: NewNameofVariable
\<- value

Create a new variable that holds the value of 17/1.8, and then call your
new variable

Like your new variable can hold numerical values, you can also use
variable names instead of numbers.

This creates a new variable, but we specifically want a new variable in
our msleep data, using the information of REM and sleep total. How will
we do this?

We can use the $ to call a specific variable in a data frame. So
`NameofDataFrame$NameofVariable` allows you to isolate that variable
from a dataframe. To practice, call the variable sleep_rem in the msleep
dataset

Now, if we were to call a variable that doesn’t currently exist, R would
create a new variable in the specified data set. So, for example,
`msleep$NewVariable` would create a new column in the msleep dataset.

So combining all of this, we can create a new variable in the data frame
that holds the ratio of REM and sleep_total.

``` r
msleep$RemSleep <- msleep$sleep_rem/msleep$sleep_total
msleep$RemSleep
```

    ##  [1]         NA 0.10588235 0.16666667 0.15436242 0.17500000 0.15277778
    ##  [7] 0.16091954         NA 0.28712871         NA 0.11320755 0.08510638
    ## [13] 0.07000000 0.12000000 0.21359223 0.24096386 0.15384615 0.17816092
    ## [19] 0.09433962 0.27222222         NA 0.19796954 0.20689655 0.12903226
    ## [25] 0.34653465 0.10091743         NA 0.25600000 0.11224490 0.21052632
    ## [31] 0.03703704 0.24193548 0.09523810 0.23750000 0.09473684         NA
    ## [37] 0.34020619 0.11881188 0.13380282 0.21678322         NA 0.11200000
    ## [43] 0.10050251         NA         NA 0.11688312         NA 0.10714286
    ## [49] 0.15789474 0.14432990         NA         NA         NA 0.10638298
    ## [55] 0.26213592         NA         NA 0.13138686 0.11428571         NA
    ## [61] 0.13513514 0.33701657 0.09259259 0.18461538         NA 0.14583333
    ## [67] 0.25000000 0.09734513 0.22641509         NA 0.24637681 0.18867925
    ## [73] 0.15625000 0.26373626         NA         NA 0.22727273 0.14743590
    ## [79] 0.29213483         NA 0.20634921         NA 0.24489796

Now use this new variable in the dataset to graph the relationship
between rem sleep/total sleep and bodyweight

#Hypothesis Testing Now that we have looked and explored the data above,
you are going to want to check to see if the data is normal. To do this,
we will be using a Shapiro-Wilk normality test. First you are going to
want to create different plots of the data to look at it individually.
The normal Q-Q plot should look linear if the data is normal. Then we
will create the Shapiro test and once you have used this command, you
will look at the p-value output. If the p-value is above 0.05 it is
normal, and if it is below 0.05 then the data is not normal.

You will want to look at each different variable separately and then you
can compare the variables together. First example is of body weight. You
can run a “simple.eda” and a “Shapiro.test” on this variable to
determine if it is normal or not. Earlier, you you created a new
variable called “msleep$RemSleep”. This compares rem sleep and sleep
total. Running a “simple.eda” and a “Shapiro.test” will help to
determine if this data related to each other is normal.

``` r
#Testing body weight
simple.eda(msleep$bodywt)
```

![](Project01_files/figure-gfm/Data%20Exploration%20for%20normality-1.png)<!-- -->

``` r
shapiro.test(msleep$bodywt)
```

    ## 
    ##  Shapiro-Wilk normality test
    ## 
    ## data:  msleep$bodywt
    ## W = 0.20938, p-value < 2.2e-16

``` r
simple.eda(msleep$RemSleep)
```

![](Project01_files/figure-gfm/Data%20Exploration%20for%20normality-2.png)<!-- -->

``` r
shapiro.test(msleep$RemSleep)
```

    ## 
    ##  Shapiro-Wilk normality test
    ## 
    ## data:  msleep$RemSleep
    ## W = 0.95184, p-value = 0.01765

In this Shapiro-Wilk example for body weight, the data is not normal
since the p-value of 2.2e-16 is below the 0.05 cutoff. Also, the graph
of the Q-Q plot is not linear showing another example that the data is
not normal.

For the new behavioral that you created ‘msleep$RemSleep’, the data is
normal because the p-value is 0.01765 which is below 0.05. Even though
the Q-Q plot looks sort of linear, the p-value is showing that the data
is not normal. This shows that you shouldn’t just got off of how the
graph looks, but what the analysis of the data shows.

To fix this, you can try to use a log on the data to try to make this
more linear and have a p-value above 0.05.  
To do this you can create a new vector associated with log of the body
weight. Then use the new vector in the same tests as you ran above. You
can do the same thing for the new variable that you created.

``` r
logbodywt <- log(msleep$bodywt)
simple.eda(logbodywt)
```

![](Project01_files/figure-gfm/Fixing%20Data%20Exploration-1.png)<!-- -->

``` r
shapiro.test(logbodywt)
```

    ## 
    ##  Shapiro-Wilk normality test
    ## 
    ## data:  logbodywt
    ## W = 0.97497, p-value = 0.1048

``` r
logmsleepRemsleep <- log(msleep$RemSleep)
simple.eda(logmsleepRemsleep)
```

![](Project01_files/figure-gfm/Fixing%20Data%20Exploration-2.png)<!-- -->

``` r
shapiro.test(logmsleepRemsleep)
```

    ## 
    ##  Shapiro-Wilk normality test
    ## 
    ## data:  logmsleepRemsleep
    ## W = 0.96519, p-value = 0.08007

As you can see, the log transformation was able to make the data more
normal for body weight. The Q-Q plot shows a more linear graph than it
did previously. Also, the p-value with the log transformation is now
0.1048 which is above the 0.05 cutoff, meaning that the data is normal.

Also, the new varaible that you created now also is normal because it
has a p-value of 0.08007 which is above 0.05. The Q-Q plot still looks
linear like it did previously, but based on the p-value, the data is now
considered normal.

*trying this idea with a different transformation* If the log
transformation didn’t work to make the data more normal, you could try
to use the square root transformation or the reciprocal root
transformation.

For this example, let’s use the square root transformation on body
weight. You will want to name the new vector “sqrtbodywt”. Instead of
using the “log” transformation you will use “sqrt”. Then you will use
the new vector in the simple.eda and the shapiro.test.

If you have done this correctly your Q-Q plot will not look linear like
it did with a log transformation. Also, the p-value is now 1.383e-15,
which is under the cutoff for 0.05 meaning that the data is not normal.
This means that the sqrt function did not make your data normal so you
will not want to use this transformation going forward.

An important note to remember going forward is that you should continue
to you the vector “logbodywt” and “logmsleepRemsleep” because this uses
the transformed data that is now normal rather than old data that was
not normal.

In case you have one quantitative variables and one categorical
variables, you will want to use a t-test on the data to interpret if
there is a significant relationship between your two groups. A t-test is
used to statistically tell if there is a difference in means between two
different groups. If you have taken a statistics class, you have likely
learned about how to do a t-test, but this will do it manually for you.

To create the t-test, you will want to create two different groups
separately. In this example, I created one group called “Carni” and the
other group called “Herbi” I then used the normal data for body weight
to compared the two different groups. The test then compares these two
different data frames to tell if they are significantly different.

``` r
Carni <- logbodywt[msleep$vore == "carni"]
Herbi <- logbodywt[msleep$vore == "herbi"]
t.test(Carni, Herbi)
```

    ## 
    ##  Welch Two Sample t-test
    ## 
    ## data:  Carni and Herbi
    ## t = 1.864, df = 47.162, p-value = 0.06855
    ## alternative hypothesis: true difference in means is not equal to 0
    ## 95 percent confidence interval:
    ##  -0.126914  3.333313
    ## sample estimates:
    ## mean of x mean of y 
    ##  2.664675  1.061476

After running the t-test independent sample, the p number is 0.06855
which is larger than the 0.05 cutoff value. Since the p-value is larger
than 0.05, this means that there is weak evidence that supports the
alternative hypothesis, which is that there is a noticeable difference
between the body weight of a carnivore compared to a herbivore. The
carnivore average body weight was 2.664675 and the average body weight
of the herbivore was 1.061476.

In case you have two quantitative variables, you will need to use a
linear model to compare the two. To do this, you will state the your y
variable (sleep_rem) needs to be depend on the x variable (logbodywt),
and then call the data from the table that you are using. Then you will
use the summary command to give information from the linear model.

``` r
fit = lm(sleep_rem ~ logbodywt, data = msleep)
summary(fit)
```

    ## 
    ## Call:
    ## lm(formula = sleep_rem ~ logbodywt, data = msleep)
    ## 
    ## Residuals:
    ##     Min      1Q  Median      3Q     Max 
    ## -1.3229 -0.8466 -0.2751  0.4685  4.6955 
    ## 
    ## Coefficients:
    ##             Estimate Std. Error t value Pr(>|t|)    
    ## (Intercept)  1.97316    0.16300  12.105   <2e-16 ***
    ## logbodywt   -0.13888    0.05305  -2.618   0.0112 *  
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## Residual standard error: 1.239 on 59 degrees of freedom
    ##   (22 observations deleted due to missingness)
    ## Multiple R-squared:  0.1041, Adjusted R-squared:  0.08889 
    ## F-statistic: 6.853 on 1 and 59 DF,  p-value: 0.01122

After running the linear model test, the p number is 0.01122 which is
smaller than the 0.05 cutoff value. Since the p-value is smaller than
0.05, this means that there is strong evidence to support that the rem
sleep is depended on body weight.

# Acknowledgements

Team Members: Sam Whittaker- Data Exploration Section and README file
Abby Gearhart - Hypothesis testing Irene Hu - Introduction to R and Data
Visualization
