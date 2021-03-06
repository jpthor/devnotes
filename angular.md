## [Angular](https://github.com/angular/angular-cli)

```
npm install -g @angular/cli
ng new my-app
cd my-app
ng serve --open --port 8000
```

(If copying from another folder, copy the .angular-cli.json file)

//updating angular
```
ng update @angular/cli @angular/core
ng update @angular/cli --migrate-only --from=1.7.3
```

Debugging:
```
rm -r node_modules
npm install
npm install node-pre-gyp // pre-gyp errors
yarn
node patch.js
ng serve -o
```

Dependencies:
```
npm install --save-dev <***>
```

testing
```
ng serve -o
```

Permisson Problems


[Error getting modules](https://github.com/angular/angular-cli/issues/11969)
```
npm i @angular/compiler@6.1.1
npm i @angular/compiler-cli@6.1.1 -D
```


## [Node]()

[Update](https://www.hostingadvice.com/how-to/update-node-js-latest-version/)
```
sudo npm cache clean -f
sudo npm install -g n
sudo n stable
```

Problems with node permissions:
https://stackoverflow.com/questions/33725639/npm-install-g-less-does-not-work/40905762#40905762

```
sudo npm install --unsafe-perm=true --allow-root
```

```
export PATH=$PATH:/usr/local/git/bin:/usr/local/bin
```

--or---
```
sudo chown -R $USER:$GROUP ~/.npm
sudo chown -R $USER:$GROUP ~/.config
```

## [YARN](https://yarnpkg.com/en/docs/install#mac-stable)
```
brew install yarn
yarn
yarn link
```


## [KARMA](https://github.com/karma-runner/karma)

```
npm install karma
```

## [Protractor](https://github.com/angular/protractor)
e2e testing

```
npm install -g protractor
webdriver-manager update
webdriver-manager start
```
