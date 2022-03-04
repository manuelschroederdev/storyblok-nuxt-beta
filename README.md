<div align="center">
	<a  href="https://www.storyblok.com?utm_source=github.com&utm_medium=readme&utm_campaign=storyblok-nuxt-beta"  align="center">
		<img  src="https://a.storyblok.com/f/88751/1776x360/b8979e5c96/sb-nuxt.png"  alt="Storyblok Logo">
	</a>
	<h1 align="center">@storyblok/nuxt-beta</h1>
	<p align="center">Nuxt 3 module for the <a href="http://www.storyblok.com?utm_source=github.com&utm_medium=readme&utm_campaign=storyblok-nuxt-beta" target="_blank">Storyblok</a>, Headless CMS.</p> <br />
</div>

<br>

## ⚠️ This module is still WIP ⚠️

<!--
<p align="center">
  <a href="https://npmjs.com/package/@storyblok/nuxt-beta">
    <img src="https://img.shields.io/npm/v/@storyblok/nuxt-beta/latest.svg?style=flat-square" alt="Storyblok JS Client" />
  </a>
  <a href="https://npmjs.com/package/@storyblok/nuxt-beta" rel="nofollow">
    <img src="https://img.shields.io/npm/dt/@storyblok/nuxt-beta.svg?style=flat-square" alt="npm">
  </a>
</p>

<p align="center">
  <a href="https://discord.gg/jKrbAMz">
   <img src="https://img.shields.io/discord/700316478792138842?label=Join%20Our%20Discord%20Community&style=appveyor&logo=discord&color=09b3af">
   </a>
  <a href="https://twitter.com/intent/follow?screen_name=storyblok">
    <img src="https://img.shields.io/badge/Follow-%40storyblok-09b3af?style=appveyor&logo=twitter" alt="Follow @Storyblok" />
  </a><br/>
  <a href="https://app.storyblok.com/#!/signup?utm_source=github.com&utm_medium=readme&utm_campaign=storyblok-nuxt-beta">
    <img src="https://img.shields.io/badge/Try%20Storyblok-Free-09b3af?style=appveyor&logo=data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAB4AAAAeCAYAAAA7MK6iAAAABGdBTUEAALGPC/xhBQAAADhlWElmTU0AKgAAAAgAAYdpAAQAAAABAAAAGgAAAAAAAqACAAQAAAABAAAAHqADAAQAAAABAAAAHgAAAADpiRU/AAACRElEQVRIDWNgGGmAEd3D3Js3LPrP8D8WXZwSPiMjw6qvPoHhyGYwIXNAbGpbCjbzP0MYuj0YFqMroBV/wCxmIeSju64eDNzMBJUxvP/9i2Hnq5cM1devMnz984eQsQwETeRhYWHgIcJiXqC6VHlFBjUeXgav40cIWkz1oLYXFmGwFBImaDFBHyObcOzdW4aSq5eRhRiE2dgYlpuYoYSKJi8vw3GgWnyAJIs/AuPu4scPGObd/fqVQZ+PHy7+6udPOBsXgySLDfn5GRYYmaKYJcXBgWLpsx8/GPa8foWiBhuHJIsl2DkYQqWksZkDFgP5PObcKYYff//iVAOTIDlx/QPqRMb/YSYBaWlOToZIaVkGZmAZSQiQ5OPtwHwacuo4iplMQEu6tXUZMhSUGDiYmBjylFQYvv/7x9B04xqKOnQOyT5GN+Df//8M59ASXKyMHLoyDD5JPtbj42OYrm+EYgg70JfuYuIoYmLs7AwMjIzA+uY/zjAnyWJpDk6GOFnCvrn86SOwmsNtKciVFAc1ileBHFDC67lzG10Yg0+SjzF0ownsf/OaofvOLYaDQJoQIGix94ljv1gIZI8Pv38zPvj2lQWYf3HGKbpDCFp85v07NnRN1OBTPY6JdRSGxcCw2k6sZuLVMZ5AV4s1TozPnGGFKbz+/PE7IJsHmC//MDMyhXBw8e6FyRFLv3Z0/IKuFqvFyIqAzd1PwBzJw8jAGPfVx38JshwlbIygxmYY43/GQmpais0ODDHuzevLMARHBcgIAQAbOJHZW0/EyQAAAABJRU5ErkJggg==" alt="Follow @Storyblok" />
  </a>
</p>

> Try out the **[LIVE DEMO](https://stackblitz.com/edit/nuxt-3-sdk-demo?file=pages%2Findex.vue&terminal=dev)** on Stackblitz and play with code yourself!

## 🚀 Usage

> If you are first-time user of the Storyblok, read the [Getting Started](https://www.storyblok.com/docs/guide/getting-started?utm_source=github.com&utm_medium=readme&utm_campaign=storyblok-nuxt-beta) guide to get a project ready in less than 5 minutes.

### Installation

_Note: This module is for Nuxt 3. [Check out `@storyblok/nuxt` for Nuxt 2](https://github.com/storyblok/storyblok-nuxt)_.

Install `@storyblok/nuxt-beta`:

```bash
npm install @storyblok/nuxt-beta
# yarn add @storyblok/nuxt-beta
```

Add following code to buildModules section of `nuxt.config.js` and replace the accessToken with API token from Storyblok space.

```js
import { defineNuxtConfig } from "nuxt3";

export default defineNuxtConfig({
  buildModules: [
    ["@storyblok/nuxt-beta", { accessToken: "<your-access-token>" }]
    // ...
  ]
});
```

You can also use the `storyblok` config if you prefer:

```js
import { defineNuxtConfig } from "nuxt3";

export default defineNuxtConfig({
  buildModules: ["@storyblok/nuxt-beta"],
  storyblok: {
    accessToken: "<your-access-token>"
  }
});
```

#### Options

When you initialize the module, you can pass all [_@storyblok/vue_ options](https://github.com/storyblok/storyblok-vue#storyblok-api) plus a `useApiClient` options:

```js
// Defaults
["@storyblok/nuxt-beta", {
  {
    accessToken: "<your-access-token>",
    bridge: true,
    apiOptions: {}, // storyblok-js-client options
    useApiClient: true
  }
}]
```

### Getting started

### 1. Creating and linking your components to Storyblok Visual Editor

To link your Vue components to their equivalent you created in Storyblok:

- First, you need to load them globally. You can just place them on the `~/components/storyblok` directory and will be discovered automagically, otherwise you can load them manually (for example, by [using a Nuxt plugin](https://stackoverflow.com/questions/43040692/global-components-in-vue-nuxt)).

- For each components, use the `v-editable` directive on its root element, passing the `blok` property that they receive:

```html
<div v-editable="blok" / >
```

- Finally, use `<StoryblokComponent>` which available globally in the Nuxt app:

```html
<StoryblokComponent blok="blok" />
```

> The `blok` is the actual blok data coming from [Storblok's Content Delivery API](https://www.storyblok.com/docs/api/content-delivery/v2?utm_source=github.com&utm_medium=readme&utm_campaign=storyblok-nuxt).

### 2. Getting Storyblok Stories and listen to Visual Editor events

#### Composition API

The simplest way is by using the `useStoryblok` one-liner composable (it's autoimported):

```html
<script setup>
  const story = await useStoryblok("vue", { version: "draft" });
</script>

<template>
  <StoryblokComponent v-if="story" :blok="story.content" />
</template>
```

Which is the short-hand equivalent to using `useStoryblokApi` and `useStoryblokBridge` functions separately:

```html
<script setup>
  const story = ref(null);
  const storyblokApi = useStoryblokApi();
  const { data } = await storyblokApi.get("cdn/stories/vue", {
    version: "draft"
  });
  story.value = data.story;

  onMounted(() => {
    useStoryblokBridge(story.value.id, (evStory) => (story.value = evStory));
  });
</script>

<template>
  <StoryblokComponent v-if="story" :blok="story.content" />
</template>
```

### API

#### useStoryblok(slug, apiOptions, bridgeOptions)

Check the available [apiOptions](https://github.com/storyblok/storyblok-js-client#class-storyblok) (passed to `storyblok-js-client`) and [bridgeOptions](https://www.storyblok.com/docs/Guides/storyblok-latest-js?utm_source=github.com&utm_medium=readme&utm_campaign=storyblok-nuxt-beta) (passed to the Storyblok Bridge).

#### useStoryblokApi()

Returns the instance of the `storyblok-js-client`.

#### useStoryblokBridge(storyId, callback, bridgeOptions)

Use this one-line function to cover the most common use case: updating the story when any kind of change happens on Storyblok Visual Editor.

## 🔗 Related Links

- **[Live Demo on Stackblitz](https://stackblitz.com/edit/nuxt-3-sdk-demo?file=pages%2Findex.vue&terminal=dev)**
- **[Nuxt.js Hub](https://www.storyblok.com/tc/nuxtjs?utm_source=github.com&utm_medium=readme&utm_campaign=storyblok-nuxt-beta)**: Learn how to develop your own Nuxt.js applications that use Storyblok APIs to retrieve and manage content;
- **[Storyblok & Nuxt.js on GitHub](https://github.com/search?q=org%3Astoryblok+topic%3Anuxt)**: Check all of our Nuxt.js open source repos;
- **[Storyblok CLI](https://github.com/storyblok/storyblok)**: A simple CLI for scaffolding Storyblok projects and fieldtypes.

## ℹ️ More Resources

### Support

- Bugs or Feature Requests? [Submit an issue](/../../issues/new);

- Do you have questions about Storyblok or you need help? [Join our Discord Community](https://discord.gg/jKrbAMz).

### Contributing

Please see our [contributing guidelines](https://github.com/storyblok/.github/blob/master/contributing.md) and our [code of conduct](https://www.storyblok.com/trust-center#code-of-conduct?utm_source=github.com&utm_medium=readme&utm_campaign=storyblok-nuxt-beta).
This project use [semantic-release](https://semantic-release.gitbook.io/semantic-release/) for generate new versions by using commit messages and we use the Angular Convention to naming the commits. Check [this question](https://semantic-release.gitbook.io/semantic-release/support/faq#how-can-i-change-the-type-of-commits-that-trigger-a-release) about it in semantic-release FAQ. -->
