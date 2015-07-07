# Off the Rip

"Future Proof" method of downloading Soundcloud audio and embedding ID3 tags (title, artist, artwork) within the resulting file.

<img src="http://i.imgur.com/flBrvcn.jpg">

## Installing
```sh
npm i -g off-the-rip

# Update
npm update -g off-the-rip
```

## Developing
After cloning the repo...
```sh
brew install eyeD3 phantomjs rtmpdump
npm install
npm link # Gives you access to `otr` in your terminal
```

## Usage

### CLI
The CLI takes two parameters, `url` and `dir`. The second is optional.
```sh
otr https://soundcloud.com/artist/track ~/Music

If a `dir` is not specified, the current directory will be used.
```

### Node
```javascript
var otr = require('off-the-rip');

otr('https://soundcloud.com/artist/track', '~/Music', function() {
   // Done
});
```

## How it works
* Network traffic on the soundcloud page is monitored and API requests and artwork are intercepted.
* Page information is scraped (Title, Artist, etc)
* Data is sent to Node where ID3 tags including artwork is written to the dist folder

## Disclaimer
This tool is in no way shape or form to be used for downloading copyrighted music, it is designed and built as a proof-of-concept.

## License
MIT
