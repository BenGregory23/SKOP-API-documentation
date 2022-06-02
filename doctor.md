# Doctor

The doctor can interact with the patient and modify the patient's audio.
## Constructor

To create an instance of the `Doctor` class, you must pass in the following parameters:

| Parameter  | Description            |
|------------|------------------------|
| API_KEY    | Your Vonage API key.   |
| API_SECRET | Your Vonage API secret |
| SESSION_ID | A Vonage Session id    |

`Doctor(API_KEY, API_SECRET, SESSION_ID)`

> **Note** : To get the API_KEY, TOKEN & SESSION_ID, you need to create an account on [Vonage](https://www.vonage.com/)

```javascript  
let doctor = new SkopAPI.Doctor(apiKey, token, sessionId);
```  

> **Note** : `SkopAPI` is the name of the library.


After the instance is created, any Patient instance with the same `SESSION_ID` will be able to communicate with the doctor.

## Methods

The Doctor class has methods that you can use to interact with the Skop API.


##### `skop(zone)` 
***

This method will modify the Patient's audio according to the given zone. <br>
The zone can be one of the following :

| Zone      | Category | Naming |
|-----------|----------| -------|
| Aortic    | Cardiac  | "Aortic" |
| Mitral    | Cardiac  | "Mitral" |
| Tricuspid | Cardiac  | "Tricuspid" |
| ...       | ...      | ...    |

```javascript
//Here we are filtering the audio to listen to the Aortic zone
doctor.skop("Aortic");
```

##### `skop()` 
***

The doctor can stop the audio filtering by calling this method , it will stop modifying the patient's audio.
<br>The patient and the doctor will be able to talk to each other.

```js
//Stops the audio filtering
doctor.skop();
```



> **Note** : It is the same method used to listen to a zone but without any parameter.

##### `setGain(gain)` 
***

This method changes the gain level of the modified audio coming from the patient.
The value can be **positive** or **negative**. <br>
If the value is positive, the audio will be amplified, if it is negative, the audio will be attenuated.

```javascript
//Here we are changing the gain level of the audio to 10
doctor.setGain(10);

```


##### `useAR(boolean)`
***
This method sets the `useAR` property of the Patient instance to the given value. <br>
When activated it will show to the patient the location of the zone on his own body.

```javascript
doctor.useAR(true);
```








