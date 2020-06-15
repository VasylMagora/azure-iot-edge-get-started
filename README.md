# azure-iot-edge-get-started
Initial guide to start simple test application on Hivecell One, connected with Azure IoT Edge
platform	device	language
enter the OS name running on edge device	
enter your device name here	
enter the language used to you edge device
We highly recommend keeping this document current, and Microsoft reserves a right to remove devices and documents from the Azure IoT Device Catalog if document contains broken URL links, incorrect information etc.

Run a simple {enter the language used to you edge device} sample on {enter your device name here} device running {enter the OS name running on edge device. Specify distribution or Windows SKU information. Ex: Ubuntu Sever 16.04, Windows 10 IoT Core. Only Tier 1 OS is allowed}
Table of Contents
Introduction
Step 1: Prerequisites
Step 2: Prepare your Device
Step 3: Manual Test for Azure IoT Edge on device
Step 4: Next Steps
Step 5: Troubleshooting
Instructions for using this template
Replace the text in {placeholders} with correct values.
Delete the lines {{enclosed}} after following the instructions enclosed between them.
It is advisable to use external links, wherever possible.
Remove this section from final document.

Introduction
About this document

This document describes how to connect {enter your device name here} device running {enter the OS name running on edge device} with Azure IoT Edge Runtime pre-installed and Device Management. This multi-step process includes:

Configuring Azure IoT Hub
Registering your IoT device
Build and Deploy client component to test device management capability

Step 1: Prerequisites
You should have the following items ready before beginning the process:

Prepare your development environment
Setup your IoT hub
Provision your device and get its credentials
Sign up to IOT Hub
Add the Edge Device
Add the Edge Modules
{enter your device name here} device.
{{Please specify if any other software(s) or hardware(s) are required.}}

Step 2: Prepare your Device
{{Write down the instructions required to setup, configure and connect your device. Please use external links when possible pointing to your own page with device preparation steps.}}

Step 3: Manual Test for Azure IoT Edge on device
This section walks you through the test to be performed on the Edge devices running the Linux operating system such that it can qualify for Azure IoT Edge certification.


3.1 Edge RuntimeEnabled (Mandatory)
Details of the requirement:

The following components come pre-installed or at the point of distribution on the device to customer(s):

Azure IoT Edge Security Daemon
Daemon configuration file
Moby container management system
A version of hsmlib
Edge Runtime Enabled:

Check the iotedge daemon command:

Open the command prompt on your IoT Edge device , confirm that the Azure IoT edge Daemon is under running state

systemctl status iotedge


Open the command prompt on your IoT Edge device, confirm that the module deployed from the cloud is running on your IoT Edge device

sudo iotedge list


On the device details page of the Azure, you should see the runtime modules - edgeAgent, edgeHub and tempSensor modueles are under running status




3.2 Device Management (Optional)
Pre-requisites: Device Connectivity.

Description: A device that can perform basic device management operations (Reboot and Firmware update) triggered by messages from IoT Hub.

3.2.1 Firmware Update (Using Microsoft SDK Samples):
Specify the path {{enter the path}} where the firmwareupdate client components are installed.

To run the simulated device application, open a shell or command prompt window and navigate to the iot-hub/Tutorials/FirmwareUpdate folder in the Node.js project you downloaded. Then run the following commands:

npm install
node SimulatedDevice.js "{your device connection string}"
To run the back-end application, open another shell or command prompt window. Then navigate to the iot-hub/Tutorials/FirmwareUpdate folder in the Node.js project you downloaded. Then run the following commands:

npm install
node ServiceClient.js "{your service connection string}"
IoT device client will get the message and report the status to the device twin.



Update firmware

Confirm the IoT hub, Device ID, method name and method payload as below:

Press “call Method” button
Check the returning status as below:


3.2.2 Reboot (Using Microsoft SDK Samples):
Specify the path {{enter the path}} where the components are installed

Confirm the IoT hub, Device ID, method name as below:

Press “call Method” button
Check the returning status as below:


IoT device client will get the message and report the status to the device twin.



3.3.3 Firmware Update (Modified SDK samples/Custom made application):
If the Client components are custom made please add the steps to execute the Firmware Update through Device Twin.

Note: Client Components must be shipped with the device

3.3.4 Reboot (Modified SDK samples/Custom made application):
If the Client components are custom made please add the steps to execute the Device Reboot through Direct Methods

Note: Client Components must be shipped with the device


Step 4: Next steps
Once you shared the documents with us, we will contact you in the following 48 to 72 business hours with next steps.


Step 5: Troubleshooting
