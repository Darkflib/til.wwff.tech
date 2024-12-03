+++
date = '2024-12-03T16:35:55Z'
draft = false
title = 'Smartthings CLI'
+++


Building my own integrations for smartthings, so I want some way to test things from my computer as opposed to having to sniff and decode app traffic from the phone.

I found this CLI tool that seems to do what I want. It isn't the most user friendly but it seems to work well. I mean, if you want user friendly, you can use the app. ;)

## Install

```bash
brew install smartthingscommunity/smartthings/smartthings
```

## Commands

```bash
Mike-MBP:miketest mike$ smartthings --help
Command Line Interface for the SmartThings APIs

VERSION
  @smartthings/cli/1.10.2 darwin-x64 node-v18.5.0

USAGE
  $ smartthings [COMMAND]

TOPICS
  apps               get a specific app or a list of apps
  capabilities       get a specific capability or a list of capabilities
  config             list config file entries
  devicepreferences  list device preferences or get information for a specific device preference
  deviceprofiles     list all device profiles available in a user account or retrieve a single profile
  devices            list all devices available in a user account or retrieve a single device
  edge
  installedapps      get a specific app or a list of apps
  installedschema    get a specific schema connector instance or a list of instances
  invites            list invitations for a schema app
  locations          list locations or get information for a specific Location
  organizations      list all organizations the user belongs to
  plugins            List installed plugins.
  presentation       query device presentation by vid
  rules              get a specific rule
  scenes             list scenes or get information for a specific scene
  schema             list all ST Schema Apps currently available in a user account
  virtualdevices     list all virtual devices available in a user account or retrieve a single device

COMMANDS
  apps               get a specific app or a list of apps
  autocomplete       display autocomplete installation instructions
  capabilities       get a specific capability or a list of capabilities
  config             list config file entries
  devicepreferences  list device preferences or get information for a specific device preference
  deviceprofiles     list all device profiles available in a user account or retrieve a single profile
  devices            list all devices available in a user account or retrieve a single device
  help               Display help for smartthings.
  installedapps      get a specific app or a list of apps
  installedschema    get a specific schema connector instance or a list of instances
  locations          list locations or get information for a specific Location
  logout
  organizations      list all organizations the user belongs to
  plugins            List installed plugins.
  presentation       query device presentation by vid
  rules              get a specific rule
  scenes             list scenes or get information for a specific scene
  schema             list all ST Schema Apps currently available in a user account
  virtualdevices     list all virtual devices available in a user account or retrieve a single device
```

## Login

No actual login method, so it puts you through the login flow on first command.

```bash
Mike-MBP:miketest mike$ smartthings devices
logging in... done
─────────────────────────────────────────────────────────────────────────────────────────────────────────────
 #   Label                  Name                                Type    Device Id
─────────────────────────────────────────────────────────────────────────────────────────────────────────────
 1   Bedroom main light     rgbw-color-bulb-2500-6500K          VIPER   bf0106b8-3444-4980-a021-47a14245d444
 2   Desk lamp 2            rgbw-color-bulb-2200-6500K          VIPER   638d812a-6a79-45bd-ac2b-4011780363b4
 3   Grey desklamp          rgbw-color-bulb-2200-6500K          VIPER   970d3d65-a185-43ca-87d9-66f89f336f6b
 4   Landing light          rgbw-color-bulb-2500-6500K          VIPER   f1c9561c-f613-41b4-ba2f-e1aa5b69613b
 5   Lounge 1               rgbw-color-bulb-2500-6500K          VIPER   b5573928-49a5-42f7-bd2c-c0d3eca74c6d
─────────────────────────────────────────────────────────────────────────────────────────────────────────────
 6   Lounge 2               rgbw-color-bulb-2500-6500K          VIPER   e6e4eb3b-3120-4c41-a1b0-f90ccd7a5304
 7   Pixel 8 Pro            Pixel 8 Pro                         MOBILE  b8b5b35c-f1d0-46cd-97da-78988d6a0b5a
 8   Samsung 7 Series (55)  Samsung 7 Series (55)               OCF     6453db03-988a-73fd-08cb-f1c48c028af2
 9   Smart Plug 2           plug-energy-usage-report            VIPER   1db8b73b-9e49-46a7-9688-04cf34a90a62
 10  Smart Plug 3           plug-energy-usage-report            VIPER   b83a6ef2-3ac5-41a4-8d4a-91f08416300c
─────────────────────────────────────────────────────────────────────────────────────────────────────────────
 11  Stained glass lamp     plug-energy-usage-report            VIPER   14b2e107-e746-4eab-82fc-511b634d0869
 12  Stairs                 rgbw-color-bulb-2500-6500K          VIPER   6c14b79c-7a5d-4976-a838-eea0ee8f9d9b
 13  Table lamp             plug-energy-usage-report            VIPER   7acbe645-01e4-4a4c-920b-dc0fcc5ad4b0
 14  Tapo_C225_LivingRoom   c2c-tplink-camera                   VIPER   a3ddbff6-aaa0-4fd8-a197-b218b6ae44ed
 15  Tapo_C320WS_Alley      c2c-tplink-camera-motion            VIPER   ab6366f8-2e1c-41d4-a2f1-10db9d9ffac7
─────────────────────────────────────────────────────────────────────────────────────────────────────────────
 16  Tapo_C500_003D         c2c-tplink-camera-motion            VIPER   0017848c-9cd0-498b-8744-ff2584253f3e
 17  Tapo_C500_DADE         c2c-tplink-camera-motion            VIPER   4318fd2e-9093-4389-8b69-e2494bde954b
 18  Tapo_D210_Doorbell     c2c-tplink-doorbell-motion-battery  VIPER   31a7311b-4972-4498-b7ad-9b2f7c6c339b
 19  Tapo_Hub_A2E0          c2c-tplink-hub                      VIPER   dbaf16ba-98be-4d9e-a15a-6a7a1567c81c
─────────────────────────────────────────────────────────────────────────────────────────────────────────────
```

## State

```bash
Mike-MBP:miketest mike$ smartthings devices 7acbe645-01e4-4a4c-920b-dc0fcc5ad4b0
Main Info
─────────────────────────────────────────────────────────
 Label              Table lamp
 Name               plug-energy-usage-report
 Id                 7acbe645-01e4-4a4c-920b-dc0fcc5ad4b0
 Type               VIPER
 Manufacturer Code  TP-Link
 Location Id        40866f80-0be4-4964-bd60-88a18579ed32
 Room Id            bb5ee6c5-fb76-4548-92bc-ca4ec44b00b3
 Profile Id         a25b207e-cbb9-40ae-8a88-906637c22ab6
 Capabilities       healthCheck
                    refresh
                    switch
                    powerConsumptionReport
─────────────────────────────────────────────────────────


Device Integration Info (from viper)
─────────────────────────────────────────────────────────────
 Unique Identifier  8022EE9C484019085ED8CB45695D20AF230697EC
 Manufacturer Name  TP-Link
 Model Name         P110   
 Sw Version         1.3.1 Build 240621 Rel.162048
 Hw Version         1.0    
─────────────────────────────────────────────────────────────
```

## Capabilities

```bash
Mike-MBP:miketest mike$ smartthings devices:capability-status 7acbe645-01e4-4a4c-920b-dc0fcc5ad4b0
───────────────────────────
 #  Id
───────────────────────────
 1  healthCheck
 2  powerConsumptionReport
 3  refresh
 4  switch
───────────────────────────
? Select a capability. 1
────────────────────────────────────
 Attribute                 Value
 checkInterval             60 s
 healthStatus
 DeviceWatch-Enroll
 DeviceWatch-DeviceStatus  "online"
────────────────────────────────────
```

## Capabilities Status

```bash
Mike-MBP:miketest mike$ smartthings devices:capability-status 7acbe645-01e4-4a4c-920b-dc0fcc5ad4b0
───────────────────────────
 #  Id
───────────────────────────
 1  healthCheck
 2  powerConsumptionReport
 3  refresh
 4  switch
───────────────────────────
? Select a capability. 2
──────────────────────────────────────────────────────────
 Attribute         Value
 powerConsumption  {    
                     "start": "2024-12-03T15:15:59.764Z",
                     "end": "2024-12-03T15:30:59.765Z",
                     "energy": 117,
                     "deltaEnergy": 0
                   }    
──────────────────────────────────────────────────────────
```

## Commands - Switch On

```bash
Mike-MBP:miketest mike$ smartthings devices:commands 7acbe645-01e4-4a4c-920b-dc0fcc5ad4b0 switch:on
Command executed successfully
```

## Setting Brightness/Hue etc

Most of these are 0-100.There is a check that they are not below 0, but anything above 100 is silently capped at 100.

```bash
Mike-MBP:miketest mike$ smartthings devices:commands b5573928-49a5-42f7-bd2c-c0d3eca74c6d 'switchLevel:setLevel(50)'
Command executed successfully
```

```bash
Mike-MBP:miketest mike$ smartthings devices:commands b5573928-49a5-42f7-bd2c-c0d3eca74c6d 'colorControl:setHue(33)'
Command executed successfully
```

```bash
Mike-MBP:miketest mike$ smartthings devices:commands b5573928-49a5-42f7-bd2c-c0d3eca74c6d 'colorControl:setSaturation(100)'
Command executed successfully
```

```bash
Mike-MBP:miketest mike$ smartthings devices:health
─────────────────────────────────────────────────────────────────────────────────────────────────────────────
 #   Label                  Name                                Type    Device Id
─────────────────────────────────────────────────────────────────────────────────────────────────────────────
 1   Bedroom main light     rgbw-color-bulb-2500-6500K          VIPER   bf0106b8-3444-4980-a021-47a14245d444
 2   Desk lamp 2            rgbw-color-bulb-2200-6500K          VIPER   638d812a-6a79-45bd-ac2b-4011780363b4
 3   Grey desklamp          rgbw-color-bulb-2200-6500K          VIPER   970d3d65-a185-43ca-87d9-66f89f336f6b
 4   Landing light          rgbw-color-bulb-2500-6500K          VIPER   f1c9561c-f613-41b4-ba2f-e1aa5b69613b
 5   Lounge 1               rgbw-color-bulb-2500-6500K          VIPER   b5573928-49a5-42f7-bd2c-c0d3eca74c6d
─────────────────────────────────────────────────────────────────────────────────────────────────────────────
 6   Lounge 2               rgbw-color-bulb-2500-6500K          VIPER   e6e4eb3b-3120-4c41-a1b0-f90ccd7a5304
 7   Pixel 8 Pro            Pixel 8 Pro                         MOBILE  b8b5b35c-f1d0-46cd-97da-78988d6a0b5a
 8   Samsung 7 Series (55)  Samsung 7 Series (55)               OCF     6453db03-988a-73fd-08cb-f1c48c028af2
 9   Smart Plug 2           plug-energy-usage-report            VIPER   1db8b73b-9e49-46a7-9688-04cf34a90a62
 10  Smart Plug 3           plug-energy-usage-report            VIPER   b83a6ef2-3ac5-41a4-8d4a-91f08416300c
─────────────────────────────────────────────────────────────────────────────────────────────────────────────
 11  Stained glass lamp     plug-energy-usage-report            VIPER   14b2e107-e746-4eab-82fc-511b634d0869
 12  Stairs                 rgbw-color-bulb-2500-6500K          VIPER   6c14b79c-7a5d-4976-a838-eea0ee8f9d9b
 13  Table lamp             plug-energy-usage-report            VIPER   7acbe645-01e4-4a4c-920b-dc0fcc5ad4b0
 14  Tapo_C225_LivingRoom   c2c-tplink-camera                   VIPER   a3ddbff6-aaa0-4fd8-a197-b218b6ae44ed
 15  Tapo_C320WS_Alley      c2c-tplink-camera-motion            VIPER   ab6366f8-2e1c-41d4-a2f1-10db9d9ffac7
─────────────────────────────────────────────────────────────────────────────────────────────────────────────
 16  Tapo_C500_003D         c2c-tplink-camera-motion            VIPER   0017848c-9cd0-498b-8744-ff2584253f3e
 17  Tapo_C500_DADE         c2c-tplink-camera-motion            VIPER   4318fd2e-9093-4389-8b69-e2494bde954b
 18  Tapo_D210_Doorbell     c2c-tplink-doorbell-motion-battery  VIPER   31a7311b-4972-4498-b7ad-9b2f7c6c339b
 19  Tapo_Hub_A2E0          c2c-tplink-hub                      VIPER   dbaf16ba-98be-4d9e-a15a-6a7a1567c81c
─────────────────────────────────────────────────────────────────────────────────────────────────────────────
? Select a device. 5
─────────────────────────────────────────────────────────
 Device Id          b5573928-49a5-42f7-bd2c-c0d3eca74c6d
 State              ONLINE
 Last Updated Date  2024-12-03T15:54:50.616Z
─────────────────────────────────────────────────────────
```

## Status

```bash
Mike-MBP:miketest mike$ smartthings devices:status b5573928-49a5-42f7-bd2c-c0d3eca74c6d
──────────────────────────────────────────────────────
 Capability        Attribute                 Value
 colorControl      saturation                100
 colorControl      color
 colorControl      hue                       100
 healthCheck       checkInterval             60 s
 healthCheck       healthStatus
 healthCheck       DeviceWatch-Enroll
 healthCheck       DeviceWatch-DeviceStatus  "online"
 switchLevel       levelRange
 switchLevel       level                     100 %
 switch            switch                    "on"
 colorTemperature  colorTemperatureRange
 colorTemperature  colorTemperature          6000 K
──────────────────────────────────────────────────────
```

## Logging

```bash
tail -F ~/Library/Caches/\@smartthings/cli/*.log
```

## Debugging

You can turn on debug output for the app by setting an environment variable. This gives you debug output from the login and request (and possibly other things)

```bash
SMARTTHINGS_DEBUG=true smartthings devices:commands b5573928-49a5-42f7-bd2c-c0d3eca74c6d 'switchLevel:setLevel(10)'
```
