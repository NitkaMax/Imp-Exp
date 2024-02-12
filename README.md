# Домашнее задание к лекции «Модули»

### **Важные моменты** 

1. Каждая задача выполняется в виде отдельного проекта с собственным репозиторием на GitHub.
2. На эти задачи не распространяется требование отсутствия ошибок в ESLint, но вы можете его запустить и изучить появившиеся ошибки.
3. Решения должны быть построены на базе [шаблона webpack](/ci-template) (для задач под номерами 1 и 2).

В личном кабинете на сайте [netology.ru](http://netology.ru/) в поле комментария к домашней работе добавьте ссылки на ваши GitHub-проекты.

---

## Import/Export

### Легенда

Вы успешно настроили загрузку модулей с webpack и сборку приложения. Пришло время грамотно разделить всё на модули.

### Описание

Разделите всё приложение на модули:
1. Модуль Domain, где будет храниться логика предметной области: персонажи, атаки и т. д.
3. Модуль Game, отвечающий за работу приложения: загрузку и сохранение.
4. Модуль App, отвечающий за запуск приложения.

Заглушки для модулей:

файл `domain.js`:
```javascript
class Character {
}
```

файл `game.js`
```javascript
class Game {
  start() {
    console.log('game started');
  }
}

class GameSavingData {
}

function readGameSaving() {
}

function writeGameSaving() {
}
```

файл `app.js`
```javascript
const game = new Game();
game.start();
```

Что нужно сделать:
- организуйте из модуля `domain` экспорт класса `Character` в качестве дефолтного;
- в модуле `game` сделайте импорт класса `Character`;
- организуйте экспорт из модуля `game` класса `Game` в качестве дефолтного, класса `GameSavingData` и функций `readGameSaving` и `writeGameSaving`;
- в модуле `app.js` одним импортом импортируйте `Game`, `GameSavingData` и функции `readGameSaving`, `writeGameSaving`. Их при импорте переименуйте в `loadGame` и `saveGame` соответственно.

С функциями и классами ничего делать не нужно. Необходимо только правильно расставить инструкции `import`/`export`.

---