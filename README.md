##### A number guessing game project that allows users to speak their guesses using a web browser's speech recognition service. The code retrieves an HTML element for displaying messages to the user, generates a random number, sets up the speech recognition service, and creates functions for handling user input and checking whether the user's spoken input is a valid number. The code also sets up event listeners for the speech recognition service and for the "Play Again" button.
<hr>

#### Js file
```window.SpeechRecognition = window.SpeechRecognition || window.webkitSpeechRecognition;``` -> sets up the speech recognition service, which is used to capture the user's spoken input. <br>
```let recognition = new window.SpeechRecognition();``` -> creates a new instance of the speech recognition service. <br>
```recognition.start();``` -> starts the speech recognition service. <br>
```function onSpeak(e){ ... }``` -> function is called whenever the speech recognition service detects speech. It extracts the user's spoken input from the event object ``e```, and then passes it to the ```writeMessage()``` and ```checkNumber()``` functions. <br>
```recognition.addEventListener('result', onSpeak)``` -> sets up an event listener that calls the ```onSpeak()``` function whenever the speech recognition service detects speech. <br>

```recognition.addEventListener('end', () => recognition.start())``` -> sets up an event listener that restarts the speech recognition service whenever it stops. <br>

```document.body.addEventListener('click', (e) => { ... })``` -> sets up an event listener that listens for clicks on the "Play Again" button and reloads the page when it is clicked.
