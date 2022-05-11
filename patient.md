# Patient

The patient is the user who has the Skop and will be using it. He does not have any methods as it is the doctor leading the call.
## Patient constructor


To create an instance of the `Patient` class, you must pass in the following parameters:

| Parameter  | Description            |
|------------|------------------------|
| API_KEY    | Your Vonage API key.   |
| API_SECRET | Your Vonage API secret |
| SESSION_ID | A Vonage Session id    |

`Patient(API_KEY, API_SECRET, SESSION_ID)`

> **Note** : To get the API_KEY, TOKEN & SESSION_ID, you need to create an account on [Vonage](https://www.vonage.com/)

```javascript  
let patient = new SkopAPI.Patient(apiKey, token, sessionId);
```  

> **Note** : `SkopAPI` is the name of the library.

After the instance is created, any Doctor instance with the same `SESSION_ID` will be able to communicate with the patient.
