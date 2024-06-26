## ConCERTS: An IoT Device activity simulator for building an IoT Cybersecurity Research Range

## Description

The repository holds the software required for simulating an IoT device. Each device has:

- Settings for devices
- Commands
- Log file of executed commands
- Activity simulation script

This version of the device simulator supports ten types of devices:

1. [Card Reader](documentation/card-README.md) - a device that can simulate the swiping of a security card
2. [Card Manager](documentation/card-README.md) - a controller that compares the value of the card read with a whitelist of cards
3. [Door Lock](documentation/card-README.md) - a door lock that can lock and unlock a door

For detailed information on REST calls, see the device documentation.

![Card Diagram](https://github.com/arsh-aps/ConCERTS-device/assets/114761529/475b9186-8960-4b8c-881e-8fab69469ab4)

To simulate all three working together, you need to provide the settings for the card reader and door manager and then set the script for the card reader.  Running the card reader script will cascade the simulation to all of the devices.  See: start.sh script for automation of the simulation.

4. [Motion Detector](documentation/motion-README.md) - a device that detects motion by measuring changes in distance using ultrasonic waves
5. [Motion Manager](documentation/motion-README.md) - a controller that turns on the light if motion is detected and turns off the light if no motion is detected for a time period
6. [Light](documentation/motion-README.md) - a light that can turn on and off

For detailed information on REST calls, see the device documentation.

![Motion Diagram](https://github.com/arsh-aps/ConCERTS-device/assets/114761529/1bde315e-1fd5-4b5a-bebd-7792ff46727a)

Similar to card reader, provide settings for motion detector and motion manager and set script for motion detector to simulate all three working together. Additionally, you can convert the logfile generated by using the detector to create a script.

7. [Thermostat](documentation/hvac-README.md) - a device that can measure the temperature in a room
8. [HVAC Controller](documentation/hvac-README.md) - a device that controls airconditioner and furnace 
9. [Airconditioner](documentation/hvac-README.md) - a device that can cool the air in a room to a set temperature
10. [Furnace](documentation/hvac-README.md) - a device that can heat the air in a room to a set temperature

For detailed information on REST calls, see the device documentation.

![HVAC Diagram](https://github.com/arsh-aps/ConCERTS-device/assets/114761529/85d3229a-db44-4e49-a1ea-e5cb8985b889)

## Running the app

```bash
# build docker image
docker build -t concerts .

# run docker container
docker run --privileged -p 3000:3000 concerts
```

## Swagger Interface

This software supports a swagger interface to view the REST API.

http://localhost:3000/api

## Project Maintainer


## License

ConCERTS is [MIT licensed](LICENSE).
