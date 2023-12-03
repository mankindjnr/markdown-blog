# flutter

```bash
flutter create --org com.example appname
flutter create --org xxx.domain appname

flutter create --org amos.njoroge trials
```

```bash
cd trials
flutter run
```
The above will run the app on the connected device or emulator.


# firebase setup for backend
https://firebase.google.com/docs/flutter/setup

## put the following in your .bashrc or .zshrc
```bash
export PATH="$PATH":"$HOME/.pub-cache/bin"
```

## install firebase tools
https://firebase.google.com/docs/cli#install_the_firebase_cli
or
```bash
curl -sL https://firebase.tools | bash
```

## login to firebase
```bash
firebase login
firebase logout
```

- after login
## configure a firebase project

- fetch all the projects

```bash
flutterfire configure
```

