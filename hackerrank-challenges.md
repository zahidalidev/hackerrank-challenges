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
# Grading StudentS

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

# Apple and Orange

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

# Forming a Magic Square
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

# Extra Long Factorials
```js
const factorialize = (num) => {
    if (num === 0n) return 1n;
    return num * factorialize(num - 1n);
};
console.log(String(factorialize(BigInt(25))));

```

# Highest Value Palindrome
```js
function maximumPalinUsingKChanges(s, n, k) {
    let str = s;
    let palin = str.split('');

    // Iinitialize l and r by leftmost and
    // rightmost ends
    let l = 0;
    let r = n - 1;

    // first try to make let palindrome
    while (l < r) {
        // Replace left and right character by
        // maximum of both
        if (str[l] != str[r]) {
            palin[l] = palin[r] = Math.max(str[l], str[r]);
            k--;
        }
        l++;
        r--;
    }

    // If k is negative then we can't make
    // let palindrome
    if (k < 0) {
        return k;
    }

    l = 0;
    r = str.length - 1;

    while (l <= r) {

        // At mid character, if K>0 then change
        // it to 9
        if (l == r) {
            if (k > 0) {
                palin[l] = '9';
            }
        }

        // If character at lth (same as rth) is
        // less than 9
        if (palin[l] < '9') {
            /* If none of them is changed in the
            previous loop then subtract 2 from K
            and convert both to 9 */
            if (k >= 2 && palin[l] == str[l] && palin[r] == str[r]) {
                k -= 2;
                palin[l] = palin[r] = '9';
            }

            /* If one of them is changed
                in the previous
                loop then subtract 1 from K
                (1 more is
                subtracted already) and make them 9 */
            else if (k >= 1 && (palin[l] != str[l] || palin[r] != str[r])) {
                k--;
                palin[l] = palin[r] = '9';
            }
        }
        l++;
        r--;
    }

    return palin.join('');
}

// Driver code to test above methods
console.log(maximumPalinUsingKChanges('3943', 4, 1));

```

# CamelCase
```js
function countCamelCase(str) {
    return str.split(/(?=[A-Z])/).length;
}
console.log(countCamelCase("saveChangesInTheEditor"))

<!-- Out Put: 5 -->
```

# Super Reduced String
Reduce a string of lowercase characters in range ascii[‘a’..’z’]by doing a series of operations. In each operation, select a pair of adjacent letters that match, and delete them.
Delete as many characters as possible using this method and return the resulting string. If the final string is empty, return Empty String
```js
function superReducedString(s) {
    let str2 = s;
    if (typeof s == 'string') {
        str2 = s.split('');
    }
    if (str2.length == 0) return "Empty String";

    if (str2.length >= 2) {
        for (let j = 1; j < str2.length; j++) {
            if (str2[j] == str2[j - 1]) {
                str2.splice(j - 1, 2)
                return superReducedString(str2);
            }
        }
    }
    return str2.join('');
}
console.log(superReducedString("aabccba"))

<!-- Output: a -->
```

# Separate the Numbers
```js
function separateTheNumbers(s) {
    if (s.length === 0) {
        console.log('NO');
        return;
    }

    for (let i = 1; i <= s.length / 2; i++) {
        let j = 1;
        let chars = s.substr(0, i);
        let validString = chars;
        while (validString.length < s.length) {
            validString = validString + (parseInt(chars) + j);
            j++;
        }
        if (validString === s) {
            console.log(`YES ${chars}`);
            return;
        }
    }

    console.log('NO');
    return;
}
separateTheNumbers("202122");

<!-- Output: YES 20 -->
```

# Weighted Uniform Strings
![image](https://user-images.githubusercontent.com/46484008/120009276-3874bf00-bff5-11eb-81f7-42fd9aea021c.png)


```js
const alpha = {
    'a': 1,
    'b': 2,
    'c': 3,
    'd': 4,
    'e': 5,
    'f': 6,
    'g': 7,
    'h': 8,
    'i': 9,
    'j': 10,
    'k': 11,
    'l': 12,
    'm': 13,
    'n': 14,
    'o': 15,
    'p': 16,
    'q': 17,
    'r': 18,
    's': 19,
    't': 20,
    'u': 21,
    'v': 22,
    'w': 23,
    'x': 24,
    'y': 25,
    'z': 25,
}
function weightedUniformStrings(s, queries) {
    const tempArr = [];
    const ans = [];

    let val = 0;
    for (let i = 0; i < s.length; i++) {
        if (i == 0 || s[i] != s[i - 1]) {
            val = alpha[s[i]]
        } else {
            val = val + alpha[s[i]];
        }
        tempArr.push(val)
    }

    for (let i = 0; i < queries.length; i++) {
        if (tempArr.includes(queries[i])) {
            ans.push('Yes')
        } else {
            ans.push('No')
        }
    }
    return ans;
}
weightedUniformStrings("abccddde", [1, 3, 12, 5, 9, 10]);

<!-- Output: [ 'Yes', 'Yes', 'Yes', 'Yes', 'No', 'No' ] -->
```
# Palindrome Index
Given a string of lowercase letters in the range ascii[a-z], determine the index of a character that can be removed to make the string a palindrome. There may be more than one solution, but any will do. If the word is already a palindrome or there is no solution, return -1. Otherwise, return the index of a character to remove.

```js
function removeChar(str, index) {
    let p1 = str.substring(0, index);
    let p2 = str.substring(index + 1, str.length);
    let ans = p1 + p2;
    ans = ans.trim();
    return ans
}

function checkPaindrom(str) {
    for (let i = 0, j = str.length - 1; i < str.length; i++, j--) {
        if (str[i] != str[j]) {
            return false;
        }
    }
    return true;
}

function palindromeIndex(s) {
    let str = s;
    let removedIndex = -1;
    let len = str.length;
    for (let i = 0; i < len / 2; i++) {
        if (str[i] !== str[len - i - 1]) {
            if (i + 1 < len) {
                let poli = checkPaindrom(str.substring(i + 1, len - i))
                if (poli) {
                    return i;
                }
                return len - i - 1
            }

        }
    }
    return removedIndex;
}

console.log(palindromeIndex("aaab"));

<!-- Output: 3 -->
```

# Two Characters

![Screenshot from 2021-11-24 13-07-38](https://user-images.githubusercontent.com/46484008/143199191-36388d29-cdcb-4a8d-9bcd-849ffb9658ab.png)

```
let str = "asvkugfiugsalddlasguifgukvsa";

let uniCharStr = [];
for (let i = 0; i < str.length; i++) {
    if (!uniCharStr.includes(str[i])) {
        uniCharStr.push(str[i])
    }
}

let checkAlterStr = (str) => {
    for (let i = 0, j = 1; i < str.length - 2 && j < str.length - 2; i += 2, j += 2) {
        if (str[i] !== str[i + 2] || str[j] !== str[j + 2]) {
            return false;
        }
    }

    if (str.length % 2 == 1) {
        if (str[0] === str[str.length - 1]) {
            return true;
        } else {
            return false
        }
    }

    return true;
}

const findAlterStr = (str) => {
    
    if(str.length === 1){
        return 0;
    }else if(str.length === 2){
        return 2;
    }
   
    for (let i = 0; i < uniCharStr.length; i++) {
        for (let j = 0; j < uniCharStr.length; j++) {

            let tempStr = str;
            for (let t = 0; t < uniCharStr.length; t++) {

                if (t != i && t != j) {
                    let patt = new RegExp(uniCharStr[t], 'g');
                    tempStr = tempStr.replace(patt, '')
                    console.log(tempStr, uniCharStr[t])

                }
            }


            if (checkAlterStr(tempStr) && tempStr[0] !== tempStr[1]) {
                console.log("tempSt,,,,,,,,,,,,,,r: ", tempStr, tempStr.length)
                return tempStr.length;
            }
        }
        return 0;

    }

}

// console.log()
console.log(findAlterStr(str))

```
