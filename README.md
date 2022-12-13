# controlco2-esphome
ESPHome configuration file to get Control CO2 into Home Assistant.

# What
During the pandemic I bought a CO2 meter from [controlco2](https://controlco2.space/nl_be/product/control-co2-bouwpakket-v2/). The project was started by hackerspaces under [Operame](https://operame.nl/Operame), but that project was only intended for use in schools. So when ControlCO2 announced a semi-commercial option, I bought one to play with and to use in my office.

# Why?
I have had my CO2 meter setup in my office for a couple of years now, but I wanted to do something more with it. I wanted to graph the temperature, humidity and CO2 PPM over time via Home Assistant. The controlco2 software has MQTT build into the firmware, but I didn't like that I needed to run an extra deamon to log this information. Instead I decided to add it to ESPHome. Now I can remotely monitor the values and easily update the firmware via OTA.

# How
Here is a good tutorial to [get you started with ESPHome in HomeAssistant](https://www.youtube.com/watch?v=7R30c-H8Rro)

In Home Assistant go to Settings -> Add Ons -> Add on store and search for "ESPHome". Install it, start it during boot and add it to your sidebar for easy access.

![Screenshot 2022-12-13 at 13 52 16](https://user-images.githubusercontent.com/242967/207324932-4045465a-f10b-4a6e-8a9e-49ede10b9e99.png)

Open ESPHome in Chrome to allow for serial connections. In ESPHome add the green button in the bottom corner to add new device. Give the device a new, for example: controlco2. Select ESP32 and press install. Now connect your Control CO2 board via USB to your computer. Choose 'Plug into your computer'. Wait for the firmware to download and press Open ESPHome Web.

![Screenshot 2022-12-13 at 13 55 29](https://user-images.githubusercontent.com/242967/207325037-5b32a688-eb02-4a04-849e-cce7a7ac9b0d.png)

Edit the ControlCO2 device, load the yaml file from this repository and press Install. If you previously loaded the firmware via USB successfully, you can now load the new firmware Wirelessly or via USB.

![Screenshot 2022-12-13 at 13 58 32](https://user-images.githubusercontent.com/242967/207325075-5ae37c1b-c26a-442f-9a78-92a857f878c9.png)

After the firmware has been loaded, it will begin displaying information on the screen and begin logging data to HomeAssistant:

![Screenshot 2022-12-13 at 14 02 05](https://user-images.githubusercontent.com/242967/207325262-ce317711-0827-4210-84f8-2801f28d7764.png)

When you go to History and you select device ControlCO2. You can now see your CO2 PPM, Temperature and Humidity values over time:

![Screenshot 2022-12-13 at 14 03 25](https://user-images.githubusercontent.com/242967/207325517-e7e6e79a-ed58-44c4-9075-6f3548e5e687.png)
