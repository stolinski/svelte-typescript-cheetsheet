# svelte-typescript-cheetsheet

### Typing Props

* required props are just defined like normal with a : to inidicate the type.
* optional props are the same, however you need to set a default value.

Basically, if need a prop to be optional, you need to assign it a value when defined instead of using `let value?: string` 

```html
<script lang="ts">
    export let someProp: string // Required prop
    export let someOtherProp: string = "hello" // Optional prop
</script>
```

### Stores

```javascript

interface BlogPost {
    status: "ACTIVE" | "HIDDEN"
}


const post = writable<BlogPost>({
	status: 'ACTIVE',
})
```

To type an expected store, like passing a store as a prop, you would use the Writable generic type.

```javascript
import type { Writable } from 'svelte/store';

export let data: Writable<BlogPost>

```


### Types in Svelte Template Code

This is not currently supported.
