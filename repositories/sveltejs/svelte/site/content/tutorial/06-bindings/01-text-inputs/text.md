---
title: Текстовые поля
---

Как правило, поток данных в Svelte идет *сверху вниз*, т.е родительский компонент может устанавливать свойства для дочернего компонента, а компонент может устанавливать атрибуты для элемента, но не наоборот.

Иногда полезно нарушить это правило. Возьмем случай с элементом `<input>` в этом компоненте — мы *могли бы* добавить обработчик события `on:input`, который присваивает переменной` name` значение свойства `event.target.value`, но это малость... многословно. А с другими видами элементов формы ситуация ещё хуже.

Вместо этого, мы можем использовать директиву `bind:value`:

```html
<input bind:value={name}>
```

Это означает, что не только изменение значения переменной `name` обновит значение в тектовом поле, но и изменение текста в поле приведет к изменению значения `name`.