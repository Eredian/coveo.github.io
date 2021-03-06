---
layout: post

title: "Customizing the Insight Panel"

tags: [Salesforce, Insight Panel, Query Builder]

author:
  name: Jonathan Garneau
  bio: Product Expert, Coveo for Salesforce
  twitter: garneaujonathan
  image: jgarneau.jpg
---

If you haven't deployed the insight panels in your organization yet, here is a link to the procedure to get it done: [Installing the Coveo for Salesforce Application](http://onlinehelp.coveo.com/en/cloud/installing_the_coveo_for_salesforce_application.htm).

Out of the box there are several predefined Insight Panels with pertinent queries. That is a great starting point, but even more usefulness can be attained by customizing the insight panels to meet the needs and the ways of working of the users.

<!-- more -->

One good example to demonstrate the usage is a "related comments" insight panel. Here at Coveo, we document our cases in the case comments, so looking up the comments that are relevant to the case can help give us precious insight that can help orient towards a path to resolution more quickly. In this post we will walk through the procedure for creating a customized insight panel using the Query Builder.

Once the Insight Panels are deployed, they should look something like this:
![Coveo Insight Panel]({{ site.baseurl }}/images/CoveoInsightPanel.png)

Let's create a new tab to hold our custom-built query by pressing the menu icon (&#9776;) at the far right and selecting "add a tab", and call it "Related Comments".

![Add a Tab]({{ site.baseurl }}/images/AddTab.png)
  	 
![Create a Coveo Insight Tab]({{ site.baseurl }}/images/CreateCoveoInsightTab.png)

Next we add a box to it pressing the menu icon (&#9776;) at the far right and selecting "add a box", or pressing the orange "add a box" button.

![Add a Box]({{ site.baseurl }}/images/AddBox.png)

And then select the Query Builder.
 
![Query Builder]({{ site.baseurl }}/images/QueryBuilder.png)

The Contextual Query tab allows us to build a query by selecting criteria from pick lists, in this example, we want to return Case Comments in our Insight Panel.
 
![Case Comment]({{ site.baseurl }}/images/CaseComment.png)

Linking fields is used to boost the ranking when its content matches that for the current Salesforce context. In this case we want to give more credence to Case Comments that match the Subject and Summary of the current case.
  
![Match Subject and Summary]({{ site.baseurl }}/images/MatchSubjectSummary.png)

Next we use the advanced filtering to give boost the relevancy of the Case Comments that match with the Case's subject or summary. In this example, we decide that a match in "Subject" should be considered more relevant than a match in "Summary"
 
![Boost the Subject]({{ site.baseurl }}/images/BoostSubject.png)

We'll also use the custom filters to make sure the comments from the last year appear first by giving them a relevancy boost. We could have made this condition mandatory, but we'd like to keep the old comments in the search results if there are any, we just want to make sure they appear after more current results.
  
![Boost Recent Comments]({{ site.baseurl }}/images/BoostRecentComments.png)

Contextual query generates the query using the Coveo query extension language based on our configuration.
 
![Generated Contextual Query]({{ site.baseurl }}/images/GeneratedContextualQuery.png)

Saving this brings us back to our case, where we can see that the Coveo Insight Panel is now returning related case comments:

![Related Recent Comments]({{ site.baseurl }}/images/RelatedRecentComments.png)

We can see that the Query builder tool can easily be used to create complex and useful queries to automatically present personalized context related content in search interfaces without the end-users even having to type a query.

Even more flexibility in the query can be obtained by [Creating a Coveo Insight Box Using the Advanced Mode](http://onlinehelp.coveo.com/en/Cloud/creating_a_coveo_insight_box_using_the_advanced_mode.htm) in Query Extension Language directly. The full reference for the query extension language is available on the [Coveo query extension language](https://developers.coveo.com/display/SearchREST/Query+Extension+Language) page.

