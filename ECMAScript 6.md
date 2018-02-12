# ECMAScript 6

## Destructuring

### Array destructuring

语法

```js
let [a, b] = [1, 2]
console.log(a, b) // 1,2
```

默认值

```js
let [a, b, c = 3] = [1, 2]
console.log(a, b, c) // 1,2,3
```

fail-soft

```js
let [a, b, c] = [1, 2]
console.log(a, b, c) // 1,2,undefined
```

rest

```js
let [a, ...b] = [1, 2, 3]
console.log(a, b) // 1,[2,3]
```

ignore

```js
let [a, , b] = [1, 2, 3]
console.log(a, b) // 1,3
```

swapping

```js
let a = 1
let b = 2
;[a, b] = [b, a]
console.log(a, b) // 2,1
```

### Object destructuring

语法

```js
const o = { a=1, b=2 }
const { a, b } = o
console.log(a, b) //  1,2
```

别名

```js
const o = {a=1, b=2}
const { a:a1, a:a2, b:bb=3 } = o
console.log(a1, a2, bb) //  1,1,2
```

默认值

```js
const o = {a=1, b=2}
const { a=3, b=4, c=5 } = o
console.log(a, b, c) //  1,2,5
```

Nested

```js
const metadata = {
  title: 'Scratchpad',
  translations: [
    {
      locale: 'de',
      localization_tags: [],
      last_edit: '2014-04-14T08:43:37',
      url: '/de/docs/Tools/Scratchpad',
      title: 'JavaScript-Umgebung'
    }
  ],
  url: '/en-US/docs/Tools/Scratchpad'
}

const { title: englishTitle, translations: [{ title: localeTitle }] } = metadata

console.log(englishTitle) // "Scratchpad"
console.log(localeTitle) // "JavaScript-Umgebung"
```

计算属性作为解构的 key

```js
let key = 'z'
let { [key]: foo } = { z: 'bar' }

console.log(foo) // "bar"
```

别名，默认值，rest，swapping variable，用计算属性作为解构的 key
