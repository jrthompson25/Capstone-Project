<h1>The Affect Population Has on Restaurant Health Inspection Scores</h1>
<h3><a href="https://docs.google.com/presentation/d/1fcSwloKtyQkshLHzh34XsCPUezdFL8lItGPbiAqVlMk/edit?usp=sharing">Capstone Project: Nashville Software School - Data Analytics Cohort 6</a></h3>
<h2>Contents</h2>
<ul>
  <li><a href="#Summary">Summary</a></li>
  <li><a href="#Motivation">Motivation</a></li>
  <li><a href="#Data Question and Sources">Data Question and Sources</a></li>
  <li><a href="#Related Articles">Related Articles</a></li>
  <li><a href="#Tools">Tools</a></li>
  <li><a href="#Challenges">Challenges</a></li>
  <li><a href="#Analysis">Analysis</a></li>
  <li><a href="#Conclusion">Conclusion</a></li>
</ul>
<h2 id="Summary">Summary</h2>
<p>This Project sets out to discover whether restaurant health inspection scores are affected by population. My goal is to potentially reveal what some may consider an unexpected cause for low restaurant health inspection scores. This analysis will be performed using three datasets consisting of restaurant inspection data for two major US cities. One dataset for a city with very low population numbers, another with very high numbers, and lastly, a population dataset categorized by zip code.</p>
<p>Some of the assumptions we can make are that restaurants in heavily populated areas receive more customers than those lightly populated. We can also assume that as these restaurants take on larger numbers of customers, serving the customer in a satisfactory fashion may take precedence over certain areas that may be considered health inspection criteria. With certain health inspections being performed without warning, at that particular time the establishment stands to receive a low score, or in the least, one that will reflect areas lacking.</p>
<h2 id="Motivation">Motivation</h2>
<p>As someone who has experience in the food service industry and health inspections, I find this topic particularly inviting. It has the potential to be informative beyond what one would typically think are causes of low health inspection scores.  If a correlation is discovered, it may be useful information primarily to one who is in the position to make changes or improvements to the establishment, but it would also be useful information to the general public or consumer as well.</p>
<p>In addition to the reasons stated above, the dataset for health inspections in Anchorage, AK also interest me on a personal note. A few years ago, my wife and I vacationed in Alaska. This vacation was one I thoroughly enjoyed, and we intend to return some time in the future.  While in Anchorage we were customers to some of the restaurants listed in this dataset. To be able to perform analysis on a place I enjoyed greatly and specifically on restaurants I visited is a rare treat.</p>
<h2 id="Data Question and Sources">Data Question and Sources</h2>
<p>Do restaurants in areas with higher populations tend to have lower 
health inspection scores?</p>
<p><a href="https://data.world/anchorage/restaurant-and-food-inspections">Restaurant and Food Inspections: City of Anchorage</a></p>
<p><a href="https://data.sfgov.org/Health-and-Social-Services/Restaurant-Scores-LIVES-Standard/pyih-qa8i/data">Restaurant Scores - LIVES Standard (San Francisco)</a></p>
<p><a href="https://simplemaps.com/data/us-zips">US Zip Codes Database</a></p>
<h2 id="Related Articles">Related Articles</h2>
<p><a href="https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5349477/">Inspection Frequency, Sociodemographic Factors, and Food Safety Violations in Chain and Nonchain Restaurants, Philadelphia, Pennsylvania, 2013-2014</a></p>
<p><a href="https://www.afdo.org/wp-content/uploads/2020/09/Beneficial-Effects-of-Implementing-an-Announced-Restaurant-Inspection-Program1-1.pdf">Beneficial Effects of Implementing an Announced Restaurant Inspection Program</a></p>
<h2 id="Tools">Tools</h2>
<p>Data analysis and building vizualizations were both done using Python. The presentation was contructed in Google Slides.</p>
<h2 id="Challenges">Challenges</h2>
<h3>Challenge #1</h3>
<p>After doing a .unique() on both datasets for their ‘violation description’ columns, the Anchorage dataset has 176 different types and the San Francisco dataset has 65. After doing a concatenation of the two datasets, the result of the .unique() is 241 different types, which is the exact total of the two separate numbers. This means there were no two violation descriptions exactly the same between these two datasets. However, there are numerous ways that one violation description is noted for both. For example, there are numerous creative ways that the inspector noted something to the effect of ‘improper food storage’ or ‘inadequate plumbing to the facility.’ Many of these can be consolidated.</p>
<h3>Solution to Challenge #1</h3>
<p>I searched for an official document that would give the violation descriptions a more standardized
violation designations. I took all the different names and categorized them into the standardized violation type groups. Before this, there were 241
different names, but after filing them away into 'buckets', there were 26. I did this by taking all the names that pertain to one standardized category and
put them into a variable. I then assigned the new standardized category name to another variable. Finally I ran a .replace() function to replace all the old
strings in the variable to the one new string in the other variable.</p>
<h3>Challenge #2</h3>
<p>The ‘inspection type’ columns for each dataset has some type names that are different, however mean the same thing or something similar. Those that are similar can possibly be consolidated to one type and for those that aren’t similar, there is an ‘other’ category on one dataset that  they might could be filed under. This may end up being a somewhat similar process to the one mentioned above dealing with the ‘violation description’ columns, but again, they’re short designations and not drastically different. </p>
<h3>Solution to Challenge #2</h3>
<p>I did something similar to the solution to challenge #1 in that I did a .replace() function to replace the old names with the new names, but  first I had to consolidate them. Ones that sounded similar or were the same thing were easy, but there were some that I didn't know the meaning to since they were specific to restaurant health code. With a little research I was able to find documents that cleared this up or for the most part and the rest were filed under the other category.</p>
<h2 id="Analysis">Analysis</h2>
<h3>Top 10 Violations</h3>
![Capstone Presentation (5)](https://user-images.githubusercontent.com/20843638/176066327-144efa56-68ec-40f2-bd0f-2a4db1b8da18.jpg)
<h3>Violations per Restaurant</h3>
![Capstone Presentation (6)](https://user-images.githubusercontent.com/20843638/176066340-6eb042e1-5676-4ef2-a453-b76695e61c76.jpg)
<h3>Postal Codes and Populations Grouped</h3>
![Capstone Presentation (7)](https://user-images.githubusercontent.com/20843638/176066352-898ca968-3e1b-4146-b9a7-1f205e231228.jpg)
<h3>Violations Per Restaurant (Median)</h3>
![Capstone Presentation (8)](https://user-images.githubusercontent.com/20843638/176066364-a3b07ac3-2afb-4964-bc3f-f2d556a2f161.jpg)
<h3>Inspection Scores and Population by Postal Code - Anchorage</h3>
![Capstone Presentation (9)](https://user-images.githubusercontent.com/20843638/176066392-a4f34555-d91c-4717-9ea1-2fe6cc1fb7a8.jpg)
<h3>Inspection Scores and Population by Postal Code - San Francisco</h3>
![Capstone Presentation (10)](https://user-images.githubusercontent.com/20843638/176066419-a6686d89-9d70-491f-ad01-01589f892659.jpg)
<h3>Average Scores per Month</h3> 
![Capstone Presentation (11)](https://user-images.githubusercontent.com/20843638/176066434-0fb89161-ee51-40f7-90ff-5967191addf9.jpg)
<h2 id="Conclusion">Conclusion/Key Takeaways</h2>
![Capstone Presentation (13)](https://user-images.githubusercontent.com/20843638/176066454-57f41115-9566-40d4-b828-7f7bdcd688d2.jpg)




