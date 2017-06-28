# ha-handson

## Excercises

### 1. Make Alexa and Google Home talk to each other

There are several examples on the internet on how to make Alexa and Google Home talk to each other. Maybe use your phone and add Siri to the mix. And oh... you can do better than the calendar example don't you?

### 2. Check out the CEC module with Home Assistant

Configure the CEC module on Hasbian on the Raspberry PI and figure out cool stuff to do with the tv:
* https://home-assistant.io/components/hdmi_cec/
Or use 
* https://home-assistant.io/components/notify.webostv/

### 3. Check out the competition

* http://www.openhab.org/
* https://calaos.fr/en/
* https://domoticz.com/
* https://www.openmotics.com/

Are there more?

### 4. Write you own module

Connect with ... and write your own home assistant module. More documentation  

### 5. AWS integration

Think bigger than python code and connect to AWS Lambda:

* https://home-assistant.io/components/notify.aws_lambda/

Or for more AWS:
 
* https://home-assistant.io/components/#search/aws


### 6. Your idea really...

There is plenty of modules in the home assistant documentation that are really interesting to play with, even without connected hardware. How about:

* cpu, battery, etc: https://home-assistant.io/components/#system-monitor 
* command line, messagebird, telegram: https://home-assistant.io/components/#notifications
* presence detection via cisco, ubiquity, etc: https://home-assistant.io/components/#presence-detection maar ook apps als owntracks en locative

The complete list: https://home-assistant.io/components/#all

### 7. KNX ETS

There is only one spot for this excercise and you are going to need GJ's computer with the physical KNX key installed. You can learn more about the ETS software. Maybe reprogram some of the components if there is the need to do so in other excercises.

### 8. Bridge Home Assistant and KNX

(There is a maximum of 5 connections to KNX possible, so just about 4 at a time please. Talk to GJ)

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

### 9. Office automation

Create a design for the new Avisi office. How can we surpass the current 433Mhz setup :-). 

Rethink the way offices work, make a design, pick components and present this to the office team.

### 10. Write the ultimate automation recipe (aka automation for rainy days)

This can be done without a computer, without hardware, without programming. The only thing you need is your imagination.

Write the ultimate automation recipe(s). Use flow charts, use plain text, or draw nice pictures on a board.
For inspiration see https://home-assistant.io/cookbook/.
Write a set of ultim
