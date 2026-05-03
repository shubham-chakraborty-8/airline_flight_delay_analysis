# Airline Flight Delay Analysis

## Introduction
Airline delays are a critical operational and customer experience challenge, but they are often analyzed in isolation - focusing either on delay frequency or duration without a unified view.

This fragmented approach makes it difficult to identify true performance bottlenecks, assess operational efficiency, and understand risk patterns across airlines.

This project aims to address this gap by combining frequency, severity, and efficiency metrics to provide a comprehensive view of airline delay behavior and enable more accurate performance comparison.

## Tools Used 
Python, Excel, Power BI

## Dataset
[Kaggle - Flight Delay Data](https://www.kaggle.com/datasets/sriharshaeedala/airline-delay)

## Key KPIs

1. On-time Performance
2. Cancellation Rate
3. Impax%
4. Disruption Score

# Exploratory data analysis
The full EDA can be found the notebook [here](https://github.com/shubham-chakraborty-8/airline_flight_delay_analysis/blob/main/flight_delay_project.ipynb).

## Flight Disruption Mix
<img width="1393" height="672" alt="flight_disruption_mix_trend" src="https://github.com/user-attachments/assets/a3d8fb35-b82c-4afa-8e5c-21b321e7f4ec" />
The figure above shows the disruption matrix of all flights for the years. Delays dominate, cancellations spike around pandemic and diversions are rare.


## Delay Cause Matrix
<img width="1084" height="687" alt="delay_cause_matrix" src="https://github.com/user-attachments/assets/0542b2e1-e5d2-42c4-bd03-0f3af5765dae" />
The figure above shows the causes and the severity - frequency matrix. Carrier delays are by far the biggest cause of disruption. Weather delays are infrequent but intense.

## Airline Performance mstrix
<img width="1080" height="693" alt="Airline_performance_matrix" src="https://github.com/user-attachments/assets/6ca7e6e6-8ff7-4332-b9ea-e204cf9f62b2" />
The standard deviation in delay rate of airlines is plotted against the average delay rate thus showing us a volatility matrix of each airline. Alaska, Horizon, Airtrain and Delta are clearly doing something right being both low delay and less volatile. Hawaiian airlines has low delay rate but unrealiable due to volatility. Jetblue, Expressjet are clearly the worst performing due to being heavily delayed and also being unreliable.


## Airline Summary
| carrier name                 | arr_flights | arr_del15 | arr_cancelled | severe delay flights | cancel rate | OTP % | ImPax % | disruption score | disruption score std |
|------------------------------|-------------|-----------|---------------|----------------------|-------------|-------|---------|------------------|----------------------|
| ExpressJet Airlines LLC      | 149234      | 29672     | 8198          | 24162                | 6.70        | 74.62 | 21.68   | 0.53             | 0.13                 |
| American Eagle Airlines Inc. | 279283      | 61132     | 15074         | 16667                | 5.29        | 72.71 | 11.37   | 0.50             | 0.15                 |
| Allegiant Air                | 613357      | 149943    | 24303         | 109832               | 4.32        | 71.59 | 21.87   | 0.43             | 0.13                 |
| Mesa Airlines Inc.           | 914298      | 170060    | 30366         | 134447               | 3.70        | 78.08 | 18.03   | 0.38             | 0.12                 |
| JetBlue Airways              | 2609697     | 647919    | 59509         | 387498               | 2.52        | 72.89 | 17.13   | 0.37             | 0.14                 |
| ExpressJet Airlines Inc.     | 2637669     | 540578    | 85844         | 325087               | 3.03        | 76.25 | 15.58   | 0.37             | 0.13                 |
| Envoy Air                    | 2073685     | 394625    | 74306         | 139931               | 3.41        | 77.39 | 10.33   | 0.36             | 0.12                 |
| PSA Airlines Inc.            | 1326337     | 231648    | 43897         | 136204               | 3.25        | 79.23 | 13.58   | 0.35             | 0.12                 |
| Frontier Airlines Inc.       | 1158943     | 291403    | 22063         | 221710               | 2.33        | 72.95 | 21.03   | 0.35             | 0.14                 |
| Spirit Air Lines             | 1526076     | 330708    | 34307         | 244802               | 2.55        | 76.08 | 18.29   | 0.34             | 0.13                 |
| Republic Airline             | 1717781     | 270036    | 55345         | 184860               | 3.43        | 81.06 | 13.98   | 0.33             | 0.10                 |
| American Airlines Inc.       | 7973061     | 1538261   | 167510        | 593153               | 2.12        | 78.61 | 9.54    | 0.32             | 0.13                 |
| Southwest Airlines Co.       | 12522217    | 2460563   | 275976        | 186790               | 2.11        | 78.15 | 3.70    | 0.32             | 0.13                 |
| SkyWest Airlines Inc.        | 6905056     | 1167810   | 138798        | 727460               | 2.45        | 81.08 | 12.55   | 0.30             | 0.11                 |
| United Air Lines Inc.        | 5464237     | 1030741   | 86820         | 504180               | 1.89        | 79.55 | 10.82   | 0.30             | 0.12                 |
| Horizon Air                  | 200419      | 28682     | 3608          | 5154                 | 2.09        | 83.89 | 4.37    | 0.26             | 0.09                 |
| Endeavor Air Inc.            | 1466178     | 200559    | 31742         | 151670               | 2.24        | 84.16 | 12.51   | 0.25             | 0.09                 |
| Virgin America               | 301908      | 64605     | 3156          | 24057                | 0.94        | 77.56 | 9.01    | 0.25             | 0.11                 |
| AirTran Airways Corporation  | 143429      | 25226     | 1812          | 2248                 | 1.17        | 81.15 | 2.83    | 0.24             | 0.11                 |
| Alaska Airlines Inc.         | 1990957     | 317730    | 25877         | 34957                | 1.55        | 82.74 | 3.06    | 0.24             | 0.09                 |
| US Airways Inc.              | 784157      | 134516    | 12167         | 7678                 | 1.06        | 81.29 | 2.53    | 0.24             | 0.11                 |
| Hawaiian Airlines Inc.       | 727265      | 89794     | 4850          | 7394                 | 0.57        | 86.99 | 1.68    | 0.23             | 0.11                 |
| Delta Air Lines Inc.         | 8661561     | 1198884   | 85395         | 531592               | 1.11        | 85.17 | 7.12    | 0.20             | 0.08                 |
The summary is sorted along the disruption score. Since I could not find any reliable universal performance scoring metric for the airline industry, I provided weighted scoring to the disruption events such as delays, cancellations and diversions. Cancellations got the highest score of 5, diversions got 3 and delays being most common and least disruptive among the three got a baseline scoring. The combination created a table that confirms the performance matrix to a high degree. Delta Air lines being the clear most reliable alternative despite being one of the larger airlines highlights their efficiency. Both the top most disruptive airlines had to rebrand themselves later on due to being highly inefficient.
