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



