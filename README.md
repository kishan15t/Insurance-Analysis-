# Insurance-Analysis-Dashboard

### Dashboard Link :  
[View Insurance Analysis Dashboard](https://app.powerbi.com/links/6ZYZvQcTbb?ctid=f5410ffc-6e44-4b90-ae76-efeeaafbdf4f&pbi_source=linkShare)

## Problem Statement

The insurance industry handles vast amounts of data related to policies, claims, premiums, and customers. Without proper visualization, it becomes difficult to identify trends, monitor performance, and make data-driven decisions.

This dashboard provides a **comprehensive analysis of insurance data** to help stakeholders understand:

* Distribution of active vs. inactive policies
* Claim trends by status and customer demographics
* Premium and claim amounts by policy types
* Overall coverage and risk exposure
* Customer segmentation by gender and age groups

With these insights, the company can **reduce claim rejection rates, optimize policy offerings, and improve customer satisfaction.**

## Steps Followed

* **Step 1:** Loaded the insurance dataset (CSV file) into **Power BI Desktop**.

* **Step 2:** Opened **Power Query Editor** and in the **View tab**, enabled
  *Column distribution*, *Column quality*, and *Column profile*.

* **Step 3:** Changed profiling settings to **analyze the entire dataset** (instead of the default 1000 rows).

* **Step 4:** Verified data quality — observed that the dataset contained no major errors or empty values across columns.

* **Step 5:** Created two **calculated columns** using DAX:

  * **Age Group Column:** Customers were grouped into different ranges for segmentation.

    ```DAX
    Age Group =
        ((
        If(Insurance[Age] <=24, ("Young Adult")),
        If(Insurance[Age] <= 60, ("Adults")),
        Else(Insurance[Age] >= 60, ("Elders")),
        
        ))
    ```

       ![Snap_1](https://github.com/user-attachments/assets/235b6856-80ac-471b-89fc-fa5d8941dbea)




  * **Policy Activity Column (Active vs. Inactive):** Based on `Policy Status`, customers were categorized.

    ```DAX
    Policy Active/inactive =
    If(Insurance[Policy_EndDate] <= 10-01-2025, ("Inactive"),
    Else ("Active")
    ```

* **Step 6:** In the **Report View**, selected a suitable **theme** under the *View tab* for consistent dashboard formatting.

* **Step 7:** Built KPI **Card Visuals** to display:

  * Total Premium Amount
  * Total Coverage Amount
  * Total Claim Amount

* **Step 8:** Added **Slicers (visual filters)** to allow users to interact with the dashboard by filtering data on:

  * Policy Number
  * Claim Number
  * Customer ID
  * Age Group

* **Step 9:** Designed **charts and visuals** for deeper analysis:

  * **Donut chart** for Active vs. Inactive policy distribution.
  * **Bar/Column charts** showing Claim Amounts by Policy Type and by Age Group.
  * **Stacked bar chart** for Claim Status (Settled, Pending, Rejected).
  * **Pie chart** for Gender distribution of policyholders.

* **Step 10:** Incorporated **demographic insights**, showing how different genders and age groups contributed to premiums and claims.

* **Step 11:** Added **KPIs & Trends** such as:

  * Claim rejection rate
  * Claim settlement rate
  * Premium contribution by policy type (Travel, Health, Auto, etc.)

* **Step 12:** Inserted **text boxes, shapes, and labels** for professional formatting — including dashboard title, business context, and clear section highlights.

* **Step 13:** Published the final **Insurance Analysis Dashboard** to **Power BI Service** for sharing and collaboration.


## Snapshot of Dashboard

![Snap_1](https://github.com/user-attachments/assets/fa76c790-8643-45b7-8b57-9cc1c3d6fab0)


## Insights

Some key findings from the dashboard:

### \[1] Policy Insights

* Travel policies contribute the highest premium amount (2.5M).
* Health and Auto policies follow with 1.2M and 1.0M respectively.
  
![Snap_1](https://github.com/user-attachments/assets/5a5dc18b-092e-4105-8cbb-424d7390d69d)



### \[2] Claim Analysis

* Total claim amount stands at **16.91M**.

![Snap_1](https://github.com/user-attachments/assets/34df1969-c1c2-49ce-9a5c-c7ecc3aaea50)


* Claim status distribution:

  * Rejected: 4.4K claims
  * Settled: 3.4K claims
  * Pending: 2.3K claims

### \[3] Customer Segmentation

* Gender distribution is almost equal (Female: 5001, Male: 5003).
* Adults contribute the highest claim amount (8.7M), followed by Elders (6.7M).

![Snap_1](https://github.com/user-attachments/assets/4d74faa6-08e6-4780-a86b-68f7e01e7334)


### \[4] Policy Activity

* Active policies: 50.19%
* Inactive policies: 49.81%

![Snap_1](https://github.com/user-attachments/assets/bea36d52-44bc-455a-b9c7-261bb61ba4ad)




## Conclusion

This dashboard enables the insurance company to **track policy performance, analyze claim outcomes, and understand customer behavior**. By leveraging these insights, decision-makers can design better policies, minimize risks, and improve customer satisfaction.
