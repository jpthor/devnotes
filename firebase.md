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

Testing:
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
