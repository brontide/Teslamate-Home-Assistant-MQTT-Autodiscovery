# Teslamate-Home-Assistant-MQTT-Autodiscovery
A Home Assistant Script to auto-discover MQTT topics populated by the Teslamate application

Forked from: https://github.com/mekaneck/Teslamate-Home-Assistant-MQTT-Autodiscovery 

See instruction below for installation from this repo or the original

## Blueprint

[![Import Blueprint](https://img.shields.io/badge/Home%20Assistant-Import%20Blueprint-blue?logo=homeassistant)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://raw.githubusercontent.com/brontide/Teslamate-Home-Assistant-MQTT-Autodiscovery/refs/heads/with-blueprint-and-sample/teslamate-routing-notification-blueprint.yaml)

The blueprint allows you to quickly create a route notification in Home Assistant that looks like the
following.

![Route Notification Android](/assets/Screenshot_20260310-114638.png)

## Sample

If the Blueprint is not sufficient for your needs, please review the sample notification that can be 
easily extended to your usecase.

## Instructions: 
  1. Copy the yaml file contents into your configuration.yaml, or if you use packages save the entire YAML file
     in your packages folder.
  2. Edit line 21 with your HA auto discovery prefix. If you don't know what this is, leave it alone.
  3. Add your vehicle on lines 27-33. If you have multiple cars, make additional list entries.
  4. In Home Assistant, go to developer tools > YAML and click SCRIPTS to reload them.
  5. In Home Assistant, go to 'automations' > 'scripts' and run 'Teslamate Entity Creator'.
     
#### (Optional:)
  6. Modify, add, or remove any sensor starting on line 51. All entries under the "config:" key are documented here:
     https://www.home-assistant.io/integrations/sensor.mqtt/#configuration-variables
     In order to pass a template, the brackets must be commented out. Use the following example as a reference:
     `value_template: "{{ '{{' }} value | float(0) * 1.234 {{ '}}' }}"`
  7. Create an automation to re-run this script whenever the software version sensor is updated. This ensures the correct software version is shown on the MQTT device page for each vehicle.

## References:
Take insipration from the Teslamate documentation regarding the types of sensors you can create:
https://docs.teslamate.org/docs/integrations/home_assistant/#mqtt_sensorsyaml-mqtt-section-of-configurationyaml
