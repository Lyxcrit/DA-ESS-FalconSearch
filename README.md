# DA-ESS-FalconSearch
Modified version of Splunk Enterprise Security Content Update leveraging basesearches in order to reduce resources used and allow for more enabled content

```diff
- THIS APP IS SELF MAINTAINED AND NOT AFFILIATED WITH SPLUNK INC. OR ESCU
- THIS APP IS DISTRIBUTED AS-IS AND MAINTAINED BY @Lyxcrit
```
# FalconSearch: Enhancing Enterprise Security with Speed and Efficiency

![FalconSearch Logo](static/appIcon.png)

## Overview

FalconSearch is a Splunk app designed to revolutionize your approach to Enterprise Security. By leveraging advanced base searching techniques, FalconSearch optimizes search times and resource usage, delivering lightning-fast results with reduced overhead. This app integrates seamlessly with your existing Splunk environment, enhancing your cybersecurity operations without sacrificing performance.

## Required Apps

Before using FalconSearch, make sure you have the following apps installed:

- [Splunk Enterprise Security](https://splunkbase.splunk.com/app/263): A comprehensive solution for security information and event management (SIEM).

- [Splunk Common Information Model (CIM)](https://splunkbase.splunk.com/app/1621/): A standardized framework for normalizing data for analysis and reporting.

- [Splunk Machine Learning Toolkit](https://splunkbase.splunk.com/app/2890): Provides ML and AI to allow detections of outliers.

- [Splunk Enterprise Security Content Update (DA-ESS-ContentUpdate)](https://splunkbase.splunk.com/app/3449/): A content update for Splunk Enterprise Security.

Ensure that these apps are properly installed and configured before setting up FalconSearch.

## Key Features

- **Efficient Search:** FalconSearch harnesses the power of base searching, enabling quicker data retrieval while conserving valuable resources.

- **Speed and Precision:** Experience accelerated search times without compromising the meticulous analysis required for effective cybersecurity.

- **Intelligent Correlation:** The app employs intelligent correlation techniques, maximizing the value of your search results.

- **Sleek Interface:** FalconSearch offers an intuitive user interface that streamlines navigation and provides a seamless user experience.

## Installation

1. Clone or download this repository.

2. Install the FalconSearch app in your Splunk environment using the Splunk Web interface.

3. Configure the app settings according to your security requirements.

## Usage

1. Access the FalconSearch app from the Splunk Home screen.

2. To properly set up the app:

    a. Modify the search macros to restrict indexes on the basesearches (by default they are set to index=*).
    
    b. Enable the base searches for the content you wish to enable.
    
    c. There are 16 base searches that drive a total of 1026 correlation searches, as shown in the table below:

    | Base Search                    | Drives Correlation Searches |
    |-------------------------------|-----------------------------|
    | Splunk ES - Authentication    | 11                          |
    | Splunk ES - Change Events     | 19                          |
    | Splunk ES - Cloudtrail Events | 96                          |
    | Splunk ES - Network Traffic Events | 31 |
    | Splunk ES - Network Resolution Events | 20 |
    | Splunk ES - Endpoint Events | 741 |
    | Splunk ES - PowerShell Events | 88 |
    | Splunk ES - Cisco Events | 6 |
    | Splunk ES - Risk Events | 12 |
    | Splunk ES - GCP Events | 14 |
    | Splunk ES - Amazon Events | 22 |
    | Splunk ES - Azure Events | 40 |
    | Splunk ES - Okta Events | 20 |
    | Splunk ES - Web Events | 26 |
    | Splunk ES - Splunk Audit Events | 10 |
    | Splunk ES - o365 Events | 12 |
    
    To enable the base searches:
    
    - Go to Settings -> Searches, Reports, and Alerts.
    
    - Filter on App: DA-ESS-FalconSearch and Owner: Nobody.
    
3. Once the base searches are enabled, you can start enabling content under the Enterprise Security App.

4. Manage correlation searches via Configure -> Content -> Content Management. Search for correlation searches starting with the "FS - " prefix.

## Changelog

### [Version 1.0.5] - 01-08-2024

- **Changed:** Modifed basesearch for Authentication logs to include EventCode field. 
- **Changesd** Modified Change Events basesearch to correct unmatched parenthesis
- **TODO:**  Look at the map portion of 'FS - Potential Password in Username - Rule' as this doesn't seem to be returning proper information.

### [Version 1.0.4] - 10-24-2023

- **Changed:** Modifed basesearches to leverage datamodels, to significantly reduce search time. This method uses the DIRECTIVES portion of Splunk which is undocumented externally
- **Changed:** App now ships with all base searches and correlation searches as disabled to align with Splunk appInspect requirements.

## Contributing

We welcome contributions from the community! If you encounter issues, have suggestions for improvements, or want to contribute code, please open an issue or pull request in this repository.

## License

FalconSearch is released under the [Apache License 2.0](LICENSE).

## Contact

For questions, feedback, or collaboration opportunities, please contact me at bmatlock@wisehawktech.com or generate an issue here.

---

© 2024 WiseHawkTech LLC, FalconSearch. All Rights Reserved.
