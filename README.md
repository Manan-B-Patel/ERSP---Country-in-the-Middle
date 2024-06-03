# ERSP---Country-in-the-Middle

### Authors: Manan Patel, Shambhavi Mittal, and Samvrit Srinath

### Research Goal

Understanding where Internet services are hosted, and how users reach them, has captured the interest of government regulators and others concerned with privacy of data flows. We consider a specific version of this question—citizens visiting their own government’s online services—that arguably merits a higher expectation of protection against foreign surveillance or interference. The goal of our research is to Identify unusual network paths to government websites and determine explanations and factors for those interesting behaviors.

### Code Description

The following codebase contains the data and the jupiter notebook that was used in our research analysis. The codebase is separated into two directories, `scripts` and `data`.

`/data` :  
- `processed_results_20240226_filtered_path_org_anycast.csv`: CSV File with Ripe Atlas Traceroute Measurements for over 20 counties.
- `hohio_20240226.csv`: Hoiho Dataset that contains mappings from domain name to IP geolocated country

`/scripts` :
- `citm_analysis.ipynb`: Jupyter Notebook that contains code to parse and analyze data


### Setting Up the Environment

Before you begin, ensure you have met the following requirements:

- **Python**: Make sure Python (version 3.x) is installed on your machine. You can download it from [python.org](https://www.python.org/downloads/).
- **pip**: Verify that you have pip installed with `pip --version`.
- **Virtual Environment**: Use a virtual environment to manage dependencies and download necessary libararies.


### Understanding and Modifying the Code

The Jupyter Notebook is separated first into high level analysis of the data and then into specific tests and filters that allow us to closely analyze interesting measurements. Make sure to follow the steps above to setup the environment. After loading the data, you can chose which country to analyze by modifying the key with a string represetnation of the country in interest. Most of the cells following this will print out high level metrics about that country such as number of convergent and divergent traceroutes, violators, and some tables/graphs to visualize these high level metrics. These high level analysis will be a sufficient starting point to your analysis.

To dive deeper into your analysis, our research group utilizes various tests such as Ping Tests and Mean Latency Analysis to validate the IP geolocation of certain IP addresses within a traceroute. For the Ping Test, you will need to create a Ripe Atlas Account with a valid API key. The code has numerous comments above each executable line that outlines what variable needs to be modified to analyze different measurements. On top of these measurements, we utilizes specific filters on probe-ids, destination AS, divergent or convergent status, etc. to analyze a measurement further and algorithms to determine whether there are similar ASes or IPs between violator and non-violator traceroutes.

Coupled with our code analysis it is also really helpful to look at the Ases of the IP addresses and utilize various online tools to learn peering relationships or any interesting relationships between ASes that help us understand the behavior of the traceroutes. Below is some of the tools that we utilzied:
- [Submarine Cables](https://www.submarinecablemap.com/)
- [BGP Tools](https://bgp.tools/)
- [Ripe Atlas](https://atlas.ripe.net/measurements/)

### Resources

Below are a list of resources to help you understand how to utilize this repo and analyze traceroute measurements for different countries.
- [Pandas Tutorial](https://github.com/dsc-courses/dsc10-2023-fa/blob/master/labs/lab01/lab01.ipynb)
- 
