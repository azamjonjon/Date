# Работа с Date, Map и Set в JavaScript

## Введение
JavaScript предоставляет мощные встроенные объекты для работы с датами и коллекциями: `Date`, `Map` и `Set`. В этом документе описаны основные методы и примеры их использования.

---

# Объект Date

## Создание объекта Date
Существует несколько способов создания объекта `Date`:

### 1. Текущая дата и время
```javascript
const now = new Date();
console.log(now); // Выводит текущую дату и время
```

### 2. Указанная дата
```javascript
const specificDate = new Date(2025, 0, 3); // 3 января 2025 года
console.log(specificDate);
```
Месяцы отсчитываются с 0 (январь - 0, декабрь - 11).

### 3. С использованием строки
```javascript
const dateFromString = new Date('2025-01-03T10:00:00');
console.log(dateFromString);
```

### 4. По числу миллисекунд с начала эпохи Unix
```javascript
const dateFromMilliseconds = new Date(1672527600000); // 1 января 2023 года
console.log(dateFromMilliseconds);
```

## Получение данных из объекта Date
Объект `Date` предоставляет методы для получения различных компонентов даты:

- `getFullYear()` — возвращает год.
- `getMonth()` — возвращает месяц (0-11).
- `getDate()` — возвращает день месяца (1-31).
- `getDay()` — возвращает день недели (0 - воскресенье, 6 - суббота).
- `getHours()` — возвращает часы (0-23).
- `getMinutes()` — возвращает минуты (0-59).
- `getSeconds()` — возвращает секунды (0-59).
- `getMilliseconds()` — возвращает миллисекунды (0-999).
- `getTime()` — возвращает количество миллисекунд с начала эпохи Unix.

### Пример
```javascript
const now = new Date();
console.log(`Год: ${now.getFullYear()}`);
console.log(`Месяц: ${now.getMonth()}`);
console.log(`День: ${now.getDate()}`);
console.log(`День недели: ${now.getDay()}`);
```

## Установка данных в объекте Date
Для изменения компонентов даты используются методы `set`:

- `setFullYear(year, [month], [date])`
- `setMonth(month, [date])`
- `setDate(date)`
- `setHours(hours, [minutes], [seconds], [ms])`
- `setMinutes(minutes, [seconds], [ms])`
- `setSeconds(seconds, [ms])`
- `setMilliseconds(ms)`
- `setTime(milliseconds)`

### Пример
```javascript
const date = new Date();
date.setFullYear(2030);
date.setMonth(11); // Декабрь
date.setDate(25); // 25 декабря 2030 года
console.log(date);
```




# Объект Map

## Введение
`Map` — это коллекция, в которой хранятся пары ключ-значение. Ключи могут быть любого типа, включая объекты.

### Создание Map
```javascript
const map = new Map();
```

### Добавление и получение значений
- `set(key, value)` — добавляет значение.
- `get(key)` — получает значение.
- `has(key)` — проверяет наличие ключа.
- `delete(key)` — удаляет пару ключ-значение.
- `clear()` — очищает коллекцию.
- `size` — возвращает количество элементов.

### Пример
```javascript
const map = new Map();
map.set('name', 'John');
map.set('age', 30);

console.log(map.get('name')); // John
console.log(map.has('age')); // true
console.log(map.size); // 2

map.delete('age');
console.log(map.size); // 1

map.clear();
console.log(map.size); // 0
```

### Итерация по Map
```javascript
const map = new Map([
  ['a', 1],
  ['b', 2],
  ['c', 3],
]);

for (const [key, value] of map) {
  console.log(`${key}: ${value}`);
}

map.forEach((value, key) => {
  console.log(`${key}: ${value}`);
});
```

---

# Объект Set

## Введение
`Set` — это коллекция уникальных значений. Повторяющиеся значения автоматически игнорируются.

### Создание Set
```javascript
const set = new Set();
```





## Полезные советы
- `Map` удобен, когда требуется ассоциировать данные с уникальными ключами.
- `Set` полезен для работы с уникальными значениями или исключения дубликатов.
- Для сложной работы с датами, используйте библиотеки, такие как [date-fns](https://date-fns.org/) или [Moment.js](https://momentjs.com/).

---
Этот файл дает обзор работы с объектами `Date`, `Map` и `Set` в JavaScript. Используйте документацию MDN для углубленного изучения.

