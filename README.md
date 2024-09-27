<img width="1631" alt="Screenshot 2024-09-27 at 10 12 38" src="https://github.com/user-attachments/assets/ee29267d-256b-411e-b9c4-a189ba49283c">

## Project Overview 🗺️
Welcome to the **Salary and Pay Equality Insights project**, where we dive deep into salary data from Montgomery County, MD paid in 2023. Using the magic of **Excel** (yes, Excel – still a powerhouse!), this project analyzes pay trends, wage disparities between men and women, and provides some eye-opening statistics. 🌟

### Analytical Methods Used:

* **Descriptive Statistics** – talking averages, standard deviation, the highest and lowest salaries plus, some handy histograms to visualize the spread.
* **Pareto Analysis** – Ever heard of the 80/20 rule? Let's see if that's true that small percentage of Departments can impact a large portion of payroll.
* **Correlation & Regression Analysis** – Want to know how variables like gender correlate with the salary? I've got you covered.

### Interesting Facts About Montgomery County, MD 🏞️

Montgomery County is home to Great Falls, one of the most stunning natural attractions in the region, offering breathtaking views and a chance to feel like you're living inside a postcard.
The county boasts some serious history – it’s where George Washington crossed the Potomac to reach Georgetown.
This area is part of the DC Metro region, so it’s a hotbed for politics, innovation, and, of course, salary data worth analyzing!

## Key Statistics 🏆
Curious which departments are raking it in after hours or where the Big Bucks are? Before we get into the data nitty-gritty, here are some quick stats.

<img width="1089" alt="Total Headcount" src="https://github.com/user-attachments/assets/3a111701-d7dc-4872-beca-16d522dcf613">

<img width="1083" alt="Screenshot 2024-09-27 at 11 28 22" src="https://github.com/user-attachments/assets/07f06d79-9dc8-4090-a130-b48da73de34b">

<img width="1088" alt="Screenshot 2024-09-27 at 11 28 48" src="https://github.com/user-attachments/assets/d7bc9b7b-364a-42c7-a64a-466da9aebb61">

<img width="1088" alt="Paid Longevity pay" src="https://github.com/user-attachments/assets/52c07c9c-98e3-4971-b4f9-868c23ec02be">

## Introducing the Data and Problem 📁

The gender pay gap is still a common issue today, with women often earning less than men for similar work. It's a topic worth exploring, as it raises important questions about fairness and equality in the workplace. Analyzing this issue can reveal interesting insights into how salaries are structured and possibly (hopefully!) where improvements can be made.

I've searched for some public data which that would be reliable and available for analysis. After some research I came across the **Employee Salaries - 2023** of Montgomery County of Maryland. It looked great so I've started my adventure right away! I've loaded the CSV file via Power Query and did a quick check of the dataset. The file was in great condition, nothing messy (no blanks, invalid formats etc.) just removed some duplicates (617). After a quick data cleanup, the set of 9,675 records was loaded to Excel spreadsheet.

<img width="1645" alt="Screenshot 2024-09-27 at 13 46 59" src="https://github.com/user-attachments/assets/bccb1fb7-c824-499e-96a3-9269911de9b3">

## Descriptive Analytics 👩‍🔬

So, let's start at a very high level. **Is there a gap between what women earn and what men earn in Montgomery County, MD?**
We can begin by looking at one of the most popular measures: the **average**. Let's first check this estimate for the entire dataset, and then we can break it down by men and women separately.

`` =AVERAGEIFS(average_range, criteria_range1, criteria1, [criteria_range2, criteria2], ...) ``

<img width="896" alt="Screenshot 2024-09-18 at 10 19 00" src="https://github.com/user-attachments/assets/bf122182-72e1-437f-8f33-4ca8fbeca4d3">


There is a significant difference in pay between men and women on a very high, company level. The average salary for men is 5% higher than the average salary for women. However, we need to remember that the average can be very very misleading because it doesn't tell us the full story. We need to use **standard deviation** to help us start to understand what's going on with our average. So let’s go ahead and calculate the standard deviation of our data and maybe that will provide a little bit more clarity on to why there is this difference between men and women in terms of pay.

`` =STDEV.S(number1,[number2],…) ``

<img width="772" alt="Screenshot 2024-09-18 at 10 57 42" src="https://github.com/user-attachments/assets/4b376a99-a0ca-4d22-a485-05bfef3d174d">

That means 68 percent of our data is between negative 1 standard deviation and one positive standard deviation of this average of **$90,726**.

<img width="631" alt="68 of all data falls within" src="https://github.com/user-attachments/assets/12b39a83-f8f9-4f2e-9cb1-15763a1e20f1">

So it means 68 percent of our data is between **$59,951** and **$121,500**

<img width="763" alt="Screenshot 2024-09-18 at 10 59 07" src="https://github.com/user-attachments/assets/1f15a101-7117-4ad2-8dd5-9fea577cadb0">

and then 95 percent of our data is between **$29,177** and **$152,274**.

<img width="774" alt="Screenshot 2024-09-18 at 10 59 36" src="https://github.com/user-attachments/assets/baf5cd63-5d85-452a-acb4-f25a136ea348">


If you think about that intuitively if 68 percent of all of our data is between let's say **sixty thousand** and **over hundred and twenty thousand**, that’s a fairly big number and a big gap.

![Gif Banner-3](https://github.com/user-attachments/assets/cb80d03c-b6f8-4630-a095-b444077ceedd)

Let’s dig a bit dipper, but this looks like a pretty big standard deviation.

So, let's go out and calculate the standard deviation by each subsection **between men and women**. We are going to do standard deviation of a sample. Let’s start with calculating the female standard deviation. 

<img width="781" alt="Screenshot 2024-09-27 at 11 51 19" src="https://github.com/user-attachments/assets/70ffc68e-394d-41b8-9833-9acbed0304f7">

When looking at the number we can see that it is even **higher** than the overall standard deviation. Well, that’s a surprise, I didn’t expect that. This means that women's salaries are spread out quite widely when we look at the overall distribution. These are not tighten to the average. We could expect some outliers here.

In order to have a better picture, we need to check the same for men. 

<img width="748" alt="Screenshot 2024-09-18 at 11 27 56" src="https://github.com/user-attachments/assets/1f8bd5ae-12f3-47fd-89f2-a667521d2d58">

These are a bit more grouped together but still, the male standard deviation is pretty big. There is no significant difference in standard deviation between men and women. Such situation could mean that there is a large disparity between the lowest and highest salaries in both subgroups.

<img width="715" alt="Screenshot 2024-09-18 at 11 44 04" src="https://github.com/user-attachments/assets/988291f5-5cd4-4e72-a145-fd2d25a6c921">

Let’s try to nail it down. We can start checking by using **minimum and maximum** salary. See if we can find where are the outliers.

`` =MIN(number1, [number2], ...) ``

<img width="773" alt="Screenshot 2024-09-18 at 11 52 40" src="https://github.com/user-attachments/assets/9ec42bc2-4895-4e77-b953-57b047e7b521">

Ok, again a source of amazement. When comparing the overall and female salaries we can see that the **minimum** salary for woman is noticeably higher. It means that the minimum salary for male needs to be much lower, equal to the overall minimum. Let’s calculate that.

<img width="748" alt="Screenshot 2024-09-18 at 11 58 54" src="https://github.com/user-attachments/assets/94c2f342-e068-4931-81a5-8608102b4700">

Correct. Women's minimum wage is 64% higher than men’s. That’s a huge gap! Women have a 64% higher minimum wage than men, suggesting that the lowest-paid women are better paid than the lowest-paid men.

![DAproject2](https://github.com/user-attachments/assets/34084bd5-7ee8-4713-9667-95a7c756b9e3)

Let’s look at the **maximum** salaries for both groups. 

`` =MAX(number1, [number2], ...) ``

<img width="775" alt="Screenshot 2024-09-18 at 12 47 33" src="https://github.com/user-attachments/assets/321bdf01-84fb-4caa-a08b-f90b5619096d">

In this case, the maximum overall salary is equal to men's maximum salary and is 16% higher than women's salary. Again, that seems to be a big disproportion. Men have higher maximum earnings ($292,000) than women ($246,162), a difference of -16%. This may suggest that men dominate the highest-paid roles.

Values ​​such as the minimum wage ($11,147 for men) and maximum wage ($292,000 for men) suggest the existence of some "outliers" - workers with extremely low or high wages, especially among men.

What else do we need to do to start to dig in? So let's look at one additional item to see how our data is grouped together. We're going to use is a formula to calculate the **percentile**.

`` =PERCENTRANK.INC(array,x,[significance]) ``

So what we want to calculate is what percent of our salaries are below, let's say $93,000. We want to see if there are more women that are being paid less than men. So at this $93,000 range, do we have more women being paid, less money or more men being paid less money, or are they about the same?

<img width="773" alt="Screenshot 2024-09-18 at 14 17 38" src="https://github.com/user-attachments/assets/49a168e8-0d16-4313-964a-39cefc64e0a7">

By calculating what percentage salaries are below $93,000, we start to get a sense of how our data is grouped. OK, what we see that 56% of the entire workforce at Montgomery County,MD earns below $93,000. Well, that doesn’t’t help us much so let’s move on to our subgroups. 

<img width="770" alt="Screenshot 2024-09-18 at 14 05 48" src="https://github.com/user-attachments/assets/0e916592-ae6b-4d6f-8018-82637f88f292">

We can see that 59% of all women are paid below $93,000 so that means there are more salaries below ninety three thousand for women than for men. We can easily prove that by looking at the percentile for men. Looking at the outcome we can see that only 53% of the men are being paid less than ninety three thousand. The difference is about **11%**.

📁Let’s put the puzzle together and summarise what we have gathered so far: 

* We know that men are getting paid more than women by about a factor of 5 percent.
* And we know that there are more lower paid women than lower paid men (59% of the women are lower paid and only 53% percent of men are lower paid)

Hang on, there should be something going on here.
![DAproject3](https://github.com/user-attachments/assets/ffcb50e7-3249-4775-ab6d-b825bed19618)

Well, maybe there's some division that is getting paid significantly more than some other department?
And so let's go ahead and break out the salaries by division and let's just see if there's some department
that's getting paid way more than another department. And maybe, by any chance that division has more men than woman. We need to check that hypothesis. 

Let’s dive in!
![Gif Banner-4](https://github.com/user-attachments/assets/8262725f-a850-4f9e-90d1-d747b13193d6)

Firstly let’s go ahead and break out the average salary by department for the whole workforce and then between women and men. 

<img width="619" alt="Screenshot 2024-09-18 at 23 06 29" src="https://github.com/user-attachments/assets/bb89e6c1-0ca1-4689-8a79-67108717b628">

So right away we see that there is some disparity in the overall pay. In order to have a better picture of the whole story, let’s sort the data descending by column **F vs. M (%)**

<img width="567" alt="Screenshot 2024-09-18 at 23 07 16" src="https://github.com/user-attachments/assets/b0082260-f616-4b8f-bdd8-6c33ab40ea62">

Ok, now some disproportions are almost jumping out at us! Let’s extract information from what we see here🤓

1. **Departments where women earn more 👩:** There are several departments where women earn more than men. Examples include for example: Community Engagement Cluster (9%), Board of Elections (9%), Correction and Rehabilitation (8%), Department of Technology and Enterprise Business Solutions (6%), Office of Human Resources (6%), County Council (5%). This could be due to a variety of reasons, including the greater number of women in senior positions in these departments.

2. **Departments with a clear gender pay gap in favour of men 👨:** There are several departments where men earn significantly more than women. Examples include: Merit System Protection Board Department (59%), Ethics Commission (39%), Office of Grants Management (40%), Office of Legislative Oversight (29%). These differences may indicate barriers to career advancement for women or differences in the availability of top positions. This is clearly something that could be looked into even further.

3. **Large pay gaps, but in favour of women 👩:** In the case of several departments, such as the Office of Food Systems Resilience (16%) and Alcohol Beverage Services (12%), women earn more than men. It would be worth investigating whether this is specific to the roles that women play in these departments or is the result of employment policies that are possibly unfavourable to men.

4. **Lack of male employees👨:** Women are employed in each of the 42 departments, however in 4 of them there are no men employed. These are: Office of Intergovernmental Relations Department, Office of Zoning and Administrative Hearings, Office of Racial Equity and Social Justice and Board of Appeals Department. This may mean that departments are dominated by women or are specific to roles in which men are not employed. However, this may again be the result of employment policies that are unfavourable to men. Since this cannot be verified simply by looking at the available data, this is clearly something that could be investigated further internally by the Montgomery County’s Office.

Alright, it looks that we’ve got a bit more idea on what is going on with our data, but do not rest on our laurels. Let's continue our investigation 🔎.

## Creating a Histogram 📶

The best way to see how our data is distributed, would be to create a histogram. Maybe there's a lot of data skewing to the right or a lot of data skewing to the left or maybe it's all come true on the average. By creating a histogram we can visualise what’s going on with our salaries. Therefore, without further due, let’s do it!

<img width="346" alt="Creating a Histogram" src="https://github.com/user-attachments/assets/57e2a95f-e868-428a-a5fa-745aa2d61104">

Ok, so the first thing we need to do is to figure out what we want as the lowest value on our histogram. Well, I suggest we go and find our minimum salary and find the minimum value. In our case that is a bit over $11,000.

<img width="601" alt="Asking Overall Descriptive Questions" src="https://github.com/user-attachments/assets/0e20f98c-ac5f-46d1-8652-6425ec806039">

Secondly, since the histogram consists of buckets, we need to decide on how we want to divide the entire range of values into a series of intervals. We want to have a small enough increment that we are actually capturing enough of our data in each bucket, but not so large that we group everything all together. Since our minimum salary is approx. $11,000 and maximum is $292,000 I would suggest setting the increments at $20,000. I’ve tried smaller values before, but $20,000 looks like a perfect match to me👌.

<img width="302" alt="Creating a Histogram" src="https://github.com/user-attachments/assets/7fffa25b-d236-4fd7-a0e1-f700f4bcca29">

Ok, now we need to count how many values fall into each interval. In order to do so, we will use our friend COUNTIFS function.

`` =COUNTIFS(criteria_range1, criteria1, [criteria_range2, criteria2]…) ``

<img width="366" alt="Creating a Histogram" src="https://github.com/user-attachments/assets/af404ed6-8be2-4516-9253-1d1f75f00046">

Once done, we can use columns Bin Name and Frequency and finally create our Histogram.

<img width="1540" alt="Screenshot 2024-09-19 at 12 56 19" src="https://github.com/user-attachments/assets/06c51e66-788b-4ac4-9633-9759e88b8ab7">

So, by looking at the diagram we can see a **fairly normal distribution**, nothing too crazy here. We have a few of lower level people, a lot in the middle, a few people in mid to upper management and then very few people in upper management. So the distribution looks fairly normal nothing too out of the ordinary. 

I would say that that’s all we can do with the histogram at this point. Sometimes the histogram will reveal the information to us and point things out we didn’t recognise before, but in this case the diagram seems fairly normal. Nothing stands out and that’s perfectly fine. Let’s move on to some different analysis.

## Pareto analysis ☯️

Pareto analysis is a decision-making technique used to statistically separate the data entries into groups with the most or least effect on the data. It can help us determine if there are certain pieces of data that we should concentrate more on. In our case, Pareto analysis can help us decide whether the departments with the greatest pay gap contribute so little to overall compensation that they can be overlooked, or, on the contrary, contribute so much to overall earnings that they cannot be ignored. 

Ok, so the easiest way to do Pareto analysis is to use a pivot table. Let’s set some questions we can ask in our analysis. The first one could be: Which 5 divisions have the highest salary, on average? You’re right we’ve already calculated it in our descriptive analysis, but this will be a good start for our pivot table. Before we begin, let’s remember about four departments in which there were no men employed (Ref. Picture 14). Since there is nothing to compare because these entities are entirely filled by women, I suggest we disregard them at that point. This of course should be a subject for further investigation (i.e. in terms of employment policy) but this will not be useful in our gender pay gap analysis. These departments are: 

* Office of Intergovernmental Relations Department
* Office of Zoning and Administrative Hearings
* Office of Racial Equity and Social Justice
* Board of Appeals Department

Ok, let’s continue with our pivot table.

<img width="418" alt="Screenshot 2024-09-23 at 22 02 55" src="https://github.com/user-attachments/assets/94feaf92-9389-4192-8ac8-b6b83bba8bc2">

When we sort the data descending, we will see that **5 divisions with the highest average salary are**: 

* Office of Labor Relations
* Ethics Commission
* Non-Departmental Account
* Office of Legislative Oversight
* Department of Technology and Enterprise Business Solutions

As we have established, Office of Intergovernmental Relations Department and Office of Zoning and Administrative Hearings will be ignored.

Ok, well that’s helpful because we know that if any of these departments makes up a significant portion of the payroll and that has the highest average salary then that might be causing a huge disparity in pay.

Let’s drag the information about the pay gap from our descriptive analysis tab to have a fuller view.

<img width="416" alt="Understanding the Data - Pareto Analysis (The 8020 Rule)" src="https://github.com/user-attachments/assets/5a3a0530-e8ea-4576-8020-8365762dab11">

Alright, that’s a good start but we need to remember that the average does not tell us the full story. We should always incorporate standard deviation with the average in order to have a more clear picture of what’s going on with the average. So let’s go ahead and calculate the standard deviation which is measuring variance and let's just see if that gives us any more information. 

The next question we can ask is: **which 5 divisions have the highest variance?** We need to quickly update our pivot table and see that the results are:

* Offices of the County Executive
* Merit System Protection Board Department
* Ethics Commission
* Office of Agriculture
* Non-Departmental Account

Worth mentioning is that for all of the above the standard deviation is pretty huge - from $42,989 up to $62,852 (remember that our standard deviation was around $30,000 ref. Picture 16). Again, to have a better view, let’s drag the pay gap data.

<img width="883" alt="Screenshot 2024-09-23 at 22 18 27" src="https://github.com/user-attachments/assets/0da0bb3e-27ec-410c-866c-d758013c257f">

Alright, when looking at our lists we see that there are some entities we can keep on the radar for a while. Especially Ethics Commission which has one of the highest average salaries, the highest standard deviations and a huge gender pay gap (39%). Ok, we can say that these validate what we have already done before. We didn’t get any new information but kind of crossed checked our previous conclusions, especially that the departments with the highest variance also have a large pay gap. 

Let’s move on with our Pareto analysis. If you remember the Pareto analysis is the 80/20 rule, meaning that roughly 80% of consequences come from 20% of causes. So let’s see if 20 percent of the divisions are accounting for 80 percent of all the salaries and find out where we need to focus our attention.

The first thing we would do is add the total salaries by department within our pivot table. 

<img width="910" alt="Screenshot 2024-09-24 at 11 17 33" src="https://github.com/user-attachments/assets/18b279da-687a-48e4-9542-5e25d0b97bbb">

So now we can see how much salary each of these departments is contributing. By sorting the data descending, we can see couple of units which clearly stand out from the crowd. In order to get more insights we need to create a running total. It will help us to see what percent each of this department contribute to the whole.

<img width="1039" alt="Screenshot 2024-09-24 at 12 06 51" src="https://github.com/user-attachments/assets/723b935d-8cb0-448c-a8b0-d898f01dc81b">

Ok, so now we have our running total of salaries and it is clear that 9 out of 42 departments make up 80% of the overall payroll.
Ou question here is: **What "20%" of divisions make up 80% of our payroll?**

* Department of Police
* Department of Health and Human Services
* Fire and Rescue Services
* Department of Transportation
* Correction and Rehabilitation
* Department of General Services
* Alcohol Beverage Services
* Department of Public Libraries
* Department of Permitting Services

Especially first four have a huge part in overall salaries: Department of Permitting Services (18%), Department of Health and Human Services (16%), Fire and Rescue Services (15%) and Department of Transportation (12%). Other don’t make up too much (5% or less).

Let’s drag the data about the pay gap and put it all side by side.

<img width="380" alt="What 20 of divisions make up 80 of our payroll" src="https://github.com/user-attachments/assets/245d73ad-611c-4b52-9938-d2b273b0ab66">

Ok, so Department of Health and Human Services and Fire and Rescue Services are pretty equal in terms of pay, but **Department of Permitting Services** and **Department of Health and Human Services** - these are not something that can be overlooked. In both of them there is a huge pay disparity and both contribute significantly to the overall earnings. To have it even clearer, so we can actually see it, let’s create a combo chart. I don’t know about you guys but for me visualisations always help to process and remember information.

<img width="1607" alt="Screenshot 2024-09-21 at 16 16 52" src="https://github.com/user-attachments/assets/ee1954de-0431-4df3-b781-5d69aa2aac39">

So even though we didn't learn too much here we still know that we can't just ignore any of these items. That’s what the Pareto analysis is for. We want some insights to stand out as say “look at us!”😉. We need to keep on digging and ask more questions. Remember, data analytics is all about asking more questions.

## Correlation Analysis 🪢

The next thing we can do is to verify if there’s some **correlation between gender and salary**. Since we know that there is some disparity in this field, maybe it’s worth checking if there is any relation between these two variables. Let's start at the macro level, examining the entire company, and then move on to examining two departments that caught our attention during the Pareto analysis. So the questions we will ask here would be:

* Is there a relationship between salary and gender?
* Is there a relationship between salary and gender in Department of Police?
* Is there a relationship between salary and gender in Dept. of Health and Human Services?

Correlation works with numbers so the first thing we need to do is to manipulate our data and just assign a number two each of these genders. Let’s say Female will be assigned 1 and Male 0. We will call our new column “Gender Variable”.

`` =IF(logical_test, [value_if_true], [value_if_false]) ``

<img width="1040" alt="Screenshot 2024-09-24 at 13 25 59" src="https://github.com/user-attachments/assets/5c805f61-fe53-4aa0-9b94-2944759c521b">

Now we can perform a correlation on our data.

`` =CORREL(array1, array2) ``

<img width="513" alt="Relationships Between Variables" src="https://github.com/user-attachments/assets/bc1e2da5-746b-4366-b19e-e73906d8be47">

Ok, so we know that overall there is 5% difference in salary, so we know that men are getting paid more than women. Then we run a correlation and see that the relationship is tiny (-0,08). There is basically no relationship between gender and pay. So the answer is not that easy. We cannot say that men are earning more simply because they’re men. At least on the high level there is nothing that would confirm that theory. Ok, so let’s lower our level and check two departments which we have on our radar. Well maybe that would reveal that there is a stronger correlation and we can start to say: Eureka!

<img width="1185" alt="Screenshot 2024-09-24 at 22 12 26" src="https://github.com/user-attachments/assets/7db1a6fc-4eab-4479-85f9-cec6525ad0c3">

<img width="1361" alt="Screenshot 2024-09-24 at 22 13 56" src="https://github.com/user-attachments/assets/fb244a73-4707-411c-b4a9-ccd8bdb1858a">


Alright, the correlation is a bit stronger in the Department of Police (-0,32) but still very small whereas in the Department of Health and Human Services is close to the overall correlation (-0,09). No point Is proven here.

## Conclusion 🥳

Our deep dive into employee salaries in Montgomery County reveals some interesting findings about the pay differences between men and women. On **average, men earn 5% more than women**, however, the situation is more complex than simply identifying a gender pay gap. For instance, **women’s minimum wages are 64% higher than men’s**, meaning that the lowest-paid women actually earn more than their male counterparts. However, **men still dominate the highest salaries, with a maximum earning that’s 16% higher than women’s**, suggesting that men are more likely to occupy the highest-paying positions.

### Key Takeaways 📋:

* The **standard deviation** indicates that women’s as well as men’s salaries are spread out quite a bit, suggesting there are some outliers in both groups.
  
* When looking at **percentiles**, we see that 59% of women earn less than $93,000 compared to 53% of men, pointing out a noticeable difference in the lower salary brackets.
  
* The **Pareto analysis** highlights that certain departments, like the **Department of Permitting Services** and **Department of Health and Human Services**, have some pretty big pay disparities that deserve a closer look.
  
* Interestingly, the correlation between gender and salary across the board is minimal, though it’s slightly more pronounced in the **Department of Police**.

* Surprisingly, **4 departments did not employ any men**. This is something that should definitely be looked into.

### What to Explore Next 🔎:

To get a better understanding of these pay gaps, it would be helpful to:

* Dive into **department-specific salary data** to spot any trends 
* Consider factors like **tenure, maternity leaves, education, and job grades** that might be affecting pay differences
* Look into **hiring and promotion practices** to see how they impact gender representation in higher-paying jobs

✨ In conclusion, while the data indicates a pay gap between genders, **it is crucial to recognize that the problem not unique to women**. Addressing these disparities will require a comprehensive approach that will certainly benefit all employees in Montgomery County.✨

## 📜 License

🎉 **And that's it!** You're all set to further practice your data analytics skills with this nice little set of data. This project is open-source and available under the MIT License. Feel free to use, modify, and distribute it as you like. Happy analyzing!

## 🔗 Source links:

* Data Gov: https://catalog.data.gov/dataset/employee-salaries-2023 

![Gif Banner-5](https://github.com/user-attachments/assets/13131057-aa42-4fe2-a313-1671c3098660)











































