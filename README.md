# Talk and Control Pentair Pool Circuits via Screenlogic IP

home assistant addon for communicating with Pentair EasyTouch via Screenlogic IP via nodejs

## Instructions

* This addon requires a local MQTT broker to pass state and commands to Screenlogic.  So install one.

* Add these entities to the HASS configuration...use those command_topic and state_topic attributes.

switch:
  - platform: mqtt
    name: pentair_pool
    command_topic: /pentair/pool/command
    state_topic: /pentair/pool/state

  - platform: mqtt
    name: pentair_spa
    command_topic: /pentair/spa/command
    state_topic: /pentair/spa/state

sensor:
  # Weather prediction
  - platform: yr

  - platform: mqtt
    name: pentair_pooltemp
    state_topic: /pentair/pooltemp/state

  - platform: mqtt
    name: pentair_spatemp
    state_topic: /pentair/spatemp/state

  - platform: mqtt
    name: pentair_airtemp
    state_topic: /pentair/airtemp/state

  - platform: mqtt
    name: pentair_alkalinity
    state_topic: /pentair/alkalinity/state

  - platform: mqtt
    name: pentair_calcium
    state_topic: /pentair/calcium/state

  - platform: mqtt
    name: pentair_cyanuricacid
    state_topic: /pentair/cyanuricacid/state

  - platform: mqtt
    name: pentair_ph
    state_topic: /pentair/ph/state

  - platform: mqtt
    name: pentair_saltppm
    state_topic: /pentair/saltppm/state

  - platform: mqtt
    name: pentair_saturation
    state_topic: /pentair/saturation/state


