# ha-handson

## Excercises

### Make Alexa and Google Home talk to each other

There are several examples on the internet on how to make Alexa and Google Home talk to each other. 

### Check out the CEC module with Home Assistant

Use the 

### Check out the competition



### Your idea really...

There is plenty of modules in the home assistant documentation that are really interesting to play with, even without connected hardware. How about:



The complete list: https://home-assistant.io/components/#all

### KNX ETS

There is only one spot for this excercise and you are going to need GJ's computer with the physical KNX key installed. You can use the ETS software to connect KNX modules together.

### Bridge Home Assistant and KNX

There is a maximum of 5 connections to KNX possible

The Mac address of the KNX IP module is 80:2a:a8:99:86:7e, but what you really need is the *ip address*, which is *...*

The installed modules are:
 
TXA 111 (just the power supply)
TXA 610D: This is a 10-fold switch actuator. It has 4 outlets wired to it and 4 additional indicator lights.
GIRA 2104: This is a co2, temperature, humidity sensor.

Check the knx folder for more documentation on these modules.

Here is snippet of configuration to connect to the example knx setup. 

```
sensor knx:                 
  - platform: knx           
    name: temperature       
    type: temperature       
    address: 0/0/1          
  - platform: knx           
    name: co2
    type: temperature       
    address: 0/0/2          

switch knx:                 
  - platform: knx           
    name: Fan               
    address: 0/1/0          
    state_address: 0/2/0    
  - platform: knx           
    name: Airco             
    address: 0/1/1          
    state_address: 0/2/1    
  - platform: knx           
    name: Espresso
    address: 0/1/2          
    state_address: 0/2/2
  - platform: knx           
    name: Floor lamp        
    address: 0/1/3          
    state_address: 0/2/3
  - platform: knx           
    name: five              
    address: 0/1/4          
    state_address: 0/2/4
  - platform: knx           
    name: six               
    address: 0/1/5          
    state_address: 0/2/5
  - platform: knx           
    name: seven             
    address: 0/1/6
    state_address: 0/2/6
  - platform: knx
    name: eight
    address: 0/1/7
    state_address: 0/2/7
```

###
