# [use-tools](https://www.npmjs.com/package/@vincecao/use-tools)

[![npm version](https://badge.fury.io/js/@vincecao%2Fuse-tools.svg)](https://badge.fury.io/js/@vincecao%2Fuse-tools)
[![npm checks](https://badgen.net/github/checks/vincecao/use-tools)](https://github.com/vincecao/use-tools/actions)

## Installation

```bash
# latest
# npm
npm i @vincecao/use-tools
# yarn
yarn add @vincecao/use-tools

# beta
# npm
npm i @vincecao/use-tools@beta
# yarn
yarn add @vincecao/use-tools@beta
```

This package was published in both [NPMJS](https://www.npmjs.com/package/@vincecao/use-tools) and [GITHUB](https://github.com/vincecao/use-tools/packages/1555582) npm registry.
To use page from Github npm registry, add below file in your repo before run `npm i` or `yarn add`.

```bash
# .npmrc
@vincecao:registry=https://npm.pkg.github.com
```

You can also install directly from git master
```bash
# npm
npm i vincecao/use-tools
npm i github:vincecao/use-tools

# yarn
yarn add vincecao/use-tools
yarn add github:vincecao/use-tools
```

### Release Method
- Github Actions will create and publish a beta version, when a Pull Request is merged to the master.
- Github Actions will create and publish a stable version, when a Release is created with a new tag version.

## Demo

Please check more samples at below
- [Demo Site](https://vince-amazing.com/use-tools/)
- [Code Sample](https://github.com/vincecao/use-tools/tree/master/example)

## Hooks
### usePromiseState

A hook that allows user to retrieve data from a remote by a `promise` function. It takes a required promise and optional options as inputs, return `data`, `error` `status` and useful `callbacks`.

```tsx
const [remoteData, { error, status, refetch }, setRemoteData] = usePromiseState<T>(promise, {
  deps,
  onPending,
  onSuccess,
  onError,
  onFinal
})
```
_The `promise` needs to be wrapped with [useCallback](https://reactjs.org/docs/hooks-reference.html#usecallback) and `options` needs to be wrapped with [useMemo](https://reactjs.org/docs/hooks-reference.html#usememo) if it is not `undefined`_.
## useTimeout

A simple implementation of `useTimeout` hook. The changes of `promise` will reset timeout delay. The `disable` option pause entire hook, `disableDelay` remove `setTimeout` behavior.

```tsx
useTimeout<T>(func, delay, disabled, disableDelay)
```

_The `func` needs to be wrapped with [useCallback](https://reactjs.org/docs/hooks-reference.html#usecallback)._

## useShuttle

A hook returns a shuttled list for each unique given array. The changes of array will also trigger re-generate a new shuttled list.

```tsx
const shuttled = useShuttle<T>(array)
```

### Running live example

```bash
yarn
yarn start

cd example
yarn
yarn start
```
