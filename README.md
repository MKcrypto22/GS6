# react-projects-7-slider

#### IN ACTION

[Gatsby-Airtable Project](https://gatsby-airtable-design-project.netlify.app/)
# Лабораторна робота 6: Створення слайдера на React

## Опис

Ця лабораторна робота присвячена створенню слайдера на базі React з використанням хуків `useState` та `useEffect`. Слайдер автоматично прокручує слайди з інтервалом у 2 секунди.

## Використання `clearInterval` у `useEffect`

У функції `useEffect`, яка налаштовує інтервал для автоматичної прокрутки слайдів, важливо використовувати функцію `clearInterval`. Це запобігає виникненню витоків пам'яті. Коли компонент буде демонтовано або оновлено, попередній інтервал все ще буде спробувати виконати свою функцію, що може призвести до помилок і непередбачуваної поведінки.

Функція `clearInterval` зупиняє інтервал, що був раніше встановлений за допомогою `setInterval`, таким чином, гарантуючи, що він більше не буде активний після того, як компонент вийде з-під контролю.

## Чому передаємо `[index]` як другий параметр?

Масив залежностей, переданий як другий параметр у `useEffect`, дозволяє контролювати, коли саме викликати ефект. У даному випадку, ми передаємо `[index]`, щоб `useEffect` виконувався щоразу, коли змінюється значення `index`. Це забезпечує актуальність інтервалу та зміни активного слайда, оскільки кожна зміна `index` означає, що ми повинні оновити інтервал для коректної прокрутки слайдів.

Таким чином, ми можемо бути впевнені, що слайдер працює належним чином, а всі попередні інтервали очищуються при кожному новому оновленні `index`.
