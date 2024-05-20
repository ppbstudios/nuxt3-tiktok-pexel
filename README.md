# Nuxt plugin for tiktok pixel (Nuxt 3)

> A Nuxt 3 module thats injects Meta Pixel (tiktok Pixel) 

## Table of Contents


## Requirements

* npm or yarn
* NuxtJS
* NodeJS

```bash
$ npm install --save nuxt3-tiktok-pixel
// or
$ yarn add nuxt3-tiktok-pixel
```

## Getting Started

Add `nuxt3-tiktok-pixel` to `modules` section of `nuxt.config.js`.

```js
{
  modules: [
    'nuxt3-tiktok-pixel',
  ],
  tiktok: {
    pixelId: 'PIXEL_KEY',
    track: "ViewContent",
    autoViewContent: true,
    debug: true,
    }
}
```

## Automatically track PageView

By default, the module won't trigger any tracking event on route change. To enable this behaviour, you must specify the `autoPageView` option and set to `true` in the Nuxt module options.

```js
{
  modules: [
    'nuxt3-tiktok-pixel',
  ],
  tiktok: {
    /* module options */
    pixelId: 'PIXEL_KEY',
    autoPageView: true
  },
}
```

## Disabling the pixel (for GDPR)

If you'd like to install the pixel disabled, and enable it later after the user has consented to its use, you can do so by setting `disabled: true` in the pixel configuration:

```js
{
  modules: [
    'nuxt3-tiktok-pixel',
  ],
  tiktok: {
    ...
    disabled: true
  },
}
```

Now, in your component, you can call the following in order to start the pixel and track the current page.

```js
this.$tt.enable()
```

The pixel can be disabled again later on by using the `.disable()` method.

## Multiple pixel codes according to route

It's possible to use multiple pixel codes according to the user's route. This can be made through the `pixels` property.
The `pixels` property expects an array of options.

```js
{
  modules: [
    'nuxt3-tiktok-pixel',
  ],
  tiktok: {
    pixelId: 'PIXEL_KEY',
  },
}
```
