<center>

# VueJs + Vite

#### Next Generation Frontend Tooling


<img src="https://vueschool.io/img/svg/vueschool_hero.svg" alt="nvm project logo" />

<a href="https://cdn.freebiesupply.com/logos/large/2x/nodejs-1-logo-png-transparent.png">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://cdn.freebiesupply.com/logos/large/2x/nodejs-1-logo-png-transparent.png" />
    <img src="https://raw.githubusercontent.com/nvm-sh/logos/HEAD/nvm-logo-color.svg" height="50" alt="nvm project logo" />
  </picture>&nbsp;&nbsp; 
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://vitejs.dev/logo-with-shadow.png" />
    <img src="https://vitejs.dev/logo-with-shadow.png" height="50" alt="nvm project logo" />
  </picture>
</a> &nbsp;&nbsp; 
<a href="https://github.com/nvm-sh/logos">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/nvm-sh/logos/HEAD/nvm-logo-white.svg" />
    <img src="https://raw.githubusercontent.com/nvm-sh/logos/HEAD/nvm-logo-color.svg" height="50" alt="nvm project logo" />
  </picture>
</a>&nbsp; &nbsp; 
<a href="https://andrejgajdos.com/wp-content/uploads/2019/11/npm-logo.png?x24361">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://andrejgajdos.com/wp-content/uploads/2019/11/npm-logo.png?x24361" />
    <img src="https://raw.githubusercontent.com/nvm-sh/logos/HEAD/nvm-logo-color.svg" height="50" alt="nvm project logo" />
  </picture>&nbsp; &nbsp; 
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://vuejs.org/images/logo.png" />
    <img src="https://vuejs.org/images/logo.png" height="50" alt="nvm project logo" />
  </picture>
</a>
</center>
<br>

- 💡 Instant Server Start
- ⚡️ Lightning Fast HMR
- 🛠️ Rich Features
- 📦 Optimized Build
- 🔩 Universal Plugin Interface
- 🔑 Fully Typed APIs


<br>

# Useful Links

### Vue Documentation: [Vue Docs](https://vuejs.org/)

### NVM Install: [Github](https://github.com/nvm-sh/nvm)

### Node Install: [Node 16.19.1](https://nodejs.org/download/release/v16.19.1/node-v16.19.1-x64.msi)

### Node Documentation: [Docs](https://nodejs.org/docs/latest-v18.x/api/)

<br>

---
<br>

# Table of Contents
1. [**Conditional Rendering**](#conditional-rendering)
    - [`v-if`](#v-if)
    - [`v-else`](#v-else)
    - [`v-show`](#v-show)
2. [**Binding Directives**](#binding-directives)
    - [`v-bind`](#v-bind)
    - [`v-on`](#v-on)
    - [`v-model`](#v-model)
    - [Event Modifiers](#event-modifiers)
3. [**Options API vs Composition API**](#options-api-vs-composition-api)
4. [**Watching for Changes**](#watching-for-changes)
    - [`watch`](#watch)
5. [**Component Communication**](#component-communication)
    - [`emits`](#emits)
6. [**Lifecycle Hooks**](#lifecycle-hooks)
    - [BeforeCreate & Created](#beforecreate--created)
    - [BeforeMount & Mounted](#beforemount--mounted)
    - [BeforeUnmount & Unmounted](#beforeunmount--unmounted)
7. [**Event Modifiers**](#vuejs-event-modifiers)
    - [`.stop`](#stop)
    - [`.prevent`](#prevent)
    - [`.capture`](#capture)
    - [`.self`](#self)
    - [`.once`](#once)
    - [`.passive`](#passive)
8. [**Iterating Over Object Properties**](#iterating-over-object-properties)

---
## NPM Commands

```shell
npm help
```  
> See all npm commands


```shell
npm install module_name
```  
> Install a dependence, you can also use npm i module_name

```shell
npm install module_name -D
```  
> Install a Development dependence

```shell
npm unninstall module_name
```  
> Remove dependence

```shell
npm update
```  
> Update modules

```shell
npm audit
```  
> Identifies and reports security vulnerabilities in project dependencies.

```shell
npm run script
```  
> Executes a custom command or task defined in `package.json` scripts.


---

## Vite Commands ⚡

```shell
npm create vite@latest
```  
> Start Vite with NPM

---

# Vue.js Documentation

## Conditional Rendering

### `v-if`
The `v-if` directive is used for conditional rendering in Vue.js. It renders the element or component only if the expression inside it evaluates to true.

```html
<div v-if="condition">Content to be rendered if condition is true</div>
```

### `v-else`
The v-else directive is used in conjunction with v-if to render content when the preceding v-if expression is false.

```html
<div v-if="condition">Content to be rendered if condition is true</div>
<div v-else>Content to be rendered if condition is false</div>
```

### `v-show`
The v-show directive also performs conditional rendering, but it toggles the element's visibility using CSS display property instead of adding or removing elements from the DOM.

```html
<div v-show="condition">Content to be shown or hidden based on condition</div>
```

# Binding Directives and API's

## `v-bind`

The `v-bind` directive is used to bind an attribute to an expression. It allows dynamic updating of an element's attribute based on the provided expression.

```html
<a v-bind:href="url">Click me</a>
```

## `v-model`

The v-model directive is a two-way binding for form inputs. It binds the input value to a variable, allowing changes in the input to update the variable, and vice versa.

```html
<input v-model="message" />
```

## `v-on`

The v-on directive is part of the Binding Directives and APIs and is used to attach event listeners to elements. It enables the execution of methods or expressions in response to events.

```html
<button v-on:click="handleClick">Click me</button>
```


# Options API vs Composition API
> In Vue.js, there are two main ways to structure a component: the Options API and the Composition API.

## Options API
Data, Props, Methods:
- data: Holds the component's data.
- props: Define the properties the component can receive.
- methods: Contains methods that can be called within the component.

## Composition API
Setup:
- setup: Used for configuring the component state, props, and other features.
- ref: Function used to create reactive data.
- reactive: Function used to create reactive objects.
- computed: Function used to create computed properties.
> Exemple:

```javascript
import { ref } from 'vue';

export default {
  setup() {
    const count = ref(0);

    const increment = () => {
      count.value++;
    };

    return { count, increment };
  },
};
```

# Component Communication : `emits`

The emits option is used to define custom events that a component can emit.

```javascript
export default {
  emits: ['custom-event'],
  methods: {
    handleClick() {
      this.$emit('custom-event', 'Event data');
    },
  },
};
```

# Lifecycle Hooks

## BeforeCreate & Created
The beforeCreate hook is called before the instance is initialized, and the created hook is called after the instance is created. 
At this point, the data observation and event/watcher setup have not been performed yet.

## BeforeMount & Mounted
The beforeMount hook is called just before the component is about to be mounted to the DOM, and the mounted hook is called after the component has been mounted.

## BeforeUnmount & Unmounted
The beforeUnmount hook is called just before a component is about to be unmounted, and the unmounted hook is called after the component has been unmounted.

---

# Vue.js Event Modifiers
In Vue.js, event modifiers are used to adjust the default behavior of events. They are attached to the event handler declaration and start with a dot.

## `.stop`

- Modifier: `.stop`
- Purpose: Calls `event.stopPropagation()`. Prevents the event from propagating to parent elements.

```html
   <a v-on:click.stop="handleClick">Click me</a>
```

## `.prevent`

- Modifier: `.prevent`
- Purpose: Calls event.preventDefault(). Prevents the default behavior of the event.

```html
<form v-on:submit.prevent="handleSubmit">Submit</form>
```

## `.capture`

- Modifier: `.capture`
- Purpose: Adds an event listener in the capture phase instead of the propagation phase.

```html
<div v-on:click.capture="handleClick">Capture Click</div>
```

## `.self`

- Modifier: `.self`
- Purpose: Triggers the handler only if the event originated from the element itself, not from children.

```html
<div v-on:click.self="handleClick">Click me (not from children)</div>
```

## `.once`

- Modifier: `.once`
- Purpose: The handler will be triggered at most once.

```html
<button v-on:click.once="handleClick">Click me once</button>
```


## `.passive`

- Modifier: `.passive`
- Purpose: Indicates to the browser that the handler will not call event.preventDefault(). Can improve scrolling performance on mobile devices.

```html
<div v-on:touchmove.passive="handleTouchMove">Touch Move</div>
```

### These modifiers can be combined as needed. For example:
```html
<a v-on:click.stop.prevent="handleClick">Click me</a>
```
<br>

# Iterating Over Object Properties

```javascript
<template>
  <div>
    <ul>
      <li v-for="(value, key) in user" :key="key">
        {{ key }}: {{ value }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      user: {
        name: 'John Doe',
        age: 25,
        occupation: 'Developer'
      }
    };
  }
};
</script>

```

# `v-for with v-if`

```javascript
<template>
  <div>
    <ul>
      <li v-for="item in items" :key="item.id" v-if="item.isActive">
        {{ item.name }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      items: [
        { id: 1, name: 'Item 1', isActive: true },
        { id: 2, name: 'Item 2', isActive: false },
        { id: 3, name: 'Item 3', isActive: true }
      ]
    };
  }
};
</script>
```

# Slots

Slots in Vue.js allow you to compose components in a flexible way by providing a mechanism for the parent component to distribute its content into the child component. This enables you to create reusable and customizable components.

## Basic Slot Example

```html
<template>
  <div>
    <slot></slot>
  </div>
</template>
```
In this example, the component defines a slot using the <slot></slot> syntax. This slot can be filled with content when using the component:

```js
<MyComponent>
  <p>This content will be placed inside the slot.</p>
</MyComponent>
```

The content provided between the opening and closing tags of MyComponent will be injected into the <slot></slot> in the component.

## Named Slots

```js
<template>
  <div>
    <slot name="header"></slot>
    <div>
      <slot></slot>
    </div>
    <slot name="footer"></slot>
  </div>
</template>
```

Here, the component has multiple named slots: header, the default slot (no name), and footer. When using the component, you can specify where the content should go:

```js
<MyComponent>
  <template v-slot:header>
    <h1>This is the header</h1>
  </template>

  <p>This content goes to the default slot.</p>

  <template v-slot:footer>
    <footer>Footer information</footer>
  </template>
</MyComponent>
```

## Scoped Slots
Scoped slots allow the child component to access data from the parent component:

```js
<template>
  <div>
    <slot :message="message"></slot>
  </div>
</template>
```
When using the component:

```js
<MyComponent>
  <template v-slot="{ message }">
    <p>{{ message }}</p>
  </template>
</MyComponent>
```
>Here, the message property from the parent component is passed to the slot, and the child component can use it.
