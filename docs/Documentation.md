# SIMATIC AX Trace Diagnostics Getting Started: Documentation

- [SIMATIC AX Trace Diagnostics Getting Started: Documentation](#simatic-ax-trace-diagnostics-getting-started-documentation)
  - [Installation of necessary applications](#installation-of-necessary-applications)
  - [Managing the running PLC](#managing-the-running-plc)
  - [Adding the PLC](#adding-the-plc)
  - [Configuration of Databus](#configuration-of-databus)
  - [Publishing the trace jobs to databus](#publishing-the-trace-jobs-to-databus)
  - [Configuration of Flow Creator](#configuration-of-flow-creator)

## Installation of necessary applications

In order to try out the main functionalities of SIMATIC AX Trace Diagnostics application and the application example itself, the following applications should be installed on your IED or IEVD:

![Installed_apps](graphics/Installed_apps.png)

## Managing the running PLC

Download the TIA portal project (Tank application) to the PLC (real one or simulated using S7-PLCSIM Advanced) which is in the same network as your IED (or IEVD). Then, run the PLC. 

## Adding the PLC (configuration of the PLC connection)

Open the application SIMATIC AX Trace Diagnostics, click on button Trace Jobs and then on button Add PLC.

![Click_on_Trace_Jobs](graphics/Click_on_Trace_Jobs.png)

![Click_on_Add_PLC](graphics/Click_on_Add_PLC.png)

Fill the IP address of your PLC (can be different that the in the image), nickname of your PLC (your choice, no impacts to functionality) and the password if it is used for accessing the PLC. Then, click on button Add.

![Add_PLC](graphics/Add_PLC.png)

If the certificate used for accessing the PLC needs to be uploaded, the Connection mode should be change from Legacy to Secure via TSL.

![Choose_certificate](graphics/Choose_certificate.png)

If everything went smoothly, the added PLC should be visible and its is Online.

## Adding and running the trace jobs

## Configuration of Databus

## Publishing the trace jobs to databus

## Configuration of Flow Creator



