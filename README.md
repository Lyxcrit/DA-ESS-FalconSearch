# DA-ESS-FalconSearch
Modified version of Splunk Enterprise Security Content Update leveraging basesearches in order to reduce resources used and allow for more enabled content
# FalconSearch: Enhancing Enterprise Security with Speed and Efficiency

![FalconSearch Logo](static/appIcon.png)

## Overview

FalconSearch is a Splunk app designed to revolutionize your approach to Enterprise Security. By leveraging advanced base searching techniques, FalconSearch optimizes search times and resource usage, delivering lightning-fast results with reduced overhead. This app integrates seamlessly with your existing Splunk environment, enhancing your cybersecurity operations without sacrificing performance.

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

2. Explore the intuitive dashboard and user-friendly interface.

3. To properly set up the app:

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
    
4. Once the base searches are enabled, you can start enabling content under the Enterprise Security App.

5. Manage correlation searches via Configure -> Content -> Content Management. Search for correlation searches starting with the "FS - " prefix.

## Contributing

We welcome contributions from the community! If you encounter issues, have suggestions for improvements, or want to contribute code, please open an issue or pull request in this repository.

## License

FalconSearch is released under the [MIT License](LICENSE).

## Contact

For questions, feedback, or collaboration opportunities, please contact me at bmatlock@splunk.com or generate an issue here.

---

© 2023 FalconSearch. All Rights Reserved.
