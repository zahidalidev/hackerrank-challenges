# Diagonal Difference

```js
let a = [
    [1, 2, 3],
    [4, 5, 6],
    [9, 8, 9]
]

let d1 = 0;
let d2 = 0;

for (let i = 0; i < a.length; i++) {
    for (let j = 0; j < a.length; j++) {
        if (i - j == 0) {
            d1 = d1 + a[i][j]
        }
        if ((i + j) == (a.length - 1)) {
            d2 = d2 + a[i][j]
        }
    }

}

console.log(Math.abs(d1 - d2))

```

# Sales by Match

```js
let arr = [10, 20, 20, 10, 10, 30, 50, 10, 20]

let temp = []
let p = 0;
for (let i = 0; i < arr.length; i++) {
    if (temp.includes(arr[i])) {
        console.log(arr[i], temp)
        let index = temp.indexOf(arr[i])
        temp.splice(index, 1)
        p++;
    } else {
        temp.push(arr[i])
    }
}
console.log('Total pairs: ', p)
```

# Staircase

```js
let l = 6;
for (let i = 0; i < l; i++) {
    let spaceHashes = '';
    for (let j = l - 1; j > i; j--) {
        spaceHashes = spaceHashes + " "
    }
    for (let j = 0; j < i + 1; j++) {
        spaceHashes = spaceHashes + "#"
    }
    console.log(spaceHashes)
    spaceHashes = ''
}
```
