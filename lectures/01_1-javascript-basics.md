# 1. Основи

## Умовні позначення
```javascript
// Коментар
//> Вивід у консоль
//=> Результат обрахування
```

## Основні поняття Крос-платформного Програмування

### Означення
Крос-платформне програмування - це написання коду що може бути виконаний на різних платформах.

Існують різні підходи в залежності від типу мови:
- Для мов що компілюються, основний підход, це перекомпіляція коду для різних платформ (C/C++, Haskell);
- Для мов що інтерпретуються це розповсюдження вихідного коду для його подальшого виконання на цільовій платформі (Ruby, Python). Також можлива попередня компіляція в проміжний код (Java, C#). Але в обох випадках, на цільовій платформі має бути программа-інтерпретатор, спеціально реалізована для цієї платформи.

## Мова JavaScript

### 1. Дані
- Число (number) - Цілі та дробові числа представлені одним типом. (Але інтерпретатор їх оброблює окремо). Приклад: `42`, `123.12`;
- Строка (string) - Набір символів, що обмежується одинарними або подвійними лапками. Оскільки подвійні лапки зазвичай використовуються в HTML, заохочується використання одинарних. Приклад: `'Hello1'`, `"Word!"`;
- Логічні (boolean) - Результати логічних операцій. Можуть мати всього два значення: `true` або `false`.

### 2. Оператори
Дії над даними.

- Математичні
  - `+` - Додавання
  - `-` - Віднімання
  - `*` - Множення
  - `/` - Ділення
  - `%` - Залишок від ділення
  - `**` - Ступінь
- Побітові
  - `&` - Побітове І (And)
  - `|` - Побітове Або (Or)
  - `^` - Побітове виключне Або (Xor)
  - `~` - Доповнення
  - `<<` - Зсув вліво
  - `>>` - Зсув вправо
  - `>>>` - Циклічний зсув вправо
- Присвоєння
  - `=` - Присвоєння
  - `+=`, `-=`, `/=`, `*=`, `%=`, `**=`, `<<=`, `>>=`, `>>>=`, `&=`, `|=`, `^=` - Присвоєння з операцією (Операція виконується між попереднім значенням змінної та операндом)
- Інкремент/декремент
  - `++` - Інкремент (збільшує змінну на одиницю)
  - `--` - Декремент (зменшує змінну на одиницю)
- Порівняння
  - `<` - Менше
  - `>` - Більше
  - `<=` - Менше або дорівнює
  - `>=` - Більше або дорівнює
  - `==` - Дорівнює
  - `!=` - Не дорівнює
  - `===` - Дорівнює без приведення типів
  - `!==` - Не дорівнює без приведення типів
- Логічні
  - `&&` - Логічне І (And). Права частина не вираховується, якщо ліва `false`.
  - `||` - Логічне Або (Or). Права частина не вираховується, якщо ліва `true`.
  - `!` - Логічне Не (Not).
- Унарні
  - `delete` - Видалити ключ з об'єкта.
  - `typeof` - Визначити тип данних.
- Відносні
  - `in` - Визначити чи права частина містить ліву. Наприклад в масиві.

### 3. Вирази (expressions)
Набір даних та операторів що повертає значення (обраховується та підставляє на своє місце).

*Приклад:*
```javascript
3 + 4 * 5
```

### 4. Приорітет операторів
Якщо протилежне не визначено дужками `()`, оператори виконуються згідно таблиці. Мають вищий приорітет, тобто виконуються першими, оператори що знаходяться вищє.

- Членство: `.`, `[]`
- Виклик / створення: `()`, `new`
- Заперечення / інкремент: `!`, `~`, `-`, `+`, `++`, `--`, `typeof`, `void`, `delete`
- Множення - ділення: `*`, `/`, `%`
- Додавання - віднімання: `+`, `-`
- Побітовий зсув: `<<`, `>>`, `>>>`
- Відносні: `<`, `<=`, `>`, `>=`, `in`, `instanceof`
- Порівняння: `==`, `!=`, `===`, `!==`
- Побітове І: `&`
- Побітове Виключне Або: `^`
- Побітове Або: `|`
- Логічне І: `&&`
- Логічне Але: `||`
- Умовні: `?:`
- Присвоєння: `=`, `+=`, `-=`, `*=`, `/=`, `%=`, `<<=`, `>>=`, `>>>=`, `&=`, `^=`, `|=`
- Кома: `,`

*Приклад:*
```javascript
1 + 2 * 3 && 4++
```
Обраховується, як:
```javascript
(1 + (2 * 3)) && (4++)
```

### 5. Інструкції (statement)
Один або декілька виразів, що закінчується на `;`. (`;` можна опускати але це може іноді призводити до неочікуванних наслідків).

### 6. Змінні
Ім'я для місця в пам'яті. Позначається `var`.

*Приклад:*
```javascript
var a = 4;
```

Тип даних що міститься в змінній може змінюватись.
Область визначення змінної об'явленої за допомогою `var` - функція. Тобто якщо змінна об'явлена в функції, то вона буде не доступна за її межами.

### 7. Пусті типи даних
Застосовуються для того щоб позначити відсутність даних.

- `null` - Нуль. Якщо значення визначене але пусте.
- `undefined` - Якщо значення не визначене.

*Приклад:*
```javascript
var student = null;
```

### 8. Коментарі
Пояснення до коду або код що відмічений, як той що не має виконуватись.

- `//` - Одностроковий коментар. Все що після позначки `//` не виконується.
- `/* ... */` - Багатостроковий коментар. Все що між `/*` і `*/` не виконується.

*Приклад:*
```javascript
// Це коментар

/*
 * А це
 *   багатостроковий
 * коментар
 */
```

### 9. Масиви
Упорядкований, пронумерований набір елементів. Елементи нумеруються починаючи з 0.
Для доступу до елемента використувується оператор `[]`.

*Приклад:*
```javascript
var items = [3, true, 'Василь'];

items[2] //=> 'Василь'
```

### 10. Приведення типів (type coercion)
Перетворення одно типу в інший.

#### Явне (explicit)
Виконується за допомогою позначення типу `Number`, `String`, `Boolean`.

*Приклад:*
```javascript
var str = '5';
Number(str);
```

#### Неявне (implicit)
Виконується під час застосування бінарних операторів (операторів для двух аргументів). За виключенням операторів `===` і `!==`, що були введені спеціально щоб запобігти приведенню типів в порівняннях.
Дії над даними різного типу можуть виявитись некомутативними (важливий порядок аргументів) та неасоциативними (важливий порядок виконання). Приведення типів може привести до несподіваних наслідків тому його бажано запобігати.

*Приклад:*
```javascript
'2' + '1' //=> '21'
'2' - '1' //=> 3

('1' + 2) + 3 //=> '123'
'1' + (2 + 3) //=> '15'

[1] + 2 //=> '12'
```

### 11. Об'єкти
Набір пар ключ - значення.

```javascript
var student = {
  name: 'Василь',
  group: 'КН'
};

items['name'] //=> 'Василь'
items.group //=> 'КН'
items.group = 'ПІ' //=> 'ПІ'
```

### 12. Умови (conditional statement)
Дозволяє виконувати чи не код в залежності від певної умови.

#### `if...else`
`if` обраховує умову і виконує блок коду, якщо умова правдива (truthy). Також може бути доданий `else`, що віконає інший блок коду, у випадку якщо умова неправдива (falsey).

*Приклад:*
```javascript
var x = 0;
var i = 0;

if (x > 0) {
  i++;
} else {
  i--;
}

i; //=> -1
```

## 13. Цикли
Дозволяють виконувати інструкції певну кількість разів. Одине виконання називається - ітерація.

#### `while`
Виконує блок коду доки умова правдива. Якщо умова одразу неправдива, не виконується жодного разу.

*Приклад:*
```javascript
var i = 0;

while (i < 5) {
  i++;
}

i; //=> 5
```

#### `do..while`
Аналогічний до циклу `while` але завжди виконується, як мінімум один раз, навіть якщо умова одразу неправдива.

*Приклад:*
```javascript
var i = 0;

do {
  i++;
} while(i < 0);

i; //=> 1
```

#### `for`
Скорочений запис циклу що виконується конкретну кількість разів.
Складається з трьох частин `for (ініціалізація; умова; зміна)`:
- Ініціалізація - для створення змінних що будуть використовуватись для контролю виконанная циклу;
- Умова - поки умова правдива, цикл виконується. Перевіряється на початку циклу. Якщо умова неправдива одразу, цикл не виконається жодного разу;
- Зміна - використовується для зміни змінних, що контролюють виконання циклу.

*Приклад:*
```javascript
for (var i = 0; i < 5; i++) {
  // ...код...
}
```

#### Контроль виконання
Для контролю виконання циклу, використовуються спеціальні інструкції.
`break` - закінчує виконная циклу;
`continue` - зікінчує виконання поточної ітераціїї, та однару переходить до наступної, якщо умова правдива.

## 14. Функції
Частина коду що об'єднана за допомогою ключового слова `function`. Зазвичай має тенденцію до повторного використання. Функція викликається за допомогою круглих дужок.

*Приклад:*
```javascript
function hello() {
  console.log('Привіт!')
}

hello();
//> Привіт!
```

### Параметри та аргументи функції
Функція може мати параметри. Параметри вказуються у дужках через кому. Під час виклику функції, їй передються конкретні аргументи, що доступні за вказаними іменами.

*Приклад:*
```javascript
function helloStudent(name, group) {
  var greeting = 'Привіт ' + name + ' з ' + group + '!';
  console.log(greeting);
}

var studentName = 'Василь';

helloStudent(studentName, '2-КН');
//> Привіт Василь з 2-КН!
```

### Значення що повертається
Функція може повертати значення за допомогою ключового слова `return`. Обраховане значення підставляється на місце виклику функції.

*Приклад:*
```javascript
function add(a, b) {
  return a + b;
}

add(3, 4); //=> 5
```
