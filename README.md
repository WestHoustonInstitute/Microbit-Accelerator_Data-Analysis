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

<img src="https://github.com/user-attachments/assets/5a5624f5-abb8-4e74-9924-46ebc63a4fbe" alt="requirements" width="1000" height="500">

# Step1: How to connect two micro:bits?

The project uses one of the micro:bit as a accelerometer sensor and the other one as a signal receiver and writer. After collecting the data, use 2-)Accelerometer_Data-Analysis/Accelerometer_Analysis.ipynb to go through the Data Analysis provided by us.

Follow the steps:
1. Download the hex file for [signal transmitter micro:bit](Microbit_Setup/microbit-data-transmitter.hex)
2. Download the hex file for [data logger micro:bit](Microbit_Setup/microbit-data-logger.hex)
3. Provide examples of how an accelerometer works and how to convert the data into meaningful format with mathematical functions.
4. 

Here is a simple example logging hello world message to the terminal:

```yaml
id: hello  
namespace: prod
tasks:
  - id: hello-world
    type: io.kestra.plugin.core.log.Log
    message: Hello world!
```

## Adding a schedule

Here is how you can add a schedule trigger to run the flow every minute: [helloParametrizedScheduled.yml](flows/getting_started/helloParametrizedScheduled.yml)

To add multiple schedules, each running with different input parameter values, use [helloParametrizedMultipleSchedules.yml](flows/getting_started/helloParametrizedSchedulesMultiple.yml)

---

# How to integrate Kestra with other tools in the Modern Data Stack 

## Airbyte

Here is an example of using Kestra with Airbyte running in other Docker container: [airbyteSync.yml](flows/airbyte/airbyteSync.yml)

And example running multiple Airbyte syncs in parallel: [airbyteSyncParallel.yml](flows/airbyte/airbyteSyncParallel.yml) 

## Fivetran

Here is an example of a flow with a single task triggering a Fivetran sync: [fivetranSync.yml](flows/fivetran/fivetranSync.yml)

---


# Custom Scripts

## How to run Bash and Python tasks

Here is an example of a Bash task: [csvKit](flows/python/csvKit.yml)


### Custom Docker image per task 

If you prefer to run the Python or Bash task in a (_potentially custom_) Docker container: [pythonScriptContainer](flows/python/pythonScriptContainer.yml)

Using `dockerOptions` with the `dockerConfig` attribute, you can also configure credentials to private Docker registries:

`auths: { "my.registry.com" : { auth: "token" } }`


### Docker image with `requirements.txt` built at runtime 


```yaml
id: hello_python_docker
namespace: company.team
tasks:
  - id: python_container
    type: io.kestra.plugin.scripts.python.Script
    beforeCommands:
      - pip install requests pandas
    taskRunner:
      type: io.kestra.plugin.scripts.runner.docker.Docker
    containerImage: python:3.11-slim
    script: |
      import pandas as pd
      import requests
      
      print(pd.__version__)
      print(requests.__version__)
```


## Keyboard shortcuts for the built-in editor in the UI

On Mac:
- fn + control + Space = Autocomplete
- command + K + C = Comment
- command + K + U = Uncomment
- opt + up/down = Move line up/down

On Windows:
- ctrl + space = Autocomplete
- ctrl + K + C = Comment
- ctrl + K + U = Uncomment
- alt + up/down = Move line up/down

---

# Credentials management

## Open-source Kestra

In the open-source version, you can leverage Secrets.

Create an `.env` file and add any environment variables there with the prefix `SECRET_`, as shown in the [.env_example](.env_example) file. The values are the passwords in the base64 encoded format.

Then, you can reference the secrets in your flow using `{{ secret('AIRBYTE_PASSWORD') }}`. Note that we drop the `SECRET_` prefix while referencing the secrets.

For security reasons, environment variables are fixed at the application startup (JVM startup).

Also, make sure that your Kestra container contains this configuration in your [docker-compose.yml](docker-compose.yml) file:

```yaml
  kestra:
    image: kestra/kestra:develop-full
    ...
    env_file:
      - .env
    environment:
      KESTRA_CONFIGURATION: |
        kestra:
          ...
```

## Cloud & Eneterprise Edition

Cloud & Enterprise Editions have a dedicated credentials managers with extra encryption, namespace-bound credential inheritance hierarchy and an RBAC-setting behind it.

You can add a Secret in the relevant namespace from the Namespace tab in the UI. You should not add the `SECRET_` prefix while setting up the secrets via the Namespace tab.

To reference that secret in your flow, use `{{ secret('AWS_ACCESS_KEY_ID') }}`.











# Microbit-Accelerator_Data-Analysis

This project includes Accelerometer Data Analysis, Radio Communication Programming, Angular Measurement Calculation. 
https://microbit.org/projects/make-it-code-it/makecode-wireless-data-logger/ is used for radio commmunication.

Requirements:
* 2x micro:bit 
* 1x Battery 
* 1x USB-C Cable
* Access to a computer with internet

<img src="https://github.com/user-attachments/assets/5a5624f5-abb8-4e74-9924-46ebc63a4fbe" alt="requirements" width="300" height="400">

The project uses one of the micro:bit as a accelerometer sensor and the other one as a signal receiver and writer. After collecting the data, use 2-)Accelerometer_Data-Analysis/Accelerometer_Analysis.ipynb to go through the Data Analysis provided by us.

<img src="https://github.com/user-attachments/assets/e1fc3fcd-e91a-4682-9fb5-a52ca20a10be" alt="chart1" width="600" height="400">

<img src="https://github.com/user-attachments/assets/71400d98-1564-46f6-b220-0fca94af859e" alt="chart2" width="600" height="400">

How to use: 
* After doing the configurations for the micro:bits, shake and accelerate the sensor micro:bit to send acceleration data.
* Then, when you finish experimenting(Suggested for approx. 1min), download the raw text.
* Download the 2-)Accelerometer_Data-Analysis/Accelerometer_Analysis.ipynb file and open it in Google Colab( https://colab.research.google.com )
* Follow the steps on the notebook.
