# Chowell Lab Real-time Forecasting Hub 

This GitHub repository contains weekly real-time forecasts related to multiple infectious diseases in the United States and the ongoing mpox outbreak in Africa. We use various modeling frameworks to produce forecasts each week, including:

1. **_n_-sub-epidemic framework** [1]  
2. **Spatial-wave framework** [2]  
3. **Auto-regressive integrated moving average (ARIMA) model** [3]  
4. **Generalized Additive Model (GAM)** [3]  
5. **Generalized Linear Model (GLM)** [3]  
6. **Facebook's Prophet model (Prophet)** [3]  
7. **Compartmental models** [4]  

Additionally, we estimate the weekly R(t) for mpox for both the United States and the ongoing outbreak in Africa.

## Model Specification and Forecasting 
We forecast four weeks out, and the table below provides additional details regarding the assumed error structure (for the _n_-sub-epidemic, spatial-wave, and compartmental models) and the calibration period used for each disease/geography. Additionally, we assume an underlying generalized logistic growth model when fitting the _n_-sub-epidemic and spatial-wave models. A normal distribution is assumed when fitting the ARIMA, GAM, GLM, and Prophet models; the calibration period is the same, as shown in the table below. Please be advised that the error structures and calibration periods during earlier forecasts may not reflect what is shown in the Table below. However, the table is the most up-to-date settings being used. 

| Disease       | Geography     | Error Structure    | Calibration Period |
|---------------|---------------|--------------------|--------------------|
| Candida auris | United States | Poisson            | 15-Weeks           |
| Dengue        | United States | Poisson            | 15-Weeks           |
| Malaria       | United States | Negative Binomial  | 15-Weeks           |
| Mpox          | United States | Poisson            | 15-Weeks           |
| Mpox          | Africa        | Coming soon.       | Coming soon.       |
| Pertussis     | United States | Poisson            | Aug 2022 - Present |
| West Nile     | United States | Poisson            | Aug 2022 - Present |

## Estimating R(t)


## Additional Information 
The data displayed in the dashboard and used for all forecasts is obtained each Friday from the Centers for Disease Control and Prevention (CDC) [5] and from the Our World in Data GitHub [6]. Forecasts are published each Sunday. All forecasting tools used to obtain forecasts and visualizations can be found in the references below.

Please email [ableichrodt1@student.gsu.edu](mailto:ableichrodt1@student.gsu.edu) with all inquiries.

## References

1. Reference 1 details  
2. Reference 2 details  
3. Reference 3 details  
4. Reference 4 details  
5. Reference 5 details  
6. Reference 6 details  
