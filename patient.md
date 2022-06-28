# Patient
The patient is the user who has a Skop and will be using it.

To create an instance of the `Patient` class, you must pass in the following parameters:

`Patient(API_KEY, SESSION_ID)`


| Parameter     | Description                                    |
|---------------|------------------------------------------------|
| API_KEY_WEMED | Your WeMed API KEY.                            |
| ROOM_ID       | A room id in which you want the patient to be. |


> **Note** : To get an API KEY, please go [here](https://www.wemed.fr/inscription-api-skop)

```javascript  
let patient = await HalfredAPI.Patient.init(apiKey, roomId);
```  

> **Note** : `await` is needed to wait for the API to be ready.

After the instance is created, any Doctor instance with the same `ROOM_ID` will be able to communicate with the patient.

## Methods

| Name                            | Description                              |
|---------------------------------|------------------------------------------|
| [**disconnect()**](#disconnect) | Disconnects the doctor from the session. |
| [**mute(boolean)**](#mute)      | Mutes the doctor.                        |
| [**turnCamera()**](#turncamera) | Flips the camera of the patient.         |

### Disconnect 

Disconnect the patient from the session.
  
```js
patient.disconnect();
```

### Mute 

Mute the patient. 
    
```js
patient.mute(boolean);
```


### TurnCamera

 Flips the camera of the patient. Calling it again will flip the camera back.

```js
patient.turnCamera();
```



