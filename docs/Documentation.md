# SIMATIC AX Trace Diagnostics Getting Started: Documentation

- [SIMATIC AX Trace Diagnostics Getting Started: Documentation](#simatic-ax-trace-diagnostics-getting-started-documentation)
  - [Installation of necessary applications](#installation-of-necessary-applications)
  - [Configuration of Databus](#configuration-of-databus)
  - [Managing the running PLC](#managing-the-running-plc)
  - [Configuration of connection to MQTT Databus](#configuration-of-connection-to-mqtt-databus)
  - [Adding the PLC](#adding-the-plc)
  - [Adding and configuring of Trace Job](#adding-and-configuring-of-trace-job)
  - [Running the Trace Job](#running-the-trace-job)
  - [Publishing the Trace Jobs to Databus](#publishing-the-trace-jobs-to-databus)
  - [Observing the Trace Jobs and data exporting](#observing-the-trace-jobs-and-data-exporting)
  - [Checking the published data in IIH Essentials](#checking-the-published-data-in-iih-essentials)
  - [Adding the second PLC and high speed sampling testing](#adding-the-second-plc-and-high-speed-sampling-testing)
 
## Installation of necessary applications

In order to try out the main functionalities of SIMATIC AX Trace Diagnostics application and the application example itself, the following applications should be installed on your IED or IEVD:

![Installed_apps](graphics/Installed_apps.png)

## Configuration of Databus

In your IEM go to the Data Connections and open the Databus. Add a user with following topic: `"ie/#"` and deploy it to IED.

![Databus_configuration_1](graphics/Databus_configuration_1.png)

![Databus_configuration_2](graphics/Databus_configuration_2.png)

![Databus_configuration_3](graphics/Databus_configuration_3.png)

![Databus_configuration_4](graphics/Databus_configuration_4.png)

![Databus_configuration_5](graphics/Databus_configuration_5.png)

![Databus_configuration_6](graphics/Databus_configuration_6.png)

## Managing the running PLC

Download the TIA portal project (Tank application) to the PLC (real one or simulated using S7-PLCSIM Advanced) which is in the same network as your IED (or IEVD). Then, run the PLC. 

The HMI interface can be also downloaded/simulated for better understanding of demo Tank application workflow. 

## Configuration of connection to MQTT Databus

Open the application SIMATIX AX Trace Diagnostics, go to the Settings and then click on the button Edit under the MQTT Connection Status. 

![MQTT_connection_configuration_1](graphics/MQTT_connection_configuration_1.png)

Then, configure the MQTT Databus Address, Port Number, Username and Password and click on the button Connect.

![MQTT_connection_configuration_2](graphics/MQTT_connection_configuration_2.png)

When this configuration is done, the MQTT Connection Status should be Connected. 

![MQTT_connection_configuration_3](graphics/MQTT_connection_configuration_3.png)

## Adding the PLC (configuration of the PLC connection)

Click on the button Trace Jobs and then on the button Add PLC.

![Click_on_Trace_Jobs](graphics/Click_on_Trace_Jobs.png)

![Click_on_Add_PLC](graphics/Click_on_Add_PLC.png)

Fill the IP address of your PLC (can be different that the one in the image), nickname of your PLC (your choice, no impacts to functionality) and the password if it is used for accessing the PLC. Then, click on the button Add.

![Add_PLC](graphics/Add_PLC.png)

If the certificate used for accessing the PLC needs to be uploaded, the Connection mode should be change from Legacy to Secure via TSL.

![Choose_certificate](graphics/Choose_certificate.png)

Then, the added PLC should be visible and its status is Online.

![Added_PLC](graphics/Added_PLC.png)

## Adding and configuring the Trace Job

Click on the button Add Trace Job.

![/Add_Trace_Job](graphics/Add_Trace_Job.png)

Then, select the PLC added in previous section and write down the Job Name. Proceed with selecting the Organization Block (OB) determining the sampling period of trace job. The sampling period will be the same as cyclic time of selected OB type cyclic interrup. In case of Tank application use in this application example, the OB `"Cyclic interrupt"` is used. The sampling frequency will be 10 ms. 

You can also lower the sampling period by typing different integer than 1 to Samplig Frequency text box. For instance, 2 means that every second sample will be taken. 

![Trace_Job_configuration](graphics/Trace_Job_configuration.png)

The specific Number of samples can be selected to take. The trace job ends after that. If Perpetual Job Type type is seletected, the sampling is continuous until the trace job is turned off. 

In order to choose the signal for tracing, its exact TIA portal's name should be written down into Signal text box. Then, the button Add Signal should be pressed.
More signals can be also traced using one trace job.

![Trace_Job_signals_more_names](graphics/Trace_Job_signals_more_names.png)

When the Trace Job is configured, click on the button Install on PLC.

Here is the table of proposed process values for tracing:

| TIA portal's name | Description | Proposed Trace Job's name |
| ------------- | ------------- | ------------- |
| GDB.signals.tankSignals.actLevel  | actual level of tank in liters | TankActLevel |
| GDB.signals.tankSignals.actTemperature  |  actual temparature in tank in degrees Celsius | TankActTemp |
| GDB.signals.tankSignals.actPressure | actual pressure in tank in hectopascals | TankActPress |
| GDB.signals.bottleSignals.outputTank | actual outflow from tank in liters per minute  | TankOutput |
| GDB.signals.bottleSignals.actLevel | actual level of filling bottle in liters | BottleActLevel |

## Running the Trace Job

When the Trace Job is configured correctly and added, it can be run by clicking on the meatballs menu and then on the button Run Job.

![Trace_Job_running](graphics/Trace_Job_running.png)

## Publishing the Trace Jobs to Databus

If the publishing of trace was not set during the configuration of the Trace Job, it can be set afterwards by clicking on the meatballs menu and then on the button Publish Job.

![Trace_Job_publishing](graphics/Trace_Job_publishing.png)

In the next window, the option of publishing only the changes to Databus can be selected. For continuos publishing, this checkbox should be left unchecked. Then, click on the button Publish. 

![Trace_Job_publishing_settings](graphics/Trace_Job_publishing_settings.png)

The publication to Databus can be deleted by clicking to the button Delete Publication in meat beals menu in corresponding Trace Job. 

![Deleting_Databus_Publication_1](graphics/Deleting_Databus_Publication_1.png)

![Deleting_Databus_Publication_1_next_window](graphics/Deleting_Databus_Publication_1_next_window.png)

In order to see the overview of Databus publications, go the Databus Publications.

![/Databus_Publications](graphics/Databus_Publications.png)

Here the Databus publication can be deleted as well.

![Deleting_Databus_Publication_2](graphics/Deleting_Databus_Publication_2.png)

![Deleting_Databus_Publication_2_next_window](graphics/Deleting_Databus_Publication_2_next_window.png)

The maximum of published Trace Jobs to databus is four.

![Maximum_of_Databus_publishing](graphics/Maximum_of_Databus_publishing.png)

![Maximum_of_Databus_publishing_Databus_Publications](graphics/Maximum_of_Databus_publishing_Databus_Publications.png)

## Observing the Trace Jobs and data exporting

Go back to the Trace Jobs and open some Trace Job by clicking on the button Read Job Data.

![Trace_Job_opening](graphics/Trace_Job_opening.png)

Then, the plot of data appears. If the mouse is moved to the curve, the details (values of each axis) are visualized. 

![Trace_Bob_data_analysis](graphics/Trace_Bob_data_analysis.png)

This can be done also if more signals are in plot. 

![Trace_Jobs_data_analysis_more_signals](graphics/Trace_Jobs_data_analysis_more_signals.png)

If the plot needed to be updated, then click on the button Update.

![Trace_Job_updating](graphics/Trace_Job_updating.png)

If zooming in or zooming out needs to be done, using these corresponding buttons it can be done.

![Trace_Job_signals_zooming](graphics/Trace_Job_signals_zooming.png)

Moreover, the specific area to zoom can be selected:

![Trace_Job_zooming_specific_area](graphics/Trace_Job_zooming_specific_area.png)

In order to export the data to desire format, click on the hamburger icon and export the data.

![Trace_Job_updating_exporting_1](graphics/Trace_Job_updating_exporting_1.png)

![Trace_Job_updating_exporting_2](graphics/Trace_Job_updating_exporting_2.png)

## Checking the published data in IIH Essentials

Open the application IIH Essentials, go to the Settings and configure the  Databus settings. 

![IIH_Essentials_Databus_settings_1](graphics/IIH_Essentials_Databus_settings_1.png)

![IIH_Essentials_Databus_settings_2](graphics/IIH_Essentials_Databus_settings_2.png)

![IIH_Essentials_Databus_settings_3](graphics/IIH_Essentials_Databus_settings_3.png)

Then, go to Connectors and configure custom connector for the data from SIMATIC AX Trace Diagnostics application.

![IIH_Essentials_adding_cutom_connector_1](graphics/IIH_Essentials_adding_cutom_connector_1.png)

![IIH_Essentials_adding_cutom_connector_2](graphics/IIH_Essentials_adding_cutom_connector_2.png)

![IIH_Essentials_adding_cutom_connector_3](graphics/IIH_Essentials_adding_cutom_connector_3.png)

When this configuration is done, the configured custom connector should look as follows:

![IIH_Essentials_adding_cutom_connector_4](graphics/IIH_Essentials_adding_cutom_connector_4.png)

Go to the Assets & Connectivity and add the variable published to Databus in SIMATIC AX Trace Diagnostics application. Only the marked setting should be done. The other fields are filled automatically and it can be kept.

![IIH_Essentials_adding_variable_1](graphics/IIH_Essentials_adding_variable_1.png)

When the variable is added, its values can be observed.

![IIH_Essentials_adding_variable_2](graphics/IIH_Essentials_adding_variable_2.png)

All other process values published to Databus in SIMATIC AX Trace Diagnostics can be added same way. 

![IIH_Essentials_adding_variables](graphics/IIH_Essentials_adding_variables.png)

## Adding the second PLC and high speed sampling testing

Reopen the SIMATIC AX Trace Diagnostics application, go to the Trace Jobs and add another PLC.

![Add_second_PLC](graphics/Add_second_PLC.png)

Then, configure the Trace Job for this PLC. Fill the OB's name `"1ms_Task"`. It means that the samplig period of this Trace Job will be 1 millisecond. 

![Trace_Job_configuration_sinus](graphics/Trace_Job_configuration_sinus.png)

Here is the table of sinus value's specifications:

| TIA portal's name | Description | Proposed Trace Job's name |
| ------------- | ------------- | ------------- |
| InstSinus.sinusVal  | value of periodic function sinus with various frequency, amplitude and offset | SinusValue |

The parameters of sinus wave can be changed in TIA portal's project by setting of corresponding values
- sinusParameter.freq
- sinusParameter.offset
- sinusParameter.amplitude

This is the Trace Job for sinus value with frequency 10 and 50 Hertz. 

![Trace_Job_sinus_10_Hz](graphics/Trace_Job_sinus_10_Hz.png)

![Trace_Job_sinus_50_Hz](graphics/Trace_Job_sinus_50_Hz.png)

The sinus wave is still well sampled for frequency 200 Hz. 

![Trace_Job_sinus_200_Hz_1](graphics/Trace_Job_sinus_200_Hz_1.png)

![Trace_Job_sinus_200_Hz_2](graphics/Trace_Job_sinus_200_Hz_2.png)

For the frequency 201 Hz the aliased frequency is already seen in the traced signal. 

![Trace_Job_sinus_201_Hz_1](graphics/Trace_Job_sinus_201_Hz_1.png)

![Trace_Job_sinus_201_Hz_2](graphics/Trace_Job_sinus_201_Hz_2.png)
