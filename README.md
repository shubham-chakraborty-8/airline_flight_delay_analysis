# Airline Flight Delay Analysis

## Project Assets

- [Presentation Deck](https://github.com/shubham-chakraborty-8/airline_flight_delay_analysis/blob/main/reports/US%20Airline%20Delay%20Performance%20Analysis.pptx)
- [Jupyter Notebook](https://github.com/shubham-chakraborty-8/airline_flight_delay_analysis/blob/main/notebooks/flight_delay_project.ipynb)
- [Power BI Dashboard](https://drive.google.com/file/d/1c9aW8vhthLCCbC4O03aup256x1wy-VRk/view?usp=drive_link)
- [Dashboard PDF](https://github.com/shubham-chakraborty-8/airline_flight_delay_analysis/blob/main/dashboards/flight_delay.pdf)


## Business Problem
Airline delays are a critical operational and customer experience challenge, but they are often analyzed in isolation - focusing either on delay frequency or duration without a unified view.

This fragmented approach makes it difficult to identify true performance bottlenecks, assess operational efficiency, and understand risk patterns across airlines.

This project aims to address this gap by combining frequency, severity, and efficiency metrics to provide a comprehensive view of airline delay behavior and enable more accurate performance comparison.

## Project Objective
This project aims to analyze airline delay patterns using frequency, severity, and operational efficiency metrics.

## Tools & Technologies

- Python 3.x
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Power BI
- Excel

## Dataset
The initial source data was obtained from [Kaggle - Flight Delay Data](https://www.kaggle.com/datasets/sriharshaeedala/airline-delay).
The final processed dataset containing the original variables and engineered features used throughout this analysis is available [here](https://docs.google.com/spreadsheets/d/1BY91xs6ZmVBmrdGWFnY4uSaIcl9CIN7H/edit?usp=drive_link&ouid=109337395518703815337&rtpof=true&sd=true)

## Dataset Overview

This project analyzes **U.S. airline delay performance** using monthly airline and airport operational data. The dataset captures airline operational performance across multiple airports and carriers, including:

- **Flight volume**
- **Cancellations**
- **Diversions**
- **Arrival delays**
- **Delay causes over time**

The objective is to understand operational efficiency, delay severity, and the major contributors to disruptions across airlines and airports.

---

## Dataset Summary

| Metric | Value |
|---------|---------|
| Records (Raw) | 171,666 |
| Records (Processed) | 171,426 |
| Original Features | 21 |
| Engineered Features | 22 |
| Time Period | 2013–2023 |
| Airlines | 21 |


Raw Dataset Shape: (171,666, 21)
Processed Dataset Shape: (171,426, 43)

---

## Original Features

The dataset consists of **four major categories of variables**.

### Time Information

Tracks the time period for airline operations.

- `year`
- `month`

---

### Airline & Airport Information

Contains identifiers and descriptive information for airlines and airports.

**Airline Information**
- `carrier`
- `carrier_name`

**Airport Information**
- `airport`
- `airport_name`

---

### Operational Metrics *(Counts / Frequency)*

These variables represent **how often disruptions occur** in airline operations.

| Feature | Description |
|----------|-------------|
| `arr_flights` | Total arriving flights |
| `arr_del15` | Flights delayed by **15+ minutes** |
| `arr_cancelled` | Cancelled flights |
| `arr_diverted` | Diverted flights |
| `carrier_ct` | Carrier-related delay count |
| `weather_ct` | Weather-related delay count |
| `nas_ct` | National Airspace System delay count |
| `security_ct` | Security-related delay count |
| `late_aircraft_ct` | Late aircraft-related delay count |

---

### Delay Metrics *(Minutes / Severity)*

These variables represent the **operational impact of delays in terms of total delay minutes**.

| Feature | Description |
|----------|-------------|
| `arr_delay` | Total arrival delay minutes |
| `carrier_delay` | Carrier-related delay minutes |
| `weather_delay` | Weather-related delay minutes |
| `nas_delay` | NAS-related delay minutes |
| `security_delay` | Security-related delay minutes |
| `late_aircraft_delay` | Late aircraft-related delay minutes |

---

## Engineered Features

To improve **interpretability** and enable **fair comparisons across airlines**, several additional operational metrics were engineered.

These engineered variables help normalize performance, identify root causes, and evaluate operational efficiency.

---

### Rates *(Efficiency Metrics)*

These features normalize disruptions relative to flight volume and measure operational efficiency.

| Feature |
|----------|
| `delay_rate` |
| `delay15_rate` |
| `cancel_rate` |
| `divert_rate` |

> *Purpose:* Helps compare airlines fairly regardless of operational scale.

---

### Shares *(Delay Composition Metrics)*

These features show the **contribution of each delay cause to total delay time**.

| Feature |
|----------|
| `carrier_delay_share` |
| `weather_delay_share` |
| `nas_delay_share` |
| `security_delay_share` |
| `late_aircraft_delay_share` |

> *Purpose:* Helps identify **what contributes most to delays**.

---

### Frequency Metrics

These features measure **how frequently specific disruptions occur**.

| Feature |
|----------|
| `carrier_delay_freq` |
| `weather_delay_freq` |
| `nas_delay_freq` |
| `security_delay_freq` |
| `late_aircraft_delay_freq` |

> *Purpose:* Measures *how often* different operational issues occur.

---

### Severity Metrics

These features measure the **average delay impact per delayed flight**.

| Feature |
|----------|
| `avg_delay_per_delayed_flight` |
| `carrier_avg_delay` |
| `weather_avg_delay` |
| `nas_avg_delay` |
| `security_avg_delay` |
| `late_aircraft_avg_delay` |

> *Purpose:* Measures *how impactful* delays are once they occur.

---

## Why These Engineered Features Matter

The engineered features help distinguish between:

- **Frequency** → *How often delays happen*
- **Severity** → *How impactful delays are*
- **Efficiency** → *Performance relative to airline scale*
- **Composition** → *What causes delays*

This enables **deeper operational analysis**, more meaningful airline comparisons, and better identification of key delay drivers.

## Key KPIs

1. On-time Performance
2. Cancellation Rate
3. Impax%
4. Disruption Score

---

# Exploratory data analysis
The full EDA can be found the notebook [here](https://github.com/shubham-chakraborty-8/airline_flight_delay_analysis/blob/main/notebooks/flight_delay_project.ipynb).

## Flight Disruption Mix
<img width="1393" height="672" alt="flight_disruption_mix_trend" src="https://github.com/user-attachments/assets/a3d8fb35-b82c-4afa-8e5c-21b321e7f4ec" />
The figure above shows the disruption matrix of all flights for the years. Delays dominate, cancellations spike around pandemic and diversions are rare.


## Delay Cause Matrix
<img width="1084" height="687" alt="delay_cause_matrix" src="https://github.com/user-attachments/assets/0542b2e1-e5d2-42c4-bd03-0f3af5765dae" />
The figure above shows the causes and the severity - frequency matrix. Carrier delays are by far the biggest cause of disruption. Weather delays are infrequent but intense.

## Airline Performance matrix
<img width="1080" height="693" alt="Airline_performance_matrix" src="https://github.com/user-attachments/assets/6ca7e6e6-8ff7-4332-b9ea-e204cf9f62b2" />
The standard deviation in delay rate of airlines is plotted against the average delay rate thus showing us a volatility matrix of each airline. Alaska, Horizon, Airtrain and Delta are clearly doing something right being both low delay and less volatile. Hawaiian airlines has low delay rate but unrealiable due to volatility. Jetblue, Expressjet are clearly the worst performing due to being heavily delayed and also being unreliable.


## Airline Summary
| carrier name                 | arr_flights | arr_del15 | arr_cancelled | severe delay flights | cancel rate | OTP % | ImPax % | disruption score |
|------------------------------|-------------|-----------|---------------|----------------------|-------------|-------|---------|------------------|
| ExpressJet Airlines LLC      | 149234      | 29672     | 8198          | 24162                | 6.70        | 74.62 | 21.68   | 0.53             |
| American Eagle Airlines Inc. | 279283      | 61132     | 15074         | 16667                | 5.29        | 72.71 | 11.37   | 0.50             |
| Allegiant Air                | 613357      | 149943    | 24303         | 109832               | 4.32        | 71.59 | 21.87   | 0.43             |
| Mesa Airlines Inc.           | 914298      | 170060    | 30366         | 134447               | 3.70        | 78.08 | 18.03   | 0.38             |
| JetBlue Airways              | 2609697     | 647919    | 59509         | 387498               | 2.52        | 72.89 | 17.13   | 0.37             |
| ExpressJet Airlines Inc.     | 2637669     | 540578    | 85844         | 325087               | 3.03        | 76.25 | 15.58   | 0.37             |
| Envoy Air                    | 2073685     | 394625    | 74306         | 139931               | 3.41        | 77.39 | 10.33   | 0.36             |
| PSA Airlines Inc.            | 1326337     | 231648    | 43897         | 136204               | 3.25        | 79.23 | 13.58   | 0.35             |
| Frontier Airlines Inc.       | 1158943     | 291403    | 22063         | 221710               | 2.33        | 72.95 | 21.03   | 0.35             |
| Spirit Air Lines             | 1526076     | 330708    | 34307         | 244802               | 2.55        | 76.08 | 18.29   | 0.34             |
| Republic Airline             | 1717781     | 270036    | 55345         | 184860               | 3.43        | 81.06 | 13.98   | 0.33             |
| American Airlines Inc.       | 7973061     | 1538261   | 167510        | 593153               | 2.12        | 78.61 | 9.54    | 0.32             |
| Southwest Airlines Co.       | 12522217    | 2460563   | 275976        | 186790               | 2.11        | 78.15 | 3.70    | 0.32             |
| SkyWest Airlines Inc.        | 6905056     | 1167810   | 138798        | 727460               | 2.45        | 81.08 | 12.55   | 0.30             |
| United Air Lines Inc.        | 5464237     | 1030741   | 86820         | 504180               | 1.89        | 79.55 | 10.82   | 0.30             |
| Horizon Air                  | 200419      | 28682     | 3608          | 5154                 | 2.09        | 83.89 | 4.37    | 0.26             |
| Endeavor Air Inc.            | 1466178     | 200559    | 31742         | 151670               | 2.24        | 84.16 | 12.51   | 0.25             |
| Virgin America               | 301908      | 64605     | 3156          | 24057                | 0.94        | 77.56 | 9.01    | 0.25             |
| AirTran Airways Corporation  | 143429      | 25226     | 1812          | 2248                 | 1.17        | 81.15 | 2.83    | 0.24             |
| Alaska Airlines Inc.         | 1990957     | 317730    | 25877         | 34957                | 1.55        | 82.74 | 3.06    | 0.24             |
| US Airways Inc.              | 784157      | 134516    | 12167         | 7678                 | 1.06        | 81.29 | 2.53    | 0.24             |
| Hawaiian Airlines Inc.       | 727265      | 89794     | 4850          | 7394                 | 0.57        | 86.99 | 1.68    | 0.23             |
| Delta Air Lines Inc.         | 8661561     | 1198884   | 85395         | 531592               | 1.11        | 85.17 | 7.12    | 0.20             |

The summary is sorted along the disruption score. Since I could not find any reliable universal performance scoring metric for the airline industry, I provided weighted scoring to the disruption events such as delays, cancellations and diversions. Cancellations got the highest score of 5, diversions got 3 and delays being most common and least disruptive among the three got a baseline scoring. The combination created a table that confirms the performance matrix to a high degree. Delta Air lines being the clear most reliable alternative despite being one of the larger airlines highlights their efficiency. Both the top most disruptive airlines had to rebrand themselves later on due to being highly inefficient.

---

## Airline Rebranding
Two airline changed their branding while keeping the same IATA code. A simple pivot chart shows the change below. You may access the filtered dataset for the rebranded airlines [here](https://github.com/shubham-chakraborty-8/airline_flight_delay_analysis/blob/main/airline_dataset_final_ev_mq_filtered.xlsx).

<img width="1576" height="580" alt="envoy_express" src="https://github.com/user-attachments/assets/f4d10cec-78b8-48b4-b7e1-371a399cf13d" />
ExpressJet Airlines Inc. became Expressjet Airlines LLC on April 2019. American Eagle Airlines Inc. rebranded to Envoy Air on April 2019.
Clearly Expressjet had to scale down their operations over the years and the pandemic may have been the final chapter in their downfall as their last flight was on the third quarter of 2020. 
American Eagle rebranded to Envoy Air and got slightly better while keeping their flights relatively stable but slowly decreased operations after the pandemic.

---

## Dashboards

The cleaned and feature-engineered dataset was used to build an interactive Power BI reporting solution focused on airline operational performance, delay behavior, and disruption analysis.
The complete Power BI Desktop file can be accessed [here](https://drive.google.com/file/d/1c9aW8vhthLCCbC4O03aup256x1wy-VRk/view?usp=drive_link).
A static PDF version of the dashboard is available [here](https://github.com/shubham-chakraborty-8/airline_flight_delay_analysis/blob/main/dashboards/flight_delay.pdf).

The report consists of five interconnected dashboards designed to analyze airline performance from multiple perspectives.

### Executive dashboard
Provides a high-level overview of airline operations and key performance indicators, including flight volume, delays, cancellations, OTP and disruption metrics.
<img width="1473" height="819" alt="fd_pbix_pg1" src="https://github.com/user-attachments/assets/3fbcf1b8-ef05-4dc6-ae1f-4e3b700b9c50" />

### Delay Trends
Examines delay patterns over time, highlighting seasonality, long-term trends, and operational fluctuations across the study period.
<img width="1476" height="829" alt="fd_pbix_pg2" src="https://github.com/user-attachments/assets/47bd9c6a-91a8-4237-a535-7cd65414e9ba" />

### Efficiency Analysis
Evaluates airline operational efficiency using engineered metrics such as delay severity and delay frequency.
<img width="1476" height="825" alt="fd_pbix_pg3" src="https://github.com/user-attachments/assets/8775e1e7-715f-4a92-b690-391dc4ce42ac" />

### Root cause of Delay
Breaks down total delays into Carrier, Weather, NAS, Security, and Late Aircraft components to identify dominant disruption drivers.
<img width="1476" height="826" alt="fd_pbix_pg4" src="https://github.com/user-attachments/assets/2cf426ad-46f6-49cf-9340-4f4efe65bbcb" />

### Airline Risk Analysis
Compares airlines using custom KPIs such as ImPax%, Disruption Score, OTP, and cancellation metrics to identify operational risk profiles.
<img width="1476" height="826" alt="fd_pbix_pg5" src="https://github.com/user-attachments/assets/66825e0e-fc05-4df3-a80d-34f4a54759f0" />

Two matrices in the dashboard provide a visual detail of the airline performance.
**Efficiency Matrix**
<img width="2196" height="786" alt="eff_matrix" src="https://github.com/user-attachments/assets/73bae1d8-d2c8-4984-b154-f28080b42729" />

**Disruption Matrix**
<img width="2170" height="786" alt="disrup_matrix" src="https://github.com/user-attachments/assets/5b398268-f697-490d-89cf-63f0535feadc" />

---

## Final Insights

- Carrier-related operational issues contributed the largest share of total delay minutes.
- Delay patterns exhibited clear seasonal behavior, with disruption levels varying throughout the year.
- Airlines showed distinct operational profiles, with some experiencing frequent low-impact delays and others facing less frequent but more severe disruptions.
- On-Time Performance (OTP) alone did not fully capture airline reliability.
- Combining frequency, severity, and disruption metrics provided a more comprehensive assessment of operational performance.
- Late aircraft and carrier-related delays emerged as the most influential disruption categories across many airlines.
- Custom KPIs such as ImPax% and Disruption Score helped differentiate airline risk beyond traditional delay statistics.
