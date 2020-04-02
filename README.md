# svelte-mui

Set of the UI components for [Svelte](https://svelte.dev) (~30 KB minzipped), inspired by Google's [Material Design](https://material.io/design/)

[View the demo](https://svelte-mui.now.sh)

## Installation

_Note that you will need to have [Node.js](https://nodejs.org) installed_

```bash
npm install --save-dev svelte-mui
```

## Usage

```html
<Textfield bind:value filled label="Name" message="Enter your name" />

<h1>Hello {value}!</h1>

<script>
    // import any components you want
    import { Textfield } from 'svelte-mui';

    let value = 'world';
</script>
```

This code on the [Svelte REPL](https://svelte.dev/repl/dfec17bd888749a1b76fa950df40f5dd?version=3.18.1)

## Quick start with new project

Create a new project based on [sveltejs/template](https://github.com/sveltejs/template)

```bash
npx degit sveltejs/template svelte-app
cd svelte-app
npm install
```

Add components

```bash
npm install --save-dev svelte-mui
```

* _Optionally_ add [focus-visible](https://github.com/WICG/focus-visible) polyfill to enable focus to be visible when using <kbd>TAB</kbd> key. This option can be applied to `Button`, `Checkbox`, `Radio` button, `Menuitem`

```bash
npm install --save-dev focus-visible
```

Modify file `src/App.svelte` in the following way

```html
<script>
    // optional import focus-visible polyfill only once
    import 'focus-visible';
    // import any components
    import { Button, Checkbox } from 'svelte-mui';

    let checked = true;
</script>

<Checkbox bind:checked>Checkbox</Checkbox>

<p>Checkbox is {checked ? 'checked' : 'unchecked'}</p>

<Button
    outlined
    shaped
    color="Red"
    on:click={() => { checked = !checked }}
>
    Inverse
</Button>
```

_Note for the [sapper](https://sapper.svelte.dev/) application, you must import components from `svelte-mui/src` like so_

```js
    import { Button, Checkbox } from 'svelte-mui/src';
```

...then start [Rollup](https://rollupjs.org/)

```bash
npm run dev
```

Navigate to [localhost:5000](http://localhost:5000)

For real applications, you have to add global styles to `disabled` state

```css
    .disabled,
    [disabled] {
        opacity: 0.5;
        pointer-events: none;
    }

    .disabled .disabled,
    .disabled [disabled],
    [disabled] .disabled,
    [disabled] [disabled] {
        opacity: 1;
    }
```

## Get started with an example

Clone repo [vikignt/svelte-mui](https://github.com/vikignt/svelte-mui.git)

```bash
git clone https://github.com/vikignt/svelte-mui.git
```

Then explore the __example__

```bash
cd svelte-mui/example
npm install
npm run dev
```

Navigate to [localhost:5000](http://localhost:5000)

### Get started with an sapper example

Clone repo [vikignt/sapper-mui](https://github.com/vikignt/sapper-mui.git)

```bash
git clone https://github.com/vikignt/sapper-mui.git
```

```bash
cd sapper-mui
npm install
npm run dev
```

Navigate to [localhost:3000](http://localhost:3000)
