# Web dev

## Tools

## Browserify & Tools

### Browserify

Makes node modules work in the browser.

Tutorial: https://scotch.io/tutorials/getting-started-with-browserify

```
npm install --global browserify
browserify main.js -o bundle.js
```

Source Maps
```
browserify --debug main.js -o bundle.js
```

### Watchify

Rebuilds the browsify `bundle.js` file on the fly

```
npm install --global watchify
watchify main.js -o bundle.js -v
```

### Beefy

Makes it easy to enable live reload alongside automatic rebuild.
http://didact.us/beefy/

```
npm install -g beefy
beefy main.js --browserify $(which browserify) --live
```

### Exorcist

docs: https://www.npmjs.com/package/exorcist

Rips out the source Maps
```
npm install --global exorcist
browserify main.js --debug | exorcist bundle.map.js > bundle.js
```

### Minify

Minifies the bundle
https://github.com/ben-ng/minifyify

```
npm install --save-dev minifyify
```

## Other

### Ramda

Adds functional library to javascript

Docs: http://ramdajs.com/0.19.1/index.html

```
npm install ramda --save
```

### Gulp

Streamline NPM scripts
https://gulpjs.com

```
npm install -g gulp && npm install gulp --save-dev
```
