# Data Storytelling #

Data scientists tell stories when building data products and when communicating with employers or clients about those products. 

Variables associated with datastories:
- Who is your audience
- What questions you're trying to answer
- Why your audience should care
- What your major insights are 
- What impact you want to have by sharing your findings

## Data Storytelling 101 ##

| History of Data Storytelling|
| :-: |
| [![x](images/datastorytelling_history.png)](https://cdn.knightlab.com/libs/timeline3/latest/embed/index.html?source=1ddq7IPe43SyEWUmJMdjRMpPPYnDwYaSoBWKFj74AmhE&font=Default&lang=en&initial_zoom=2&height=650) |

## Storytelling through Exploratory Data Analysis ##

Harvard CS 109 Lecture #3
- [slides](https://github.com/cs109/2015/blob/master/Lectures/03-EDA.pdf)
- [video](https://matterhorn.dce.harvard.edu/engage/player/watch.html?id=a4e81697-fd86-415c-9b29-c14ea7ec15f2)

### Exploratory Data Analysis & Effective Visualizations ###

Data exploration is difficult because we're not always sure what we're looking for...

| ![What to look for?](images/CS109_Lecture3_EDA/Slide_05.jpg) |
| :-: |
| Typical process: |
| ![Process](images/CS109_Lecture3_EDA/Slide_04.jpg) |
| You ought to always be guided by initial hypotheses. Having a good question is important because of its purpose as a guide. |

To overcome this it's best to use visualizations and questions that will guide your exploration. Ultimately, you're looking at what it is that this data can tell you.

That said, once you start exploring the data, your question may change. More questions may arise and you may find things in the data you didn't expect.

| Antibiotics example from 1951 |
| :-: |
| ![Data](images/CS109_Lecture3_EDA/Slide_07.jpg) |
| Data Explanation:<br>Gram Staining: positive = purple<br>Gram Staining: negative = pink<br>Min. Inhibitory Concentration = amount of antibiotic needed to combat that particular bacteria, in ml per gram |
| ![Data questions](images/CS109_Lecture3_EDA/Slide_08.jpg) |
| Initially one can ask about most/least effective antibiotic against the different bacteria.<br>Also, how does gram stain status impact/correlate to the effectiveness of the antibiotic? |
| ![Data visualizations 1](images/CS109_Lecture3_EDA/Slide_09.jpg) |
| This visualization tells us about the effectiveness of the antibiotic and whether the gram stain is positive/negative. |
| ![Data visualizations 2](images/CS109_Lecture3_EDA/Slide_10.jpg) |
| Here, a different question can be asked/answered regarding antibiotice resistance.<br>Once you ask the right questions you'll get surprising results. In this case it took science about 30 years to figure this out. |
| ![Data visualizations scatterplot](images/CS109_Lecture3_EDA/Slide_11.jpg) |
| In science, it's not always about the eureka, but more the 'that's funny' moment. You look at your data and think, 'wow, that's weird.'<br>That's Funny [article](https://www.americanscientist.org/article/thats-funny) by Howard Wainer & Shaun Lysen |

The term **Exploratory Data Analysis** came about as a result of the work of statistician John Tukey.<br><br>

| ![Tukey](images/CS109_Lecture3_EDA/Slide_12.jpg) |
| :-: |
| He was a big proponent of visualizing your data ASAP to assess any patterns early on, to come up with new, intereting questions.<br>Also, it can help find bugs if your data isn't quite what you expected. |

**Visualization** can be defined as:
| ![Tukey](images/CS109_Lecture3_EDA/Slide_13.jpg) |
| :-: |
| Seaborn is a new-ish library for python to accomplish this task. |

Goals of a visualization are two fold: **Explanatory** and/or **Exploratory**

- Communicate (**Explanatory**)
  - Present data and ideas
  - Explain and inform
  - Provide evidence and support (for whatever message you have)
  - Influence and persuade
  
- Analyze (**Exploratory**)
  - Explore the data
  - Assess a situation
  - Determine how to proceed
  - Decide what to do (next, or what questions to ask)
  
**Communication** is usually done without you being present, in the case of a report, for instance. Printed media offer great examples of this:
  
| ![Communicate](images/CS109_Lecture3_EDA/Slide_15.jpg) |
| :-: |

**Analysis** on the other hand is very much dependent on what you are able to suss out of the data:

| An example of data exploration looking at public transit. |
| :-: |
| [![Explore](images/CS109_Lecture3_EDA/Slide_16.jpg)](http://mbtaviz.github.io) |

#### Effective Visualizations ####

| Visualizations that aren't effective are cluttered, crowded and use 3D effects that aren't helpful. |
| :-: |
| ![Ineffective](images/CS109_Lecture3_EDA/Slide_19.jpg) |
| None of these help to decrease the cognitive load.<br>Visualizations are supposed to help you offload your mental processes onto the visualization. |

The goal is to detect visual patterns without having to think very hard.

Great examples of _fails_ can be seen via the [WTF Visualizations](https://viz.wtf) site.

**Five principles** of effective visualizations:
- Have graphical integrity
- Keep it simple
- Use the right display
- Use color strategically
- Tell a story with data

Chart wizards, like those in Excel, have many that're not effective because often they give you the wrong choices to clearly explain data.

**Graphical Integrity** 

| One hard rule: your bar chart has to start at 0 |
| :-: |
| ![Integrity](images/CS109_Lecture3_EDA/Slide_23.jpg) |
| In a bar chart, we're looking for height or length, and it's important to represent this criteria accurately. |
| ![Scale distortion](images/CS109_Lecture3_EDA/Slide_24.jpg) |

In order to show minute changes, it's more ideal to show a dot plot, to show position rather than length/height.

| In this case, the x-axis is inconsistent |
| :-: |
| ![X-axis inconsistency](images/CS109_Lecture3_EDA/Slide_25.jpg) |
| A more accurate visualization. |
| ![X-axis correction](images/CS109_Lecture3_EDA/Slide_26.jpg) |

Once it comes up that a graph/plot is lying, it's hard to regain integrity. The goal should be to not lose it.

| The exact same data represented on the same plot but with one dataset that starts at 0 vs. the other that doesn't. |
| :-: |
| ![0 vs non-0](images/CS109_Lecture3_EDA/Slide_27.jpg) |

If you want to represent those minute changes in data, via using a non-zero based dataset, then alert your audience to it as most will assume a zero-based dataset/representation.

| ![non-zero](images/CS109_Lecture3_EDA/Slide_28.jpg) |
| :-: |

**Keep it Simple**

Edward Tufte introduced the **Data-Ink Ratio** to help guide data visualizations.

| ![Data-Ink Ratio](images/CS109_Lecture3_EDA/Slide_32.jpg) |
| :-: |
| Maximize the ink showing your data while minimizing everything else, like so (getting rid of the 3D shadows): |
| ![Maximized data-ink ratio](images/CS109_Lecture3_EDA/Slide_33.jpg) |

3D data tends to be _bad_ because:
- It wastes ink/pixels on the 3D facets, like shadows
- The 3D perspective distorts the data

| Remove extraneous elements in a visualization |
| :-: |
| ![Chartjunk 0](images/CS109_Lecture3_EDA/Slide_35.jpg) |
| ![Chartjunk 1](images/CS109_Lecture3_EDA/Slide_36.jpg) |
| ![Chartjunk 2](images/CS109_Lecture3_EDA/Slide_37.jpg) |
| ![Chartjunk 3](images/CS109_Lecture3_EDA/Slide_38.jpg) |
| ![Chartjunk 4](images/CS109_Lecture3_EDA/Slide_39.jpg) |

| **NO!** |
| :-: |
| ![Big no-no](images/CS109_Lecture3_EDA/Slide_40.jpg) |

**Use the Right Display**

| A starting point |
| :-: |
| [![Starting point](images/CS109_Lecture3_EDA/Slide_42.jpg)](https://extremepresentation.typepad.com/blog/files/choosing_a_good_chart.pdf) |

- Comparisons

| Do: |
| :-: |
| ![Bar chart](images/CS109_Lecture3_EDA/Slide_44.jpg) |
| Dont: |
| ![Big no-no](images/CS109_Lecture3_EDA/Slide_45.jpg) |
| Lines imply there's a relationship to the data, that it's continuous where bars imply separate, or discrete data. Discrete categories = Bars |

Flowing Data blog post, [_Bar Chart Baselines Start at Zero_](https://flowingdata.com/2015/08/31/bar-chart-baselines-start-at-zero) by Nathan Yau (statistician)

- Trends

| Do: |
| :-: |
| ![Trends](images/CS109_Lecture3_EDA/Slide_48.jpg) |
| Note the bar charts on the bottom. This is done to show the volume of trades versus the trend line above it. The bar chart implies no relationship, which is correct to do. |

- Proportion

| Most widely used method of showing proportions: | 
| :-: |
| ![Pie chart](images/CS109_Lecture3_EDA/Slide_50.jpg) |
| To see pie chart _fails_ go to [eagerpies](https://twitter.com/eagerpies?lang=en) |
| ![Stacked bar chart](images/CS109_Lecture3_EDA/Slide_52.jpg) |
| ![Stacked area chart](images/CS109_Lecture3_EDA/Slide_53.jpg) |
| Caveat: this kind of visualization is not as effective given you have to image reducing the areas unerneath the category you're looking at to 0. For showing proportion it's "Ok" |
| **NO!** |
| ![Pie chart](images/CS109_Lecture3_EDA/Slide_54.jpg) |

- Correlations

| Typically represented in the following manner: |
| :-: |
| [![scatterplot](images/CS109_Lecture3_EDA/Slide_56.jpg)](https://xkcd.com/388/) |
| In the past, scatterplots were considered too complicated for the **public**, but the visual literacy of the public is increasing and they're now Ok to use. |
| ![3D Scatterplots](images/CS109_Lecture3_EDA/Slide_57.jpg) |

- Distributions

| Typically shown via: |
| :-: |
| ![Histogram](images/CS109_Lecture3_EDA/Slide_59.jpg) |
| Play with the bin size to see if there's a pattern that you ddin't realize existed before. |
| ![Bin size playing](images/CS109_Lecture3_EDA/Slide_60.jpg) |
| A continous version of a histogram typically uses a Kernel density estimation. |
| ![Density plot](images/CS109_Lecture3_EDA/Slide_61.jpg) |
| The 2D version of Density Plots are also called **heatmaps** |
| ![2D density plots](images/CS109_Lecture3_EDA/Slide_62.jpg) |

For more examples, follow the [Seaborn tutorial](http://seaborn.pydata.org/tutorial/distributions.html).

#### Exercise ####

| Given the following data what kinds of visualizations can be developed? |
| :-: |
| ![Exercise data](images/CS109_Lecture3_EDA/Slide_65.jpg) |
| Potential visualization 1: Pie Chart |
| ![Exercise pie chart](images/CS109_Lecture3_EDA/Slide_66.jpg) |
| Potential visualization 2: Stacked Bar Chart |
| ![Exercise stacked bar chart](images/CS109_Lecture3_EDA/Slide_67.jpg) |
| Potential visualization 3: Grouped Bar Chart |
| ![Exercise grouped bar chart](images/CS109_Lecture3_EDA/Slide_68.jpg) |
| Potential visualization 4: Difference Bar Chart |
| ![Exercise difference bar chart](images/CS109_Lecture3_EDA/Slide_69.jpg) |
| Potential visualization 5: Slope Graph |
| ![Exercise slope graph](images/CS109_Lecture3_EDA/Slide_70.jpg) |
| Here, the bar thickness also shows how much the before & after changed. |

Sometimes the best approach, is to single out a specific metric to communicate:

![single number](images/CS109_Lecture3_EDA/Slide_71.jpg)

#### Perceptual Effectivenss ####

So, how do you know which visualizations are better than other? The answer comes out of perceptual research that's been going on for 30+ years.

| A few studies: |
| :-: |
| ![perception studies](images/CS109_Lecture3_EDA/Slide_73.jpg) |
| Humans have a linear relatinoship with Length (Upper Left), versus overestimting electric shock and heaviness. |

- Examples of how well-defined our visual sense is:

| We're good at judging length |
| :-: |
| ![Length](images/CS109_Lecture3_EDA/Slide_74.jpg) |
| It's a bit harder to determine angle |
| ![Slope](images/CS109_Lecture3_EDA/Slide_75.jpg) |
| Even harder to determine area, especially because we underestimate it |
| ![Area](images/CS109_Lecture3_EDA/Slide_76.jpg) |
| Intensity is even harder to determine | 
| ![Intensity](images/CS109_Lecture3_EDA/Slide_77.jpg) | 
| Absolute color judgement is also incredibly difficult to determine | 
| ![Absolute color](images/CS109_Lecture3_EDA/Slide_78.jpg) |

- Summary of perception research (for quantitative data):

| ![Summary perception research](images/CS109_Lecture3_EDA/Slide_79.jpg) |
| :-: |
| ![Most effective](images/CS109_Lecture3_EDA/Slide_80.jpg) |
| ![Least effective](images/CS109_Lecture3_EDA/Slide_81.jpg) |
| You can combine visualizations so they better inform than they could alone: |
| ![Together](images/CS109_Lecture3_EDA/Slide_82.jpg) |
| Color is least effective (especially whenyou use the rainbow color scale): |
| ![Color least effective](images/CS109_Lecture3_EDA/Slide_83.jpg) |

- Colors

Often, the best thing you can do with color, is **not** to use it.

| When you do use color, be specific |
| ![Discriminant color](images/CS109_Lecture3_EDA/Slide_85.jpg) |
| Humans typically differentiate 5-8 colors: |
| ![Color maximum](images/CS109_Lecture3_EDA/Slide_86.jpg) |
| ![Color gradients](images/CS109_Lecture3_EDA/Slide_87.jpg) |

The problem with the rainbow scale is that Red & Yellow are colors that we're more likely to see than blue and green. That visual dominance is called **non-linearity**.
  - So, we see the colors in a non-linear way that doesn't correspond to the data.
  
| Avoid this at all costs! |
| :-: |
| ![Rainbow Colormap 0](images/CS109_Lecture3_EDA/Slide_89.jpg) |
| You can see how the Red & Yellow dominate and how it's not related to the the underlying data. |
| ![Rainbow Colormap 1](images/CS109_Lecture3_EDA/Slide_90.jpg) |
| ![Rainbow Colormap 2](images/CS109_Lecture3_EDA/Slide_91.jpg) |

Another reason to avoid the rainbow color scales are due to color blindness in humans. It's not a nominal thing, but rather gradients of color blindness.

| ![Colorblind 0](images/CS109_Lecture3_EDA/Slide_92.jpg) |
| :-: |
| ![Colorblind 1](images/CS109_Lecture3_EDA/Slide_93.jpg) |

| A tool that can be used to work with color:|
| :-: |
| ![Color Brewer 0](images/CS109_Lecture3_EDA/Slide_94.jpg) |
| ![Color Brewer 1](images/CS109_Lecture3_EDA/Slide_95.jpg) |
| Luckily Seaborn lets you use the [Color Brewer palette](https://seaborn.pydata.org/tutorial/color_palettes.html#using-categorical-color-brewer-palettes) |

#### Recap ####

| ![Effective Visualizations](images/CS109_Lecture3_EDA/Slide_21.jpg) |
| :-: |
| Further Reading |
| ![Edward Tufte](images/CS109_Lecture3_EDA/Slide_98.jpg) |
| ![Stephen Few](images/CS109_Lecture3_EDA/Slide_99.jpg) |


## Show me the Data ##

TED x Claremont Colleges by Talithis Williams
- [YouTube](https://www.youtube.com/watch?v=TDCYJ3_gx2w)

Interest in seeing the data & making your own conclusions based on how people have communicated wiht data in the past.
- In particular with what may be hidden via data?

Using data to understand how your individual story may/will differ from what is being conceptualized about you, without your consent.

For instance, your thyroid tries to keep an optimal temperature for your body.
- If you collect your temperature data then you can find some indications on the condition of your thyroid.
  - In the clinical setting, you may have a blood test that measures the thyroid-stimulating hormones in your blood.
    - The problem is that it's not an indication of how active your thyroid is.
  - Your temperatue data tells a different story than what the blood test does.
  
By taking ownership of your data, you become the expert on what you're collecting/analyzing. You become the authority. 
- Other experts are authority figures on the general population, but you can be an expert in what data you collect... say, about your body temperature/blood pressure/weight, etc.
  - When two experts come togetehr, a better decision can be made... than just your doctor alone.
  
Oath: I challenge you to take ownership of your data, and today I hereby confer upon you a Tedx associates degree in elementary statistics with a concetrationin time-dependent data analysis, with all the right and privileges that pertain within there to (your name).

Your response when presented with a situation: Show me the Data!

## Storytelling & Effective Communication ##

Harvard CS 109 Lecture #6
- [slides](https://github.com/cs109/2015/blob/master/Lectures/06-StoryTelling.pdf)
- [video](https://matterhorn.dce.harvard.edu/engage/player/watch.html?id=7f968df9-404a-46a2-ae5f-e35479875f95)

#### How do you Communicate? ####

- Two Fundamental Questions: (your audience should always know this about your data/purpose)
  - What is the goal?
  
![goal](images/CS109_Lecture6_Storytelling/Slide_03.jpg)

  - Who cares?
    - Keep your audience in mind in order to answer this question.

- One way to organize statistics or data science: IMAC

![IMAC](images/CS109_Lecture6_Storytelling/Slide_05.jpg)

- Key Principles:
  - The Golden Rule: Do onto others as you would have done unto yourself.
  - Know your audience
  - Tell a story
  - Choose and use notation carefully
    - Speakers forget that they may have been living with data for years, but as an audience everything may be completely new to you.
  - Read great writers
    - Not only will you learn about the content but also how to parse informatino out well
  - Create a clear sense of direction (the the help of signposts), with clear flow of logic
    - A reader may have certain expectations of where you're going, thematically, and you're trying to staisfy those expectations, unless there's a good reason to surprise the reader by going in a different direction
	- Remind the reader, 'here's where we were, here's where we are and here's where we're going'

| Examples of bad notation: |
| :-: |
| ![bad notation](images/CS109_Lecture6_Storytelling/Slide_07.jpg) |
| Keep things consistent for the reader/audience. Epsilon that goes to 0 as epsilon goes to infinity vioaltes the convention in math where epsilon is usually a very small positive number, and 'n' as an integer. |

- Four useful references on scientific notation
  - **Marie Davidian**: _Written Communication: Conveying Scientific Informaiton Effectively_ 
    - [handout](articles/Davidian_WrittenCommunication.pdf) (PDF)
  - **Rod Little**: _Some Style and Grammar Tips for Biostatistics and Statistics Students_ 
    - [article](articles/Little_StyleTips.pdf) (PDF)
  - **Paul Halmos**: _How to Write Mathematics_ 
    - [article](articles/Halmos_WriteMathematics.pdf) (PDF)
  - **George Gopen** & **Judith Swan**: _The Science of Scientific Writing_ 
    - [blog](https://www.americanscientist.org/blog/the-long-view/the-science-of-scientific-writing) 
	- [article](articles/Gopen_Swan_ScientificWriting.pdf)

| Examples of bad scientific writing from Gopen & Swan article: |
| :-: |
| ![bad writing](images/CS109_Lecture6_Storytelling/Slide_09.jpg) |
| Too much jargon but the real problem is the length of the technical terms & structure. |
| ![sans jargon](images/CS109_Lecture6_Storytelling/Slide_10.jpg) |
| For instance, look at how far apart the subject and verb are: |
| ![subject verb distance](images/CS109_Lecture6_Storytelling/Slide_13.jpg) |
| This abstract is too vague: |
| ![abstract](images/CS109_Lecture6_Storytelling/Slide_15.jpg) |
| From PHD Comics: | 
| ![phdcomics](images/CS109_Lecture6_Storytelling/Slide_16.jpg) |