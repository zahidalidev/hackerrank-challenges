# 1- Diagonal Difference

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

# 2- Sales by Match

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

# 3- Staircase

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

# 4- Mini-Max Sum
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
# 5- Birthday Cake Candles
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

# 6- Time Conversion
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
# 7- Grading StudentS

Examples

GRADE = 84 round to (85 - 84 is less than 3)
GRADE = 29 do not round (result is less than 40)
GRADE = 57 do not round (60 - 57 is 3 or higher)
 
```js
let grades = [73, 67, 38, 33];

let n = grades.length;

for (let i = 0; i < n; i++) {
    if (grades[i] > 37) {
        if ((5 - (grades[i] % 5) + grades[i] - grades[i]) < 3) {
            grades[i] = grades[i] + (5 - (grades[i] % 5));
        }
    }
}
console.log(grades)
```

# 8- Apple and Orange

![image](https://user-images.githubusercontent.com/46484008/114458081-2fbc5b00-9bf8-11eb-989c-d4c6ab93de17.png)

```js

// sam's house lies between s and t
let s = 7;
let t = 10;

let a = 4;  //location of apple tree
let b = 12; //location of orange tree
let apples = [2, 3, -4];
let oranges = [3, -2, -4];
let appleCount = 0;
let orangeCount = 0;

for (let i = 0; i < apples.length; i++) {
    apples[i] = apples[i] + a;
    if (apples[i] >= s && apples[i] <= t) {
        appleCount++;
    }
}
for (let i = 0; i < oranges.length; i++) {
    oranges[i] = oranges[i] + b;
    if (oranges[i] >= s && oranges[i] <= t) {
        orangeCount++;
    }
}

console.log(appleCount, orangeCount)

```

# 9- Forming a Magic Square
We define a magic square to be an  matrix of distinct positive integers from  to  where the sum of any row, column, or diagonal of length  is always equal to the same number: the magic constant.

```js

let s = [
    [4, 8, 2],
    [4, 5, 7],
    [6, 1, 6]
]

// 8 unique possibiities of magic squares
const magicSquarePossibilites = [
    [8, 1, 6, 3, 5, 7, 4, 9, 2],
    [4, 3, 8, 9, 5, 1, 2, 7, 6],
    [2, 9, 4, 7, 5, 3, 6, 1, 8],
    [6, 7, 2, 1, 5, 9, 8, 3, 4],
    [6, 1, 8, 7, 5, 3, 2, 9, 4],
    [8, 3, 4, 1, 5, 9, 6, 7, 2],
    [4, 9, 2, 3, 5, 7, 8, 1, 6],
    [2, 7, 6, 9, 5, 1, 4, 3, 8]
];


// Converting to single dimension array to check distance from magic square possibiities
let singleArray = []
for (let i = 0; i < s.length; i++) {
    for (let j = 0; j < s.length; j++) {
        singleArray.push(s[i][j])
    }
}

// Calculating distance using single 
let minCost = Math.min();
for (let i = 0; i < magicSquarePossibilites.length; i++) {
    let cost = 0;
    for (let j = 0; j < singleArray.length; j++) {
        cost += Math.abs(singleArray[j] - magicSquarePossibilites[i][j]);
        console.log(cost)
    }
    if (cost < minCost) minCost = cost;
}
console.log(minCost)
```

# -10 Extra Long Factorials
```js
const factorialize = (num) => {
    if (num === 0n) return 1n;
    return num * factorialize(num - 1n);
};
console.log(String(factorialize(BigInt(25))));

```
