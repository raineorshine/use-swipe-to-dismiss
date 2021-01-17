# use-swipe-to-dismiss
[![npm version](https://img.shields.io/npm/v/use-swipe-to-dismiss.svg)](https://npmjs.org/package/use-swipe-to-dismiss)

A simple React hook to dismiss an element by swiping, similar to mobile notifications.

Currently it only dismisses by swiping up, but let me know if you need it to work in a different direction and I can easily make it configurable.

![Screen Capture](https://user-images.githubusercontent.com/750276/104828137-43d40480-5823-11eb-95bd-3aaf0aee2a05.gif)

## Features

- Touch and Mouse compatible
- Exponential resistance to swiping in the opposite direction
- Snapback animation when dismiss is not completed
- Configure dismiss threshold in px or % of height

## Install

```sh
npm install --save use-swipe-to-dismiss
```

## Usage

```jsx
const useSwipeToDismiss = require('use-swipe-to-dismiss')

const AlertComponent = () => {

  const [dismissed, setDismissed] = useState(false)

  const useSwipeToDismissProps = useSwipeToDismiss({ 
    onDismiss: () => {
      setDismissed(true)
    }
  })

  return <div {...useSwipeToDismissProps}>Alert!</div>
}
```

**Options**:

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

## Tips

- The hook state will not reset on its own, so if the component seems to be dismissed permanently, you may need to force it to re-mount by giving it a `key`.

## Thanks

Inspired by https://github.com/hosembafer/react-swipe-to-dismiss
