Модификация Хромиума
====================

Реализовать возможность ручного управления когортами  FLoC 
----------------------------------------------------------
На основе пользовательской истории механизм FLoC автоматически вычисляет и выдает сайтам уникальный номер когорты. Для контроля над тем, что именно выдаёт АПИ FLoC можно сделать ручное управление номером когорты. Нужно реализовать новую внутреннюю страницу браузера (например, `chrome://floc-internals`), на которой сделать:
  1. возможность задать ID когорты вручную, как целое число
  2. возможность задать список доменов, которые будут подставлены для вычисления FLoC, вместо настоящих
  3. настройку для рандомизации FLoC в пределах сессии.
  4. логирование сайтов, которые когда-либо использовали FLoC (пример сайта в лекции).
  5. любые задумки: например, выборка случайного подмножества доменов из большого списка для пункта (2)

Указания по реализации
----------------------
  * [Руководство по сборке браузера](https://chromium.googlesource.com/chromium/src/+/master/docs/linux/build_instructions.md), обязательно использовать [эти настройки](https://chromium.googlesource.com/chromium/src/+/master/docs/linux/build_instructions.md#tips_tricks_and-troubleshooting). Лучше всего собирать браузер на Линуксе, хуже всего на Винде.
  * Детали реализации и использования FLoC в лекции про обратную сторону API браузера
  * Примеры внутренних страниц: `version_ui.h`, `device_log_ui.h` и т. д. (больше примеров на chrome://about)
  * Все параметры с новой страницы сохранять в настройки профиля (`PrefService`).

