# @datafire/smart_me

Client library for smart-me

## Installation and Usage
```bash
npm install --save @datafire/smart_me
```
```js
let smart_me = require('@datafire/smart_me').create({
  username: "",
  password: ""
});

smart_me.AccessToken_Put({
  "accessTokenToPut": {}
}).then(data => {
  console.log(data);
});
```

## Description

With the smart-me REST API you get Access to all your devices in the smart-me Cloud and you can add your own devices. So it's a easy way to add the smart-me Cloud support to your Hardware or Software Product.

## Actions

### AccessToken_Put
Creates a Access Token to write on a Card (e.g. NFC)


```js
smart_me.AccessToken_Put({
  "accessTokenToPut": {}
}, context)
```

#### Input
* input `object`
  * accessTokenToPut **required** [AccessTokenToPut](#accesstokentoput)

#### Output
* output `string`

### Actions_Post
Set an action for the specified device.


```js
smart_me.Actions_Post({
  "actionToPost": {}
}, context)
```

#### Input
* input `object`
  * actionToPost **required** [ActionToPost](#actiontopost)

#### Output
*Output schema unknown*

### Actions_Get
Gets all available Actions of a Device


```js
smart_me.Actions_Get({
  "id": ""
}, context)
```

#### Input
* input `object`
  * id **required** `string`: The ID of the device

#### Output
* output `array`
  * items [ActionInformation](#actioninformation)

### api.CustomDevice.get
Gets all Devices


```js
smart_me.api.CustomDevice.get(null, context)
```

#### Input
*This action has no parameters*

#### Output
* output `array`
  * items [CustomDeviceToPost](#customdevicetopost)

### CustomDevice_Post
Creates or updates a Custom Device or updates it's values.
            A Custom Device can be any device that like to add some measurement values to the smart-me Cloud.
            Only use a custom device for all non meters.
            For a new device leave the ID empty. To create a device you have to set the DeviceEnergyType.
            To update values, add the ID of the device and the values you like to set.  (See the Data Type Model for more Information)


```js
smart_me.CustomDevice_Post({
  "newDevice": {}
}, context)
```

#### Input
* input `object`
  * newDevice **required** [CustomDeviceToPost](#customdevicetopost)

#### Output
* output [CustomDeviceToPost](#customdevicetopost)

### api.CustomDevice.id.get
Gets a Device by it's ID


```js
smart_me.api.CustomDevice.id.get({
  "id": ""
}, context)
```

#### Input
* input `object`
  * id **required** `string`: The ID of the device

#### Output
* output [CustomDeviceToPost](#customdevicetopost)

### DeviceBySerial_Get
Gets a Device by it's Serial Number. The Serial is the part before the "-".


```js
smart_me.DeviceBySerial_Get({
  "serial": 0
}, context)
```

#### Input
* input `object`
  * serial **required** `integer`: The Serial Number of the device

#### Output
* output [Device](#device)

### api.Devices.get
Gets all Devices


```js
smart_me.api.Devices.get(null, context)
```

#### Input
*This action has no parameters*

#### Output
* output `array`
  * items [Device](#device)

### Devices_Post
Creates or updates a Device or updates it's values. 
            For a new device leave the ID empty. To create a device you have to set the DeviceEnergyType.
            To update values, add the ID of the device and the values you like to set.  (See the Data Type Model for more Information)


```js
smart_me.Devices_Post({
  "newDevice": {}
}, context)
```

#### Input
* input `object`
  * newDevice **required** [DeviceToPost](#devicetopost)

#### Output
* output [DeviceToPost](#devicetopost)

### api.Devices.id.get
Gets a Device by it's ID


```js
smart_me.api.Devices.id.get({
  "id": ""
}, context)
```

#### Input
* input `object`
  * id **required** `string`: The ID of the device

#### Output
* output [Device](#device)

### Devices_Put
Updates the On/Off Switch on a device
            For new implementations please use the "actions" command


```js
smart_me.Devices_Put({
  "id": "",
  "switchState": true
}, context)
```

#### Input
* input `object`
  * id **required** `string`: The ID of the device
  * switchState **required** `boolean`: The new state of the switch
  * switchNumber `integer`: The number of the switch if there are multiple (1 for L1, 3 for L3)

#### Output
* output [Object](#object)

### DevicesByEnergy_Get
Gets all Devices for an Energy Type


```js
smart_me.DevicesByEnergy_Get({
  "meterEnergyType": ""
}, context)
```

#### Input
* input `object`
  * meterEnergyType **required** `string` (values: MeterTypeUnknown, MeterTypeElectricity, MeterTypeWater, MeterTypeGas, MeterTypeHeat, MeterTypeHCA, MeterTypeAllMeters, MeterTypeTemperature, MeterTypeMBusGateway, MeterTypeRS485Gateway, MeterTypeCustomDevice, MeterTypeCompressedAir, MeterTypeSolarLog, MeterTypeVirtualMeter)

#### Output
* output `array`
  * items [Device](#device)

### DevicesBySubType_Get
Gets all Devices by it's Sub Type (e.g. E-Charging Station)


```js
smart_me.DevicesBySubType_Get({
  "meterSubType": ""
}, context)
```

#### Input
* input `object`
  * meterSubType **required** `string` (values: MeterSubTypeUnknown, MeterSubTypeCold, MeterSubTypeHeat, MeterSubTypeChargingStation, MeterSubTypeElectricity, MeterSubTypeWater, MeterSubTypeGas, MeterSubTypeElectricityHeat, MeterSubTypeTemperature)

#### Output
* output `array`
  * items [Device](#device)

### Folder_Get
Gets the Values for a folder or a meter


```js
smart_me.Folder_Get({
  "id": ""
}, context)
```

#### Input
* input `object`
  * id **required** `string`

#### Output
* output [FolderData](#folderdata)

### MBus_Post
M-BUS API: Adds data of a M-BUS Meter to the smart-me Cloud.
            Just send us the M-BUS Telegram (RSP_UD) and we will do the Rest.


```js
smart_me.MBus_Post({
  "mbusData": {}
}, context)
```

#### Input
* input `object`
  * mbusData **required** [MBusData](#mbusdata)

#### Output
* output [Object](#object)

### MeterFolderInformation_Post
Sets the Name of a Meter or a Folder


```js
smart_me.MeterFolderInformation_Post({
  "meterFolderInformation": {}
}, context)
```

#### Input
* input `object`
  * meterFolderInformation **required** [MeterFolderInformationToPost](#meterfolderinformationtopost)

#### Output
*Output schema unknown*

### MeterFolderInformation_Get
Beta: Gets the General Information for a Meter or a Folder


```js
smart_me.MeterFolderInformation_Get({
  "id": ""
}, context)
```

#### Input
* input `object`
  * id **required** `string`

#### Output
* output [MeterFolderInformation](#meterfolderinformation)

### MeterValues_Get
Gets the Values for a Meter at a given Date. The first Value found before the given Date is returned.


```js
smart_me.MeterValues_Get({
  "id": "",
  "date": ""
}, context)
```

#### Input
* input `object`
  * id **required** `string`
  * date **required** `string`

#### Output
* output [DeviceInPast](#deviceinpast)

### SignUp_Post
Sign up a new User.
            The sign up is done on the smart-me Cloud.


```js
smart_me.SignUp_Post({
  "signUpData": {}
}, context)
```

#### Input
* input `object`
  * signUpData **required** [SignUpData](#signupdata)

#### Output
* output [User](#user)

### User_Get
Gets the informations for the user.


```js
smart_me.User_Get(null, context)
```

#### Input
*This action has no parameters*

#### Output
* output [User](#user)

### Values_Get
Gets all (last) values of a device


```js
smart_me.Values_Get({
  "id": ""
}, context)
```

#### Input
* input `object`
  * id **required** `string`: The ID of the device

#### Output
* output [ValuesData](#valuesdata)

### ValuesInPast_Get
Gets the Values for a device at a given Date. The first Value found before the given Date is returned.


```js
smart_me.ValuesInPast_Get({
  "id": "",
  "date": ""
}, context)
```

#### Input
* input `object`
  * id **required** `string`: The ID of the device
  * date **required** `string`: the date of the value

#### Output
* output [ValuesData](#valuesdata)

### ValuesInPastMultiple_Get
Gets multiple values of a device. This call needs a smart-me professional licence.


```js
smart_me.ValuesInPastMultiple_Get({
  "id": "",
  "startDate": "",
  "endDate": "",
  "interval": 0
}, context)
```

#### Input
* input `object`
  * id **required** `string`: The ID of the device
  * startDate **required** `string`: The date when the first value should start
  * endDate **required** `string`: The date when the last value should start
  * interval **required** `integer`: The interval in minutes betwenn the values. 0 means as fast as possible. Only 1000 values can be get in one call.

#### Output
* output `array`
  * items [ValuesData](#valuesdata)

### VirtualBillingMeterActive_Get
Beta: Gets all active virtual meters.


```js
smart_me.VirtualBillingMeterActive_Get(null, context)
```

#### Input
*This action has no parameters*

#### Output
* output `array`
  * items [Device](#device)

### VirtualBillingMeterActive_Post
Beta: Virtual Meter API: Activates a Meter and add the Consumption to a Virtual Meter assosiated with the User.


```js
smart_me.VirtualBillingMeterActive_Post({
  "meterToActivate": {}
}, context)
```

#### Input
* input `object`
  * meterToActivate **required** [VMeterToActivate](#vmetertoactivate)

#### Output
* output [Device](#device)

### VirtualBillingMeterDeactivate_Post
Beta: Virtual Meter API: Deactivates a Virtual Meter.


```js
smart_me.VirtualBillingMeterDeactivate_Post({
  "meterToDeactivate": {}
}, context)
```

#### Input
* input `object`
  * meterToDeactivate **required** [VMeterToDeactivate](#vmetertodeactivate)

#### Output
* output [Object](#object)

### VirtualBillingMeters_Get
Beta: Gets all Meters available to activate as a Virtual Meter.


```js
smart_me.VirtualBillingMeters_Get(null, context)
```

#### Input
*This action has no parameters*

#### Output
* output `array`
  * items [Device](#device)

### VirtualMeterCalculateFormula_Get
Calculates a virtual meter from a formula.
            
            A meter is coded as ID("METERID")
            Ariphmetical operators:
             ()  parentheses;  
             +   plus (a + b); 
             -  minus (a - b); 
             *  multiplycation symbol (a * b); 
             /  divide symbol (a / b); 
            Example: (ID("63ac09cb-4e5f-4f3e-bd27-ad8c30bdfc0c") + ID("0209555e-9dc4-4e84-a166-a864488b4b12")) * 2


```js
smart_me.VirtualMeterCalculateFormula_Get({
  "formula": ""
}, context)
```

#### Input
* input `object`
  * formula **required** `string`

#### Output
* output [Device](#device)

### api.VirtualTariff.get
Gets all Virtual Tariffs of a user


```js
smart_me.api.VirtualTariff.get(null, context)
```

#### Input
*This action has no parameters*

#### Output
* output `array`
  * items [VirtualTariffsOfFolder](#virtualtariffsoffolder)

### api.VirtualTariff.id.get
Gets all virtual tariffs of a folder


```js
smart_me.api.VirtualTariff.id.get({
  "id": ""
}, context)
```

#### Input
* input `object`
  * id **required** `string`: The ID of the Folder

#### Output
* output [VirtualTariffsOfFolder](#virtualtariffsoffolder)

### VirtualTariffConsumption_Get
Gets the consumption of a folder with a virtuall tariffs.


```js
smart_me.VirtualTariffConsumption_Get({
  "folderId": "",
  "startDate": "",
  "endDate": ""
}, context)
```

#### Input
* input `object`
  * folderId **required** `string`: The ID of the Folder
  * startDate **required** `string`: The start date (UTC)
  * endDate **required** `string`: The end date (UTC)

#### Output
* output `array`
  * items [VirtualTariffConsumptionData](#virtualtariffconsumptiondata)



## Definitions

### AccessTokenToPut
* AccessTokenToPut `object`: Container Class for the Put action of an Access Token
  * CardId `integer`: The ID of the Card
  * UserId `integer`: The ID of the User. The credentials provided must have permission to edit the user.

### ActionInformation
* ActionInformation `object`: The Information about an Action of a device
  * ActionType `string` (values: OnOffAction, AnalogAction): The Type of this action.
  * MaxValue `number`: The maximum value of this action (e.g. for an AnalogAction)
  * MinValue `number`: The minimum value of this action (e.g. for an AnalogAction)
  * Name `string`: The Name of this action
  * ObisCode `string`: The Obis Code of this action. This is used as ID.

### ActionToPost
* ActionToPost `object`: Container Class for an action to post
  * Actions `array`: List with all Actions for this device
    * items [ActionToPostItem](#actiontopostitem)
  * DeviceID `string`: The ID of the Device

### ActionToPostItem
* ActionToPostItem `object`: Container class for an action item
  * ObisCode `string`: The ObisCode (ID) of the Action
  * Value `number`: The Value to Post

### CustomDeviceToPost
* CustomDeviceToPost `object`: Container Class for the Web API
  * Id `string`: The ID of the device
  * Name `string`: The Name of the Device
  * Serial `integer`: The Serial number
  * ValueDate `string`: The Date of the Value (in UTC). If this is null the Server Time is used.
  * Values `array`: The Values of the custom Device
    * items [CustomDeviceValues](#customdevicevalues)

### CustomDeviceValues
* CustomDeviceValues `object`: Container Class for the Custom Device Values
  * Name `string`: The Name of the Value.
  * Value `number`: The Value

### Device
* Device `object`: Container Class for the Web API
  * ActivePower `number`: The Actvie Power or current flow rate
  * ActivePowerL1 `number`: The Actvie Power Phase L1
  * ActivePowerL2 `number`: The Actvie Power Phase L2
  * ActivePowerL3 `number`: The Actvie Power Phase L3
  * ActivePowerUnit `string`: The Unit of the Active Power Value
  * ActiveTariff `integer`: The Number of the Active Tariff
  * AnalogOutput1 `integer`: The analog output number 1 (PWM signal) (0 - 32183)
  * AnalogOutput2 `integer`: The analog output number 2 (PWM signal) (0 - 32183)
  * CounterReading `number`: The Meter Counter Reading (Total Energy used)
  * CounterReadingExport `number`: The Meter Counter Reading only export
  * CounterReadingImport `number`: The Meter Counter Reading only import
  * CounterReadingT1 `number`: The Meter Counter Reading Tariff 1
  * CounterReadingT2 `number`: The Meter Counter Reading Tariff 2
  * CounterReadingT3 `number`: The Meter Counter Reading Tariff 3
  * CounterReadingT4 `number`: The Meter Counter Reading Tariff 4
  * CounterReadingUnit `string`: The Unit of the Counter Reading
  * Current `number`: The Current (in A)
  * CurrentL1 `number`: The Current Phase L1 (in A)
  * CurrentL2 `number`: The Current Phase L2 (in A)
  * CurrentL3 `number`: The Current Phase L3 (in A)
  * DeviceEnergyType `string` (values: MeterTypeUnknown, MeterTypeElectricity, MeterTypeWater, MeterTypeGas, MeterTypeHeat, MeterTypeHCA, MeterTypeAllMeters, MeterTypeTemperature, MeterTypeMBusGateway, MeterTypeRS485Gateway, MeterTypeCustomDevice, MeterTypeCompressedAir, MeterTypeSolarLog, MeterTypeVirtualMeter): The Energy Type of this device
  * DigitalInput1 `boolean`: The digital input number 1
  * DigitalInput2 `boolean`: The digital input number 2
  * DigitalOutput1 `boolean`: The digital output number 1
  * DigitalOutput2 `boolean`: The digital output number 2
  * FamilyType `string` (values: MeterFamilyTypeUnknown, MeterFamilyTypeSmartMeConnectV1, MeterFamiliyTypeSmartMeMeter, MeterFamiliyTypeSmartMeMeterWithSwitch, MeterFamilyTypeMBusGatewayV1, MeterFamilyTypeRS485GatewayV1, MeterFamilyTypeKamstrupModule, MeterFamilyTypeSmartMe3PhaseMeter80A, MeterFamilyTypeSmartMe3PhaseMeter32A, MeterFamilyTypeSmartMe3PhaseMeterTransformer, MeterFamilyTypeLandisGyrModule, MeterFamilyTypeRestApiMeter, MeterFamilyTypeVirtualBillingMeter): The Family Type of the device.
  * Id `string`: The ID of the device
  * Name `string`: The Name of the Device
  * PowerFactor `number`: The Power Factor (cos phi). Range: 0 - 1
  * PowerFactorL1 `number`: The Power Factor (cos phi) Phase L1. Range: 0 - 1
  * PowerFactorL2 `number`: The Power Factor (cos phi) Phase L2. Range: 0 - 1
  * PowerFactorL3 `number`: The Power Factor (cos phi) Phase L3. Range: 0 - 1
  * Serial `integer`: The Serial number
  * SwitchOn `boolean`: Flag if the Switch is on on this device.
  * SwitchPhaseL1On `boolean`: Flag if the Phase L1 is on on this device.
  * SwitchPhaseL2On `boolean`: Flag if the Phase L2 is on on this device.
  * SwitchPhaseL3On `boolean`: Flag if the Phase L3 is on on this device.
  * Temperature `number`: The Temperature (in degree celsius)
  * ValueDate `string`: Time of last successful connection the the smart-me Cloud.
  * Voltage `number`: The Voltage (in V)
  * VoltageL1 `number`: The Voltage Phase L1 (in V)
  * VoltageL2 `number`: The Voltage Phase L2 (in V)
  * VoltageL3 `number`: The Voltage Phase L3 (in V)

### DeviceInPast
* DeviceInPast `object`: Container Class for the Web API. Conatinas the MeterValues in the Past
  * CounterReading `number`: The Meter Counter Reading (Total Energy used)
  * CounterReadingExport `number`: The Meter Counter Reading Export
  * CounterReadingExportT1 `number`: The Meter Counter Reading Export Tariff 1
  * CounterReadingExportT2 `number`: The Meter Counter Reading Export Tariff 2
  * CounterReadingExportT3 `number`: The Meter Counter Reading Export Tariff 3
  * CounterReadingExportT4 `number`: The Meter Counter Reading Export Tariff 4
  * CounterReadingImport `number`: The Meter Counter Reading Import
  * CounterReadingImportT1 `number`: The Meter Counter Reading Import Tariff 1
  * CounterReadingImportT2 `number`: The Meter Counter Reading Import Tariff 2
  * CounterReadingImportT3 `number`: The Meter Counter Reading Import Tariff 3
  * CounterReadingImportT4 `number`: The Meter Counter Reading Import Tariff 4
  * CounterReadingT1 `number`: The Meter Counter Reading Tariff 1
  * CounterReadingT2 `number`: The Meter Counter Reading Tariff 2
  * CounterReadingT3 `number`: The Meter Counter Reading Tariff 3
  * CounterReadingT4 `number`: The Meter Counter Reading Tariff 4
  * CounterReadingUnit `string`: The Unit of the Counter Reading
  * Date `string`: The Date of the Values
  * Id `string`: The ID of the device
  * Serial `integer`: The Serial number

### DeviceToPost
* DeviceToPost `object`: Container Class for the Web API
  * ActivePower `number`: The Active Power or current flow rate. In kW or m3/h
  * CounterReading `number`: The Meter Counter Reading (Total Energy used) in kWh or m3.
  * CounterReadingT1 `number`: The Meter Counter Reading Tariff 1 in kWh or m3.
  * CounterReadingT2 `number`: The Meter Counter Reading Tariff 2 in kWh or m3.
  * DeviceEnergyType `string` (values: MeterTypeUnknown, MeterTypeElectricity, MeterTypeWater, MeterTypeGas, MeterTypeHeat, MeterTypeHCA, MeterTypeAllMeters, MeterTypeTemperature, MeterTypeMBusGateway, MeterTypeRS485Gateway, MeterTypeCustomDevice, MeterTypeCompressedAir, MeterTypeSolarLog, MeterTypeVirtualMeter): The Energy Type of this device
  * Id `string`: The ID of the device
  * MeterSubType `string` (values: MeterSubTypeUnknown, MeterSubTypeCold, MeterSubTypeHeat, MeterSubTypeChargingStation, MeterSubTypeElectricity, MeterSubTypeWater, MeterSubTypeGas, MeterSubTypeElectricityHeat, MeterSubTypeTemperature): The Sub Type of this Meter.
  * Name `string`: The Name of the Device
  * Serial `integer`: The Serial number
  * Temperature `number`: The Temperature (in degree celsius)
  * ValueDate `string`: The Date of the Value (in UTC). If this is null the Server Time is used.

### FolderData
* FolderData `object`: Container class for the folder API
  * ElectricityCounterValue `number`: The Counter values for electricity (kWh)
  * ElectricityPower `number`: The Power for electricity (kW)
  * GasCounterValue `number`: The Counter values for Gas (m3)
  * GasFlowRate `number`: The Flow Rate for Gas (m3/h)
  * HeatCounterValue `number`: The Counter values for Heat (kWh)
  * HeatPower `number`: The Power for Heat (kW)
  * WaterCounterValue `number`: The Counter values for Water (m3)
  * WaterFlowRate `number`: The Flow Rate for Water (m3/h)

### InputInformation
* InputInformation `object`: Informations about the Inputs of a Meter or Folder
  * Name `string`: The Name of the Input
  * Number `integer`: The Number of this Input. Use this as ID to switch it on or off.

### MBusData
* MBusData `object`
  * Date `string`: The Date of the M-BUS Telegram Readout (in UTC). If this is null the Server Time is used.
  * Telegram `string`: The M-BUS Telegram as Hex string. 

### MeterFolderInformation
* MeterFolderInformation `object`: Container Class for the Web API
  * FirmwareVersion `integer`: The Firmware Version of a Meter
  * HardwareVersion `integer`: The Hardware Version of a Meter.
  * InputInformations `array`: Informations about the available Inputs
    * items [InputInformation](#inputinformation)
  * IsFolder `boolean`: Flag if it's a Folder or a Meter
  * Name `string`: Name of the Meter or Folder
  * OutputInformations `array`: Informations about the available Outputs
    * items [OutputInformation](#outputinformation)

### MeterFolderInformationToPost
* MeterFolderInformationToPost `object`: Container for a Meter or Folder Information to Post
  * Id `string`: The ID of the device or folder
  * Name `string`: Name of the Meter or Folder

### Object
* Object `object`

### OutputInformation
* OutputInformation `object`: Informations about the Outputs of a Meter or Folder
  * ActionType `string` (values: OnOffAction, AnalogAction): The type of the Output
  * Name `string`: The Name of the Output
  * Number `integer`: The Number of this Output. Use this as ID to switch it on or off.
  * ObisCode `string`: The Obis Code for this Output

### SignUpData
* SignUpData `object`: Container for the Sign UP API
  * Email `string`: The Email Address to register
  * Password `string`: The Password to register

### User
* User `object`: Container Class for the Web API
  * ChildUsers `array`: The Users created by this users.
    * items [User](#user)
  * Email `string`: The EMail Address of the User
  * Id `integer`: The ID of the User
  * IsAdmin `boolean`: Flag if this User is an Admin User
  * Username `string`: The Username of the User

### VMeterToActivate
* VMeterToActivate `object`: Actives a virtual Meter
  * SerialNumber `string`: The Serialnumber of the Meter to activate.

### VMeterToDeactivate
* VMeterToDeactivate `object`: Deactivates a virtual Meter
  * ID `string`: The ID of the Virtual meter to deactivate

### ValueData
* ValueData `object`: API Container for a (Device) Value
  * Obis `string`: The Obis code of this value. 
  * Value `number`: The Value

### ValuesData
* ValuesData `object`: API Container for a Meter Value
  * Date `string`: The Date of the Value
  * DeviceId `string`: The ID of the device
  * Values `array`: All values
    * items [ValueData](#valuedata)

### VirtualTariff
* VirtualTariff `object`: Container class for the virtual tariffs
  * Factor `number`: Says how many of the active power is used in this tariff. This is calculated from the last meter values.
  * Id `string`: The ID of the virtual tariff
  * Name `string`: The name of this tariff
  * Type `string` (values: Battery, Solar, Normal): The Type of the tariff
  * Unit `string`: The Unit of this value
  * Value `number`: The Counter Value of this tariff

### VirtualTariffConsumptionData
* VirtualTariffConsumptionData `object`: Container class for the virtual tariff consumption
  * Consumption `number`: The consumption (e.g. kWh) of this tariff
  * Currency `string`: The currency of the price
  * Name `string`: The Name of this virtual tariff
  * Price `number`: The price of the energy in this timerange
  * TariffType `string` (values: Battery, Solar, Normal): The type of the virtual tariff (e.g. solar)

### VirtualTariffsOfFolder
* VirtualTariffsOfFolder `object`: Container class for a Virtual Tariff
  * Date `string`: The DateTime (UTC) of this virtual tarfifs
  * FolderId `string`: The ID of the Folder
  * Name `string`: The name of this folder
  * VirtualTariffs `array`: The Name of the Virtual Tariff
    * items [VirtualTariff](#virtualtariff)


