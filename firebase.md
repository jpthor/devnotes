## firebase

### Getting Started

https://firebase.google.com/docs/cli/?authuser=6

```
npm install -g firebase-tools
```

From project directory:
```
firebase login
firebase list
firebase init
```

Move `index.html` and `assets` into the distribution folder set in `init`. Most likely `public`

### Testing:

```
firebase serve
```

### Deploying

If deploying Angular, deploy to `dist`

Then in Angular:
```
ng build --prod
```

In `firebase.json`:
```
"public": "dist/<project_name>",
```

Or in `angular.json`:
```
"outputPath": "dist",
```

Then deploy:
```
firebase deploy
```
