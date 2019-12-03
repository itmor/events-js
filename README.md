# Events-js ![](https://svgshare.com/i/GR1.svg)
Small library for creating and listening for js events
 ******
#### Browser support
###### IE 9+
###### Firefox 20+
###### Chrome 30+
 ******
#### Installation
Find and download the file from the repository
``
events-js/***/build/events.min.js
``

include library file in html
```html
<script src="events.min.js"></script>
```

#### Usage example
```javascript
const events = new Events();

let trigger = false;

events.add({
  triggered: () =>  {
    if (trigger === true) {
      return true;
     }
  }
});

function printText () {
  console.log('Еhe trigger worked!');
}

events.on('triggered', printText);
```

### Methods
| Method name | Description                    |
| ------------- | ------------------------------ |
| `.add(Object: eventsDescriptions)`      |  Adds event descriptions. It takes an object, the key is the name of the event, and its value should be a function that should return (true) when the event occurred. |
| `.remove(String: eventName)`   | Deletes the event description. Accepts the name of the event, clears all handlers that were bound via .on(). |
| `.on(String: eventName, Function: Callback, Boolean: onceMode)`     |Adds a listener. 1. Accepts the name of the event that was described using .add ().  2. Link to the function executed after the event.  3. Once mode, if true, then the listener will fire 1 time.|
| `.off(String: eventName, Function: Callback)`   | Removes all listeners. Accepts listener names and a callback function link. |
### DEV
```
$ git clone https://github.com/itmor/events-js.git
$ cd events-js/js
$ npm i
```

### Additionally
You can specify the event verification call speed in (ms)you can specify the event verification call speed in (ms).
 ******
```javascript
const events = new Events({
  workerCallInterval: 300
});
``` 
You can also use once mode so that the callback function that works only 1 time. 
Just pass the truth with the last argument when describing the event.
 ******
```javascript
events.add({
  triggered: () =>  {
    if (trigger === true) {
      return true;
     }
  }
}, true);
``` 
