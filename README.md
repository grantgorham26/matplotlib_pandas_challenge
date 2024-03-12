# matplotlib_pandas_challenge
Pymaceuticals is a pharmaceutical company that specializes in anti cancer medications. Pymaceutials recently started research on squamous cell carcinoma(scc).

A recent study animal study ha just been completed to analyze treatments of scc. In this study, 249 mice who were identified with SCC tumors received treatment with a range of drug regimens. Over the course of 45 days, tumor development was observed and measured. The purpose of this study was to compare the performance of Pymaceuticals’ drug of interest, Capomulin, against the other treatment regimens.


### Analysis

- There were a total of 249 mice used for the study 
- When comparing the avergae tumor volume of each treament Capomulin and Ramicane had the lowest average volume while Ketapril and Naftisol had the highest, the same results occured when compaaring the median volume of the tumor size 
- 1 of the mice had duplicate time points so it needed to be taken out of the data to ensure an accurate study
- of the 10 treaments used Capomulin and Ramicane had the highest number of participants 
- the data consisted of more male mice then female but it was very close to a 50/50 split with it being 51% male and 49% female mice
- when analysing the average final tumor size when using Capomulin, Ramicane, Infubinol, and Ceftamin Infubinol had the largest average while ramicane had the smallest. Along with that Infubinol had one potential outlier while the other 3 treaments had none when using IQR to find outliers
- When looking at a specific mouse (l509) under the Capomulin treatment the tumor size fluxuated over the 45 day treament but did decrease in size after the duration of the treament
- When analyzing the average tumor size of the mice based on their weight there was a postive correlation, the more mass a mouse had the higher the average tuor volume the mouse would have.
- The r-value of the mouse weight vs tumor volume was 0.84 for the Capomulin treatment 


The analysis started by combining the two csv files that contained the mice information and the results of the study into a single data frame. Next the number of mice in the study was found using the .nunique() function. To see if any mice had unusable data I counted the number of times that a mouse id occured in the data. One mouse had 3 extra data points than the rest so this resulted in this specific mouse to be deleted from the data. After this the follwoing statistcis: mean, median, variance, standard deviation, and SEM were calculated on the tumor volume of each unique treatment by utilizng the .groupby() function and the .agg() function in pandas. Using both matplotlib and pandas a bar graph was created to show the number of time points counted for each treatment. .groupby() was again utilized to create the specific  data frames that I wanted. Next two pie charts were created to show the difference of male and female mice in the study. To create the specific dataframe for plotting this I used the .loc() fucntion. After these two charts were created I moved onto analyzing four specific treamnents. When looking at these four treatments a box plot of each treatment was created. To begin this process the IQR was calculated by using a for loop to iterate through all the data and only grab the final tumor volume of each mouse that had undergone one of the four specific treaments. To help me write this code I utilized the BCS learning assistant app in slack as well as a TA in office hours. This for loop was able to calculate the IQR as well as outliers in the data. The for loop also created a list of data that was very useful in creating the box plots. To help create the box plots I utilized the activities from the data-visualization module speciifcally day 3 activity 2 as well as this link: https://matplotlib.org/3.1.1/gallery/statistics/boxplot.html to help customize outliers and customize the box plots. Once the boxplots were complete I looked a specific mouse under the Capomulin treatment. To find this specific mouse I used the .loc() function to first locate the treament and then the specific mouse id. After this a line plot using pandas was created to visualize the change in the tumor volume over the 45 day period. Next a scatter plot and the correlation of the average tumor volume compared to the weight of the mice using the Capomilin treament needed to be created. To create a dataframe for this plot .groupby() was again utilized as well as .mean(). To calculate the correlation linear regression of this data was then created I used the data-visualization day 3 activity 8 and 9 to help write this code. 



