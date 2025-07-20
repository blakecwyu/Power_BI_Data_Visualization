[中文版本](README_zh.md) | [English](README.md)  
  
# Taiwan Tourism Inbound&Outbound Report   
  
## Project Overview  
This Power BI dashboard analyzes inbound and outbound visitor trends in Taiwan from 2019 to 2025, featuring dynamic year and month selection buttons. It offers visual insights into monthly seasonality, country/region distributions, visitor purposes, and hotel occupancy rates by city and county. The dashboard also compares current figures to pre-COVID levels and highlights the significant gap between inbound and outbound travel volumes.  

## Data Source  
- Source:  
  - Tourism Statistics Database of The Tourism Administration, M.O.T.C.  
    1. [Hotel Operation Report by City and County](https://admin.taiwan.net.tw/businessinfo/FilePage?a=9711)  
    2. [Visitor Arrivals by Gender and by Purpose of Visit](https://stat.taiwan.net.tw/statistics/month/inbound/gender/purpose)  
    3. [Outbound Departures of Nationals of the Republic of China by Destination](https://stat.taiwan.net.tw/statistics/month/outbound/destination)  
- Coverage:  
  - 2019–2025, monthly breakdown  
- Notes:  
  - A manually created country/region table is used to match inbound and outbound data for Power BI relationships. Note that some country/region names are not fully aligned between the two datasets. For example, Hong Kong and Macao are combined in the Inbound data but listed separately in the Outbound data.  
  - Alias tables for visitor purposes and city/county names are created in Power BI for translation.
  - A Date table is created in Power BI.  
  - Data cleaning and transformation are handled in Power BI using Power Query.  

## Dashboard Features  
![Preview Images](preview_images/Preview_Taiwan_Tourism_Inbound&Outbound_Report_01.png)  
- Automatic data cleaning and transformation with Power Query.  
- Dynamic year and month buttons.  
- Inbound and outbound volumes compared to previous month, same month last year, and pre-COVID(2019).  
- Selectable top inbound and outbound countries/regions for the selected month.  
- Breakdown of inbound travelers' visiting purposes.  
- Year over year monthly inbound trends, highlighting pre- and post-COVID shifts.  
- Line and column chart displaying monthly inbound-outbound gap.  
- Choropleth map showing average hotel occupancy rates by city/county.  

## Demo Video  
![Dashboard Demo](demo_video/Demo_Taiwan_Tourism_Inbound&Outbound_Report.gif)  
  
## Project Structure  
Taiwan Tourism Inbound&Outbound Report/  
├── data/  
│   └── Hotels by CountyCity/  
│   └── Inbound/  
│   └── Outbound/  
├── demo_video/  
│   └── Demo_Taiwan Tourism Inbound&Outbound Report.gif  
├── pbip/  
│   └── Taiwan Tourism Inbound&Outbound Report.pbip  
├── preview_images/  
│   └── Preview_Taiwan_Tourism_Inbound&Outbound_Report_01.png  
│   └── Preview_Taiwan_Tourism_Inbound&Outbound_Report_02.png  
│   └── Preview_Taiwan_Tourism_Inbound&Outbound_Report_03.png  
├── .gitignore  
└── README.md  
  
## Limitations  
- The data is typically released three months after the end of each month, meaning it may not immediately reflect recent events or emerging trends.  
- Due to Power BI limitations, month buttons cannot be disabled for months with no data (future months). Instead, they are styled to appear unavailable but can still be selected.  
- Outbound data indicates departure destinations, which may not accurately represent travelers' nationalities or final destinations.  
- Country/region names in inbound and outbound datasets are not fully aligned.  
- Alias tables for country/region names, visitor purposes, and city/county names are manually created for translation. Any changes in source data categories may require updating these tables.
- The shape map relies on Mandarin location names to match the TopoJSON file, limiting flexibility to switch location labels in visuals.  

## Credits  
- Data Sources: Tourism statistics from the Tourism Administration, M.O.T.C. Taiwan (交通部觀光署)
- Map Files (TopoJSON): Taiwan TopoJSON files created by [jason2506](https://github.com/jason2506/Taiwan.TopoJSON), based on Taiwan’s official geographic boundary data.  

## License  
This dashboard uses publicly available data from the Taiwanese government for non-commercial, academic purposes.  
All Power BI files, M code transformations, and visuals in this repository are licensed under the MIT License.  
Disclaimer: This project is for personal learning and demonstration purposes only and is not affiliated with any government agency or the creator of the TopoJSON files.  
