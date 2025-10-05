# nct_distr
This project's purpose: for managing data pipeline of psycotic active substances distribution

# Bacis requirements and installation
This project is based on  [Jupyter lab](https://jupyter.org/) notebook and generally require for most operations.
The installation for Jupyter lab should follow [Jupyter lab](https://jupyter.org/install).

The other dependencies require for this project, Please refer to requirement.txt
with general python dependecies installation

<code>!pip install -r requirements.txt </code>

<li>For colab notebook users, please follow:</li>
<a>https://colab.research.google.com/</a>

with modification on [plotly.express](https://plotly.com/python/)

the line: <code>pio.renderers.default</code> can be omitted

<li>For local machine users,</li>
<code>pio.renderers.default = "browser"</code> is recommended. (Otherwise the file size will be very large)

# The data source
Should be requested directly from [Narcotics revolving fund](https://nrf.fda.moph.go.th/)
the important sources include:
<li>Sale report</li> (based on the form: <a href="https://nrf.fda.moph.go.th/media.php?id=676326838452232192&name=%E0%B9%81%E0%B8%9A%E0%B8%9A%E0%B8%84%E0%B8%B3%E0%B8%82%E0%B8%AD%E0%B8%8B%E0%B8%B7%E0%B9%89%E0%B8%AD%20%E0%B8%82.%E0%B8%A7%E0%B8%88.2.pdf">[แบบ ข.วจ. 2]</a>)
<li>Disburse report</li>
<br>
<li>Approval dataset should be requested from Pre-marketing group of Narcotics control division</li>

# API endpoints
<li>for nrf smart inventory endpoint should be from [Narcotics revolving fund](https://nrf.fda.moph.go.th/) as well.</li>
<br>
<li>hcodes endpoint can be found on <a>https://hcode.moph.go.th/</a></li>

# Loading Dataset
most of dataset using in this project are .csv files and can be loaded using <code>pd.read_csv()</code> with the dedicated dataframe variable names
except for Approval Dataset which XML format is expected(namespaces were provided in notebook)
<br>
- geojson files can be downloaded or forked from <a>https://github.com/chingchai/OpenGISData-Thailand</a>
credit to <a>https://github.com/chingchai</a>
- datetime fields (e.g., SendReportDate) can be implied dtype to datetime[ns] by passing <code>pd.to_datetime()</code> method. Execept for <code>ce_report_month</code> which is calculated end-of-month offset, the calculation steps are provided within the relavant notebook sections.


# Navigating section
<img width="1138" height="937" alt="image" src="https://github.com/user-attachments/assets/2cb3e7a6-e3dd-48be-b87d-bee017fd7cf6" />
Running cell by cell is recommended. However, user can navigate only to see or use relavant sections by selecting Table of Content sections.

# Aggregating and Dimensional Reduction for Visualization
Aggregations are provided as necessary based on previously insight finding.
As is reference can be found on ...

# Output file
- All charts plotted with <code>plotly.express</code> can be exported using method <code>fig.write_html() </code>
- All DataFrame can be exported to csv with df.to_csv() method utf-8 encoding by default is recommended

