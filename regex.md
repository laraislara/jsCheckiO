#### Найти самую популярную букву

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
#### Убрать из строки повторяющиеся символы (гласные и согласные). Bird language. 

```js
function translate(phrase){
    const re = new RegExp(`([^${VOWELS}\\s])(.)`,'gi')
    phrase = phrase.replace(re,'$1')
    const re2 = new RegExp(`([${VOWELS}]){3}`,'gi')
    return phrase.replace(re2,'$1')
   }

function translate(phrase){
    return phrase
        .replace(/([^aeiouy ])\w/g,'$1')
        .replace(/([aeiouy]){3}/g,'$1');
  }
```

#### Взять первое слово в строке

```js
function firstWord(text) {
    return text.match(/[a-zA-Z']+/)[0];
}
```

#### Найти только заглавные буквы и соединить

```js
function findMessage(data) {
    return data.replace(/[^A-Z]/g, '');
}
```

#### Проверить есть ли в исходной строке три слова подряд.

```js
function threeWords(data) {
    const re = /\s?[a-z]+\s[a-z]+\s[a-z]+\s?/gi;
    return re.test(data);
}
```

```js
function threeWords(data) {
    return /\D+\s\D+\s\D+/.test(data);
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
