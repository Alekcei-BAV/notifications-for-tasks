


Если вкратце, то получилось очень хорошо поработать над оптимизацией, улучшить мобильный и компьютерный интерфейс планера. 

<details>
<summary>Подробнее</summary>

###### 1. Улучшение редактора задач Планера

- Добавили удобный цифровой ввод времени в формате `ЧЧ:ММ` для полей «Время» и «Время окончания» на мобильных устройствах.
    
- Реализовали автоматический переход от ввода часов к минутам.
    
- Сохранили работу кнопок изменения времени на ±1 час и автоматический пересчёт длительности задачи.
    
- Выровняли подписи End time input и Complex Tasks rule.
    
- Добавили настройку дополнительной прокрутки мобильного редактора.
    
- Реализовали числовое поле для указания запаса прокрутки от 0 до 150%, по умолчанию 70%.
    
- Предусмотрели возможность отключать дополнительное пустое пространство, сохраняя обычную прокрутку.
    
- Убрали лишнюю видимую полосу прокрутки в редакторе на компьютере, сохранив возможность прокрутки при недостаточной высоте окна.
    

###### 2. Упрощение интерфейса

- Добавили пометку (Mobile) к новым настройкам, относящимся только к мобильным устройствам.
    
- Сократили названия вариантов поля «При выполнении» до `default`, `keep`, `delete`.
    
- Вернули компактную ширину этого поля — 145 пикселей.
    
- Переименовали галочку Planner notification в Notification («Уведомление»).
    
- Сохранили прежнюю логику выполнения задач и отправки уведомлений.
    

###### Модернизация `main.js`

- Разделили исходный JavaScript на 16 тематических модулей для удобства разработки и сопровождения.
    
- Добавили механизм сборки модулей в единый `main.js`, необходимый для установки в Obsidian.
    
- Реализовали проверку воспроизводимости сборки.
    
- Оптимизировали поиск ближайшего локального напоминания: вместо сортировки списка используется один проход по записям.
    
- Проверили производительность нового алгоритма на историях уведомлений разного размера.
    

###### Организация `styles.css`

- Разделили исходные стили на четыре тематические части.
    
- Добавили их сборку в единый `styles.css`.
    
- Сохранили существующее оформление интерфейса, за исключением согласованных изменений.
    
- Обеспечили возможность удобнее поддерживать стили Desktop и Mobile отдельно.
    

###### Анализ `data.json`

- Изучили структуру вашего реального файла настроек и рабочего состояния.
    
- Определили основные источники роста размера файла: историю отправок, состояния задач, переписку и журналы соединений.
    
- Обнаружили дублирование некоторых данных ntfy и входящих сообщений.
    
- Проверили состояние очередей, задач и восстановления.
    
- Выделили потенциальные направления оптимизации сохранений.
    
- Сохранили существующий формат `data.json` без изменений, чтобы не подвергать риску настройки, историю и защиту от повторных уведомлений.
    
- Добавили инструмент безопасного анализа структуры JSON без вывода личных данных и токенов.
    

###### Тестирование и надёжность

- Добавили новые автоматизированные offline-проверки мобильного ввода времени, настроек прокрутки и Desktop-интерфейса.
    
- Проверили новую логику поиска ближайшего напоминания.
    
- Выполнили исторические регрессионные проверки с сохранением оригинальных тестов.
    
- Проверили синтаксис JavaScript и JSON, разбор CSS, целостность ZIP-архивов и контрольные суммы SHA-256.
    
- Зафиксировали ограничения: часть исторической регрессии выполнялась на предыдущих исходниках, а реальное поведение на Android и Desktop ещё требует ручных испытаний.
</details>

Скоро возвращается мой сосед по квартире, мне нужно вернуть ему его телевизор, который я использовал в качестве монитора. 

По этому мне придётся заморозить разработку плагина на несколько месяцев. Моему ноутбуку примерно 15 лет, экран у него старого типа, он мерцает. Мне достаточно использовать его в течении часа, чтобы на следующий день у меня появилось боязнь света. 
Если вдруг, у кого-то есть один лишний современный монитор с функцией FreeSync и вы живёте в центре Барселоны, то подарите мне его ха-ха) 

На данный момент, я буду только периодически редактировать описание плагина. 



In short, it turned out to be very good work on optimization, improving the mobile and desktop interface of the planner.

<details>
<summary>More details</summary>

###### 1. Planner Task Editor Improvements

- Added convenient numeric time input in `HH:MM` format for the "Time" and "End time" fields on mobile devices.
    
- Implemented automatic transition from hour input to minutes.
    
- Preserved the functionality of the ±1 hour time adjustment buttons and automatic recalculation of task duration.
    
- Aligned the End time input and Complex Tasks rule labels.
    
- Added a setting for additional scrolling of the mobile editor.
    
- Implemented a numeric field for specifying scroll margin from 0 to 150%, default 70%.
    
- Provided the ability to disable additional empty space while preserving normal scrolling.
    
- Removed the extra visible scrollbar in the editor on desktop while preserving scrollability when the window height is insufficient.
    

###### 2. Interface Simplification

- Added a (Mobile) label to new settings that apply only to mobile devices.
    
- Shortened the option names of the "On completion" field to `default`, `keep`, `delete`.
    
- Restored the compact width of this field — 145 pixels.
    
- Renamed the Planner notification checkbox to Notification.
    
- Preserved the previous task completion and notification sending logic.
    

###### main.js Modernization

- Split the original JavaScript into 16 thematic modules for easier development and maintenance.
    
- Added a mechanism for building the modules into a single `main.js` required for installation in Obsidian.
    
- Implemented build reproducibility verification.
    
- Optimized the search for the nearest local reminder: instead of sorting the list, a single pass through the records is used.
    
- Verified the performance of the new algorithm on notification histories of various sizes.
    

###### styles.css Organization

- Split the original styles into four thematic parts.
    
- Added their build into a single `styles.css`.
    
- Preserved the existing interface appearance, except for the agreed changes.
    
- Provided the ability to more conveniently maintain Desktop and Mobile styles separately.
    

###### data.json Analysis

- Studied the structure of your real settings and working state file.
    
- Identified the main sources of file size growth: send history, task states, correspondence, and connection logs.
    
- Discovered duplication of some ntfy data and incoming messages.
    
- Checked the state of queues, tasks, and recovery.
    
- Identified potential directions for optimizing saves.
    
- Preserved the existing `data.json` format unchanged to avoid risking settings, history, and protection against duplicate notifications.
    
- Added a tool for safe analysis of the JSON structure without outputting personal data and tokens.
    

###### Testing and Reliability

- Added new automated offline checks for mobile time input, scroll settings, and the Desktop interface.
    
- Verified the new logic for finding the nearest reminder.
    
- Performed historical regression checks while preserving the original tests.
    
- Verified JavaScript and JSON syntax, CSS parsing, ZIP archive integrity, and SHA-256 checksums.
    
- Documented limitations: part of the historical regression was performed on previous source files, and real behavior on Android and Desktop still requires manual testing.
</details>

My roommate is coming back soon, and I need to return his TV, which I was using as a monitor. 

Because of this, I'll have to freeze the plugin development for a few months. My laptop is about 15 years old, its screen is an old type, and it flickers. It's enough for me to use it for an hour for me to develop photophobia the next day. 
If by any chance someone has an extra modern monitor with FreeSync and lives in the center of Barcelona, then gift it to me ha-ha) 

For now, I'll only be periodically editing the plugin description.