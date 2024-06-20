# Svelte 5 Snippets

This extension is a set of Snippets for Svelte. They are created so that scaffolding with Svelte can be easy. You can try to remember most of these.

![Demo](https://github.com/Chanzhaoyu/svelte-5-snippets/raw/master/images/cover.png)

## Snippets Documentation

| Prefix | Description         |
| ------ | ------------------- |
| `s-`   | Svelte Snippets     |
| `sk-`  | Svelte-Kit Snippets |

## Svelte

<details>
<summary>s-base</summary>

```html
<script lang="ts"></script>

<div></div>

<style></style>
```

</details>

<details>
<summary>s-base-component</summary>

```html
<script lang="ts">
  import type { Snippet } from "svelte";

  let { children }: { children: Snippet } = $props();
</script>

<div>{@render children()}</div>

<style></style>
```

</details>

<details>
<summary>s-script</summary>

```html
<script lang="ts"></script>
```

</details>

<details>
<summary>s-css</summary>

```html
<style></style>
```

</details>

<details>
<summary>s-css-lang</summary>

```html
<style lang=""></style>
```

</details>

<details>
<summary>s-if</summary>

```
{#if }

{/if}
```

</details>

<details>
<summary>s-if-else</summary>

```
{#if }

{:else}

{/if}
```

</details>

<details>
<summary>s-if-else-if</summary>

```
{#if }

{:else if }

{/if}
```

</details>

<details>
<summary>s-each</summary>

```
{#each items as item}

{/each}
```

</details>

<details>
<summary>s-each-else</summary>

```
{#each items as item}

{:else}

{/each}
```

</details>

<details>
<summary>s-each-index</summary>

```
{#each items as item, i}

{/each}
```

</details>

<details>
<summary>s-each-index-key</summary>

```
{#each items as item, i (item.id)}

{/each}
```

</details>

<details>
<summary>s-await</summary>

```
{#await promise}

{:then value}

{:catch error}

{/await}
```

</details>

<details>
<summary>s-debug</summary>

```
{@debug }
```

</details>

<details>
<summary>s-html</summary>

```
{@html }
```

</details>

<details>
<summary>s-snippet</summary>

```
{#snippet fc(value)}

{/snippet}
```

</details>

<details>
<summary>s-slot</summary>

```
<slot></slot>
```

</details>

<details>
<summary>s-slot-name</summary>

```
<slot name=""></slot>
```

</details>

<details>
<summary>s-render</summary>

```
{@render }
```

</details>

<details>
<summary>s-render-fallback</summary>

```
{#if children}
	{@render children()}
{:else}
	<span>default</span>
{/if}
```

</details>

<details>
<summary>s-bind-value</summary>

```
bind:value={}
```

</details>

<details>
<summary>s-bind-this</summary>

```
bind:this={}
```

</details>

<details>
<summary>s-transition-fade</summary>

```
transition:fade="{{delay: 250, duration: 300}}"
```

</details>

<details>
<summary>s-transition-blur</summary>

```
transition:blur="{{amount: 10}}"
```

</details>

<details>
<summary>s-transition-fly</summary>

```
transition:fly="{{delay: 250, duration: 300, x: 100, y: 500, opacity: 0.5, easing: quintOut}}"
```

</details>

<details>
<summary>s-transition-slide</summary>

```
transition:slide="{{delay: 250, duration: 300, easing: quintOut }}"
```

</details>

<details>
<summary>s-transition-scale</summary>

```
transition:scale="{{duration: 500, delay: 500, opacity: 0.5, start: 0.5, easing: quintOut}}"
```

</details>

<details>
<summary>s-transition-draw</summary>

```
transition:draw="{{duration: 5000, delay: 500, easing: quintOut}}"
```

</details>

<details>
<summary>s-animate-flip</summary>

```
animate:flip="{{delay: 250, duration: 250}}"
```

</details>

<details>
<summary>s-self</summary>

```
<svelte:self></svelte:self>
```

</details>

<details>
<summary>s-options</summary>

```
<svelte:options />
```

</details>

<details>
<summary>s-window</summary>

```
<svelte:window  />
```

</details>

<details>
<summary>s-head</summary>

```
<svelte:head>

</svelte:head>
```

</details>

<details>
<summary>s-body</summary>

```
<svelte:body  />
```

</details>

## Svelte Kit

<details>
<summary>sk-page</summary>

```html
<script lang="ts">
  import type { PageData } from "./$types";

  export let data: PageData;
</script>
```

</details>

<details>
<summary>sk-page-load</summary>

```ts
import type { PageLoad } from "./$types";

export const load: PageLoad = async (event) => {
  return {};
};
```

</details>

<details>
<summary>sk-page-params</summary>

```html
<script lang="ts">
  import { page } from "$app/stores";

  const { id } = $page.params;
</script>
```
</details>

<details>
<summary>sk-page-server-load</summary>

```ts
import type { PageServerLoad } from "./$types";

export const load: PageServerLoad = async (event) => {
  return {};
};
```

</details>

<details>
<summary>sk-layout-load</summary>

```ts
import type { LayoutLoad } from "./$types";

export const load: LayoutLoad = async (event) => {
  return {};
};
```

</details>

<details>
<summary>sk-layout-server-load</summary>

```ts
import type { LayoutServerLoad } from "./$types";

export const load: LayoutServerLoad = async (event) => {
  return {};
};
```

</details>

<details>
<summary>sk-actions</summary>

```ts
import type { Actions } from "./$types";

export const actions: Actions = {
  async default({}) {},
};
```

</details>

<details>
<summary>sk-hooks</summary>

```ts
import type { Handle } from "./$types";

export const handle: Handle = async ({ event, resolve }) => {
  const response = await resolve(event);
  return response;
};
```

</details>

<details>
<summary>sk-error</summary>

```ts
error(404, {
  message: "Not found",
});
```

</details>

<details>
<summary>sk-api-get</summary>

```ts
import type { RequestHandler, RequestEvent } from "./$types";
import { json } from "@sveltejs/kit";

export const GET = (async ({ request }: RequestEvent) => {
  return json({ message: "GET" });
}) satisfies RequestHandler;
```

</details>

<details>
<summary>sk-api-post</summary>

```ts
import type { RequestHandler, RequestEvent } from "./$types";
import { json } from "@sveltejs/kit";

export const POST = (async ({ request }: RequestEvent) => {
  return json({ message: "POST" });
}) satisfies RequestHandler;
```

</details>

<details>
<summary>sk-api-put</summary>

```ts
import type { RequestHandler, RequestEvent } from "./$types";
import { json } from "@sveltejs/kit";

export const PUT = (async ({ request }: RequestEvent) => {
  return json({ message: "PUT" });
}) satisfies RequestHandler;
```

</details>

<details>
<summary>sk-api-delete</summary>

```ts
import type { RequestHandler, RequestEvent } from "./$types";
import { json } from "@sveltejs/kit";

export const DELETE = (async ({ request }: RequestEvent) => {
  return json({ message: "DELETE" });
}) satisfies RequestHandler;
```

</details>

<details>
<summary>sk-api-patch</summary>

```ts
import type { RequestHandler, RequestEvent } from "./$types";
import { json } from "@sveltejs/kit";

export const PATCH = (async ({ request }: RequestEvent) => {
  return json({ message: "PATCH" });
}) satisfies RequestHandler;
```

</details>

<details>
<summary>sk-browser</summary>

```ts
import { browser } from "$app/environment";

if (browser) {
}
```

</details>

<details>
<summary>sk-env-private</summary>

```ts
import { env } from "$env/dynamic/private";
```

</details>

## TypeScript / JavaScript

<details>
<summary>s-state</summary>

```ts
let state = $state();
```

</details>

<details>
<summary>s-state-frozen</summary>

```ts
let state = $state.frozen();
```

</details>

<details>
<summary>s-state-snapshot</summary>

```ts
$state.snapshot();
```

</details>

<details>
<summary>s-state-is</summary>

```ts
$state.is(state1, state2);
```

</details>

<details>
<summary>s-derived</summary>

```ts
let value = $derived();
```

</details>

<details>
<summary>s-derived-by</summary>

```ts
let value = $derived.by(() => {});
```

</details>

<details>
<summary>s-effect</summary>

```ts
$effect(() => {});
```

</details>

<details>
<summary>s-effect-pre</summary>

```ts
$effect.pre(() => {});
```

</details>

<details>
<summary>s-effect-tracking</summary>

```ts
$effect(() => {
  console.log("in effect:", $effect.tracking());
});
```

</details>

<details>
<summary>s-effect-root</summary>

```ts
const cleanup = $effect.root(() => {
  $effect(() => {});

  return () => {};
});
```

</details>

<details>
<summary>s-computed</summary>

```ts
let value = $state("");

let valueComputed = {
  get value() {
    return value;
  },
  set value(newValue) {
    value = newValue;
  },
};
```

</details>

<details>
<summary>s-props</summary>

```ts
let { children } = $props();
```

</details>

<details>
<summary>s-host</summary>

```ts
$host().dispatchEvent();
```

</details>

<details>
<summary>s-flush-sync</summary>

```ts
flushSync(() => {});
```

</details>

<details>
<summary>s-hook</summary>

```ts
export function useCounter() {
  let count = $state(0);

  function increment() {
    count += 1;
  }

  return {
    get count() {
      return count;
    },
    increment,
  };
}
```

</details>

<details>
<summary>s-store</summary>

```ts
import { writable } from "svelte/store";

export function createCounter() {
  const { subscribe, update } = writable(0);

  function increment() {
    update((count) => count + 1);
  }

  return {
    subscribe,
    increment,
  };
}
```

</details>

<details>
<summary>s-set-context</summary>

```ts
setContext("key", "value");
```

</details>

<details>
<summary>s-get-context</summary>

```ts
const context = getContext("key");
```

</details>

<details>
<summary>s-has-context</summary>

```ts
if (hasContext("key")) {
}
```

</details>

## Css

<details>
<summary>s-global-css</summary>

```css
:global() {
}
```

</details>

## License

[MIT](license)
