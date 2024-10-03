# Practical Application 5.1 - Will the Customer Accept the Coupon?

## Question I explored: What factors drive acceptance of takeaway/carry-out coupons?
In this exercise, I wanted to explore what attributes differentiate customers who accept vs reject a coupon for takeaway/carry-out restaurants. I looked at three main factors:
1. What time of day the driver received the coupon
2. Where the driver was originally planning to go (work, home, or nowhere in particular)
3. Whether the restaurant was in the same or opposite direction from where the driver was originally planning to go

I explored these questions in this Jupyter notebook: https://github.com/umaunni3/berkeley-ml-ai-2024-umaunni/blob/main/practical_application_5_1/practical_application_5_1.ipynb

## Findings

### 1. Time of day
I found that drivers who received a coupon at 2 PM or 6 PM were most likely to accept the coupon, and drivers who received it at 7 AM were least likely to accept. This can be seen in the graph below.

![coupon_acceptance_vs_time_of_day](https://github.com/user-attachments/assets/348fdc99-7b3a-428f-8944-10a7efd3670d)

In particular, 86.6% of drivers accepted a takeout coupon at 2 PM, and 82.08% of drivers accepted it at 6 PM. This is much higher than the 66.12% of customers who accepted it at 7 AM.

### 2. Original driver destination
I found that customers are most likely to accept a coupon when they're heading home, or have no destination in mind.
![coupon_acceptance_vs_destination](https://github.com/user-attachments/assets/d79643bc-dcbe-43bb-9f51-08274f400d54)


Customers who are heading home are 79.19% likely to accept a takeout coupon, and customers without a destination in mind are 76.15% likely to accept it. Meanwhile, customers heading to work are only 66.12% likely to accept the coupon.

### 3. Same vs opposite direction
I found that drivers do not seem to care much whether the coupon they receive is in the same direction as their destination, or the opposite. 

![coupon_acceptance_vs_direction](https://github.com/user-attachments/assets/962ba7da-c498-4e72-afdc-b1464b1d34a9)



Specifically, 70.58% of drivers accepted a coupon when when the restaurant was in the same direction as their destination, while 75.36% of drivers accepted a coupon when the restaurant was in the opposite direction.

This finding was actually rather unintuitive, as even on the margin, I expected that drivers would be more likely to accept coupons for places that were along their path home.

## Recommendations

Based on the findings above, I would make the following three recommendations to companies interested in maximizing the likelihood of customers accepting coupons sent by the company.

1. Aim to send the most coupons around 2 PM and 6 PM, and avoid sending coupons early in the morning (e.g. 7 AM, or even 10 AM). This can lead to an increase of up to 20 percentage points in coupon acceptance rate.
2. If the customer's destination is known, prioritize sending coupons to customers who are either heading home, or don't have a particular destination in mind. This can increase coupon acceptance rate by 10+ percentage points!
3. Don't spend resources on trying to optimize on choosing restaurants that are in the same direction that the customer is heading. This has a minimal effect on coupon acceptance rate, only around 5 percentage points of difference.
