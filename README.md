# Microbit-Accelerator_Data-Analysis

This repository will:
1. Help you **get started** with intermediate electronics programming and data related operations.
2. Provide examples of how to do professional Data Analysis using python and jupyter notebook environment.
3. Provide examples of how an accelerometer works and how to convert the data into meaningful format with mathematical functions.


# What do you need for this project?

* 2x micro:bit v2
* 1x micro:bit battery
* 1x USB-C Cable
* Access to a computer with internet

<img src="https://github.com/user-attachments/assets/6e55cffb-de00-4dd4-9ec8-cc0b9925e0dc" alt="requirements" width="1000" height="500">

# Step1: How to connect two micro:bits?

The project uses one of the micro:bit as a accelerometer sensor and the other one as a signal receiver and writer. After collecting the data, use 2-)Accelerometer_Data-Analysis/Accelerometer_Analysis.ipynb to go through the Data Analysis provided by us.

Follow the steps:
1. Download the hex file for [signal transmitter micro:bit](Microbit_Setup/microbit-data-transmitter.hex)
2. Download the hex file for [data logger micro:bit](Microbit_Setup/microbit-data-logger.hex)
3. Upload both to the makecode website https://makecode.microbit.org/# using this link.
4. After they are uploaded to the website, click on the data transmitter and download it to the first micro:bit. Unplug the USB cable and wire the battery.
5. Exit the data transmitter file and click on the data logger. Wire usb and download the code to the second micro:bit. After it is downloaded do NOT unplug the USB cable and click on simulate device.
6. Accelerate the battery-wired microbit and monitor the changes in the dimensions on the simulation.
7. After you have accelerated the data transmitter for a while, click on the 'Save raw text' button on the top right.
8. Now is the time to analyze the data you just collected from your two micro:bit system! You will use Google's Lab Website, which will provide you with the computing, and we will provide you with the code that will run on that website. To download the code, click on this [link](Accelerometer_Data-Analysis/Accelerometer_Analysis.ipynb) and click on "Download raw file".
9. Now that you have the code, the only step left is to go to [Google Colab](https://colab.research.google.com/) and upload your code to that website and follow the steps provided for the Data Analysis section.
10. IMPORTANT: After you upload your raw data to the notebook environment, DON'T forget to change the name of the file in the Import Data section. For example: your .txt file's name will be different than the example provided in the original code, which was 'microbit-console-2024-10-15T20-25-42-764Z.txt'. Just delete the filename between the brackets and copy-paste the name of your file with .txt extension.


<img src="https://github.com/user-attachments/assets/e1fc3fcd-e91a-4682-9fb5-a52ca20a10be" alt="chart1" width="1000" height="500">

<img src="https://github.com/user-attachments/assets/71400d98-1564-46f6-b220-0fca94af859e" alt="chart2" width="1000" height="500">


