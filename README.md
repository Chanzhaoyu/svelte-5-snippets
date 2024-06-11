# Svelte 5 Snippets

This extension is a set of Snippets for Svelte. They are created so that scaffolding with Svelte can be easy. You can try to remember most of these but. Before reading the full snippets down below. The snippets are made so that you write your HTML before writing your scripts and styles.

## Snippets Documentation

| Prefix | Description         |
| ------ | ------------------- |
| `sv`   | Svelte Snippets     |
| `sk`   | Svelte-Kit Snippets |

## Svelte

`sv-base`

```
<script lang="ts">

</script>

<div>

</div>

<style>

</style>
```

`sv:base-component`

```
<script lang="ts">
import type { Snippet } from 'svelte';

let { children }:{ children:Snippet } = $props();

</script>

<div>
  {@render children()}
</div>

<style>

</style>
```

## Svelte Kit

| Prefix                  | Description        |
| ----------------------- | ------------------ |
| `sk:page`               | PageData           |
| `sk:page-load`          | Page Load          |
| `sk:page-server-load`   | Page Server Load"  |
| `sk:layout-load`        | Layout Load        |
| `sk:layout-server-load` | Layout Server Load |
| `sk:actions`            | Actions            |
| `sk:handle`             | Hooks Handle       |
| `sk:error`              | Error              |

## **Css**

| Prefix            | Description |
| ----------------- | ----------- |
| `sv:style-global` | `:global()` |
