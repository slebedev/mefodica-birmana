Что это?
========

Это комплект раскладок для Mac OS X, основанных на нескольких известных раскладках:

* «[Русская машинопись](https://ru.wikipedia.org/wiki/ЙЦУКЕН#.C2.AB.D0.A0.D1.83.D1.81.D1.81.D0.BA.D0.B0.D1.8F_.28.D0.BC.D0.B0.D1.88.D0.B8.D0.BD.D0.BE.D0.BF.D0.B8.D1.81.D1.8C.29.C2.BB)»

  ![](https://upload.wikimedia.org/wikipedia/ru/a/a9/Keyboard_layout_ru_%28typewriter%29.gif)
* «[Мефодица](http://www.tema.ru/rrr/soft/)» Лебедева
* «[Типографская раскладка](http://ilyabirman.ru/projects/typography-layout/)» Бирмана
 
  ![](http://ilyabirman.ru/projects/typography-layout/i/layout-mac.png)
* «[Colemak](https://ru.wikipedia.org/wiki/Colemak)»
  ![](https://upload.wikimedia.org/wikipedia/commons/thumb/8/84/KB_US-Colemak.svg/800px-KB_US-Colemak.svg.png)
 

Он нужен для того, чтобы можно было переключать язык по кнопке «Caps Lock» безо всяких дополнительных ухищрений и использовать все возможности перечисленных раскладок.

Зачем это?
==========

Начнём с того, что переключать раскладку по Caps Lock — удобно. В раскладке «Мефодица» оба языка — английский и русский прекрасно уместились в одной раскладке и переключаются с помощью кнопки «Caps Lock».

Некоторым при этом хочется иметь стандартную русскую раскладку, некоторым — русскую машинопись, а некоторым — ещё и поменять английскую раскладку на Коулмак

Ну а «Типографская раскладка» оказалась сдесь совершенно к месту — все мы любим эти ваши типографские штучки, вроде кавычек и тире.

Установка
=========

Для установки достаточно:

- Скопировать все три файла .keylayout в папку «~/Library/Keyboard Layouts/» (или «/Library/Keyboard Layouts/», чтобы она была доступна всем пользователям)
- Перелогиниться (или перезагрузиться).
- Выбрать в настройках одну из раскладок:
  - «Мефодица», если вам хочется классическую русскую раскладку.
  - «Мефодица(машинопись)», если вы хотите раскладку «Русскую машинопись»
  - «Мефодица(машинопись) + Коулмак», если вы хотите раскладку «Русскую машинопись» и английскую раскладку «Colemak».
- ...
- Profit!

P/S: Все раскладки содержат Бирмановские типографские знаки и поддерживают переключение по Caps Lock.

Маленькие хитрости
==================

Чтобы удалить раскладку по умолчанию и оставить только «Мефодицу», можно обратиться к следующему [руководству](https://discussions.apple.com/thread/2705973?start=0&tstart=0):

- Сделать бэкап настроек.
- Установить редактор файлов *.plist (Xcode подойдёт).
- Убрать галочки со ВСЕХ раскладкок, кроме основной системной («U.S.») и нашей «Мефодицы Бирмана» в настройках тут: System Preferences > Languages & Text > Input sources
- Открыть файл ~/Library/Preferences/ByHost/com.apple.HIToolbox.<БЛА-БЛА-БЛА>.plist («БЛА-БЛА-БЛА» - это просто какая-то непонятная строка) с помощью редактора plist-файлов.
- В пункте "AppleEnabledInputSources" удалить первую запись. Она будет выглядеть вот так:

        <dict>
          <key>InputSourceKind</key>
          <string>Keyboard Layout</string>
          <key>KeyboardLayout ID</key>
          <integer>0</integer>
          <key>KeyboardLayout Name</key>
          <string>U.S.</string>
        </dict>
- Сохранить файл, перелогиниться (или перезагрузиться).

После удаления всех раскладок, значок переключения раскладок становится не нужен и его можно отключить.
