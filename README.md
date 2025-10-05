# NCT Distribution Data Pipeline

A data pipeline management system for psychotropic active substances distribution in Thailand.

## Purpose

This project manages and analyzes data related to the distribution of controlled psychotropic substances, providing insights through data processing, aggregation, and visualization.

## Prerequisites

### Core Requirements

This project is built on [Jupyter Lab](https://jupyter.org/) and requires it for most operations.

**Installation:**
```bash
pip install jupyterlab
```

For detailed installation instructions, visit the [Jupyter Lab Installation Guide](https://jupyter.org/install).

### Python Dependencies

Install all required dependencies using:
```bash
pip install -r requirements.txt
```

### Platform-Specific Setup

#### Google Colab Users
1. Access [Google Colab](https://colab.research.google.com/)
2. When using [Plotly Express](https://plotly.com/python/), you can omit the line:
   ```python
   pio.renderers.default
   ```

#### Local Machine Users
For local installations, set the renderer to browser to reduce file size:
```python
pio.renderers.default = "browser"
```

## Data Sources

All primary data should be requested from the [Narcotics Revolving Fund (NRF)](https://nrf.fda.moph.go.th/).

### Required Datasets

1. **Sales Report** - Form [ข.วจ. 2](https://nrf.fda.moph.go.th/media.php?id=676326838452232192&name=%E0%B9%81%E0%B8%9A%E0%B8%9A%E0%B8%84%E0%B8%B3%E0%B8%82%E0%B8%AD%E0%B8%8B%E0%B8%B7%E0%B9%89%E0%B8%AD%20%E0%B8%82.%E0%B8%A7%E0%B8%88.2.pdf)
2. **Disbursement Report** Form [แบบ ร.ย.ส.2/ว.จ.2/เดือน,แบบ ร.ย.ส. 2/ว.จ. 2 – จ1](https://narcotic.fda.moph.go.th/for-entrepreneur/category/%E0%B9%81%E0%B8%9A%E0%B8%9A%E0%B8%9F%E0%B8%AD%E0%B8%A3%E0%B9%8C%E0%B8%A1%E0%B8%A3%E0%B8%B2%E0%B8%A2%E0%B8%87%E0%B8%B2%E0%B8%99-%E0%B8%A2%E0%B8%B2%E0%B9%80%E0%B8%AA%E0%B8%9E%E0%B8%95%E0%B8%B4%E0%B8%94/)
3. **Approval Dataset** - Should be requested from the Pre-marketing Group of the Narcotics Control Division

### API Endpoints
- **NRF Smart Inventory**: endpoint should be requested from [Narcotics revolving fund](https://nrf.fda.moph.go.th/)
- **Health Facility Codes (HCODE)**: please refer to [https://hcode.moph.go.th/](https://hcode.moph.go.th/)

### Additional Resources

- **GeoJSON files**: Available at [OpenGISData-Thailand](https://github.com/chingchai/OpenGISData-Thailand)
  - Credit: [@chingchai](https://github.com/chingchai)

## Loading Datasets

Most datasets in this project are CSV files. Load them using:
```python
df = pd.read_csv('filename.csv')
```
**Note:** Dedicated dataframe variable names are recommended.

### XML Files (Approval Dataset)
The Approval Dataset uses XML format. Namespace handling is provided in the notebooks.

### DateTime Processing
Convert datetime fields using:
```python
df['SendReportDate'] = pd.to_datetime(df['SendReportDate'])
```
- geojson files can be downloaded or forked from <a>https://github.com/chingchai/OpenGISData-Thailand</a>
credit to <a>https://github.com/chingchai</a>
- datetime fields (e.g., SendReportDate) can be implied dtype to datetime[ns] by passing <code>pd.to_datetime()</code> method. Execept for <code>ce_report_month</code> which is calculated end-of-month offset, the calculation steps are provided within the relavant notebook sections.

**Note:** For `ce_report_month` (calculated as end-of-month offset), refer to the calculation steps in the relevant notebook sections.

## Usage
### Navigation
<!-- <img width="1138" height="937" alt="image" src="https://github.com/user-attachments/assets/2cb3e7a6-e3dd-48be-b87d-bee017fd7cf6" /> -->
![Project Navigation](https://github.com/user-attachments/assets/2cb3e7a6-e3dd-48be-b87d-bee017fd7cf6)

**Recommended Workflow:**
- Run cells sequentially for complete analysis
- Use the Table of Contents to jump to specific sections

### Data Aggregation

Aggregations are provided based on previous insight findings and analytical requirements.
As is reference can be found on ...

# Output file
- All charts plotted with <code>plotly.express</code> can be exported using method <code>fig.write_html() </code>
- All DataFrame can be exported to csv with df.to_csv() method utf-8 encoding by default is recommended

## Output and Export

### Exporting Visualizations
Save Plotly charts as HTML:
```python
fig.write_html('output_chart.html')
```

### Exporting DataFrames
Export DataFrames to CSV with UTF-8 encoding (recommended):
```python
df.to_csv('output_data.csv', encoding='utf-8', index=False)
```

## Project Structure

```
nct_distr/
├── notebooks/          # Jupyter notebooks
├── data/              # Data files (CSV, XML, GeoJSON)
├── outputs/           # Generated charts and reports
├── requirements.txt   # Python dependencies
└── README.md         # This file
```

## Contributing

For issues, questions, or contributions, please contact the project maintainer or submit an issue through the repository.

## Contact

[Konrawit Wetchakan](https://github.com/konrawit13)

