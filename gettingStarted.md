
# Getting started

## Loading the library

### Script 
You can start using SKOP API by simply adding our script directly to your html file.


```html
<script src="https://cdn.jsdelivr.net/npm/skop-api/dist/SkopAPI.js"></script>
```

### Install the package

You can also install the package with npm.

    $ npm install skop-api

 > **Note** : The package is currently under development. It may not work as expected.

## Initialization

To start using the API you must first create an instance of a `Doctor` and a `Patient`. To do so you must call the `init` method of each class.
The `init` method takes two parameters: the API KEY and the ROOM ID.  The API KEY is the key you got from WeMed. The ROOM ID is the id of the room you want to use.

> **Note** : If you don't have an API KEY, please go [here](https://www.wemed.fr/inscription-api-skop) to get one.

Let's instantiate a `Doctor` in a html file.

```javascript
let doctor = await SkopAPI.Doctor.init(apiKey, 12);
```

Now we can instantiate a `Patient` in another html file.

    
```javascript
let patient = await SkopAPI.Patient.init(apiKey, 12);
```

The Doctor and the Patient, having the same ROOM ID, will be able to communicate with each other. You can now interact with the Doctor and the Patient by calling their methods.

## Filter the audio 

When the Doctor wants to listen to a focus he has to set a focus on the patient with [`setCurrentFocus`](doctor.md#setcurrentfocus). The focus is a string that will be sent to the patient.
Then the Patient's audio will be filtered according to the focus. Here is the [list of available focuses](focus.md).

```javascript
doctor.setCurrentFocus("Mitral");
```
Once the current focus is set you can call [`useSkop`](doctor.md#useskop) to start filtering the audio.

```javascript
doctor.useSkop();
```

> **Note** : Setting a new focus will automatically start filtering the audio for the this focus.

From there you can call [`stopUsingSkop`](doctor.md#stopusingskop) to stop the filtering.

```javascript
doctor.stopUsingSkop();
```


