# nct_distr
This project's purpose: for managing data pipeline of psycotic active substances distribution

# Bacis requirements and installation
This project is based on  [Jupyter lab](https://jupyter.org/) notebook and generally require for most operations.
The installation for Jupyter lab should follow [Jupyter lab](https://jupyter.org/install).

The other dependencies require for this project, Please refer to requirement.txt
with general python dependecies installation

<code>!pip install -r requirements.txt </code>

For colab notebook users, please follow:
<a>https://colab.research.google.com/</a>

with modification on [plotly.express](https://plotly.com/python/)

the line: <code>pio.renderers.default</code> can be omitted

For local machine users,
<code>pio.renderers.default = "browser"</code> is recommended. (Otherwise the file size will be very large)

# The data source
Should be requested directly from [Narcotics revolving fund](https://nrf.fda.moph.go.th/)
the important sources include:
<li>Sale report</li> (based on the form: [แบบ ข.วจ. 2](https://nrf.fda.moph.go.th/media.php?id=676326838452232192&name=%E0%B9%81%E0%B8%9A%E0%B8%9A%E0%B8%84%E0%B8%B3%E0%B8%82%E0%B8%AD%E0%B8%8B%E0%B8%B7%E0%B9%89%E0%B8%AD%20%E0%B8%82.%E0%B8%A7%E0%B8%88.2.pdf))
<li>Disburse report</li>
<br>
<li>Approval dataset should be requested from Pre-marketing group of Narcotics control division</li>

# API endpoints
<li>for nrf smart inventory endpoint should be from [Narcotics revolving fund](https://nrf.fda.moph.go.th/) as well.</li>
<br>
<li>hcodes endpoint can be found on <a>https://hcode.moph.go.th/</a></li>

# Loading Dataset
