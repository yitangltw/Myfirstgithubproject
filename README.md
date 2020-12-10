# Analysis on the best location to open a coffee cart business in Taipei, Taiwan
If you want to open up your own business, what's the first thing that comes to your mind? Here's some suggestions: build an electric car brand that has state-of-art autonomous driving and battery technology, and by the way make some rockets that can perform off-shore landing, E-A-S-Y. Well...you and I probably just realized that we're not Elon, but there's still hope! Unlike a lot of businesses that require deep expertise and/or enourmous capital to kickstart, opening a coffee cart business needs neither. It only takes as little as $2500 to start your own coffee cart business!
<br><br>
<a href="https://ferlabikes.com/ferla-mini"><img src = "https://ferlabikes.com/wp-content/uploads/2019/05/ferla_mini_gallery_01.jpg" width = 450></a> 
<br><br>
To operate a successful coffee cart business, you'll need to know **where you're customers are at**. Coffee has become a necessity for people in the modern era, and this is more so the case for office workers that are sleep-deprived. For this project, I'll utilize the dataset containing <a href="https://data.nat.gov.tw/comment/539679">in and out of station passenger number of each MRT(Mass Rapid Transit) station in the greater Taipei area</a>, and also the data from <a href="https://developer.foursquare.com/places">Foursqaure API calls</a> to **identify the best location(MRT station) to open a coffee cart business targeting office workers in Taipei, Taiwan**.<br><br>
***First Part: Using the MRT passenger flow data to categorize each station***<br><br>
I use k-means clustering to cluster all MRT stations into 4 clusters, and found out that cluster 2 fits the characteristics of MRT stations that mainly serves office workers.<br>
<a href="https://github.com/yitangltw/My_first_github_project/blob/master/Images/cluster_2_exit.png"><img src = "https://github.com/yitangltw/My_first_github_project/blob/master/Images/cluster_2_exit.png" width = 700></a></br>
The line plot above represents the number of passengers **exiting** each stations in cluster 2 each weekly hour. We can see that there are 2 peaks in each weekday with a big one in the morning likely due to workers exiting the station to their office, and a small one in the afternoon/evening representing the residents returning to their home. Furthermore, the passenger number in the weekend sharply decreases.</br>
<a href="https://github.com/yitangltw/My_first_github_project/blob/master/Images/cluster_2_enter.png"><img src = "https://github.com/yitangltw/My_first_github_project/blob/master/Images/cluster_2_enter.png" width = 700></a></br>
From the line plot presenting number of passengers **entering** each station in cluster 2 we can see that it mirrors the previous graph during weekdays with a small peak in the morning and a big peak in the evening.</br><br>
***Second Part: Find the best candidate station for coffee cart business among cluster 2***</br><br>
Now there are 15 potential candidates from cluster 2, and the next step is to further narrow it down. I investigated **the correlation between passenger and coffee shop numbers** in each station in order to find locations that have high number of passengers and low number of coffee shops.</br>
<a href="https://github.com/yitangltw/My_first_github_project/blob/master/Images/cluster_comparison_regplot.png"><img src = "https://github.com/yitangltw/My_first_github_project/blob/master/Images/cluster_comparison_regplot.png" width = 1200></a></br>
From the figure above I confirmed that **stations in cluster 2 generally have more coffee shops per monthly passengers compared to other clusters**, indicating a need of coffee from office workers.
<a href="https://github.com/yitangltw/My_first_github_project/blob/master/Images/cluster_2_regplot.png"><img src = "https://github.com/yitangltw/My_first_github_project/blob/master/Images/cluster_2_regplot.png" width = 1200></a></br>
I make 2 regplots for the final analysis, and the only difference between 2 figures is that the **left one sets total passengers** and the **right one sets number of passengers during morning rush hours** as x. We can see that **station BL13 and BR17** stood out in both analysis. The area these 2 stations are in have less coffee shops per passenger compared to other stations in cluster 2.<br><br>
***Conclusion: BL13(Shandao Temple) and BR17(Gangqian) are the best locations for a coffee cart business**</br>
