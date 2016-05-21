# watson-html5-speech-recognition

A Library to provide speech recognition capability in browsers.

## Support
The library enables speech recognition support for any browser that includes support for either:

- [Web Speech API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Speech_API) **or**
- [Web Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API) + [getUserMedia](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/getUserMedia) support

If the browser does not support either of the above, then currently you're out of luck.


watson-html5-speech-recognition use Web Speech API when present and Watson Speech To Text service for all other (supported) cases.

Currently, the following are supported:

- Webkit speech recognition
	- Chrome
	- Safari
	
- Watson Speech to Text
	- Microsoft Edge
	- Firefox

## Prequisites

1. An instance of [Watson Speech To Text Service](https://console.ng.bluemix.net/catalog/services/speech-to-text/) (requires a [Bluemix](http://www.bluemix.net) account)
2. Watson Speech to Text Websocket server (provided. see **Example** section below)


## Install

```shell
npm install watson-html5-speech-recognition
```

## Usage
```javascript
speech.listen({
    onStart: function() {
        console.log('starting');
    },
    onResult: function(e) {
        console.log(e.text);
    },
    onError: function(e) {
        console.log('error', e);
    },
    onEnd: function(e) {
        console.log('end', e);
    }
});
```

## Example
The example contains a simple web front end, along with a backend web socket server that communicates with the Watson Speech To Text service

### Setup the example
Clone the example:

```shell
git clone https://github.com/cdimascio/watson-html5-speech-recognition
```

Navigate to the example root:

```shell
cd examples
```

Install dependencies:

```shell
npm install
```

Build the example:

```shell
npm compile
```

### Run the example:

Open `stt-token.js` to line 10 

Set `'<your-username>'` and `'<your-username>'` to match your [Watson Speech To Text Service](https://console.ng.bluemix.net/catalog/services/speech-to-text/) credentials.

```shell
npm start
```

Try it:

- Navigate to [http://localhost:3000](http://localhost:3000)
- Click the 'mic' button
- Speak


## License

Apache 2.0