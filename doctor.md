# Doctor
The doctor can interact with the patient and modify the patient's audio.<br>
To create an instance of the `Doctor` class, you must pass in the following parameters:

`Doctor(API_KEY_WEMED, SESSION_ID)`

| Parameter | Description                                    |
|-----------|------------------------------------------------|
| API_KEY   | Your WeMed API KEY.                            |
| ROOM_ID   | A room id in which you want the patient to be. |


> **Note** : To get the API_KEY, TOKEN & SESSION_ID, you need to create an account on [Vonage](https://www.vonage.com/)

```javascript  
let doctor = await HalfredAPI.Doctor.init(apiKey, roomId);
```  

> **Note** : `await` is needed to wait for the API to be ready.


After the instance is created, any Patient instance with the same `ROOM_ID` will be able to communicate with the doctor.

## Methods

| Name                                            | Description                                                           |
|-------------------------------------------------|-----------------------------------------------------------------------|
| [**disconnect()**](#disconnect)                 | Disconnects the doctor from the session.                              |
| [**mute(boolean)**](#mute)                      | Mutes the doctor.                                                     |
| [**useSkop()**](#useskop)                       | Filters the Patient's audio according to the current focus.           |
| [**stopUsingSkop()**](#stopusingskop)           | Stops the audio filtering.                                            |
| [**setCurrentFocus(string)**](#setcurrentfocus) | Sets the current focus to the given string.                           |
| [**getCurrentFocus(string)**](#getcurrentfocus) | Gets the current focus.                                               |
| [**setGain(value)**](#setgain)                  | Changes the gain level of the modified audio coming from the patient. |
| [**useAR(boolean)**](#usear)                    | Shows to the patient the focus on his own body.                       |


### Disconnect

Disconnect the doctor from the session.

```javascript
doctor.disconnect();
```

### Mute

Mute the doctor.

```javascript
doctor.mute(boolean);
```

### useSkop
`useSkop` will filter the Patient's audio according to the given focus. <br>


```javascript
doctor.useSkop();
```

> **Note** : The focus to be used must be set before using [`setCurrentFocus`](#setcurrentfocus).



### stopUsingSkop

`stopUsingSkop` will stop the audio filtering.

```javascript
doctor.stopUsingSkop();
```

> **Note** : It is the same method used to listen to a zone but without any parameter.

### setCurrentFocus

`setCurrentFocus` will set the current focus to the given string.

```javascript
doctor.setCurrentFocus(string);
```

### getCurrentFocus

`getCurrentFocus` will get the current focus.

```javascript
let variable = doctor.getCurrentFocus();
```


### setGain

`setGain` changes the gain level of the modified audio coming from the patient.
The value can be **positive** or **negative**. <br>
If the value is positive, the audio will be amplified, if it is negative, the audio will be attenuated.

```javascript
//Here we are changing the gain level of the audio to 10
doctor.setGain(10);
```


### useAR 

`useAR` will use an AR algorithm to show to the patient the focus on his own body.

 Parameter : 
 - boolean : true to use the AR algorithm, false to stop using it.

```javascript
doctor.useAR(true);
```















