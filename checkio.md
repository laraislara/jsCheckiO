####Найти самую популярную букву

```js
function mostWanted(data) {
    return data.replace(/[^a-z]/gi,'').toLowerCase()
     .split('').sort().join('')
     .match(/(.)\1*/g)
     .sort((a,b)=> b.length !== a.length ? b.length-a.length : a.localeCompare(b))[0][0]
 }
```
#### Поиск длины самой длинной последовательности в строке

```js
function longRepeat(line) {
    if (line.length === 0) return 0;
    return line.match(/(.)\1*/g).sort((a,b) => b.length-a.length)[0].length;
}
```

#### Вернуть массив, состоящий только из неуникальных элементов данного массива

```js
function nonUniqueElements(data) {
    return data.filter(i => data.indexOf(i) !== data.lastIndexOf(i))
}
```

####Преобразовать римские цифры

```js
const NUM_TO_ROMAN = [
    [1000, 'M'],
    [900, 'CM'],
    [500, 'D'],
    [400, 'CD'],
    [100, 'C'],
    [90, 'XC'],
    [50, 'L'],
    [40, 'XL'],
    [10, 'X'],
    [9, 'IX'],
    [5, 'V'],
    [4, 'IV'],
    [1, 'I'],
]
```

```js
function romanNumerals(number) {
    let roman = '';
    while(number > 0){
        for (let [n,r] of NUM_TO_ROMAN){
            while(number >= n) {
                roman += r
                number -= n
            }
        }
    }
    return roman;
}
```

#### Деление без остатка на 15, 3, 5

```js
function fizzBuzz(data) {
    if (data%15 === 0) {
        return "Fizz Buzz";
    } else if (data%3 === 0) {
        return "Fizz";
    } else if (data%5 === 0) {
        return "Buzz";
    } else {
        return data.toString();
    }
}
```

####Предложения всегда должны начинаться с большой буквы и заканчиваться точкой

```js
function correctSentence(text) {
    if (!text) return '';
    text = text.charAt(0).toUpperCase() + text.slice(1);
    if (!text.endsWith('.')) {
        return text + '.'
    }
    return text;
}
```

####Для работы в онлайн кодере (убрать дубли)

```html
<div id='ccc'>
<p id='vvvv'>1,2,3,4,5,6,7,1,2,3,4,5</p>
</div>
```

```js
let p = document.getElementById('vvvv')
const data = p.textContent;
const uniqData = getUniq(parseData(data));
p.innerHTML = uniqData;

function getUniq(data) {
  let hashMap = {}
  for (let el of data) {
    hashMap[el] = true
  }
  return Object.keys(hashMap)
}

function parseData(data) {
	return data.split(',')
}
```

####Поиск неуникальных элементов (уникальных)

```js
function nonUniqueElements(data) {
  return data.filter(i => data.indexOf(i) !== data.lastIndexOf(i))
}
```

```js
function nonUniqueElements(data) {
   return data.filter(i => data.indexOf(i) === data.lastIndexOf(i))
}
```

#### Взять первое слово в строке

```js
function firstWord(text) {
    return text.match(/[a-zA-Z']+/)[0];
}
```

####Найти сумму элементов с четными индексами, затем перемножить эту сумму
и последний элемент исходного массива.

```js
function evenLast(data) {
    return data.filter((item, i) => i % 2 === 0)
    .reduce((prev, cur) => prev + cur, 0) * data[data.length - 1] || 0;
}
```

#### Нахождение второго вхождения элемента

```js
function secondIndex(text, symbol) {
    let indices = []
    let arrStr = text.split('')
    let idx = arrStr.indexOf(symbol)
    while (idx !== -1) {
        indices.push(idx);
        idx = arrStr.indexOf(symbol, idx + 1);
    }
    return indices[1];
}
```

####Найти текст, заключенный между двумя маркерами.

```js
function betweenMarkers(text, begin, end) {
    let begin_index = text.includes(begin) ? text.indexOf(begin) + begin.length : 0;
    let end_index = text.includes(end) ? text.indexOf(end) : text.length;
    return text.slice(begin_index, end_index);
}
```

####Найти только заглавные буквы и соединить

```js
function findMessage(data) {
    return data.replace(/[^A-Z]/g, '');
}
```

#### Проверить есть ли в исходной строке три слова подряд.

```js
function threeWords(data) {
    var re = /\s?[a-z]+\s[a-z]+\s[a-z]+\s?/gi;
    return re.test(data);
}
```

```js
function threeWords(data) {
    return /\D+\s\D+\s\D+/.test(data);
}
```

####Найти N-ую степень элемента в массиве с индексом N

```js
function indexPower(array, n){
    return Math.pow(array[n],n) || -1;
}
```

#### Разница между max и min элементами массива

```js
function mostNumbers(...args){
    return args.length === 0 ? 0 : Math.max(...args) - Math.min(...args)
}
```

#### Перемножить цифры в числе

```js
function digitsMultip(data) {
    return parseInt(data
		.toString()
    	.replace(/0+/g, '')
		.split('')
        .reduce((multiple, current) => multiple * current));
}
```

#### Найти все слова, которые появляются в обеих строках

```js
function commonWords(first, second) {
    let data = `${first},${second}`;
    let temp = {};
    return data
    .split(',')
    .filter(i => data.indexOf(i) !== data.lastIndexOf(i))
    .sort()
    .filter(i => temp[i] || !(temp[i]=!0))
    .join()
}
```

####Подсчитать число инверсий в последовательности.

```js
function countInversion(sequence){
    count = 0
    for(i = 0; i < sequence.length; i++){
        for(j = i + 1; j < sequence.length; j++){
            if(sequence[i] > sequence[j]) count++
        }
    }
    return count
}
```

#### Сортировка абсолютных значений

```js
function absoluteSorting(arr){
    return arr.sort((prev, next) => Math.abs(prev) - Math.abs(next))
}
```

#### Преобразовать строку в число в определенной системе исчесления

```js
function numberRadix(str_number, radix) {
    const res = Number.parseInt(str_number, radix)
    if (str_number.toLowerCase() === res.toString(radix)) {
        return res;
    } else {
        return -1;
    }
}
```

```js
function numberRadix(n1, radix){
    let n2 = n1.slice(0, n1.length -1);
    return parseInt(n1, radix) === parseInt(n2, radix) ? -1 : parseInt(n1, radix) || -1
}
```

#### Найти топ объектов. Определенное кол-во

```js
function biggerPrice(limit, data) {
    return data.sort((a,b) => b.price - a.price).slice(0,limit)
}
```