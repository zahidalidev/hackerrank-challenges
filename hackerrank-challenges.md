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

# Mini-Max Sum
```js
let n = arr.length;
let sumArray = [];
for (let i = 0; i < n; i++) {
    let sum = 0;
    for (let j = 0; j < n; j++) {
        if (i != j) {
            sum = sum + arr[j]
            // console.log(i, j)
        }
    }
    sumArray.push(sum)
}

let min = Infinity;
let max = -Infinity;
for (let i = 0; i < sumArray.length; i++) {
    if (sumArray[i] < min) {
        min = sumArray[i]
    }
    if (sumArray[i] > max) {
        max = sumArray[i]
    }
}
console.log(min, max)
```
# Birthday Cake Candles
Example
candles = [4, 4, 1, 3]
The maximum height candles are 4 units high. There are 2 of them, so return 2.
```js
function birthdayCakeCandles(candles) {
    let n = candles.length;
    let max = 0;

    for (let i = 0; i < n; i++) {
        if (candles[i] > max) {
            max = candles[i]
        }
    }
    let count = 0;
    for (let i = 0; i < n; i++) {
        if (candles[i] == max) {
            count++;
        }
    }

    return count;
}
```

# Time Conversion
Given a time in 12-hour AM/PM format, convert it to military (24-hour) time.

Note: - 12:00:00AM on a 12-hour clock is 00:00:00 on a 24-hour clock.
- 12:00:00PM on a 12-hour clock is 12:00:00 on a 24-hour clock.
```js
function processData(input) {
    //Enter your code here
    var hh = parseInt(input.substr(0, 2));
    var mmss = input.substr(2, 6);
    var pm = input.substr(8) === 'PM';
    var is12 = hh === 12;
    var res = (is12 ? (pm ? 12: 0):(pm ? hh + 12: hh));
    console.log('' + (res < 10 ? '0': '') + res + mmss);
} 

```
