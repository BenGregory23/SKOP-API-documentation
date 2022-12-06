# Doctor
The doctor can interact with the patient and modify the patient's audio.<br>
To create an instance of the `Doctor` class, you must pass in the following parameters:

`Doctor(API_KEY_WEMED, SESSION_ID)`

| Parameter | Description                                    |
|-----------|------------------------------------------------|
| API_KEY   | Your WeMed API KEY.                            |
| ROOM_ID   | A room id in which you want the patient to be. |


> **Note** : To get the API_KEY, TOKEN & SESSION_ID, you need to create an account on [Vonage](https://www.vonage.com/).

```javascript  
let doctor = await SkopAPI.Doctor.init(apiKey, roomId);
```  

> **Note** : `await` is needed to wait for the API to be ready.


After the instance is created, any Patient instance with the same `ROOM_ID` will be able to communicate with the doctor.

## Methods

| Name                                                            | Description                                                           |
|-----------------------------------------------------------------|-----------------------------------------------------------------------|
| [**disconnect()**](#disconnect)                                 | Disconnects the doctor from the session.                              |
| [**mute(boolean)**](#mute)                                      | Mutes the doctor.                                                     |
| [**useSkop()**](#useskop)                                       | Filters the Patient's audio according to the current focus.           |
| [**stopUsingSkop()**](#stopusingskop)                           | Stops the audio filtering.                                            |
| [**setCurrentFocus(string)**](#setcurrentfocus)                 | Sets the current focus to the given string.                           |
| [**getCurrentFocus(string)**](#getcurrentfocus) &rarr; *string* | Gets the current focus.                                               |
| [**setGain(value)**](#setgain)                                  | Changes the gain level of the modified audio coming from the patient. |
| [**useAR(boolean)**](#usear)                                    | Shows to the patient the focus on his own body.                       |
| [**useMonoyer(boolean)**](#usemonoyer)                          | Activates/Deactivates the the monoyer eyesight test.                  |
| [**getMediaDevices()**](#getMediaDevices)             | Returns all the available media devices. |
| [**setInputDevice(string)**](#setInputDevice(string)) | Sets the current microphone of the user. |


### Disconnect

Disconnects the doctor from the session.

```javascript
doctor.disconnect();
```

### Mute

Mutes the doctor.

Parameter:
- `state`: `true` to mute the doctor, `false` to unmute the doctor.

```javascript
doctor.mute(state);
```

### useSkop
`useSkop` filters the Patient's audio according to the given focus. If a **new** focus is set while this method is called, the filter will be **automatically updated**.

```javascript
doctor.useSkop();
```

> **Note** : The focus to be used must be set beforehand using [`setCurrentFocus`](#setcurrentfocus).


### stopUsingSkop

`stopUsingSkop` stops the audio filtering and resets the Patient's audio to normal. The Doctor and the Patient can now communicate freely.

```javascript
doctor.stopUsingSkop();
```

### setCurrentFocus

`setCurrentFocus` sets the current focus to the given string. The focus must be part of the [list of focuses available].(focus.md)

```javascript
doctor.setCurrentFocus(string);
```

### getCurrentFocus

`getCurrentFocus` returns the current focus as a string.

```javascript
let variable = doctor.getCurrentFocus();
```

### setGain

`setGain` changes the gain level of the modified audio coming from the patient.
The value can be **positive** or **negative**. <br>
If the value is positive, the audio will be amplified, if it is negative, the audio will be attenuated.

Parameter: 
- `value`: The value to be used. It must be a number.

```javascript
//Here we are changing the gain level of the audio to 10
doctor.setGain(10);
```

### useAR 

`useAR` uses an augmented reality algorithm to show to the patient the focus on his own body. When toggled on for the first time there is a short delay before the augmented reality algorithm starts. Afterwards toggling on/off will be relatively fast.

 Parameter : 
 - boolean : true to use the AR algorithm, false to stop using it.

```javascript
doctor.useAR(true);
```




### useMonoyer

`useMonoyer` activates/deactivates the the monoyer eyesight test.

Parameter : 
- boolean : true to activate the monoyer eyesight test, false to deactivate it.
    
```javascript
doctor.useMonoyer(true);
```


### getMediaDevices

Returns all the available media devices.

> **Note** : To see the labels of the devices this method has to be called after the user has given permission to use a microphone. This method is asynchronous and returns a `Promise`.

```js
doctor.getMediaDevices();
```

### setInputDevice(string)

Sets the current microphone of the user.

Parameter:
- `deviceId`: The id of the microphone to use as a string.

```js
doctor.setInputDevice(deviceId);
```










