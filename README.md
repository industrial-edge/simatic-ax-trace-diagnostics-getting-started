# SIMATIC AX Trace Diagnostics Getting Started

- [SIMATIC AX Trace Diagnostics Getting Started](#simatic-ax-trace-diagnostics-getting-started)
  - [Description](#description)
    - [Overview](#overview)
    - [General Task](#general-task)
  - [Requirements](#requirements)
    - [Prerequisites](#prerequisites)
    - [Used components](#used-components)
    - [Further requirements](#further-requirements)
    - [TIA project](#tia-project)
  - [Configuration steps and Usage](#configuration-steps-and-usage)
  - [Usage](#usage)
  - [Documentation](#documentation)
  - [Contribution](#contribution)
  - [Licence and Legal Information](#licence-and-legal-information)
  - [Disclaimer](#disclaimer)

## Description

### Overview

The SIMATIC AX Trace Diagnostics is web-based application running on SIEMENS Industrial Edge. It is used for tracing the PLC signals same way as it is done in the TIA Portal. This appication example shows how to manage the connection with PLC and trace the chosen variables. 

### General task

In this application example, SIMATIC AX Trace Diagnostics is managing connection to the PLC and traces several signals from the bottles' filling process. The app is publishing those signals to Databus. Then, the signals from Databus are read using IIH Essentials application. 

This application has an ability to trace high frequency signals. So, to demonstrate this, the high speed traicing of simple sinus wave is also shown.  The sampling period of traced signals is derived directly from cyclic time of the PLC's cyclic interrupt.

![task](docs/graphics/Overview.png)

## Requirements

###  Prerequisites

- Access to an Industrial Edge Management System (IEM)
- Onboarded Industrial Edge Device (IED) or Industrial Edge Virtual Device (IEVD) on IEM
- Installed system configurator for Databus
- Installed system app Databus
- Installed apps SIMATIC AX Trace Diagnostics and IIH Essentials
- IED/IEVD is in the same network as PLC (PLC is reachable from IED)
- TIA Portal project (EdgeHowTos including the Tank and Sinus wave application) loaded on two PLCs (real ones or simulated using S7-PLCSIM Advanced)

### Used components

- Industrial Edge Management V1.5.2-4
- Industrial Edge Virtual Device V1.12.0-3-a
- SIMATIC AX Trace Diagnostics V1.0.2
- Databus V2.1.0-4
- Databus Configurator V2.0.0-4
- IIH Essentials V1.8.0
- Common Connector Configurator V1.8.2-3
- TIA Portal V16
- S7-PLCSIM Advanced V3.0 Upd2
- S7-1513-1 PN
- Web browser (Google Chrome)

### TIA project

The used TIA Portal project EdgeHowTos (including the Tank and Sinus wave application) can be found in the [src](src) directory under the following name: 

- [EdgeHowTos.7z](src/EdgeHowTos.7z)

## Configuration steps and Usage

- Installation of all necessary applications
- Configuration of Databus
- Managing the running PLC
- Configuration of connection to MQTT Databus
- Adding the PLC
- Adding and configuring of Trace Job
- Running the Trace Job
- Publishing the Trace Jobs to Databus
- Observing the Trace Jobs and data exporting
- Checking the published data in IIH Essentials
- Adding the second PLC and high speed sampling testing

You can find the further information about the following steps in the [Documentation](docs/Documentation.md).

## Usage

The application SIMATIC AX Trace Diagnostics offers the following functionalities:

- Connection to PLC via integrated S7 connector
- Definition of Trace Jobs
- Visualization of traced signals
- Exporing the plots to .svg, .png. and .csv files
- Publishing the signals' data to Databus (up to 4 signals)
- High speed sampling (sampling period of PLC's cyclic intertup)

## Documentation

You can find further documentation and help in the following links
  - [SIMATIC AX Trace Diagnostics documentation](https://support.industry.siemens.com/cs/document/109815579/simatic-ax-trace-diagnostics-for-industrial-edge-v1-0-0?dti=0&dl=en&lc=de-WW)
  - [Industrial Edge Hub](https://iehub.eu1.edge.siemens.cloud/#/documentation)
  - [Industrial Edge Forum](https://www.siemens.com/industrial-edge-forum)
  - [Industrial Edge landing page](https://new.siemens.com/global/en/products/automation/topic-areas/industrial-edge/simatic-edge.html)

## Contribution

Thank you for your interest in contributing. Anybody is free to report bugs, unclear documentation, and other problems regarding this repository in the Issues section.
Additionally everybody is free to propose any changes to this repository using Pull Requests.

If you haven't previously signed the [Siemens Contributor License Agreement](https://cla-assistant.io/industrial-edge/) (CLA), the system will automatically prompt you to do so when you submit your Pull Request. This can be conveniently done through the CLA Assistant's online platform. Once the CLA is signed, your Pull Request will automatically be cleared and made ready for merging if all other test stages succeed.

## License and Legal Information

Please read the [Legal information](LICENSE.txt).

## Disclaimer

IMPORTANT - PLEASE READ CAREFULLY:

This documentation describes how you can download and set up containers which consist of or contain third-party software. By following this documentation you agree that using such third-party software is done at your own discretion and risk. No advice or information, whether oral or written, obtained by you from us or from this documentation shall create any warranty for the third-party software. Additionally, by following these descriptions or using the contents of this documentation, you agree that you are responsible for complying with all third party licenses applicable to such third-party software. All product names, logos, and brands are property of their respective owners. All third-party company, product and service names used in this documentation are for identification purposes only. Use of these names, logos, and brands does not imply endorsement.
