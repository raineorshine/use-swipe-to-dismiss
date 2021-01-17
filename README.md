# use-swipe-to-dismiss
[![npm version](https://img.shields.io/npm/v/use-swipe-to-dismiss.svg)](https://npmjs.org/package/use-swipe-to-dismiss)

A simple React hook to dismiss an element by swiping, similar to mobile notifications.

## Features

- Configure dismiss threshold in px or % of height

## Install

```sh
npm install --save use-swipe-to-dismiss
```

## Usage

```js
const useSwipeToDismiss = require('use-swipe-to-dismiss')
```

Options:

```js
{
  // y offset at which onDismiss is fired, in px or % (of height)
  // Default: '50%'
  dismissThreshold?: string | number,

  // dismiss handler
  onDismiss?: () => void,

  // dismiss after animating element off screen
  onDismissEnd?: () => void,

  // time in seconds to animate the element back into place after releasing
  // Default: 0.1
  snapbackDuration?: number,

  // easing function to animate the element back into place after releasing
  // Default: ease-out
  snapbackEasing?: string,
}
```
