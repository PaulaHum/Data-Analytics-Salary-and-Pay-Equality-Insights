<img width="1631" alt="Screenshot 2024-09-27 at 10 12 38" src="https://github.com/user-attachments/assets/ee29267d-256b-411e-b9c4-a189ba49283c">

## Project Overview 
Welcome to the Salary and Pay Equality Insights project, where we dive deep into salary data from Montgomery County, MD, in 2023. Using the magic of Excel (yes, Excel – still a powerhouse!), this project analyzes pay trends, wage disparities between men and women, and provides some eye-opening statistics. 🌟

### Analytical Methods Used:

* **Descriptive Statistics** – talking averages, standard deviation, the highest and lowest salaries plus, some handy histograms to visualize the spread.
* **Pareto Analysis** – Ever heard of the 80/20 rule? Let's see if that's a true that small percentage of employees can impact a large portion of payroll.
* **Correlation & Regression Analysis** – Want to know how variables like gender correlate with salary? Let's check this out.

### Fun Facts About Montgomery County, MD 🎉
Montgomery County is home to Great Falls, one of the most stunning natural attractions in the region, offering breathtaking views and a chance to feel like you're living inside a postcard.
The county boasts some serious history – it’s where George Washington crossed the Potomac to reach Georgetown.
This area is part of the DC Metro region, so it’s a hotbed for politics, innovation, and, of course, salary data worth analyzing!

## Key Statistics
Curious which departments are raking it in after hours or where the Big Bucks are? Before we get into the data nitty-gritty, here are some quick and fun stats.

<img width="1089" alt="Total Headcount" src="https://github.com/user-attachments/assets/3a111701-d7dc-4872-beca-16d522dcf613">

<img width="1083" alt="Screenshot 2024-09-27 at 11 28 22" src="https://github.com/user-attachments/assets/07f06d79-9dc8-4090-a130-b48da73de34b">

<img width="1088" alt="Screenshot 2024-09-27 at 11 28 48" src="https://github.com/user-attachments/assets/d7bc9b7b-364a-42c7-a64a-466da9aebb61">

<img width="1088" alt="Paid Longevity pay" src="https://github.com/user-attachments/assets/52c07c9c-98e3-4971-b4f9-868c23ec02be">

## Descriptive Analytics

There is a significant difference in men and women pay. Average salary for men is higher by 5% than the average salary of women.

`` =AVERAGEIFS(average_range, criteria_range1, criteria1, [criteria_range2, criteria2], ...) ``

<img width="896" alt="Screenshot 2024-09-18 at 10 19 00" src="https://github.com/user-attachments/assets/bf122182-72e1-437f-8f33-4ca8fbeca4d3">


The average can be very very misleading because it doesn't tell us the full story.

We need to use **standard deviation** to help us start to understand what's going on with our average. So let’s go ahead and calculate the standard deviation of our data and maybe that will provide a little bit more clarity on to why there is this difference between men and women in terms of pay.

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

Let’s dig a bit dipper, but intuitively this looks like a pretty big standard deviation.

So let's go out and calculate the standard deviation by each subsection between men and women. We are going to do standard deviation of a sample. Let’s start with calculating the female standard deviation. 

<img width="781" alt="Screenshot 2024-09-27 at 11 51 19" src="https://github.com/user-attachments/assets/70ffc68e-394d-41b8-9833-9acbed0304f7">

When looking at the number we can see that it is even **higher** than the overall standard deviation. Well, that’s a surprise, I didn’t expect that. This means that women's salaries are spread out quite widely when we look at the overall distribution. These are not tighten to the average. We could expect some outliers here.

In order to have a better picture, we need to check the same for men. 

<img width="748" alt="Screenshot 2024-09-18 at 11 27 56" src="https://github.com/user-attachments/assets/1f8bd5ae-12f3-47fd-89f2-a667521d2d58">

These are a bit more grouped together but still, the male standard deviation is pretty big. There is no significant difference in standard deviation between men and women. Such situation could mean that there is a large disparity between the lowest and highest salaries in both subgroups.

<img width="715" alt="Screenshot 2024-09-18 at 11 44 04" src="https://github.com/user-attachments/assets/988291f5-5cd4-4e72-a145-fd2d25a6c921">

Let’s try to nail it down. We can start checking by using minimum and maximum. See if we can find where are the outliers.

`` =MIN(number1, [number2], ...) ``

<img width="773" alt="Screenshot 2024-09-18 at 11 52 40" src="https://github.com/user-attachments/assets/9ec42bc2-4895-4e77-b953-57b047e7b521">

Ok, again a source of amazement. When comparing the overall and female salaries we can see that the minimum salary for woman is noticeably higher. It means that the minimum salary for male needs to be much lower, equal to the overall minimum. Let’s calculate that.

<img width="748" alt="Screenshot 2024-09-18 at 11 58 54" src="https://github.com/user-attachments/assets/94c2f342-e068-4931-81a5-8608102b4700">

Correct. Women's minimum wage is 64% higher than men’s. That’s a huge gap! Women have a 64% higher minimum wage than men, suggesting that the lowest-paid women are better paid than the lowest-paid men.

![DAproject2](https://github.com/user-attachments/assets/34084bd5-7ee8-4713-9667-95a7c756b9e3)













