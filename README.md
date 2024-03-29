# learn-words-android
### Выпускной проект Samsung IT Академии по треку "Разработка мобильных приложений на языке Java" – Android-приложение для изучения английского

Используемые технологии: БД – **Firebase Realtime Database, Firebase Storage**; загрузка картинок из Firebase – **библиотека Picasso**. 

## Сертификат об окончании IT академии на [русском](d5026797-ec41-4659-9152-b6118a0d0ca8.jpg), [английском](6e1d6561-9010-4b0e-b31d-3e2bb7261e36.jpg)

## Ссылка на гугл-диск (видео, презентация, apk-файл) https://drive.google.com/drive/folders/1t-yZ9zL6czwqo5wIn2ELa9FXjEUoPZER

### Описание

LearnWords (англ. изучай слова) – мобильное приложение для изучения английских слов.

Пользователь выступает в роли персонажа Бориса – парня из России, выигравшего грин-карту и уехавшего искать счастья в Америку. С текущими знаниями английского Борису могут предложить только низкооплачиваемую работу, и ему нужно усердно учиться, чтобы идти вверх по карьере. История персонажа рассказывается при первом запуске приложения, сразу после регистрации. «Текущее состояние персонажа» – он, его дом и транспортное средство, доступны на вкладке «Борис» приложения.

Все количество слов (может расширяться) поделено на главы по 100 штук, каждая глава разделена на 10 уровней (уроков) по 10 слов. Главы и уроки можно проходить только последовательно, без пропусков. Пройденные главы и уроки подсвечены зеленым, текущие – голубым, а еще недоступные – серым цветом. 

Один урок состоит из упражнений и теста. К текущему моменту добавлено 3 упражнения:
«Учить» – пользователю показывается слово на двух языках, и ассоциирующаяся с ним картинка для лучшего запоминания. Так повторяется 10 раз для 10 слов.
«Карточки» в двух видах – пользователю показывается слово на английском (или русском), картинка и кнопка «показать», при нажатии на которую показываются: перевод на другой язык и 2 кнопки: «запомнил» и «не запомнил» (смог ли самостоятельно вспомнить перевод слова). Так повторяется, пока пользователь не нажмет кнопку «запомнил» для всех десяти слов.

При прохождении теста необходимо написать перевод на английский язык для всех десяти слов данного упражнения. Допускается совершить только две ошибки, на третьей тест завершается и урок не считается пройденным.

При успешном прохождении урока он помечается зеленым. При прохождении десяти уроков глава, в которой они находятся, помечается зеленым, и «улучшается» текущее состояние персонажа – меняется его одежда, дом и транспортное средство. Задача пользователя – изучить все слова и добиться самых больших высот с Борисом.

### Структура

MainActivity – основная Avtivity приложения, в которой помещены фрагменты:
ProfileFragment – фрагмент с отображением картинки текущего состояния персонажа
SettingsFragment – фрагмент с отображением текущего аккаунта пользователя и кнопки выхода из аккаунта
HomeFragment – фрагмент с отображением списка глав (recycler view), по нажатию на каждый элемент открывается LessonsFragment 
LessonsFragment – фрагмент с отображением уроков текущей главы (recycler view), по нажатию на каждый открывается CurrentLessonFragment.
CurrentLessonFragment – 10 соответствующих уроку слов (recycler view) и упражнения к ним.
Навигация между ProfileFragment, SettingsFragment и HomeFragment осуществляется с помощью BottomNavigationBar.
Упражнения и тест реализованы в отдельных Activity: LearnActivity, TestActivity, CardsActivity.
Экран регистрации реализован в Activity LoginActivity. Сама регистрация реализована в Firebase Authentication. При регистрации необходимо указать e-mail и подтвердить его. Есть возможность восстановить пароль.
История персонажа рассказывается в StoryActivity.

Слова, ссылки на картинки к ним и поля объекта «текущий пользователь» хранятся в Firebase Realtime Database.
Картинки к словам хранятся в Firebase Storage.
