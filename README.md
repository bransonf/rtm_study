## Replication Materials for Fox et al. "Assessing the Differential Impact of Vacancy on Criminal Violence"

This repository contains much of the necessary data for replicating the Risk Terrain Modeling methodology found in the manuscript. Unfortunately, the point of interest data and software we used were licensed, meaning there is a monetary cost associated with replicating our results.

![](Rtm_Result.png)

### Boundary

A novel contribution to literature is the fitting of sub-regional models based on an empirically known demographic diving line. In St. Louis this is known as the Delmar Divide, and similar racial and economic divides exist in other prominent American cities, such as the 8-Mile Road in Detroit.

In order to sub-divide the region for our models, we used ArcGIS to edit the geometry of the boundary, bifurcating the region along Delmar Blvd. Because the road is not topologically continuous, we combined road segments by their endpoints.

The boundary used, including the sub-divisions is included at:

```
/data/boundary/
```

### Crime Data

The St. Louis Metropolitan Police Department releases data pertaining to incidence of crime on a monthly basis. We obtained all recorded homicides and aggravated assaults between 2018 and 2019.

These data can be found at:

```
/data/crime/aggravated_assault/
/data/crime/homicide/
```

Most major metropolitan regions release crime data in some format. All that is necessary for risk terrain modeling is the category of the crime (i.e. Aggravated Assault or Homicide) as well as geocoded point locations.

### Vacancy

Because there is no canonical source for property vacancy in the City of St. Louis, we have to derive this from a variety of sources. We used the St. Louis Vacancy Collaborative's methodology for estimating parcel vacancy using data obtained in December 2019.

The R code used to produce this dataset may be found [here](https://github.com/bransonf/stlvacancy).

The exact dataset used in our analyses can be found at:

```
/data/vacancy/buildings/
/data/vacancy/lots/
```

Depending on the region in which you intend to study, vacancy data may be readily available or more fragmented than the data used in this study.

Both the US Census Bureau and US Postal Service capture and release aggregate metrics of property vacancy. Unfortunately, such aggregate data is not suitable for Risk Terrain Modeling.

### Points of Interest

We used an institutional license to obtain 2018 Business Analyst points of Interest. Categories were subset based on NAICS classifications matching our theoretical environmental factors. Due to the terms of the license, we are unable to share these data.

We used these data specifically because of availability and quality. However, there are a number of other vendors for point of interest data, such as SafeGraph. Some open data may be available, such as those available through OpenStreetMap, but accuracy and coverage may be of concern depending on the region.

Some risk factors, however, we obtained from local sources. These are provided when possible, at the following:

```
/data/housing/lihtc/
/data/housing/pub_housing/
/data/parks/
/data/schools/
/data/transit/MetroBus/
/data/transit/MetroLink/
```

### Risk Terrain Modeling Software

We obtained a license to use RTMDx, a web application for fitting Risk Terrain Models. This software is now licensed through [Simsi](https://www.simsi.com/). The underlying methodology of RTMDx is precisely that which Joel Caplan originally published.

To precisely replicate our results, you may observe the same parameters we used in our models. Note that we used 6 different stratifications, fitting models independently for homicide and aggravated assault, and to 3 regions (whole city, north region, south region).

```yaml
Model Type: Aggravating
Unit of Measurement: Feet
Standard Value: 300
Place Size: 150
For All 22 Risk Factors:
  Operationalization: Proximity or Density
  Standard Value Multiplier: 3
  Analysis Increments: Half
```

## Contact

Please direct any correspondence to bransonf@wustl.edu
