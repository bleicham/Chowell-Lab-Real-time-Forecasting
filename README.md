# Chowell Lab Real-time Forecasting Hub 

This GitHub repository contains weekly real-time forecasts related to multiple infectious diseases in the United States and the ongoing mpox outbreak in Africa. We use various modeling frameworks to produce forecasts each week, including:

1. **_n_-sub-epidemic framework** [1]  
2. **Spatial-wave framework** [2]  
3. **Auto-regressive integrated moving average (ARIMA) model** [3]  
4. **Generalized Additive Model (GAM)** [3]  
5. **Generalized Linear Model (GLM)** [3]  
6. **Facebook's Prophet model (Prophet)** [3]  
7. **Compartmental models** [4]  

Additionally, we forecast the weekly R(t) for mpox for both the United States and the ongoing outbreak in Africa.

## Model Specification and Forecasting 
We forecast four weeks out, and the table below provides additional details regarding the assumed error structure (for the _n_-sub-epidemic, spatial-wave, and compartmental models) and the calibration period used for each disease/geography. Additionally, we assume an underlying generalized logistic growth model when fitting the _n_-sub-epidemic and spatial-wave models. A normal distribution is assumed when fitting the ARIMA, GAM, GLM, and Prophet models; the calibration period is the same, as shown in the table below. Please be advised that the error structures and calibration periods during earlier forecasts may not reflect what is shown in the table below. However, the table is the most up-to-date settings being used. 

| Disease       | Geography     | Error Structure    | Calibration Period |
|---------------|---------------|--------------------|--------------------|
| Candida auris | United States | Poisson            | 15-Weeks           |
| Dengue        | United States | Poisson            | 15-Weeks           |
| Malaria       | United States | Negative Binomial  | 15-Weeks           |
| Mpox          | United States | Poisson            | 15-Weeks           |
| Mpox          | Africa        | Coming soon.       | Coming soon.       |
| Pertussis     | United States | Poisson            | 15-Weeks           |
| West Nile     | United States | Negative Binomial  | 10-Weeks           |

## Estimating R(t)
Each week, we forecast the R(t) value over the next four weeks (from date of forecast) using the most recent 10-weeks and 20-weeks of data for mpox both in the United States and for the ongoing outbreak in Africa. As part of the forecasting process, we employ a generalized logistic growth model, and assume a Poisson error structure. We assume a gamma generational interval distribution with a mean of 1.78 and a variance of 0.65 as found in [5][(https://www.ncbi.nlm.nih.gov/pmc/articles/PMC9514338/#SD1)]. 

## Additional Information 
The data displayed in the dashboard and used for all forecasts is obtained each Friday from the Centers for Disease Control and Prevention (CDC) [6] and from the Our World in Data online resource [7]. Forecasts are published each Sunday. All forecasting tools used to obtain forecasts and visualizations can be found in the references below.

Please email [ableichrodt1@student.gsu.edu](mailto:ableichrodt1@student.gsu.edu) with all inquiries.

## References

1. Chowell G, Dahal S, Bleichrodt A, Tariq A, Hyman JM, Luo R. SubEpiPredict: A tutorial-based primer and toolbox for fitting and forecasting growth trajectories using the ensemble n-sub-epidemic modeling framework. Infect Dis Model. 2024 Feb 9;9(2):411-436. doi: 10.1016/j.idm.2024.02.001. PMID: 38385022; PMCID: PMC10879680.
2. Chowell G, Tariq A, Dahal S, Bleichrodt A, Luo R, Hyman JM. SpatialWavePredict: a tutorial-based primer and toolbox for forecasting growth trajectories using the ensemble spatial wave sub-epidemic modeling framework. BMC Med Res Methodol. 2024 Jun 7;24(1):131. doi: 10.1186/s12874-024-02241-2. PMID: 38849766; PMCID: PMC11157887.
3. Bleichrodt, Amanda and Phan, Amelia and Luo, Ruiyan and Kirpich, Alexander and Chowell-Puente, Gerardo, StatModPredict: A User-Friendly R-Shiny Interface for Fitting and Forecasting with Statistical Models (May 30, 2024). Available at SSRN: https://ssrn.com/abstract=4849702 or http://dx.doi.org/10.2139/ssrn.4849702.
4. Chowell G., Bleichrodt A., Luo R. (2024): "Parameter Estimation and Forecasting with Quantified Uncertainty for ODE Models using QuantDiffForecast: A MATLAB Toolbox and Tutorial". Statistics in Medicine, 43(9), 1826-1848. [https://onlinelibrary.wiley.com/doi/full/10.1002/sim.10036]. 
5. Chowell G, Bleichrodt A, Dahal S, Tariq A, Roosa K, Hyman JM, Luo R. GrowthPredict: A toolbox and tutorial-based primer for fitting and forecasting growth trajectories using phenomenological growth models. Sci Rep. 2024 Jan 18;14(1):1630. doi: 10.1038/s41598-024-51852-8. PMID: 38238407; PMCID: PMC10796326.
6. Centers for Disease Control and Prevention. National Notifiable Diseases Surveillance System, Weekly Tables of Infectious Disease Data. Atlanta, GA. Office of Public Health Data, Surveillance, and Technology. Available at: https://www.cdc.gov/nndss/data-statistics/index.html.
7. Edouard Mathieu, Fiona Spooner, Saloni Dattani, Hannah Ritchie and Max Roser (2022) - “Mpox” Published online at OurWorldInData.org. Retrieved from: 'https://ourworldindata.org/mpox' [Online Resource]
