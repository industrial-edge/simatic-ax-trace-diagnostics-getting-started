# SIMATIC  AX Trace Diagnostics Getting Started

## Description

### Overview

The SIMATIC AX Trace Diagnostics is web-based application running on SIEMENS Industrial Edge used for tracing the PLC signals same way as it is done in the TIA Portal. This appication example demonstrates how to manage the connection with PLC and trace the chosen variables. 

### General task

In this application example, the connection to the PLC using this application is managed and several signals from the bottles' filling process are traced.  The publishing of signals' data to Databus is also shown in this application example. Then, the corresponding signals are read using the Flow Creator.

It can be noticed that a high frequency noise can be traced using this application as well. It is due to the ability of this application to trace high frequency signals. Why this application can do that? As will be explained in the Configuration guide, the sampling period of the signals is directly derived from the PLC's cyclic interrupt's sampling period.

![task](docs/graphics/Overview.png)

## Requirements

###  Prerequisites

- Access to an Industrial Edge Management System (IEM)
- Onboarded Industrial Edge Device (IED) or Industrial Edge Virtual Device (IEVD) on IEM
- Installed System Configurator for Databus
- Installed System App Databus
- Installed Apps SIMATIC AX Trace Diagnostics and Flow Creator
- IED in the same network as PLC (PLC is reachable from IED)
- TIA portal project (Tank Application) loaded on PLC (real one or simulated using S7-PLCSIM Advanced)

### Used components

- Industrial Edge Management V1.5.2-4
  - SIMATIC AX Trace Diagnostics V1.0.2
  - Databus V2.1.0-4
  - Databus Configurator V2.0.0-4
  - Flow Creator V 1.12.0-1
  - Common Connector Configurator V1.8.2-3
- Industrial Edge Virtual Device V1.12.0-3-a
- TIA Portal V16
- S7-PLCSIM Advanced V3.0 Upd2
- S7-1511C
- Web browser (Google Chrome)

### Further requirements

- Databus Configurator is deployed to the IEM
- Databus is deployed to the IED
- Flow Creator is deployed to the IED

### TIA Project

The used TIA Portal project (Tank Application) can be found in the [src](docs/src) directory under the following name and is also used for several further application examples: 

* [HowTos_Sinus_Wave.7z](docs/src/HowTos_Sinus_Wave.7z)

## Usage

The application SIMATIC AX Trace Diagnostics offers following functionalities:

* Connection to PLC via integrated S7 connector
* Definition of trace jobs
* Visualization of traced signals
* Publishing the signals' data to Databus (up to 4 signals)
