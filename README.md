Home-Assistant Lovelace card for carnet  


1. Download the images in the www folder and put them in /config/www

Optional, if you want the image to represent your car, log in to car-net on your computer and save the top image on the page as passat.png
Double check the dimensions of the image. The style below was set based on my image which is 820x461 pixels.

2. Put below content in your ui-lovelace.yaml

```yaml
#START VW CAR IMAGE
      - type: picture-elements
        image: /local/passat.png
        elements:

#State images to illustrate on top of car
          - type: image
            entity: switch.CARID_climatisation
            image: /local/blank.png
            style:
              top: 39.5%
              left: 55%
              width: 43%
            state_image:
              "on": /local/passat_heat.png

          - type: image
            entity: binary_sensor.CARID_external_power
            image: /local/blank.png
            style:
              top: 62.8%
              left: 21.2%
              width: 43%
            state_image:
              "on": /local/passatcharging.png

          - type: image
            entity: binary_sensor.CARID_parking_light
            image: /local/blank.png
            style:
              top: 66.8%
              left: 37.2%
              width: 37%
            state_image:
              "on": /local/passat_light.png

          - type: image
            entity: lock.CARID_doors_locked
            image: /local/blank.png
            style:
              top: 42.3%
              left: 57%
              width: 2%
            state_image:
              locked: /local/blink.gif

# Top left row with state icons

          - type: state-icon
            entity: lock.CARID_doors_locked
            style:
              top: 87%
              left: 47%

          - type: state-icon
            entity: switch.CARID_climatisation
            hold_action: toggle
            style:
              top: 87%
              left: 58%

          - type: state-icon
            entity: switch.CARID_window_heater
            hold_action: toggle
            style:
              top: 87%
              left: 69%

#Top right icons
          - type: state-icon
            entity: switch.CARID_charging
            style:
              top: 87%
              left: 80%

          - type: state-label
            entity: sensor.CARID_battery_level
            style:
              top: 96%
              left: 81%

          - type: state-icon
            entity: sensor.CARID_fuel_level
            style:
              top: 87%
              left: 91%

          - type: state-label
            entity: sensor.CARID_fuel_level
            style:
              top: 96%
              left: 92%


#END VW IMAGE CARD
```
