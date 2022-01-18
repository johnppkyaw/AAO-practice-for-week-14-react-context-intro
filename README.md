# Practice: Context - Introduction to Provider and Consumer

In this series of practices, you will set up a React Context `Provider` to
provide values to any component that needs it without `prop drilling` or `prop
threading`. You will also set up `Consumer` using the `useContext` hook to
acquire and use any values received from the `Provider`.

## Setup

Click the `Download Project` button at the bottom of this page to go to the
starter repo, then load the repo into [CodeSandbox].

## Create Context

To start, in your __src__ directory, create a new directory called __context__.
In this __context__ directory, create a file called __HoroscopeContext.js__.
This is where all your horoscope context will be placed.

At the top of this file, import `createContext` from `react` and create your
context called `HoroscopeContext`. If you're lost, check out the
[documentation][create-context]. Don't forget to `export` your
`HoroscopeContext`.

Awesome! You have created your context, now you can use your `Provider`
component.

## Create Context Provider

In your __src/index.js__ file, import `HoroscopeContext` from your __context__
directory.

Inside your `Root` functional component, wrap `<App />` with the
`HoroscopeContext.Provider` component. This is how you will give the horoscope
context to your entire application.

Let's make sure things are going smoothly.

If you look at the console in your sandbox browser, you should see a warning
message from React that says your `Context.Provider` is missing a `value` prop.
This means that you have successfully created your context provider, but now you
must deal with this warning message.

## Consume the Context

As you have seen in your DevTools, React is warning you that you need to have a
`value` prop in your `Context.Provider`. This `value` prop is what holds all of
your global state. Your goal is to pass a value in the `value` prop object and
later consume that context value.

In the `HoroscopeContext.Provider` component, include your `value` prop and set
it to an object with a key of `sign` and a value of `Leo`. (Feel free to use any
other sign.) The object should look like this:

```js
{ sign: "Leo" }
```

The warning message in your sandbox browser should disappear.

Now it is time to consume the context. Navigate to your `Detail` component. At
the top, import `useContext` from react. Next, import `HoroscopeContext` from
__context/HoroscopeContext.js__. Inside your `Detail` component, create the
variable `horoscopesObj` and have it equal to `useContext` invoked with
`HoroscopeContext` passed in as your argument.

### It's time to test!

Go to your sandbox browser's React DevTools. You should be able to see your
component tree and--most importantly--your `Context.Provider`.

If you click on your `Context.Provider`, you should see your `value` under the
`prop` section. That is what your global state looks like.

If you click on your `Detail` component, you should see a `hooks` section, where
your context is located. This is where your `Detail` component is _consuming_
the context.

## What you have learned

**Congratulations!** In this practice you have learned how to

1. Create context with `createContext`
2. Use your `Context.Provider` and wrap your entire application with it.
3. Consume the context in your `Detail` component.

[create-context]: https://reactjs.org/docs/context.html#reactcreatecontext
[CodeSandbox]: https://www.codesandbox.io