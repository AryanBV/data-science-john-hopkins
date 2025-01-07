# Weather Analysis Dashboard

**Name:** Aryan BV  
**Date:** 7th Jan 2025

## Synopsis

The Weather Analysis Dashboard is an interactive Shiny application that visualizes temperature and rainfall patterns across major global cities. The dashboard provides dynamic visualizations and statistical summaries to help users understand weather patterns and trends.

## Features

1. **City Selection**
   - Interactive dropdown for choosing different cities
   - Currently includes New York, London, Tokyo, and Sydney

2. **Visualization Options**
   - Temperature trends (line plot)
   - Rainfall distribution (bar chart)
   - Interactive Plotly integration

3. **Statistical Analysis**
   - Summary statistics for both temperature and rainfall
   - Monthly data breakdown

## Dataset Structure

The application uses a structured dataset with the following columns:
- **City:** Metropolitan area names
- **Month:** Monthly data points (Jan-Dec)
- **Temperature:** Temperature readings in Celsius
- **Rainfall:** Precipitation measurements in millimeters

## Technology Stack

- **Programming Language:** R
- **Framework:** Shiny
- **Visualization Libraries:**
  - ggplot2
  - Plotly
- **Deployment:** ShinyApps.io

## Installation and Setup

### Prerequisites

Install required R packages:
```r
install.packages(c("shiny", "ggplot2", "plotly"))
```

### Local Development

1. Clone the repository
2. Open the project in RStudio
3. Install dependencies
4. Run the application:
```r
library(shiny)
runApp()
```

## Application Structure

```
WeatherAnalysis/
├── app.R         # Main application code
├── README.md     # Documentation
└── .gitignore    # Git ignore file
```

## Code Components

### Data Structure
```r
weather_data <- data.frame(
  City = rep(c("New York", "London", "Tokyo", "Sydney"), each = 12),
  Month = rep(month.abb, 4),
  Temperature = c(
    # New York
    0,2,7,12,19,23,26,25,21,15,9,3,
    # London
    4,5,7,9,13,16,18,18,15,11,7,5,
    # Tokyo
    5,6,9,14,19,22,26,27,23,17,12,8,
    # Sydney
    23,23,22,19,16,14,13,14,16,18,20,22
  ),
  Rainfall = c(
    # New York
    83,78,86,94,99,95,116,110,87,71,89,85,
    # London
    55,39,35,43,50,45,44,49,49,71,63,55,
    # Tokyo
    52,56,117,125,138,185,128,148,180,158,84,44,
    # Sydney
    102,118,130,129,100,133,97,81,68,76,83,77
  )
)
```

## Deployment Instructions

1. Install rsconnect package:
```r
install.packages("rsconnect")
```

2. Configure ShinyApps.io credentials:
```r
rsconnect::setAccountInfo(
  name="your-account",
  token="your-token",
  secret="your-secret"
)
```

3. Deploy the application:
```r
rsconnect::deployApp(
  appDir = "path/to/WeatherAnalysis",
  appName = "weather-analysis"
)
```

## Maintenance

To update the application:
1. Make changes to the code locally
2. Test thoroughly
3. Re-deploy using rsconnect::deployApp()

## Future Enhancements

Potential improvements:
- Add more cities
- Include historical data comparison
- Add forecast capabilities
- Implement data download options
