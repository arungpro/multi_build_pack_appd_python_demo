# Appd PCF Python multibuildpack demo

[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

Sample demo to demonstrate the use of multibuild pack PCF - for more details refer - https://docs.pivotal.io/partners/appdynamics/index.html
Note:
  - If there are any changes by the time you go through this demo in comparision with docs above, Author don't own the responsibility.
  
# Steps

## Step 1: Create a service
There are two ways to do it
1. Using Appdynamics tiles:
 - via Apps manager you can, you can navigate to Marketplace and search for appdynamics App. In Console/Terminal, You should be able to see
    ```sh
    $ cf marketplace -s appdynamics
    service plan                   description                    free or paid
    pcf-appd                       pcf-appd                       free
    pcf-appd-test                  pcf-appd-test                  free
    ```
- Create a service instance of the appdynamics service and a plan of your choice
    ```sh
        $ cf create-service appdynamics pcf-appd demo
    ```

2. Using User defined Service (CUPS)
    ```sh
        $ cf cups demo -p '{"account-access-key":"acce$$key", "account-name":"customer1", "host-name":"demo.appdynamics.com", "port":"8090", "ssl-enabled":false}' 
    ```
## Step 2: Clone the repo
```sh
    $ git clone  && cd  
```

## Step 3: Make necessary changes at manifest.yml file
ENV variables Names that you define should with https://docs.appdynamics.com/display/PRO45/Python+Agent+Settings

## Step 4: Push the app
```sh
    $ cf push
```

## Step 5: Drive load to the app route
