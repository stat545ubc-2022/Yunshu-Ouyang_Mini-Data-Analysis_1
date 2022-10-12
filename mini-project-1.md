Mini Data-Analysis Deliverable 1
================

# Welcome to your (maybe) first-ever data analysis project!

And hopefully the first of many. Let’s get started:

1.  Install the [`datateachr`](https://github.com/UBC-MDS/datateachr)
    package by typing the following into your **R terminal**:

<!-- -->

    install.packages("devtools")
    devtools::install_github("UBC-MDS/datateachr")

2.  Load the packages below.

``` r
library(datateachr)
library(tidyverse)
```

    ## ── Attaching packages ─────────────────────────────────────── tidyverse 1.3.2 ──
    ## ✔ ggplot2 3.3.6      ✔ purrr   0.3.4 
    ## ✔ tibble  3.1.8      ✔ dplyr   1.0.10
    ## ✔ tidyr   1.2.1      ✔ stringr 1.4.1 
    ## ✔ readr   2.1.2      ✔ forcats 0.5.2 
    ## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()

3.  Make a repository in the <https://github.com/stat545ubc-2022>
    Organization. You will be working with this repository for the
    entire data analysis project. You can either make it public, or make
    it private and add the TA’s and Lucy as collaborators. A link to
    help you create a private repository is available on the
    \#collaborative-project Slack channel.

# Instructions

## For Both Milestones

-   Each milestone is worth 45 points. The number of points allocated to
    each task will be annotated within each deliverable. Tasks that are
    more challenging will often be allocated more points.

-   10 points will be allocated to the reproducibility, cleanliness, and
    coherence of the overall analysis. While the two milestones will be
    submitted as independent deliverables, the analysis itself is a
    continuum - think of it as two chapters to a story. Each chapter, or
    in this case, portion of your analysis, should be easily followed
    through by someone unfamiliar with the content.
    [Here](https://swcarpentry.github.io/r-novice-inflammation/06-best-practices-R/)
    is a good resource for what constitutes “good code”. Learning good
    coding practices early in your career will save you hassle later on!

## For Milestone 1

**To complete this milestone**, edit [this very `.Rmd`
file](https://raw.githubusercontent.com/UBC-STAT/stat545.stat.ubc.ca/master/content/mini-project/mini-project-1.Rmd)
directly. Fill in the sections that are tagged with
`<!--- start your work below --->`.

**To submit this milestone**, make sure to knit this `.Rmd` file to an
`.md` file by changing the YAML output settings from
`output: html_document` to `output: github_document`. Commit and push
all of your work to the mini-analysis GitHub repository you made
earlier, and tag a release on GitHub. Then, submit a link to your tagged
release on canvas.

**Points**: This milestone is worth 45 points: 43 for your analysis, 1
point for having your Milestone 1 document knit error-free, and 1 point
for tagging your release on Github.

# Learning Objectives

By the end of this milestone, you should:

-   Become familiar with your dataset of choosing
-   Select 4 questions that you would like to answer with your data
-   Generate a reproducible and clear report using R Markdown
-   Become familiar with manipulating and summarizing your data in
    tibbles using `dplyr`, with a research question in mind.

# Task 1: Choose your favorite dataset (10 points)

The `datateachr` package by Hayley Boyce and Jordan Bourak currently
composed of 7 semi-tidy datasets for educational purposes. Here is a
brief description of each dataset:

-   *apt_buildings*: Acquired courtesy of The City of Toronto’s Open
    Data Portal. It currently has 3455 rows and 37 columns.

-   *building_permits*: Acquired courtesy of The City of Vancouver’s
    Open Data Portal. It currently has 20680 rows and 14 columns.

-   *cancer_sample*: Acquired courtesy of UCI Machine Learning
    Repository. It currently has 569 rows and 32 columns.

-   *flow_sample*: Acquired courtesy of The Government of Canada’s
    Historical Hydrometric Database. It currently has 218 rows and 7
    columns.

-   *parking_meters*: Acquired courtesy of The City of Vancouver’s Open
    Data Portal. It currently has 10032 rows and 22 columns.

-   *steam_games*: Acquired courtesy of Kaggle. It currently has 40833
    rows and 21 columns.

-   *vancouver_trees*: Acquired courtesy of The City of Vancouver’s Open
    Data Portal. It currently has 146611 rows and 20 columns.

**Things to keep in mind**

-   We hope that this project will serve as practice for carrying our
    your own *independent* data analysis. Remember to comment your code,
    be explicit about what you are doing, and write notes in this
    markdown document when you feel that context is required. As you
    advance in the project, prompts and hints to do this will be
    diminished - it’ll be up to you!

-   Before choosing a dataset, you should always keep in mind **your
    goal**, or in other ways, *what you wish to achieve with this data*.
    This mini data-analysis project focuses on *data wrangling*,
    *tidying*, and *visualization*. In short, it’s a way for you to get
    your feet wet with exploring data on your own.

And that is exactly the first thing that you will do!

1.1 Out of the 7 datasets available in the `datateachr` package, choose
**4** that appeal to you based on their description. Write your choices
below:

**Note**: We encourage you to use the ones in the `datateachr` package,
but if you have a dataset that you’d really like to use, you can include
it here. But, please check with a member of the teaching team to see
whether the dataset is of appropriate complexity. Also, include a
**brief** description of the dataset here to help the teaching team
understand your data.

<!-------------------------- Start your work below ---------------------------->

1: CHOICE_1\_cancer_sample  
2: CHOICE_2\_parking_meters  
3: CHOICE_3\_steam_games  
4: CHOICE_4\_vancouver_trees

<!----------------------------------------------------------------------------->

1.2 One way to narrowing down your selection is to *explore* the
datasets. Use your knowledge of dplyr to find out at least *3*
attributes about each of these datasets (an attribute is something such
as number of rows, variables, class type…). The goal here is to have an
idea of *what the data looks like*.

*Hint:* This is one of those times when you should think about the
cleanliness of your analysis. I added a single code chunk for you below,
but do you want to use more than one? Would you like to write more
comments outside of the code chunk?

<!-------------------------- Start your work below ---------------------------->

``` r
### EXPLORE HERE ###
#get the first part of cancer_sample dataset, number of rows and columns and the type of this dataset
head(cancer_sample)
```

    ## # A tibble: 6 × 32
    ##       ID diagn…¹ radiu…² textu…³ perim…⁴ area_…⁵ smoot…⁶ compa…⁷ conca…⁸ conca…⁹
    ##    <dbl> <chr>     <dbl>   <dbl>   <dbl>   <dbl>   <dbl>   <dbl>   <dbl>   <dbl>
    ## 1 8.42e5 M          18.0    10.4   123.    1001   0.118   0.278   0.300   0.147 
    ## 2 8.43e5 M          20.6    17.8   133.    1326   0.0847  0.0786  0.0869  0.0702
    ## 3 8.43e7 M          19.7    21.2   130     1203   0.110   0.160   0.197   0.128 
    ## 4 8.43e7 M          11.4    20.4    77.6    386.  0.142   0.284   0.241   0.105 
    ## 5 8.44e7 M          20.3    14.3   135.    1297   0.100   0.133   0.198   0.104 
    ## 6 8.44e5 M          12.4    15.7    82.6    477.  0.128   0.17    0.158   0.0809
    ## # … with 22 more variables: symmetry_mean <dbl>, fractal_dimension_mean <dbl>,
    ## #   radius_se <dbl>, texture_se <dbl>, perimeter_se <dbl>, area_se <dbl>,
    ## #   smoothness_se <dbl>, compactness_se <dbl>, concavity_se <dbl>,
    ## #   concave_points_se <dbl>, symmetry_se <dbl>, fractal_dimension_se <dbl>,
    ## #   radius_worst <dbl>, texture_worst <dbl>, perimeter_worst <dbl>,
    ## #   area_worst <dbl>, smoothness_worst <dbl>, compactness_worst <dbl>,
    ## #   concavity_worst <dbl>, concave_points_worst <dbl>, symmetry_worst <dbl>, …

``` r
dim(cancer_sample)
```

    ## [1] 569  32

``` r
class(cancer_sample)
```

    ## [1] "spec_tbl_df" "tbl_df"      "tbl"         "data.frame"

``` r
#get the first part of parking_meters dataset, number of rows and columns and the type of this dataset
head(parking_meters)
```

    ## # A tibble: 6 × 22
    ##   meter_head  r_mf_9a_6p r_mf_…¹ r_sa_…² r_sa_…³ r_su_…⁴ r_su_…⁵ rate_…⁶ time_…⁷
    ##   <chr>       <chr>      <chr>   <chr>   <chr>   <chr>   <chr>   <chr>   <chr>  
    ## 1 Twin        $2.00      $4.00   $2.00   $4.00   $2.00   $4.00   <NA>    METER …
    ## 2 Pay Station $1.00      $1.00   $1.00   $1.00   $1.00   $1.00   $ .50   METER …
    ## 3 Twin        $1.00      $1.00   $1.00   $1.00   $1.00   $1.00   <NA>    METER …
    ## 4 Single      $1.00      $1.00   $1.00   $1.00   $1.00   $1.00   <NA>    METER …
    ## 5 Twin        $2.00      $1.00   $2.00   $1.00   $2.00   $1.00   <NA>    METER …
    ## 6 Twin        $2.00      $1.00   $2.00   $1.00   $2.00   $1.00   <NA>    METER …
    ## # … with 13 more variables: t_mf_9a_6p <chr>, t_mf_6p_10 <chr>,
    ## #   t_sa_9a_6p <chr>, t_sa_6p_10 <chr>, t_su_9a_6p <chr>, t_su_6p_10 <chr>,
    ## #   time_misc <chr>, credit_card <chr>, pay_phone <chr>, longitude <dbl>,
    ## #   latitude <dbl>, geo_local_area <chr>, meter_id <chr>, and abbreviated
    ## #   variable names ¹​r_mf_6p_10, ²​r_sa_9a_6p, ³​r_sa_6p_10, ⁴​r_su_9a_6p,
    ## #   ⁵​r_su_6p_10, ⁶​rate_misc, ⁷​time_in_effect

``` r
dim(parking_meters)
```

    ## [1] 10032    22

``` r
class(parking_meters)
```

    ## [1] "tbl_df"     "tbl"        "data.frame"

``` r
#get the first part of steam_games dataset, number of rows and columns and the type of this dataset
head(steam_games)
```

    ## # A tibble: 6 × 21
    ##      id url          types name  desc_…¹ recen…² all_r…³ relea…⁴ devel…⁵ publi…⁶
    ##   <dbl> <chr>        <chr> <chr> <chr>   <chr>   <chr>   <chr>   <chr>   <chr>  
    ## 1     1 https://sto… app   DOOM  Now in… Very P… Very P… May 12… id Sof… Bethes…
    ## 2     2 https://sto… app   PLAY… PLAYER… Mixed,… Mixed,… Dec 21… PUBG C… PUBG C…
    ## 3     3 https://sto… app   BATT… Take c… Mixed,… Mostly… Apr 24… Harebr… Parado…
    ## 4     4 https://sto… app   DayZ  The po… Mixed,… Mixed,… Dec 13… Bohemi… Bohemi…
    ## 5     5 https://sto… app   EVE … EVE On… Mixed,… Mostly… May 6,… CCP     CCP,CCP
    ## 6     6 https://sto… bund… Gran… Grand … NaN     NaN     NaN     Rockst… Rockst…
    ## # … with 11 more variables: popular_tags <chr>, game_details <chr>,
    ## #   languages <chr>, achievements <dbl>, genre <chr>, game_description <chr>,
    ## #   mature_content <chr>, minimum_requirements <chr>,
    ## #   recommended_requirements <chr>, original_price <dbl>, discount_price <dbl>,
    ## #   and abbreviated variable names ¹​desc_snippet, ²​recent_reviews,
    ## #   ³​all_reviews, ⁴​release_date, ⁵​developer, ⁶​publisher

``` r
dim(steam_games)
```

    ## [1] 40833    21

``` r
class(steam_games)
```

    ## [1] "spec_tbl_df" "tbl_df"      "tbl"         "data.frame"

``` r
#get the first part of vancouver_trees dataset, number of rows and columns and the type of this dataset
head(vancouver_trees)
```

    ## # A tibble: 6 × 20
    ##   tree_id civic_number std_str…¹ genus…² speci…³ culti…⁴ commo…⁵ assig…⁶ root_…⁷
    ##     <dbl>        <dbl> <chr>     <chr>   <chr>   <chr>   <chr>   <chr>   <chr>  
    ## 1  149556          494 W 58TH AV ULMUS   AMERIC… BRANDON BRANDO… N       N      
    ## 2  149563          450 W 58TH AV ZELKOVA SERRATA <NA>    JAPANE… N       N      
    ## 3  149579         4994 WINDSOR … STYRAX  JAPONI… <NA>    JAPANE… N       N      
    ## 4  149590          858 E 39TH AV FRAXIN… AMERIC… AUTUMN… AUTUMN… Y       N      
    ## 5  149604         5032 WINDSOR … ACER    CAMPES… <NA>    HEDGE … N       N      
    ## 6  149616          585 W 61ST AV PYRUS   CALLER… CHANTI… CHANTI… N       N      
    ## # … with 11 more variables: plant_area <chr>, on_street_block <dbl>,
    ## #   on_street <chr>, neighbourhood_name <chr>, street_side_name <chr>,
    ## #   height_range_id <dbl>, diameter <dbl>, curb <chr>, date_planted <date>,
    ## #   longitude <dbl>, latitude <dbl>, and abbreviated variable names
    ## #   ¹​std_street, ²​genus_name, ³​species_name, ⁴​cultivar_name, ⁵​common_name,
    ## #   ⁶​assigned, ⁷​root_barrier

``` r
dim(vancouver_trees)
```

    ## [1] 146611     20

``` r
class(vancouver_trees)
```

    ## [1] "tbl_df"     "tbl"        "data.frame"

<!----------------------------------------------------------------------------->

1.3 Now that you’ve explored the 4 datasets that you were initially most
interested in, let’s narrow it down to 2. What lead you to choose these
2? Briefly explain your choices below, and feel free to include any code
in your explanation.

<!-------------------------- Start your work below ---------------------------->

    I would like to choose *cancer_sample* and *vancouver_trees* datasets for my project. The main reason is that I am more famililar with the content in these dataset after running glimpse() or head() function.

<!----------------------------------------------------------------------------->

1.4 Time for the final decision! Going back to the beginning, it’s
important to have an *end goal* in mind. For example, if I had chosen
the `titanic` dataset for my project, I might’ve wanted to explore the
relationship between survival and other variables. Try to think of 1
research question that you would want to answer with each dataset. Note
them down below, and make your final choice based on what seems more
interesting to you!

<!-------------------------- Start your work below ---------------------------->

*cancer_sample*  
research question: Do research on cancer sample data and find out the
response variable- diagnoisis and its independent variables as well as
the relation between selected indenpendent variables and the trend
within variables.

<!----------------------------------------------------------------------------->

# Important note

Read Tasks 2 and 3 *fully* before starting to complete either of them.
Probably also a good point to grab a coffee to get ready for the fun
part!

This project is semi-guided, but meant to be *independent*. For this
reason, you will complete tasks 2 and 3 below (under the **START HERE**
mark) as if you were writing your own exploratory data analysis report,
and this guidance never existed! Feel free to add a brief introduction
section to your project, format the document with markdown syntax as you
deem appropriate, and structure the analysis as you deem appropriate.
Remember, marks will be awarded for completion of the 4 tasks, but 10
points of the whole project are allocated to a reproducible and clean
analysis. If you feel lost, you can find a sample data analysis
[here](https://www.kaggle.com/headsortails/tidy-titarnic) to have a
better idea. However, bear in mind that it is **just an example** and
you will not be required to have that level of complexity in your
project.

# Task 2: Exploring your dataset (15 points)

If we rewind and go back to the learning objectives, you’ll see that by
the end of this deliverable, you should have formulated *4* research
questions about your data that you may want to answer during your
project. However, it may be handy to do some more exploration on your
dataset of choice before creating these questions - by looking at the
data, you may get more ideas. **Before you start this task, read all
instructions carefully until you reach START HERE under Task 3**.

2.1 Complete *4 out of the following 8 exercises* to dive deeper into
your data. All datasets are different and therefore, not all of these
tasks may make sense for your data - which is why you should only answer
*4*. Use *dplyr* and *ggplot*.

1.  Plot the distribution of a numeric variable.

``` r
#To load ggplot2 first before graphing
library(ggplot2)
#plot a histogram of fractal dimention mean on cancer_sample data
cancer_dat <- cancer_sample
ggplot(cancer_sample,aes(x=fractal_dimension_mean))+
  geom_histogram(position="identity")
```

    ## `stat_bin()` using `bins = 30`. Pick better value with `binwidth`.

![](mini-project-1_files/figure-gfm/unnamed-chunk-4-1.png)<!-- -->

2.  Create a new variable based on other variables in your data (only if
    it makes sense)

3.  Investigate how many missing values there are per variable. Can you
    find a way to plot this?

4.  Explore the relationship between 2 variables in a plot.

``` r
ggplot(cancer_dat, aes(x=perimeter_mean, y=radius_mean)) + 
  geom_point()+
  geom_smooth(method=lm, se=FALSE)
```

    ## `geom_smooth()` using formula 'y ~ x'

![](mini-project-1_files/figure-gfm/unnamed-chunk-5-1.png)<!-- -->

``` r
#pairs(~radius_mean+perimeter_mean+area_mean,data = cancer_dat)
```

5.  Filter observations in your data according to your own criteria.
    Think of what you’d like to explore - again, if this was the
    `titanic` dataset, I may want to narrow my search down to passengers
    born in a particular year…

``` r
cancer_dat_sub <- cancer_dat%>%
  filter(area_mean<=500)
print(cancer_dat_sub)
```

    ## # A tibble: 230 × 32
    ##          ID diagnosis radius_m…¹ textu…² perim…³ area_…⁴ smoot…⁵ compa…⁶ conca…⁷
    ##       <dbl> <chr>          <dbl>   <dbl>   <dbl>   <dbl>   <dbl>   <dbl>   <dbl>
    ##  1 84348301 M              11.4     20.4    77.6    386.  0.142   0.284   0.241 
    ##  2   843786 M              12.4     15.7    82.6    477.  0.128   0.17    0.158 
    ##  3 84501001 M              12.5     24.0    84.0    476.  0.119   0.240   0.227 
    ##  4  8510824 B               9.50    12.4    60.3    274.  0.102   0.0649  0.0296
    ##  5   853612 M              11.8     18.7    77.9    441.  0.111   0.152   0.122 
    ##  6   855563 M              11.0     21.4    71.9    371.  0.123   0.122   0.104 
    ##  7 85713702 B               8.20    16.8    51.7    202.  0.086   0.0594  0.0159
    ##  8   857155 B              12.0     14.6    78.0    449.  0.103   0.0909  0.0659
    ##  9   857343 B              11.8     21.6    74.7    428.  0.0864  0.0497  0.0166
    ## 10   857374 B              11.9     18.2    75.7    438.  0.0826  0.0475  0.0197
    ## # … with 220 more rows, 23 more variables: concave_points_mean <dbl>,
    ## #   symmetry_mean <dbl>, fractal_dimension_mean <dbl>, radius_se <dbl>,
    ## #   texture_se <dbl>, perimeter_se <dbl>, area_se <dbl>, smoothness_se <dbl>,
    ## #   compactness_se <dbl>, concavity_se <dbl>, concave_points_se <dbl>,
    ## #   symmetry_se <dbl>, fractal_dimension_se <dbl>, radius_worst <dbl>,
    ## #   texture_worst <dbl>, perimeter_worst <dbl>, area_worst <dbl>,
    ## #   smoothness_worst <dbl>, compactness_worst <dbl>, concavity_worst <dbl>, …

6.  Use a boxplot to look at the frequency of different observations
    within a single variable. You can do this for more than one variable
    if you wish!

``` r
ggplot(cancer_dat,aes(x=fractal_dimension_mean,color=diagnosis))+geom_boxplot()
```

![](mini-project-1_files/figure-gfm/unnamed-chunk-7-1.png)<!-- -->

7.  Make a new tibble with a subset of your data, with variables and
    observations that you are interested in exploring.
8.  Use a density plot to explore any of your variables (that are
    suitable for this type of plot).

2.2 For each of the 4 exercises that you complete, provide a *brief
explanation* of why you chose that exercise in relation to your data (in
other words, why does it make sense to do that?), and sufficient
comments for a reader to understand your reasoning and code.

<!-------------------------- Start your work below ---------------------------->

**exercise 1**  
\*I want to get a better idea of the frequency of fractal_dimension_mean
as one of the independent variables in this dataset. By ploting
histagram, I can obviously observe the highest and smallest frequency of
fractal_dimension_mean.

**exercise 4**  
\*I want to find out if there is linear relation between perimeter_mean
and radius_mean by applying ggplot with lm() function.

**exercise 5**  
\*I want to store all data diagnosis with area_mean under 500 and
explore more on the data filtered.

**exercise 6**  
\*I want to check the fractal_dimension_mean by groups which refer to
diagnosis B and diagnosis M. By ploting this boxplot with
color=diagnosis, I can draw conclusion immediately.

    <!----------------------------------------------------------------------------->

    # Task 3: Write your research questions (5 points)

    So far, you have chosen a dataset and gotten familiar with it through exploring the data. Now it's time to figure out 4 research questions that you would like to answer with your data! Write the 4 questions and any additional comments at the end of this deliverable. These questions are not necessarily set in stone - TAs will review them and give you feedback; therefore, you may choose to pursue them as they are for the rest of the project, or make modifications!

    **research questions**  
      1.What is the difference between patients with malignant breast mass and benign breast mass in mean fractal dimension of nuclei?
      2.What is the minimum, maximum and median value for mean smoothness of nuclei in total?
      3.Are patients with benign breast mass showing bigger or smaller mean radius of nuclei? 
      4.Which smoothness of nuclei has the highest mean concavity of nuclei?


    <!--- *****START HERE***** --->

    # Task 4: Process and summarize your data (13 points)

    From Task 2, you should have an idea of the basic structure of your dataset (e.g. number of rows and columns, class types, etc.). Here, we will start investigating your data more in-depth using various data manipulation functions.

    ### 1.1 (10 points)

    Now, for each of your four research questions, choose one task from options 1-4 (summarizing), and one other task from 4-8 (graphing). You should have 2 tasks done for each research question (8 total). Make sure it makes sense to do them! (e.g. don't use a numerical variables for a task that needs a categorical variable.). Comment on why each task helps (or doesn't!) answer the corresponding research question.

    Ensure that the output of each operation is printed!  
    #### research question1  
    **Summarizing:**

    1.  Compute the *range*, *mean*, and *two other summary statistics* of **one numerical variable** across the groups of **one categorical variable** from your data.

    ```r
    cancer_dat%>%group_by(diagnosis)%>%summarise(
      range_frac_dim_min= range(fractal_dimension_mean)[1],
      range_frac_dim_max= range(fractal_dimension_mean)[2],
      mean_frac_dim = mean(fractal_dimension_mean),
      median_frac_dim = median(fractal_dimension_mean),
    )

    ## # A tibble: 2 × 5
    ##   diagnosis range_frac_dim_min range_frac_dim_max mean_frac_dim median_frac_dim
    ##   <chr>                  <dbl>              <dbl>         <dbl>           <dbl>
    ## 1 B                     0.0518             0.0958        0.0629          0.0615
    ## 2 M                     0.0500             0.0974        0.0627          0.0616

**Graphing:**

5.  Create a graph out of summarized variables that has at least two
    geom layers.

``` r
ggplot(cancer_dat,aes(x=fractal_dimension_mean,color=diagnosis))+
  geom_density()+geom_histogram(fill="white",alpha=0.5)
```

    ## `stat_bin()` using `bins = 30`. Pick better value with `binwidth`.

![](mini-project-1_files/figure-gfm/unnamed-chunk-9-1.png)<!-- -->

#### research question2

**Summarizing:**

3.  Create a categorical variable with 3 or more groups from an existing
    numerical variable. You can use this new variable in the other
    tasks! *An example: age in years into “child, teen, adult, senior”.*

``` r
summary(cancer_dat$smoothness_mean)
```

    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    ## 0.05263 0.08637 0.09587 0.09636 0.10530 0.16340

``` r
cancer_dat<-cancer_dat%>%mutate(categ_smoothness=case_when(
    smoothness_mean<=0.08637~"category 1",
    smoothness_mean<=0.09587~"category 2", #0.086<smth_mean<0.0958
    smoothness_mean<=0.10530~"category 3",
    smoothness_mean<=0.16340~"category 4"
  )
)
```

**Graphing:**  
5. Create a graph out of summarized variables that has at least two geom
layers.

``` r
ggplot(cancer_dat,aes(x=smoothness_mean,color=diagnosis))+
  geom_density()+geom_histogram(fill="grey",alpha=0.5)
```

    ## `stat_bin()` using `bins = 30`. Pick better value with `binwidth`.

![](mini-project-1_files/figure-gfm/unnamed-chunk-11-1.png)<!-- -->

#### research question3

**Summarizing:**

1.  Compute the *range*, *mean*, and *two other summary statistics* of
    **one numerical variable** across the groups of **one categorical
    variable** from your data.

``` r
cancer_dat%>%group_by(diagnosis)%>%summarise(
  range_radius_mean_min= range(radius_mean)[1],
  range_radius_mean_max= range(radius_mean)[2],
  mean_radius_mean = mean(radius_mean),
  IQR_radius_mean = IQR(radius_mean),#qt3-qt1
  first_quantile = quantile(radius_mean)[2],
  third_quantile = quantile(radius_mean)[4]
)
```

    ## # A tibble: 2 × 7
    ##   diagnosis range_radius_mean_min range_radius…¹ mean_…² IQR_r…³ first…⁴ third…⁵
    ##   <chr>                     <dbl>          <dbl>   <dbl>   <dbl>   <dbl>   <dbl>
    ## 1 B                          6.98           17.8    12.1    2.29    11.1    13.4
    ## 2 M                         11.0            28.1    17.5    4.51    15.1    19.6
    ## # … with abbreviated variable names ¹​range_radius_mean_max, ²​mean_radius_mean,
    ## #   ³​IQR_radius_mean, ⁴​first_quantile, ⁵​third_quantile

**Graphing:**

6.  Create a graph of your choosing, make one of the axes logarithmic,
    and format the axes labels so that they are “pretty” or easier to
    read.

``` r
ggplot(cancer_dat,aes(x=log(radius_mean),color=diagnosis))+
  geom_density()
```

![](mini-project-1_files/figure-gfm/unnamed-chunk-13-1.png)<!-- -->

#### research question4

**Summarizing:**

2.  Compute the number of observations for at least one of your
    categorical variables. Do not use the function `table()`!

``` r
cancer_dat%>%count(categ_smoothness)
```

    ## # A tibble: 4 × 2
    ##   categ_smoothness     n
    ##   <chr>            <int>
    ## 1 category 1         143
    ## 2 category 2         142
    ## 3 category 3         142
    ## 4 category 4         142

**Graphing:**  
5. Create a graph out of summarized variables that has at least two geom
layers.

``` r
ggplot(cancer_dat,aes(x=concavity_mean,color=categ_smoothness))+
  geom_density()+geom_histogram(fill="white",alpha=0.5)
```

    ## `stat_bin()` using `bins = 30`. Pick better value with `binwidth`.

![](mini-project-1_files/figure-gfm/unnamed-chunk-15-1.png)<!-- -->

**Summarizing:**

1.  Compute the *range*, *mean*, and *two other summary statistics* of
    **one numerical variable** across the groups of **one categorical
    variable** from your data.
2.  Compute the number of observations for at least one of your
    categorical variables. Do not use the function `table()`!
3.  Create a categorical variable with 3 or more groups from an existing
    numerical variable. You can use this new variable in the other
    tasks! *An example: age in years into “child, teen, adult, senior”.*
4.  Based on two categorical variables, calculate two summary statistics
    of your choosing.

**Graphing:**

5.  Create a graph out of summarized variables that has at least two
    geom layers.
6.  Create a graph of your choosing, make one of the axes logarithmic,
    and format the axes labels so that they are “pretty” or easier to
    read.
7.  Make a graph where it makes sense to customize the alpha
    transparency.
8.  Create 3 histograms out of summarized variables, with each histogram
    having different sized bins. Pick the “best” one and explain why it
    is the best.

Make sure it’s clear what research question you are doing each operation
for!

<!------------------------- Start your work below ----------------------------->
<!----------------------------------------------------------------------------->

### 1.2 (3 points)

Based on the operations that you’ve completed, how much closer are you
to answering your research questions? Think about what aspects of your
research questions remain unclear. Can your research questions be
refined, now that you’ve investigated your data a bit more? Which
research questions are yielding interesting results?

<!-------------------------- Start your work below ---------------------------->

**research question 1**  
\*Patients with malignant breast mass and benign breast mass have
similar mean fractal dimension of nuclei.

**research question 2**  
\*I have answered this question by summarize the data.

**research question 3**  
\* The fisrt summarizing answer the research question and graphing can
also help with it.

**research question 4**  
\*The summarizing did not help answer this question while the graphing
can solve the problem.

*Research question 4 has an interesting result*

<!----------------------------------------------------------------------------->

### Attribution

Thanks to Icíar Fernández Boyano for mostly putting this together, and
Vincenzo Coia for launching.
