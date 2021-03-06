---                             
title: "IoTHubClient_LL_SetDeviceTwinCallback function reference | Microsoft Docs" 
titleSuffix: "Azure IoT C SDK"            
description: "This is the function reference page for the IoTHubClient_LL_SetDeviceTwinCallback() function in the Azure IoT C SDK. This SDK is used with Azure IoT Hub and Azure IoT Hub Device Provisioning Service"            
manager: timlt                 
author: wesmc7777              
ms.author: wesmc               
ms.date: 10/24/2018                    
ms.service: "iot-hub"             
ms.custom: ""                
ms.topic: "reference"        
---                            

# IoTHubClient_LL_SetDeviceTwinCallback()

This API specifies a call back to be used when the device receives a desired state update.

## Syntax

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_client_ll.h](../iothub-client-ll-h.md)"  
```C
IOTHUB_CLIENT_RESULT IoTHubClient_LL_SetDeviceTwinCallback(
  IOTHUB_CLIENT_LL_HANDLE             iotHubClientHandle,
  IOTHUB_CLIENT_DEVICE_TWIN_CALLBACK  deviceTwinCallback,
  void *                              userContextCallback
);
```

## Parameters
* `iotHubClientHandle` The handle created by a call to the create function. 

* `deviceTwinCallback` The callback specified by the device client to be used for updating the desired state. The callback will be called in response to patch request send by the IoTHub services. The payload will be passed to the callback, along with two version numbers:

* Desired:

* LastSeenReported: 

* `userContextCallback` User specified context that will be provided to the callback. This can be NULL.

**NOTE:** The application behavior is undefined if the user calls the [IoTHubClient_LL_Destroy](../iothub-client-ll-h/iothubclient-ll-destroy.md) function from within any callback.

## Return Value
IOTHUB_CLIENT_OK upon success or an error code upon failure.

