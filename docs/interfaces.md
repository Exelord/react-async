# Interfaces

React Async provides several ways to use it. The classic interface is through the `<Async>` component, which is
backwards compatible to React v16.3. More recent React applications will be using hooks, of which two are provided:
`useAsync` and `useFetch`. Functionally, `<Async>` and `useAsync` are equivalent. `useFetch` is a special type of `useAsync` which is tied to the native `fetch` API.

React Async accepts a range of [configuration options](/api/options) and returns a set of [render props](/api/props).
The way you use these differs slightly between the `useAsync` and `useFetch` hooks, and the `<Async>` component.

## `<Async>`

```jsx
<Async {...options}>{props => ...}</Async>
```

- [`options`](/options) Configuration options
- [`props`](/props) Render props object

> We recommend that you pass the options individually, rather than using JSX [spread attributes]. React Async uses
> [render props] to return its state back to you, so it can be used by other components further down the tree.

[spread attributes]: https://reactjs.org/docs/jsx-in-depth.html#spread-attributes
[render props]: https://reactjs.org/docs/render-props.html

## `useAsync`

```js
const props = useAsync(options)
```

- [`props`](/props) Render props object
- [`options`](/options) Configuration options

> We recommend that you pass `options` as an inline object literal, and that you [destructure] the `props` object to
> extract the properties you need, unless you have multiple instances in the same component.

[destructure]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment#Object_destructuring

## `useFetch`

```js
const props = useFetch(resource, init, options)
```

- [`props`](/props) Render props object
- [`resource`][fetch api] The resource you want to fetch
- [`init`][fetch api] Custom request options
- [`options`](/options) Configuration options

[fetch api]: https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/fetch#Syntax