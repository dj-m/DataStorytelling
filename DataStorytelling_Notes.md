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

| ![x](images/CS109_Lecture3_EDA/Slide_05.jpg) |
| :-: |
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
| ![Maximized data-ink ratio](images/CS109_Lecture3_EDA/Slide_23.jpg) |

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
| **NO!** |
| ![Pie chart](images/CS109_Lecture3_EDA/Slide_54.jpg) |

- Correlations
