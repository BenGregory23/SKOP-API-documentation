
# Getting started

## Loading the library

### Script 
You can start using Halfred API by simply adding our script directly to your html file.

```html
<script src="SkopAPI.js"></script>

```
[Download here]("https://ufile.io/f/s72cu")

### Install the package

You can also install the package with npm.

    $ npm install halfred-api

## Initialization

To start using the API you must first create an instance of a `Doctor` and a `Patient`. To do so you must call the `init` method of each class. <br>
The `init` method takes two parameters: the API KEY and the ROOM ID.  The API KEY is the key you got from WeMed. The ROOM ID is the id of the room you want to use.

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

When the Doctor wants to listen to a focus he has to set a focus on the patient with [`setCurrentFocus`](doctor.md#setcurrentfocus). <br> The focus is a string that will be sent to the patient.
Then the Patient's audio will be filtered according to the focus.

```javascript
doctor.setCurrentFocus("Mitral");
```
