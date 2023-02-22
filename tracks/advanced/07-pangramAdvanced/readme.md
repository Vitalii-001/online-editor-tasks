# pangramAdvanced

Разом з командою ви продовжуєте працюєте над новою [CMS](https://uk.wikipedia.org/wiki/Система_керування_вмістом). У минулому спринті [/js-track/basic/pangram](Pangram) для відділу дизайну ви розробили функцію `pangram` (вже є частиною адмін-панелі), яка для фрагменту тексту перевіряє, чи є той [панграмою](https://uk.wikipedia.org/wiki/Панграма).

Приклад української панграми:

> Хвацький юшковар Філіп щодня на ґанку готує сімʼї вечерю з жаб.

В цьому спринті, відділ дизайну хоче доробити цей модуль, аби їм було простіше створювати власні панграми та варіант [lorem ipsum](https://uk.wikipedia.org/wiki/Lorem_ipsum) тексту. В оновленій версії вони хочуть, щоб виводились всі літери і символи, яких немає в наданому тексті та знати довжину наданого фрагменту.

Тому вашим завданням є створити функцію `pangramAdvanced`, яка приймає на вхід текст для перевірки `text` і повертає обʼєкт з полями:

- `length`: довжина тексту (враховуючи тільки літери, без символів та пробілів, але з урахуванням апострофу "ʼ")
- `letters`: відсутні літери абетки
- `symbols`: відсутні символи

Обмеження:

- Розмір тексту не більше 1024 символів
- Текст містить цифри, літери української абетки та знаки пунктуації: ".", "!", "-", "ʼ" та " "; знаки не враховувати
- Пошук має бути нечутливий до регістру літер
- Послідовність літер у масиві `letters` має бути наступною: "а", "б", "в", "г", "ґ", "д", "е", "є", "ж", "з", "и", "і", "ї", "й", "к", "л", "м", "н", "о", "п", "р", "с", "т", "у", "ф", "х", "ц", "ч", "ш", "щ", "ь", "ю", "я"
- Послідовність символів у масиві `symbols` має бути наступною: ".", "!", "-", "ʼ", " "
- Швидкість роботи алгоритму та обсяг використовуваної пам'яті значення не мають

**Приклад:**

```js
pangramAdvanced("Хвацький юшковар Філіп щодня на ґанку готує вечерю.");
```

Повертає результат:

```js
{
  length: 43,
  letter: ["б", "ж", "з", "ї", "м", "с"],
  symbols: ["!", "-", "ʼ"],
}
```

<details>
  <summary>Підказка</summary>

---

  В [UTF-8](https://en.wikipedia.org/wiki/UTF-8) літери української абетки розташовані не у тій самій послідовності, тому щоб зберігти послідовність як у завданні, скористайтеся масивом і методом [filter](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter).

</details>