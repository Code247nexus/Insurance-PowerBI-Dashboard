DAX Measures – Insurance Analytics Dashboard

This document describes the key DAX measures used to analyze insurance performance across premiums, claims, profitability, customers, and regions.

Base Measures
Total Premium

Calculates the total premium amount collected from insurance policies.

Total Premium = SUM(Insurance_Data[PremiumAmount])

Total Claims

Calculates the total claim amount paid by the insurance provider.

Total Claims = SUM(Insurance_Data[ClaimAmount])

Total Policies

Counts the number of insurance policies.

Total Policies = COUNT(Insurance_Data[PolicyID])

Profitability Measures
Profit

Measures overall profitability by subtracting claims from premiums.

Profit = [Total Premium] - [Total Claims]

Profit Margin %

Calculates profit as a percentage of total premium.

Profit Margin % = DIVIDE([Profit], [Total Premium])

Risk & Claims Analysis
Claim Ratio

Key insurance KPI showing claim amount relative to premium.

Claim Ratio = DIVIDE([Total Claims], [Total Premium])

Average Claim Amount

Calculates the average claim value.

Average Claim Amount = AVERAGE(Insurance_Data[ClaimAmount])

Time-Based Analysis
Policies by Year

Used for trend analysis across years.

Policies by Year =
CALCULATE(
    [Total Policies],
    VALUES(Insurance_Data[PolicyYear])
)

Claims Trend

Tracks claim amount trends over time.

Claims Trend =
CALCULATE(
    [Total Claims],
    DATESYTD(Insurance_Data[PolicyDate])
)

Customer Analysis
Customers Count

Counts unique customers.

Total Customers = DISTINCTCOUNT(Insurance_Data[CustomerID])

Average Premium per Customer

Measures customer value.

Avg Premium per Customer =
DIVIDE([Total Premium], [Total Customers])

Regional Performance
Premium by Region

Used in regional comparison visuals.

Premium by Region =
CALCULATE(
    [Total Premium],
    VALUES(Insurance_Data[Region])
)

Claims by Region

Identifies high-risk regions.

Claims by Region =
CALCULATE(
    [Total Claims],
    VALUES(Insurance_Data[Region])
)

##Notes for Reviewers

All measures were created using DAX best practices

DIVIDE() is used to safely handle divide-by-zero scenarios

Measures support interactive filtering via slicers for region, policy type, and time

Tools Used

Power BI Desktop

DAX

Power Query

GitHub

IMPORTANT
