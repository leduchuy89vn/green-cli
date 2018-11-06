# ⚛️ generator-react-native

The aim of of this generator is to **provide structure** and a **set of patterns**
to eliminate the time you would spend bootstrapping your own. While this comes
with some opinion, there’s no overarching framework on top of React Native; it’s
purely a collection of commonly used modules and some sensible architecture to
get you or your team off the ground.

## Installation

```
npm install -g genny
```

```
yarn global add genny
```

## Getting started

Create a new React Native project using their CLI tool.

```
react-native init MyApp && cd MyApp
```

Once this is complete, simply run the main generator command. This will rework
and add to the files that are generated by React Native and give you something
more akin to what you might find with `rails new`.

```
genny init
```

## Feature overview

- A sensible `README` providing consistent instructions between projects
- Router using `react-navigation`
- Redux setup
  - Store is persisted using `redux-persist`
  - Helpful state changes logged in the debugger using `redux-logger`
  - Actions are prevent from being dispatched before the cache is restored
- UI niceities
  - CSS-in-JS support for `styled-components`
  - Start to a styleguide to list your components
  - Example Button component
  - Layout component example to DRY up screen layouts
  - Pattern to organise components and their styles
- Helpful utilities
  - `log` helper to output coloured logs to the debug console
  - Visual display of your app’s environment while it’s running, this gets hidden
    in production
- Optional support for different locales using `react-native-i18n`
- Environment variables available in JavaScript, Objective C and Java using
  `react-native-config`
- Sagas (to handle async tasks like HTTP requests) using `redux-saga`
- Initial setup for deep linking
- Requests are setup to be handled with `axios` with clear logging in the
  debugger provided
- Automatic versioning of iOS and Android versions based on the `package.json`
  version
- Pattern to manage Flow types across the app
- Generic app icon that can be processed through a separate generator to handle
  all your iOS and Android icons

### Application structure

After running the `base` command, on top of the features above your application
will then receive this structure.

```
App/
├── Actions/
│   ├── App.js
│   └── index.js
├── Assets/
│   └── AppIcon.png
├── Components/
│   ├── App/
│   │   └── index.js
│   ├── Button/
│   │   ├── index.js
│   │   └── styles.js
│   ├── Layout/
│   │   ├── index.js
│   │   └── styles.js
│   ├── Text/
│   │   ├── index.js
│   │   └── styles.js
│   └── Utilities/
│       └── Environment/
│           ├── index.js
│           └── styles.js
├── Config/
│   ├── Locales/
│   │   └── en.json
│   └── index.js
├── Helpers/
│   ├── Translations.js
│   └── Log.js
├── Reducers/
│   ├── App.js
│   └── index.js
├── Sagas/
│   ├── index.js
│   └── RequestExample.js
├── Screens/
│   ├── Styleguide/
│   │   ├── Container.js
│   │   └── index.js
│   ├── index.js
│   └── Main.js
├── Services/
│   └── API/
│       ├── index.js
│       └── logging.js
├── Store/
│   ├── Middleware/
│   │   ├── Buffer.js
│   │   ├── index.js
│   │   ├── Logger.js
│   │   └── Saga.js
│   └── index.js
├── Styles/
│   └── Theme.js
├── Types/
│   └── index.js
├── App.js
└── Router.js
```

## Documentation

- [Commands](docs/commands.md)

## Manual Notes

### After `genny init`

The default `react-native init` now comes with tvOS targets... These add un-needed cruft to the project. Best plan is to open the XCode project, remove the tvOS targets and then delete the files in the project themselves.

Follow the Android version of these instructions to add automatic build numbers.

[https://medium.com/@andr3wjack/versioning-react-native-apps-407469707661#.quhgn05gf](https://medium.com/@andr3wjack/versioning-react-native-apps-407469707661#.quhgn05gf)

## Resources

- [Introduction to Sagas](https://redux-saga.github.io/redux-saga/docs/introduction/BeginnerTutorial.html)
- [A great simple intro to Redux Sagas](https://www.youtube.com/watch?v=msx0Qiu8NxQ&list=PLw7fHewFA6OTyUnLiZ1HQvYdzjp9ARMQw)
- [Intro to Redux](http://redux.js.org/docs/basics/Reducers.html)
- [Flow](https://flowtype.org/)
