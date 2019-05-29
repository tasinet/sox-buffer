# sox-buffer - A sox-audio clone with buffer support
This adds buffer support to the [sox-audio](https://github.com/psaylor/sox-audio) project. 

It does not write any temporary files to disk, but rather creates a readable and writable stream and uses the sox-audio stream functionality.

Other changes from sox-audio: removed logging.

## Usage
Usage is as in sox-audio with two differences:

To pass a buffer to sox as input:
```js
SoxCommand()
    .input(inputBuffer)
    // ...
```

To get a buffer from sox as output:
```js
SoxCommand()
    .input(inputBuffer)
    .output('buffer')
    .on('end', function(stdout, stderr, buffer) {
    	buffer && console.log('Received buffer', buffer.length);
    });

```

## License
This code is under the MIT License. 
