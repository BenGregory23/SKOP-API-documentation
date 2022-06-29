# Sample code

If you want to use the API, here are some examples of how to use it. Each example is a snippet of code either for the patient or the doctor.

### Create a new instance of the Patient class - *Patient*

```js
let patient = await HalfredAPI.Patient.init(apiKey, roomId);
```

### Setting the current focus - *Doctor*

When the Doctor wants to listen to a focus he has to set a focus on the patient. To do so you can use a select box : 

```html
<select id="select">
    <option value="Mitral">Mitral</option>
    <option value="Aortic">Aortic</option>
    <option value="Pulmonary">Pulmonary</option>
    <option value="Tricuspid">Tricuspid</option>
    <option value="ANT1L">ANT1L</option>
</select>
```

Then using javascript you can set the focus each time the user selects a new option :

```javascript
let focus = document.getElementById("select");

focus.addEventListener("change", function(){
    // on change of focus, set the focus
    doctor.setCurrentFocus(value);
});
```

### Filtering the audio - *Doctor*

When a focus is set, the Doctor can start filtering the audio. This can be done with 2 buttons : 

- `start` : When the button is clicked, the Doctor will start filtering the audio.
- `stop` : When the button is clicked, the Doctor will stop filtering the audio.

```html
<button id="start">Start filtering</button>
<button id="stop">Stop filtering</button>
```

Then using javascript you can start and stop the filtering :

```javascript
let start = document.getElementById("start");
let stop = document.getElementById("stop");
    
start.addEventListener("click", function(){
    // on click of start, start filtering
    doctor.useSkop();
});
    
stop.addEventListener("click", function(){
    // on click of stop, stop filtering
    doctor.stopUsingSkop();
});
```



### Using augmented reality - *Doctor*

When using augmented reality it can be useful to be able to toggle it on/off. To do so a possibility is to have a toggle button, then in javascript you can listen to the state of the button and call `useAR(boolean)` on thedoctor instance.

```html
<button id="AR">Toggle AR</button>
```

```js
let toggleAR = document.getElementById('AR');

toggleAR.addEventListener("change", (e) =>{
    if (e.target.checked) {
        doctor.useAR(true);
    } else {
        doctor.useAR(false)
    }
})
```





