# React Native Architecture Blueprints

React Native Architecture Blueprints includes the following rock-solid technical and Clean Architecture principles

## Requirements

- [react-native 0.68.2](https://www.npmjs.com/package/react-native?activeTab=versions)

## Environment

**iOS**
- iOS 13+

**Android**
- Android 5.1+
    - minSdkVersion 22
- targetSdkVersion 30

## Documentation

- [React Navigation 6](https://reactnavigation.org/blog/2021/08/14/react-navigation-6.0/)
- [MobX-State-Tree](https://mobx-state-tree.js.org/intro/welcome)
- [TypeScript](https://reactnative.dev/docs/typescript)
- [AsyncStorage](https://react-native-async-storage.github.io/async-storage/docs/install/)
- [apisauce](https://github.com/infinitered/apisauce)
- [eslint](https://www.npmjs.com/package/@react-native-community/eslint-config)
- [i18n-js](https://github.com/AlexanderZaytsev/react-native-i18n)
- [Jest](https://jestjs.io/docs/tutorial-react-native)
- [react-native-size-matters](https://github.com/nirsky/react-native-size-matters)
- [fastlane](https://docs.fastlane.tools/getting-started/cross-platform/react-native/)


# Project's structure 

```
Blueprint-project
├── app
│   ├── components
│   ├── i18n
│   ├── utils
│   ├── models
│   ├── navigators
│   ├── screens
│   ├── services
│   ├── theme
│   ├── app.tsx
├── storybook
│   ├── views
│   ├── index.ts
│   ├── storybook-registry.ts
│   ├── storybook.ts
│   ├── toggle-storybook.tsx
├── test
│   ├── setup.ts
│   ├── storyshots.test.ts
├── README.md
├── android
│   ├── app
├── index.js
├── ios
│   ├── Blueprint.xcodeproj
├── .env
└── package.json

```

### ./app directory

Included in an Blueprint boilerplate project is the `app` directory. This is a directory you would normally have to create when using vanilla React Native.

The inside of the src directory looks similar to the following:

```
app
│── components
│── i18n
├── models
├── navigators
├── screens
├── services
├── theme
├── utils
└── app.tsx
```

# Components
This is where your React components will live. Each component will have a directory containing the `.tsx` file, along with a story file, and optionally `.presets`, and `.props` files for larger components. The app will come with some commonly used components like Button.

# Models
This is where your app's models will live. Each model has a directory which will contain the `mobx-state-tree` model file, test file, and any other supporting files like actions, types, etc.

# Navigators
This is where your `react-navigation` navigators will live.

# Screens
This is where your screen components will live. A screen is a React component which will take up the entire screen and be part of the navigation hierarchy. Each screen will have a directory containing the `.tsx` file, along with any assets or other helper files.

# Services
Any services that interface with the outside world will live here (think REST APIs, Push Notifications, etc.).

# Theme
Here lives the theme for your application, including spacing, colors, and typography.

# Utils
This is a great place to put miscellaneous helpers and utilities. Things like date helpers, formatters, etc. are often found here. However, it should only be used for things that are truely shared across your application. If a helper or utility is only used by a specific component or model, consider co-locating your helper with that component or model.

### ./ignite directory

The `ignite` directory stores all things Ignite, including CLI and boilerplate items. Here you will find generators, plugins and examples to help you get started with React Native.

### ./storybook directory

This is where your stories will be registered and where the Storybook configs will live.

### ./test directory

This directory will hold your Jest configs and mocks, as well as your [storyshots](https://github.com/storybooks/storybook/tree/master/addons/storyshots) test file. This is a file that contains the snapshots of all your component storybooks.

### Fastlane

**Build IOS**

```
cd ios
fastlane ios build
fastlane ios publish
```

**Build Android**

```
cd android
fastlane android build
fastlane android publish


## The latest and greatest boilerplate for Infinite Red opinions

This is the boilerplate that [Infinite Red](https://infinite.red) uses as a way to test bleeding-edge changes to our React Native stack.
