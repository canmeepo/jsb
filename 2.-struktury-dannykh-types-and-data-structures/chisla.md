# 2.1 Числа

## Number

Number - примитивный тип данных используемых для хранения числовых значений \(integers, floats, etc\),

* Способы записи:

  ```javascript
  typeof(5) // "number"
  typeof(5.5) // "number"
  typeof(0xff) // "number"
  ```

* Если математическая операция не может быть совершена, то возвращается специальное значение NaN \(к примеру 0/0 вернет NaN\) 
* Деление на 0 возвращает infinity, который в точности ведется себя как математическая "бесконечность" обозначаемая символом ∞
* Преобразвоание к числу

  для каста строки к намберу/интеджеру нужно добавить перед строкой математические оператор \(+, -\)

  ```javascript
  console.log("5") // 5 - type string
  console.log(+"5") // 5 - type number
  console.log(-"5") // -5 - type number
  ```

  так это сработает для \(\*, / \) но понадобятся два операнда;

  ```javascript
  console.log("5" * "2") // 10 - type number
  ```

  всегда можешь привести тип с помощью объекта-обертки Number

  ```javascript
  console.log(Number("5") - 5 type number
  ```

  Также в js есть методы для преведния к числу parseInt и parseFloat

  Функция parseInt и ее аналог parseFloat преобразуют строку символ за символом, пока это возможно.

  parseInt читает из строки целое число, а parseFloat – дробное.

  ```javascript
  parseInt('12px' ) // 12, ошибка на символе 'p'
  parseFloat('12.3.4') // 12.3, ошибка на второй точке
  ```

* Округление
  * Math.floor - Округляет вниз
  * Math.ceil - Округляет вверх
  * Math.round - Округляет до ближайшего целого

    ```javascript
    Math.floor(3.1)  // 3
    Math.ceil(3.1)   // 4
    Math.round(3.1)  // 3
    ```
* Неточные вычисления

  ```javascript
  0.1 + 0.3 // 0.30000000000000004
  ```

  Объяснение - 

  Всё дело в том, что в стандарте IEEE 754 на число выделяется ровно 8 байт\(=64 бита\), не больше и не меньше. Число 0.1 \(одна десятая\) записывается просто в десятичном формате. Но в двоичной системе счисления это бесконечная дробь, так как единица на десять в двоичной системе так просто не делится. Также бесконечной дробью является 0.2 \(=2/10\). Двоичное значение бесконечных дробей хранится только до определенного знака, поэтому возникает неточность.

  ```javascript
  (0.1 * 10 + 0.2 * 10) / 10 ); // 0.3
  ```

### Объект Number <a id="&#x41E;&#x431;&#x44A;&#x435;&#x43A;&#x442;_Number"></a>

У этого встроенного объекта [`Number`](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Number) есть свойства для целочисленных констант, таких как максимальное число, не-число и бесконечность. Вы не можете изменить значения этих свойств, и Вы должны использовать их следующим образом:

```javascript
var biggestNum = Number.MAX_VALUE;
var smallestNum = Number.MIN_VALUE;
var infiniteNum = Number.POSITIVE_INFINITY;
var negInfiniteNum = Number.NEGATIVE_INFINITY;
var notANum = Number.NaN;
```

Как видно из примера выше, для получения перечисленных значений, нужно обращаться к свойствам предопределенного глобального объекта `Number`. Тогда как у экземпляра этого объекта, созданного вами при работе программы, этих свойств не будет. 

В следующей таблице приведен список свойств объекта `Number`.

| Свойства объекта  |  |
| :--- | :--- |
| `Number` |  |
| Свойство | Описание |
| [`Number.MAX_VALUE`](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Number/MAX_VALUE) | Наибольшее число из возможных для представления |
| [`Number.MIN_VALUE`](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Number/MIN_VALUE) | Наименьшее число из возможных для представления |
| [`Number.NaN`](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Number/NaN) | Специальное "Не числовое" \("not a number"\) значение |
| [`Number.NEGATIVE_INFINITY`](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Number/NEGATIVE_INFINITY) | Специальное значение "Минус бесконечность"; возвращается при переполнении |
| [`Number.POSITIVE_INFINITY`](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Number/POSITIVE_INFINITY) | Специальное значение "Плюс бесконечность"; возвращается при переполнении |
| [`Number.EPSILON`](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Number/EPSILON) | Разница между единицей и наименьшим значением, большим единицы, которое может быть представлено типом [`Number`](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Number). |
| [`Number.MIN_SAFE_INTEGER`](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Number/MIN_SAFE_INTEGER) | Минимальное целое, безопасное число в JavaScript. |
| [`Number.MAX_SAFE_INTEGER`](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Number/MAX_SAFE_INTEGER) | Максимальное целое, безопасное число в JavaScript. |

| Методы объекта  |  |
| :--- | :--- |
| `Number` |  |
| Метод | Описание |
| [`Number.parseFloat()`](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Number/parseFloat) | Принимает строку как аргумент, и возвращает числовое значение с плавающей точкой, которое удалось распознать. Тоже самое что и глобальная функция [`parseFloat()`](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/parseFloat). |
| [`Number.parseInt()`](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Number/parseInt) | Принимает строку как аргумент, и возвращает целочисленное значение в заданной системе исчисления, которое удалось распознать. Тоже самое что и глобальная функция [`parseInt()`](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/parseInt). |
| [`Number.isFinite()`](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Number/isFinite) | Определяет, является ли число, переданное в качестве аргумента, конечным. |
| [`Number.isInteger()`](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Number/isInteger) | Определяет, является ли число, переданное в качестве аргумента, целым. |
| [`Number.isNaN()`](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Number/isNaN) | Определяет, является ли число, переданное в качестве аргумента, [`NaN`](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/NaN) \(не числом\). Аналогичный, но более надежный метод чем глобальная функция [`isNaN()`](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/isNaN). |
| [`Number.isSafeInteger()`](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Number/isSafeInteger) | Определяет, является ли .число, переданное в качестве аргумента, целым и безопасным. |

`Прототип Number` предоставляет ряд методов, для получения значения числа в различных форматах. В следующей таблице перечислены методы, доступные через `Number.prototype`.

| Методы  |  |
| :--- | :--- |
| `Number.prototype` |  |
| Метод | Описание |
| [`toExponential()`](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Number/toExponential) | Возвращает строку, представляющую число в экспоненциальном представлении. |
| [`toFixed()`](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Number/toFixed) | Возвращает строку, представляющую число с заданным количеством разрядов после запятой. |
| [`toPrecision()`](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Number/toPrecision) | Возвращает строку, представляющую число с указанной точностью. |

### Объект Math

Встроенный объект Math содержит методы для математических операций.

В отличии от большинства других объектов, вам не нужно создавать свои экземпляры объекта `Math`. Всегда следует использовать глобальный объект `Math` непосредственно.

```javascript
Math.PI // обращение к числу pi 
Math.sin(1.56)
```

В следующей таблице перечислены методы объекта `Math`.

| Метод | Описание |
| :--- | :--- |
| [`abs()`](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Math/abs) | Возвращает абсолютное значение \(модуль\) аргумента |
| [`sin()`](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Math/sin), [`cos()`](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Math/cos), [`tan()`](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Math/tan) | Стандартные тригонометрические функции; принимают аргументы в радианах |
| [`asin()`](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Math/asin), [`acos()`](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Math/acos), [`atan()`](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Math/atan), [`atan2()`](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Math/atan2) | Обратные тригонометрические функции; возвращают значения в радианах |
| [`sinh()`](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Math/sinh), [`cosh()`](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Math/cosh), [`tanh()`](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Math/tanh) | Гиперболические тригонометрические функции; принимают аргументы в гиперболических углах |
| [`asinh()`](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Math/asinh), [`acosh()`](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Math/acosh), [`atanh()`](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Math/atanh) | Обратные гиперболические тригонометрические функции; возвращают значения в гиперболических углах |
| [`pow()`](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Math/pow), [`exp()`](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Math/exp), [`expm1()`](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Math/expm1), [`log10()`](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Math/log10), [`log1p()`](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Math/log1p), [`log2()`](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Math/log2) | Экпоненциальные и логорифмические функции |
| [`floor()`](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Math/floor), [`ceil()`](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Math/ceil) | Возвращают наибольшее/наименьшее целое, которое меньше/больше или равно входному значению |
| [`min()`](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Math/min), [`max()`](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Math/max) | Возвращают наибольшее или наименьшее \(соответственно\) из входных числовых значений, перечисленных через запятую |
| [`random()`](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Math/random) | Возвращает случайное число от 0 до 1 |
| [`round()`](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Math/round), [`fround()`](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Math/fround), [`trunc()`](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Math/trunc), | Функции округления и отсечения дробной части |
| [`sqrt()`](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Math/sqrt), [`cbrt()`](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Math/cbrt), [`hypot()`](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Math/hypot) | Корень квадратный, корень кубический, корень квадратный из суммы квадратов аргументов |
| [`sign()`](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Math/sign) | Знак числа, показывает является ли входное число позитивным, негативным или равным нулю |
| [`clz32()`](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Math/clz32), [`imul()`](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Math/imul) | Количество первых нулевых бит в 32-битном двоичном представлении. Возвращает результат Cи-подобного 32-битного целочисленного умножения двух аргументов. |

