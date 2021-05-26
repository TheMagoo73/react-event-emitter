# @magoo/react-event-emitter

React hook for event subscription and publishing

[![npm version](https://badge.fury.io/js/@jcmagoo/react-event-emitter.svg)](https://badge.fury.io/js/@jcmagoo/react-event-emitter)
[![Known Vulnerabilities](https://snyk.io/test/github/TheMagoo73/flagsmith-react/badge.svg)](https://snyk.io/test/github/TheMagoo73/react-event-emitter)
![CI Build](https://github.com/TheMagoo73/react-event-emitter/actions/workflows/ci-build.yml/badge.svg)
[![Test Coverage](https://api.codeclimate.com/v1/badges/3d634028cffba29aba92/test_coverage)](https://codeclimate.com/github/TheMagoo73/react-event-emitter/test_coverage)

## Contents

- [Installation](#installation)
- [Getting Started](#getting-started)
- [API Reference](#api-reference)

If you're creating a React hook, and need to provide a mechanism for client components to subscribe to events that the hook raises, then this module is for you!

## Instalation

Using [npm](https://npmjs.org)

```bash
npm install @jcmagoo/react-event-emitter
```

Using [yarn](https://yarnpkg.com)

```bash
yarn add @jcmagoo/react-event-emitter
```

## Getting Started

Here's a very simple example of subscribing to an emitter, and emitting an event.

```javascript
import useEventEmitter from './src'

const {useSubscription, emit} = useEventEmitter()

useSubscription(() => console.log('Hello Foo!'))
useSubscription(() => console.log('Hello Bar'))

emit()

// Hello Foo
// Hello Bar
```

When used in a custom hook, typically the hook would expose the `useSubscription` method to allow consumers to register callbacks to be notified of events by the hook. The hook itself would call `emit` when it needed to trigger the notification.

## API Reference

### useEventEmitter

```javascript
const {
    useSubscription,
    emit
} = useEventEmitter();
```

Use the `useEventEmitter` hook to add pub/sub event support to your components and hooks.

### useSubscription

```javascript
useSubscription(callback)
```

Add a subscription to the event emitter.

### emit

```javascript
emit()
```

Call the callback for each attached subscriber.