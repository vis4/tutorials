---
layout: post
title: Using Data Visualisation to Find Insights in Data
---

*This is the draft of a chapter I'm contribution to the [Data Journalism handbook](https://docs.google.com/document/d/18YOaGj0LyRn6x1tcCH2wIWHYqwnMiDCGInbVHe210rM/edit?authkey=CLrotIQH&hl=en_US&authkey=CLrotIQH)*

## When do you need to visualise a dataset to explore it and find a story? When don’t you need to?

Where to put this? *Often, the visual analysis of a new dataset feels like an exciting journey to an unknown country. You start with some basic bar charts to get a first overview, like you would take a first look at a tourist map. With every step you make, with every chart you render, you get new insights about the topic. Based on those early insights, you make decisions for your next steps and what issues to investigate into. At the end of this journey, you became some kind of domain expert.*

By itself, every dataset is invisible to us. Data consist of bits and bytes, stored in a file on a computers hard-drive. To make any sense of data, we need to visualise it. In a broader understanding of the term *visualising*, even that 'picture', that we are seeing on a computer screen after opening a table in a spreadsheet software, can be considered as a kind of data visualisation. In fact, coinciding with the rise of computers in almost every part of our lives, visualisation became an fundamental part of the way we interact. Therefor, the questions is not whether journalists need to visualise data or not, but which kind of visualisation may be the most useful in which situation.

When comparing different kinds of visualisations, it's important to understand a bit of psychology. Humans are well trained to use their high-performance visual perception system  to make all kinds of decisions for our life. Our visual perception system sometimes allows us to make decisions within milliseconds, while in other situations we need to search minutes to find what we need. 

Some of the most important types of visualisations:

* table - displaying the raw numbers
* charts - (http://www.flickr.com/photos/amit-agarwal/3196386402/sizes/l/)
* maps - displaying geographical context
* graphs - displaying relations in networks

The choice of which visualisation to use largely depends on the dataset and what you want to show. 

## How to discover a story in a dataset?

*How do you go about discovering a story? What tools do you use? What “protocol” do you follow? What clues do you follow, what do you pay attention to? (lessons, tips, advice).*

Well, discovering a story is a rather big goal to start with. In fact, there is no set of rules or "protocol" that will guarantee us to discover a story. Instead of finding stories, I like to think of finding insights in the data. Some of these insights might be already known (but maybe not proven) while other insights might be completely new to us. Some of those new insights might actually mean the beginning of a story, while others could just be errors in the data.  

But how do we actually start working with a dataset? But the visualisations are not an end in itself. They help us to learn something about the data, which we have not known before. With every visualisation we see we get new insights about the data and all these insights eventually form our story at the end. The knowledge we get from one image brings us to new questions which leads us to some transformation of our data which at the end will give us new images. 

![finding insights in data](/img/ddjbook/insightsindata.png)

Each of these steps will be discussed further in this section. 

Let's start with the most important step of the process, which is also the one we most likely tend to skip: document new findings and the decisions we make. 

### How to start

If you think of this process as a journey through the dataset, the documentation is your diary. It will tell you where you have traveled to, what you have seen there and how you made your decisions for your next steps. But how can we start this documentation even before we took the first look at the data. 

In most cases when we start to work with a previously unseen dataset we are already filled up with expectations and assumptions about the data. Obviously, there is some kind of reason why we want to deal with that dataset. It's a good idea to start the documentation by writing down these initial thoughts. This helps us to identify our bias and reduces the risk of mis-interpretation of the data in order to find what we actually wanted to find.


### Visualise data

Visualising data is the central point of this process. Each visualisation provides a unique perspective on the dataset. 

### Analyse and interpret what you see

Sometimes you might end up with visualization that, despite of eventual beauty, seem to tell you nothing of value about your data. This is a common starting point in network visualization. But, again, for this process it's important that you force yourself to identify some new insights. The questions mentioned above might help you. 

*What can I see in this image?*

*What does this mean in the context of our data?*



### Document your insights



### Transform data

Now the time has come where we can really move on. The good news is that we've already solved the hardest question of moving on, that is: in which direction should be move on? Remember that insight you got from the last visualization? The one you've written down in you story documentation? The next step is trying to remove this insight from our data. The theory behind this is that every insight in your data might prevent us from seeing some other insights. Removing something we already know is no problem, as long as we're keeping everything for our records. And this is what I call the transform step.


### Which tools to use

In general, there's no . Every tool available at the moment is good at something.

Here are a few advices for choosing the right tools:

* Visualisation and data wrangling should be easy. If changing parameters of the visualizations takes you hours, you won't experiment that much. That doesn't necessarily mean that you don't need to learn how to use the tool. But once you learned it, it should be efficient.
* For some reasons it makes much sense to choose a tool that covers both the data wrangling and the data visualisation issues. Separating the tasks in different tools possibly means that you have to import and export your data very often.

The example visualizations in the next section were created using the R project, which is kind of the swiss army knife of scientific data visualisation.

## Example: making sense of US election contribution data

*Examples of how to explore a dataset with a visualisation tool with a step by step description of the “protocol” followed to find the story.*

Let us have look at the US Presidential Campaign Finance database which contains about 450,000 contributions to US Presidential candidates. The CSV file is 60 megabytes and way to large to handle it easily in Excel.

Here are my assumptions on the FEC contributions dataset:

* Obama get's the most contributions (since he's the president and has the highest popularity)
* The number of donations increases as the time moves closer to election date
* Obama gets more small donations than republican candidates.

To answer the first question we need to transform the data. Instead of each single contributions we need to know the total amounts contributed to each candidate. This transformation is called aggregation. Of course, a quick look at the aggregated values in a sorted table already confirms our assumption that Obama would raise the most money.

<table cellspacing="5" width="60%" style="margin:1.5em auto;"><tbody><tr> <th align="left"> Candidate </th> <th align="right"> Amount ($)</th>  </tr>  <tr> <td> Obama, Barack </td>  <td align="right"> 72,453,620.39 </td> </tr>  <tr> <td> Romney, Mitt </td>  <td align="right"> 50,372,334.87 </td> </tr>  <tr> <td> Perry, Rick </td>  <td align="right"> 18,529,490.47 </td> </tr>  <tr> <td> Paul, Ron </td>  <td align="right"> 11,844,361.96 </td> </tr>  <tr> <td> Cain, Herman </td>  <td align="right"> 7,010,445.99 </td> </tr>  <tr> <td> Gingrich, Newt </td>  <td align="right"> 6,311,193.03 </td> </tr>  <tr> <td> Pawlenty, Timothy </td>  <td align="right"> 4,202,769.03 </td> </tr>  <tr> <td> Huntsman, Jon </td>  <td align="right"> 2,955,726.98 </td> </tr>  <tr> <td> Bachmann, Michelle </td>  <td align="right"> 2,607,916.06 </td> </tr>  <tr> <td> Santorum, Rick </td>  <td align="right"> 1,413,552.45 </td> </tr>  <tr> <td> Johnson, Gary Earl </td>  <td align="right"> 413,276.89 </td> </tr>  <tr> <td> Roemer, Charles E. 'Buddy' III </td>  <td align="right"> 291,218.80 </td> </tr>  <tr> <td> McCotter, Thaddeus G </td>  <td align="right"> 37,030.00 </td> </tr>   </tbody></table>

But despite of showing the minimum and maximum amounts and the order the table does not tell very much about the underlying patterns in candidate ranking. Here's another view on the data, a chart type that is called *dot chart* and can easily be [created using R](https://gist.github.com/1769733).

![contributions per candidate](/img/ddjbook/contr_per_cand.png)

As a first step I simply visualised all contributed amounts over time:

![contributed amounts over time](/img/ddjbook/all.png)

In this plot we can see that almost all donations are very very small compared to three really big outliers. Furhter investigation returns that these huge contributions, which are labeled with "*Obama Victory Fund 2012*" were made on June 29th ($450k), September 29th ($1.5mio) and December 30th ($1.9mio).

The dataset holds a column for the form type which classifies the contributions in three categories: contributions by individuals, refunds to individuals and contributions by authorized comittees. For now let us focus on the contributions that were made by or refunded to individuals. 

![Contributions by individuals](/img/ddjbook/indiv-refunds.png)

According to the [contribution limits placed by the FECA](http://www.fec.gov/pages/brochures/fecfeca.shtml#Contribution_Limits) individuals are not allowed to donate more than $2500 to each candidate. As we see in the plot, there are numberous donations made above that limit. In particular two big contributions in May attract our attention. It seems that they are 'mirrored' in June and July. Further investigation in the data reveals the following transactions:

* On May 10 *Stephen James Davis*, San Francisco, employed at Banneker Partners (attorney), has donated **$25,800** to Obama.
* On May 25 *Cynthia Murphy*, Little Rock, employed at the Murphy Group (public relations), has donated **$33,300** to Obama.
* On June 15 the amount of **$30,800** was refunded to *Cynthia Murphy*, which reduced the donated amount to $2500.
* On July 8 the amount **$25,800** was refunded to *Stephen James Davis*, which reduced the donated amount to $0.

What's intersting about these numbers? The $30,800 refunded to Cynthia Murphy equals the maximum amount individuals may give to *national party committees* per year. Maybe she just wanted to combine both donations in one transaction which was rejected. The $25,800 refunded to Stephen James Davis possibly equals the $30,800 minus $5000 (the contribution limit to any other political committee). Let's get rid of those outliers for the moment to give the data more space.

![Contributions by individuals](/img/ddjbook/contr-refunds2.png)

Maybe we will learn more about the negative contributions by looking at the refunds to individuals.

![Contributions to Obama](/img/ddjbook/contr-obama.png)

Let's see how this compares to the republican candidates:

![Contributions to Republican Candidates](/img/ddjbook/contr-rep.png)




