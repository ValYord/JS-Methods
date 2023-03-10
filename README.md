# JS-Methods
Reverat by Valer Yordanyan

## NUMBER.METHODS


### 1number.isFinite(),

Определяет, является ли переданное значение конечным числом.
если число является конечным Метод Number.isFinite()возвращает true.
В отличии от глобальной функции isFinite(), этот метод принудительно не преобразует параметр в число. Это означает, что он возвращает true только для конечных значений числового типа.

Here`s an exampls

```js
Number.isFinite(Infinity);  // false    Nan ,Infinity, -Infinity всегда возвращает  false
Number.isFinite(NaN);       // false
Number.isFinite(-Infinity); // false

Number.isFinite(0);         // true
Number.isFinite(2e64);      // true

Number.isFinite('0');       // false, при использовании глобальной
                            // функции isFinite('0') было бы true
                            
                            
isFinite('0'); // true; разница между isFinite() и Number.isFinite
Number.isFinite("0"); // false                           

```


### 2Number.isInteger()

Метод Number.isInteger() определяет, является ли переданное значение целым числом.
Если целевое значение является целым числом, возвращает true. Если значение NaN или Infinity, то возвращает false. Метод также возвращает true, если это вещественное число с точкой, которое может быть представлено в целочисленном виде.
Here`s an exampls
```js

Number.isInteger(0);         // true
Number.isInteger(1);         // true
Number.isInteger(-100000);   // true
Number.isInteger(99999999999999999999999); // true

Number.isInteger(0.1);       // false
Number.isInteger(Math.PI);   // false

Number.isInteger(NaN);       // false
Number.isInteger(Infinity);  // false
Number.isInteger(-Infinity); // false
Number.isInteger('10');      // false
Number.isInteger(true);      // false
Number.isInteger(false);     // false
Number.isInteger([1]);       // false

```

Обратите внимание, что некоторые числовые литералы, хотя и выглядят как нецелые числа, на самом деле представляют целые числа — из-за предела точности кодирования чисел с плавающей запятой ECMAScript (IEEE-754). 
Here`s an exampls

```js

Number.isInteger(5.0);       // true
Number.isInteger(5.000000000000001); // false
Number.isInteger(5.0000000000000001); // true

```

### 3Number.isNaN()

Метод Number.isNaN() определяет, является ли переданное значение NaN. Это более надёжная версия оригинальной глобальной функции isNaN().
Number.isNaN() метод в JavaScript используется для проверки, является ли переданное значение NaN (Not-A-Number). Этот метод отличается от встроенной функции isNaN(), которая может возвращать true для значений, которые не являются числами.

here`s an exampls
```js

Number.isNaN(NaN); // true
Number.isNaN(Number.NaN); // true
Number.isNaN(0 / 0) // true

// При использовании глобальной функции isNaN() это всё будет true
Number.isNaN('NaN');      // false
Number.isNaN(undefined);  // false
Number.isNaN({});         // false
Number.isNaN('blabla');   // false

// А это всё в любом случае будет false
Number.isNaN(true);
Number.isNaN(null);
Number.isNaN(37);
Number.isNaN('');
```

### 4Number.isSafeInteger()

Метод Number.isSafeInteger() определяет, является ли переданное значение безопасным целым числом.
Безопасные целые числа состоят из всех целых чисел в диапазоне от -(253 - 1) до 253 - 1 включительно (± 9007199254740991 или ± 9,007,199,254,740,991).

Безопасное целое число это такое число, которое:

может быть точно представлено числом IEEE-754 двойной точности и
чьё представление IEEE-754 не может быть результатом округления любого другого целого числа, соответствующего представлению IEEE-754.

here`s an exampls.
```js
Number.isSafeInteger(3);                    // true
Number.isSafeInteger(Math.pow(2, 53));      // false
Number.isSafeInteger(Math.pow(2, 53) - 1);  // true
Number.isSafeInteger(NaN);                  // false
Number.isSafeInteger(Infinity);             // false
Number.isSafeInteger('3');                  // false
Number.isSafeInteger(3.1);                  // false
Number.isSafeInteger(3.0);                  // true
```

### 5Number.parseFloat()


Метод Number.parseFloat() разбирает строковый аргумент и возвращает число с плавающей запятой. Этот метод ведёт себя идентично глобальной функции parseFloat() и является частью ECMAScript 6 (его целью является модуляризация глобальных сущностей).

```js
Number.parseFloat("54.5"); // 54.5
Number.parseFloat("32"); // 32 
Number.parseFloat("12.345e6"); // 1234500 
Number.parseFloat("string"); // NaN
```


### 6Number.parseInt()


Метод Number.parseInt() разбирает строковый аргумент и возвращает целое число. Этот метод ведёт себя идентично глобальной функции parseInt() и является частью ECMAScript 6 (его целью является модуляризация глобальных сущностей).

here`s an sintacs
```js
Number.parseInt(string[, radix])
```
Вот примеры использования parseInt():

```js
Number.parseInt("123"); // 123
Number.parseInt("1010", 2); // 10
Number.parseInt("FF", 16); // 255

```
В первом примере parseInt() преобразует строку "123" в целое число 123.

Во втором примере parseInt() преобразует строку "1010" в целое число 10, используя основание системы счисления 2 (двоичная система счисления).

В третьем примере parseInt() преобразует строку "FF" в целое число 255, используя основание системы счисления 16 (шестнадцатеричная система счисления).



### 7Number.prototype.toExponential()

Метод toExponential() возвращает строку, представляющую объект Number в экспоненциальной записи.

```js
Синтаксис

toExponential([fractionDigits])
```
Метод toExponential() в JavaScript используется для преобразования числа в экспоненциальную форму. Этот метод может принимать один аргумент - количество знаков после десятичной точки.

Вот примеры использования toExponential():

```js
console.log((123456789).toExponential()); // 1.23457e+8
console.log((123456789).toExponential(4)); // 1.2346e+8
```
В первом примере toExponential() преобразует число 123456789 в экспоненциальную форму с десятью знаками после десятичной точки.

Во втором примере toExponential() преобразует число 123456789 в экспоненциальную форму с четырьмя знаками после десятичной точки.


### 8Number.prototype.toFixed()


Метод toFixed() форматирует число, используя запись с фиксированной запятой.
Синтаксис
```js
.toFixd()
.toFixed([digits])
```

Метод toFixed()преобразует число в строку.

Метод toFixed()округляет строку до указанного числа десятичных знаков.
here`s an exampls

```js
let num = 12345.6789;

num.toFixed();       // Вернёт '12346': обратите внимание на округление, дробной части нет
num.toFixed(1);      // Вернёт '12345.7': обратите внимание на округление
num.toFixed(6);      // Вернёт '12345.678900': обратите внимание на дополнение нулями
(1.23e+20).toFixed(2);  // Вернёт '123000000000000000000.00'
(1.23e-10).toFixed(2);  // Вернёт '0.00'
2.34.toFixed(1);        // Вернёт '2.3'
-2.34.toFixed(1);       // Вернёт -2.3 (в соответствии с приоритетом операций,
                        // отрицательные числовые литералы не возвращают строку...)
(-2.34).toFixed(1);     // Вернёт '-2.3' (...до тех пор, пока вы не заключите их в круглые скобки)

```


### 9.toLocaleString()

Метод toLocaleString() возвращает объект Date в виде строки с использованием настроек локали.

Язык по умолчанию зависит от региональных настроек на вашем компьютере.
Метод toLocaleString() возвращает строку с языкозависимым представлением числа.

Новые аргументы locales и options позволяют приложениям определять язык, чьё поведение и соглашения по форматированию которого оно хочет использовать. В старых реализациях, игнорирующих аргументы locales и options, используемая локаль и форма возвращённой строки целиком зависит от реализации.

here`s an exampls

```js
let number = 3500;

console.log(number.toLocaleString()); // Отобразит '3,500' в локали U.S. English

let number = 123456.789;

// В Германии в качестве разделителя целой и дробной части используется запятая, а в качестве разделителя разрядов - точка
console.log(number.toLocaleString('de-DE'));
// → 123.456,789

// В России в качестве разделителя целой и дробной части используется запятая, а в качестве разделителя разрядов - пробел
console.log(number.toLocaleString('ru-RU'));
// → 123 456,789

// В большинстве арабоговорящих стран используют настоящие арабские цифры
console.log(number.toLocaleString('ar-EG'));
// → ١٢٣٤٥٦٫٧٨٩


// Запрашиваем формат валюты
console.log(number.toLocaleString('de-DE', { style: 'currency', currency: 'EUR' }));
// → 123.456,79 €

console.log(number.toLocaleString('ru-RU', { style: 'currency', currency: 'RUB' }));
// → 123 456,79 ₽

// Японская йена не использует младшие единицы
console.log(number.toLocaleString('ja-JP', { style: 'currency', currency: 'JPY' }))
// → ￥123,457

```


### 10.toPrecision()


Метод toPrecision() возвращает строку, представляющую объект Number с указанной точностью.
Метод toPrecision()форматирует число до указанной длины.

Добавляются десятичная точка и нули (при необходимости) для создания указанной длины.
```js
let numObj = 5.123456;

console.log(numObj.toPrecision());    // выведет '5.123456'
console.log(numObj.toPrecision(5));   // выведет '5.1235'
console.log(numObj.toPrecision(2));   // выведет '5.1'
console.log(numObj.toPrecision(1));   // выведет '5'

numObj = 0.000123;

console.log(numObj.toPrecision());    // выведет '0.000123'
console.log(numObj.toPrecision(5));   // выведет '0.00012300'
console.log(numObj.toPrecision(2));   // выведет '0.00012'
console.log(numObj.toPrecision(1));   // выведет '0.0001'

// Обратите внимание, что если заданного количества разрядов
// недостаточно для точного отображения целой части числа,
// значение может быть возвращено в экспоненциальной записи.
console.log((1234.5).toPrecision(2)); // выведет '1.2e+3'
```


В этом примере метод toPrecision() вызывается на числе и передается количество значимых цифр, которые нужно отобразить. Метод возвращает строковое представление числа, отформатированное с указанным количеством значимых цифр. Строка может содержать научную нотацию, в зависимости от числа и количества указанных значимых цифр.


### 11 .toString()


Метод toString() возвращает строковое представление указанного объекта Number.
У каждого объекта JavaScript есть toString()метод.

Этот toString()метод используется внутри JavaScript, когда объект необходимо отобразить в виде текста (например, в HTML) или когда объект необходимо использовать в виде строки.
Синтаксис

.toString([radix])

Параметры

radix

    Необязательный параметр. Целое число между 2 и 36, определяющее основание системы счисления, используемой для представления числового значения.


here`s an exampls
```js
let count = 10;

console.log(count.toString());    // Выведет '10'
console.log((17).toString());     // Выведет '17'


(123).toString()); // "123"
(123).toString(2); // "1111011"
(123).toString(16); // "7b"


```

### 12 number.valueOf()


Метод valueOf() возвращает примитивное значение объекта Number.
Этот метод обычно вызывается внутренними механизмами движка JavaScript, а не явно в коде.

Метод valueOf() в прототипе JavaScript Number возвращает примитивное значение объекта Number. Этот метод вызывается автоматически, когда объект Number используется в контексте, требующем примитивного значения, таким как при использовании оператора + или при сравнении двух чисел.

Вот пример использования метода valueOf():

javascript
Copy code
```js
let num = new Number(123);
console.log(num.valueOf()); // 123
```
В этом примере создается объект Number со значением 123. Когда метод valueOf() вызывается для этого объекта, он возвращает примитивное значение 123.

Обратите внимание, что метод valueOf() вызывается автоматически в большинстве случаев, поэтому вам не нужно вызывать его явно. Однако он может быть полезен в некоторых ситуациях, когда вам нужно извлечь примитивное значение объекта Number.

## Boolean Methods.

### 1 Boolean.prototype.toString()


Метод toString() возвращает строковое представление указанного объекта Boolean.
```js
let bool = true;
console.log(bool.toString()); // 'true'
```

### 2 Boolean.prototype.valueOf()

Метод valueOf объекта Boolean возвращает примитивное значение объекта или литерала логического типа.

Этот метод обычно вызывается внутри движка JavaScript, а не явно в коде.

```js

let bool = false;
console.log(bool.valueOf()) // false;
```

## Array Methods

### 1 Array.prototype.at()
Метод at() принимает значение в виде целого числа и возвращает элемент массива с данным индексом. В качестве аргумента метод принимает положительные и отрицательные числа. При отрицательном значении отсчёт происходит с конца массива.Элемент массива, соответствующий переданному индексу. Если переданный индекс не может быть найден, возвращает undefined.Обычной практикой является получении числа элементов массива length и последующее вычисление значения индекса — например, array[array.length - 1]. Метод at() разрешает относительную индексацию, поэтому может быть сокращено до array.at(-1).

Метод at() — это generic. Он ожидает только, что значение this будет иметь свойство length и свойства с числовыми ключом.

```js
let arr = [1, 2, 3, 4, 5];
let element = arr.at(-1);
console.log(element); // Output: 5
```


### 2 Array.prototype.concat()

Метод concat() возвращает новый массив, состоящий из массива, на котором он был вызван, соединённого с другими массивами и/или значениями, переданными в качестве аргументов.Метод concat не изменяет данный массив или любой из массивов, переданных в аргументах, а вместо этого возвращает поверхностную копию, содержащую копии тех элементов, что были объединены с исходными массивами. Элементы оригинальных массивов копируются в новый массив по следующим правилам:

exampl
```js
let alpha = ['a', 'b', 'c'],
    numeric = [1, 2, 3];

let alphaNumeric = alpha.concat(numeric);

console.log(alphaNumeric); // Результат: ['a', 'b', 'c', 1, 2, 3]
```

### 3 Array.prototype.copyWithin()

Метод copyWithin() копирует последовательность элементов массива внутри него в позицию, начинающуюся по индексу target. Копия берётся по индексам, задаваемым вторым и третьим аргументами start и end. Аргумент end является необязательным и по умолчанию равен длине массива.

syntax

array.copyWithin(target, start[, end]);

target

    Начальный индекс позиции цели, куда копировать элементы.
start

    Начальный индекс позиции источника, откуда начинать копировать элементы.
end

    Необязательный параметр. Конечный индекс позиции источника, где заканчивать копировать элементы, не включая элемент на позиции end.
    

```js
[1, 2, 3, 4, 5].copyWithin(0, 3);
// [4, 5, 3, 4, 5]

[1, 2, 3, 4, 5].copyWithin(0, 3, 4);
// [4, 2, 3, 4, 5]

[1, 2, 3, 4, 5].copyWithin(0, -2, -1);
// [4, 2, 3, 4, 5]
```


### 4 Array.prototype.entries()

Метод entries() возвращает новый объект итератора массива Array Iterator, содержащий пары ключ / значение для каждого индекса в массиве
```js
const array = ["a", "b", "c"];
const arrayEntries = array.entries();

for (const element of arrayEntries) {
  console.log(element);
}

// [0, 'a']
// [1, 'b']
// [2, 'c']
```
### 5 Array.prototype.every()

Метод every() проверяет, удовлетворяют ли все элементы массива условию, заданному в передаваемой функции.

Синтаксис

arr.every(callback(currentValue[, index[, array]])[, thisArg])
Метод every() вызывает переданную функцию callback один раз для каждого элемента, присутствующего в массиве до тех пор, пока не найдёт такой, для которого callback вернёт ложное значение (значение, становящееся равным false при приведении его к типу Boolean). Если такой элемент найден, метод every() немедленно вернёт false. В противном случае, если callback вернёт true для всех элементов массива, метод every() вернёт true. Функция callback вызывается только для индексов массива, имеющих присвоенные значения; она не вызывается для индексов, которые были удалены или которым значения никогда не присваивались.
```js
function isBigEnough(element, index, array) {
  return element >= 10;
}
[12, 5, 8, 130, 44].every(isBigEnough);   // false
[12, 54, 18, 130, 44].every(isBigEnough); // true
```

### 6 Array.prototype.fill()


Метод fill()заполняет указанные элементы массива значением.
Метод fill()перезаписывает исходный массив.
Можно указать начальную и конечную позиции. Если нет, все элементы будут заполнены.
Метод fill принимает до трёх аргументов — value, start и end. Аргументы start и end являются необязательными со значениями по умолчанию, равными 0 и length объекта this соответственно.

```js
const array1 = [1, 2, 3, 4];

// Fill with 0 from position 2 until position 4
console.log(array1.fill(0, 2, 4));
// Expected output: Array [1, 2, 0, 0]

// Fill with 5 from position 1
console.log(array1.fill(5, 1));
// Expected output: Array [1, 5, 5, 5]

console.log(array1.fill(6));
// Expected output: Array [6, 6, 6, 6]
```
### 7 Array.prototype.filter()

Метод filter() создаёт новый массив со всеми элементами, прошедшими проверку, задаваемую в передаваемой функции.

```js
let arr = [1, 2, 3, 4, 5];
let filteredArr = arr.filter(value => value % 2 === 0);
console.log(filteredArr); // Output: [2, 4]
```
Метод filter() вызывает переданную функцию callback один раз для каждого элемента, присутствующего в массиве, и создаёт новый массив со всеми значениями, для которых функция callback вернула значение, которое может быть приведено к true. Функция callback вызывается только для индексов массива с уже определёнными значениями; она не вызывается для индексов, которые были удалены или которым значения никогда не присваивались. Элементы массива, не прошедшие проверку функцией callback, просто пропускаются и не включаются в новый массив.


### 8 Array.prototype.find()

Метод find() возвращает значение первого найденного в массиве элемента, которое удовлетворяет условию переданному в callback функции. В противном случае возвращается undefined.
Синтаксис

arr.find(callback[, thisArg])
Метод find вызывает переданную функцию callback один раз для каждого элемента, присутствующего в массиве, до тех пор, пока она не вернёт true. Если такой элемент найден, метод find немедленно вернёт значение этого элемента. В противном случае, метод find вернёт undefined.

```js
let arr = [1, 2, 3, 4, 5];
let result = arr.find(value => value > 3);
console.log(result); // Output: 4

```
### 9 Array.prototype.findIndex()

Метод findIndex() возвращает индекс в массиве, если элемент удовлетворяет условию проверяющей функции. В противном случае возвращается -1.
Метод findIndex()возвращает индекс (позицию) первого элемента, прошедшего проверку.

Синтаксис

arr.findIndex(callback[, thisArg])
Метод findIndex вызывает переданную функцию callback один раз для каждого элемента, присутствующего в массиве, до тех пор, пока она не вернёт true. Если такой элемент найден, метод findIndex немедленно вернёт индекс этого элемента. В противном случае, метод findIndex вернёт -1. 
```js
let arr = [1, 2, 3, 4, 5];
let result = arr.findIndex(value => value > 3);
console.log(result); // Output: 3
```
### 10 Array.prototype.findLast()

findLast()Метод перебирает массив в обратном порядке и возвращает значение первого элемента, удовлетворяющего предоставленной функции тестирования. Если никакие элементы не удовлетворяют функции тестирования, возвращается undifiend.
The findLast()метод является итеративным методом . Он вызывает предоставленный callbackFnфункция один раз для каждого элемента в массиве в порядке убывания индекса, пока callbackFnвозвращает истинное значение. findLast()затем возвращает этот элемент и прекращает итерацию по массиву. Если callbackFnникогда не возвращает истинное значение, findLast()возвращается undefined. 
```js
nst array1 = [5, 12, 50, 130, 44];

const found = array1.findLast((element) => element > 43);

console.log(found);
// Expected output: 44
```

### 11 Array.prototype.findLastIndex()

findLastIndex()Метод выполняет итерацию массива в обратном порядке и возвращает индекс первого элемента, который удовлетворяет предоставленной функции тестирования. Если никакие элементы не удовлетворяют функции тестирования, возвращается -1.

```js
const array1 = [5, 12, 50, 130, 44];

const isLargeNumber = (element) => element > 45;

console.log(array1.findLastIndex(isLargeNumber));
// Expected output: 3
// Index of element with value: 130
```

### 12 Array.prototype.flat()

Метод flat() возвращает новый массив, в котором все элементы вложенных подмассивов были рекурсивно "подняты" на указанный уровень depth.
exampls
```js
var arr1 = [1, 2, [3, 4]];
arr1.flat();
// [1, 2, 3, 4]

var arr2 = [1, 2, [3, 4, [5, 6]]];
arr2.flat();
// [1, 2, 3, 4, [5, 6]]

var arr3 = [1, 2, [3, 4, [5, 6]]];
arr3.flat(2);
// [1, 2, 3, 4, 5, 6]

var arr4 = [1, 2, [3, 4, [5, 6, [7, 8, [9, 10]]]]];
arr4.flat(Infinity);
// [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```


### 13 Array.prototype.flatMap()

Метод flatMap() сначала применяет функцию к каждому элементу, а затем преобразует полученный результат в плоскую структуру и помещает в новый массив. Это идентично map функции, с последующим применением функции flat с параметром depth ( глубина ) равным 1, но flatMap часто бывает полезным, так как работает немного более эффективно.
```js
array.flatMap(callback(element[, index[, array]])[, thisArg])
```
```js
exampls
let arr1 = [1, 2, 3, 4];

arr1.map(x => [x * 2]);
// [[2], [4], [6], [8]]

arr1.flatMap(x => [x * 2]);
// [2, 4, 6, 8]

// выравнивается только один уровень
arr1.flatMap(x => [[x * 2]]);
// [[2], [4], [6], [8]]
```

### 14 Array.prototype.forEach()

Метод forEach() выполняет указанную функцию один раз для каждого элемента в массиве.
```js
array.forEach(callback(element[, index[, array]])[, thisArg])
```
Метод forEach() выполняет функцию callback один раз для каждого элемента, находящегося в массиве в порядке возрастания. Она не будет вызвана для удалённых или пропущенных элементов массива. Однако, она будет вызвана для элементов, которые присутствуют в массиве и имеют значение undefined.
```js
let arr = [1, 2, 3, 4];

arr.forEach(function(element, index, array) {
  console.log(element, index);
});

// Output:
// 1 0
// 2 1
// 3 2
// 4 3
```

### 15 Array.from()

Метод Array.from() создаёт новый экземпляр Array из массивоподобного или итерируемого объекта.

```js
console.log(Array.from('foo'));
// Expected output: Array ["f", "o", "o"]

console.log(Array.from([1, 2, 3], x => x + x));
// Expected output: Array [2, 4, 6]
```
Синтаксис
```js
Array.from(arrayLike[, mapFn[, thisArg]])
```
     

Array.from() имеет необязательный параметр mapFn, который позволяет вам выполнять функцию map для каждого элемента создаваемого массива (или его подкласса). Проще говоря, вызов Array.from(obj, mapFn, thisArg) эквивалентен цепочке Array.from(obj).map(mapFn, thisArg), за исключением того, что он не создаёт промежуточного массива. Это особенно важно для некоторых подклассов массива, вроде типизированных массивов, поскольку промежуточный массив неизбежно приведёт к усечению значений, чтобы они подпали под подходящий тип.


### 16 Array.prototype.includes()


Метод includes() определяет, содержит ли массив определённый элемент, возвращая в зависимости от этого true или false.

Синтаксис
```js
arr.includes(searchElement[fromIndex = 0])
```

exampls
```js
const array1 = [1, 2, 3];

console.log(array1.includes(2));
// Expected output: true

const pets = ['cat', 'dog', 'bat'];

console.log(pets.includes('cat'));
// Expected output: true

console.log(pets.includes('at'));
// Expected output: false
```


### 17 Array.prototype.indexOf()


Метод indexOf() возвращает первый индекс, по которому данный элемент может быть найден в массиве или -1, если такого индекса нет.
Индекс, с которого начинать поиск. Если индекс больше или равен длине массива, возвращается -1, что означает, что массив даже не просматривается. Если индекс является отрицательным числом, он трактуется как смещение с конца массива. Обратите внимание: если индекс отрицателен, массив всё равно просматривается от начала к концу. Если рассчитанный индекс оказывается меньше 0, поиск ведётся по всему массиву. Значение по умолчанию равно 0, что означает, что просматривается весь массив.

```js
let arr = [1, 2, 3, 4];

console.log(arr.indexOf(3)); // 2
console.log(arr.indexOf(5)); // -1
```


### 18 Array.isArray()

Метод Array.isArray() возвращает true, если объект является массивом и false, если он массивом не является.
exampls 
```js
// Все следующие вызовы вернут true
Array.isArray([]);
Array.isArray([1]);
Array.isArray(new Array());
// Малоизвестный факт: Array.prototype сам является массивом:
Array.isArray(Array.prototype);

// Все следующие вызовы вернут false
Array.isArray();
Array.isArray({});
Array.isArray(null);
Array.isArray(undefined);
Array.isArray(17);
```


### 19 Array.prototype.join()

Метод join() объединяет все элементы массива (или массивоподобного объекта) в строку.
Определяет строку, разделяющую элементы массива. В случае необходимости тип разделителя приводится к типу Строка. Если он не задан, элементы массива разделяются запятой ','. Если разделитель - пустая строка, элементы массива ничем не разделяются в возвращаемой строке.
exampls
```js
const elements = ['Fire', 'Air', 'Water'];

console.log(elements.join());
// Expected output: "Fire,Air,Water"

console.log(elements.join(''));
// Expected output: "FireAirWater"

console.log(elements.join('-'));
// Expected output: "Fire-Air-Water"
```

### 20 Array.prototype.keys()

Метод keys() возвращает новый итератор массива Array Iterator, содержащий ключи каждого индекса в массиве.

```js
const array1 = ['a', 'b', 'c'];
const iterator = array1.keys();

for (const key of iterator) {
  console.log(key);
}

// Expected output: 0
// Expected output: 1
// Expected output: 2
```
### 21 Array.prototype.lastIndexOf()

Метод lastIndexOf() возвращает последний индекс, по которому данный элемент может быть найден в массиве или -1, если такого индекса нет. Массив просматривается от конца к началу, начиная с индекса fromIndex.

Синтаксис
``js
arr.lastIndexOf(searchElement[, fromIndex = arr.length])

let array = [2, 5, 9, 2];
array.lastIndexOf(2);     // 3
array.lastIndexOf(7);     // -1
array.lastIndexOf(2, 3);  // 3
array.lastIndexOf(2, 2);  // 0
array.lastIndexOf(2, -2); // 0
array.lastIndexOf(2, -1); // 3


```
### 23 Array.prototype.map()

Метод map() создаёт новый массив с результатом вызова указанной функции для каждого элемента массива.
Описание

Метод map вызывает переданную функцию callback один раз для каждого элемента, в порядке их появления и конструирует новый массив из результатов её вызова. Функция callback вызывается только для индексов массива, имеющих присвоенные значения, включая undefined. Она не вызывается для пропущенных элементов массива (то есть для индексов, которые никогда не были заданы, которые были удалены или которым никогда не было присвоено значение.

Функция callback вызывается с тремя аргументами: значением элемента, индексом элемента и массивом, по которому осуществляется проход.
```js
Syntax

// Arrow function
map((element) => { /* … */ })
map((element, index) => { /* … */ })
map((element, index, array) => { /* … */ })

// Callback function
map(callbackFn)
map(callbackFn, thisArg)
```

Examples
```js
const numbers = [1, 4, 9];
const roots = numbers.map((num) => Math.sqrt(num));

// roots is now     [1, 2, 3]
// numbers is still [1, 4, 9]
```
### 24 Array.of()

Метод Array.of() создаёт новый экземпляр массива Array из произвольного числа аргументов, вне зависимости от числа или типа аргумента.

Разница между Array.of() и конструктором Array заключается в обработке целочисленных аргументов: Array.of(7) создаёт массив с одним элементом 7, а Array(7) создаёт пустой массив со значением свойства length равным 7 (Замечание: подразумевается 7 пустых слотов, а не слоты со значением undefined).

```js
Array.of(7);       // [7]
Array.of(1, 2, 3); // [1, 2, 3]

Array(7);          // массив с 7 пустыми слотами
Array(1, 2, 3);    // [1, 2, 3]
```

### 25 Array.prototype.pop()


Метод pop() удаляет последний элемент из массива и возвращает его значение.

Синтаксис

arr.pop()
exampls
```js
const myFish = ["angel", "clown", "mandarin", "sturgeon"];
const popped = myFish.pop();
console.log(myFish); // ['angel', 'clown', 'mandarin' ]
console.log(popped); // 'sturgeon'
```
### 26 Array.prototype.push()

Метод push() добавляет один или более элементов в конец массива и возвращает новую длину массива.
Синтаксис

arr.push(element1, ..., elementN)

exampls
```js
let sports = ['футбол', 'бейсбол'];
let total = sports.push('американский футбол', 'плавание');

console.log(sports); // ['футбол', 'бейсбол', 'американский футбол', 'плавание']
console.log(total);  // 4
```
### 27Array.prototype.reduce()

Метод reduce() применяет функцию reducer к каждому элементу массива (слева-направо), возвращая одно результирующее значение.

### 28Array.prototype.reduceRight()

Метод reduceRight() применяет функцию к аккумулятору и каждому значению массива (справа-налево), сводя его к одному значению.

### 29 Array.prototype.reverse()

Метод reverse() на месте обращает порядок следования элементов массива. Первый элемент массива становится последним, а последний — первым.
```js
const array1 = ['one', 'two', 'three'];
console.log('array1:', array1);
// Expected output: "array1:" Array ["one", "two", "three"]
```

### 30 Array.prototype.shift()


Метод shift() удаляет первый элемент из массива и возвращает его значение. Этот метод изменяет длину массива.

### 31 Array.prototype.slice()

Метод slice() возвращает новый массив, содержащий копию части исходного массива.
exampls
```js
const animals = ['ant', 'bison', 'camel', 'duck', 'elephant'];

console.log(animals.slice(2));
// Expected output: Array ["camel", "duck", "elephant"]

console.log(animals.slice(2, 4));
// Expected output: Array ["camel", "duck"]

console.log(animals.slice(1, 5));
// Expected output: Array ["bison", "camel", "duck", "elephant"]
```

### 32 Array.prototype.some()

Метод some() проверяет, удовлетворяет ли какой-либо элемент массива условию, заданному в передаваемой функции.

example
```js
const array = [1, 2, 3, 4, 5];

// Checks whether an element is even
const even = (element) => element % 2 === 0;

console.log(array.some(even));
// Expected output: true
```
### 33 Array.prototype.sort()

Метод sort() на месте сортирует элементы массива и возвращает отсортированный массив. Сортировка не обязательно устойчива (англ.). Порядок сортировки по умолчанию соответствует порядку кодовых точек Unicode.

examples
```js
const stringArray = ["Blue", "Humpback", "Beluga"];
const numberArray = [40, 1, 5, 200];

function compareNumbers(a, b) {
  return a - b;
}

stringArray.join(); // 'Blue,Humpback,Beluga'
stringArray.sort(); // ['Beluga', 'Blue', 'Humpback']

numberArray.join(); // '40,1,5,200'
numberArray.sort(); // [1, 200, 40, 5]
numberArray.sort(compareNumbers); // [1, 5, 40, 200]
```
### 34 Array.prototype.splice()

Метод splice() изменяет содержимое массива, удаляя существующие элементы и/или добавляя новые.

exampls
```js
const months = ['Jan', 'March', 'April', 'June'];
months.splice(1, 0, 'Feb');
// Inserts at index 1
console.log(months);
// Expected output: Array ["Jan", "Feb", "March", "April", "June"]

months.splice(4, 1, 'May');
// Replaces 1 element at index 4
console.log(months);
// Expected output: Array ["Jan", "Feb", "March", "April", "May"]
```
### 35 Array.prototype.toLocaleString()
Сводка

Метод toLocaleString() возвращает строковое представление элементов массива. Элементы преобразуются в строки с использованием своих собственных методов toLocaleString и эти строки разделяются локале-зависимой строкой (например, запятой «,»).

### 36 Array.prototype.toString()
Сводка

Метод toString() возвращает строковое представление указанного массива и его элементов.

examples
```js
const array1 = [1, 2, 'a', '1a'];

console.log(array1.toString());
// Expected output: "1,2,a,1a"
```
### 37 Array.prototype.unshift()
Сводка

Метод unshift() добавляет один или более элементов в начало массива и возвращает новую длину массива.
```js
const array1 = [1, 2, 3];

console.log(array1.unshift(4, 5));
// Expected output: 5

console.log(array1);
// Expected output: Array [4, 5, 1, 2, 3]
```
