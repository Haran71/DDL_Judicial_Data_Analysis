### Analysis section
The main purpose of the analysis was to understand the time taken for a case to be concluded, from the time of filing of the case to the date of the decision. Each Analysis notebook tries to understand different aspects of this feature by looking at it's correlation with various other features. 

###### Analysis-1
In the first analysis notebook, the correlation between the time taken and the gender of the judge is analyzed. The time taken for both Male and Female judges given a case under a particular act and section is compared and the difference is further analyzed by looking at time taken in criminal and non-criminal cases. The analysis is done year wise from the years 2010 - 2018.

According to the most recent data from 2018,it was found that Female judges on average take a week longer than Male judges to decide a case. The analysis of the criminal and non-crimmnal cases are interesting. Male judges take 15 days less on average in dealing with criminal cases, while in non-criminal cases, it is women who ouutshine men, taking 12 days less thanmen on average. 

**Insights**
1. Criminal Cases are more frequently dealt with and take more time on average to conclude, and hence any Legal AI system built to augment the judicial process will be more valued in criminal cases

2. Female judges have rapidly caught up with Male judges in terms of the time taken to decide cases, and in fact are seen to decide non-crminal cases more quickly than male judges. This may show that Male judges in particular may need some help in deciding non-criminal cases, and may be more benefitted by a Legal AI system in these cases. Also, understanding the deeper reasons behind why female judges are dealing woth non-crminal cases more quickly could help in the building of such an AI system

###### Analysis-2
In the second analysis notebook, a state wise analysis is conducted to understand the average time taken for a case to be concluded in each state. The number of cases in each state in the year 2018 is also analyzed and with this information, the analysis tries to understand which states may need more resources poured into legal system.

Analysis was also done on the ratio of Female judges in each state, and it's correlation between the time taken to conclude a case. It was found that out of the 6 states that have the Female judge ratio of over 40 percent, in 5 of these states the average time raken is well below the national average.

**Insights**

1.West Bengal, Gujarat and the other states that were seen to be above or close to the national average in both No of cases and average time taken to handle cases are the places where resources are needed to help with the judicial system. These states also might be a startng to point to begin the implementation of a legal AI system to help augment the judicial process

2.The infusion of female judges into the judiciary seems to have a positive effect on the time taken to decide a case. While it is clearly not the only factor at play, understanding this correlation may help in improving the judicial syatem in India.

###### Analysis-3
In the third analysis notebook, the correlation between the time taken to and the gender of the both the judge and the defendant is analyzed. Furtherore, the analysis also dives into both Male and Female judges, and the tinme they take to conclude cases with defendants of both gender.

**Insights**
1. Both male and female judges seem to take more time to decide cases where the defendant is female. This insight points us in a direction where we can further analyze the time taken by judges and ways to reduce them.


###### Analysis-4
In analysis notebook 4, a new feature is introduced. "Tenure" of a judge which is the days of of experience the judge had at the time of decision.  The data was initially clustered using the k-means clustering algorithmn. These clusters were used for further analysis, and the correlation between the tenure of the judge and the time taken for a case to be concluded was analyzed.

**Insights**
1. Average tenure of judges dealing with non-criminal cases is higher than that of the judges dealing with criminal cases. This could be a contributing factor to the reduced time_taken to deal with non-criminal cases, which we have seen here and in more detail in Analysis-1.

2. The correlation between tenure and time_taken can again be seen when we observe the gender split. The tenure of Female judges can be seen to be less than that of Male judges on average, and this correlates to the time taken of Female judges greater than that of Male judges