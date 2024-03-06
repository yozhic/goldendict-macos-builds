# goldendict-macos-builds

Неофициальные сборки раннего доступа программы GoldenDict для macOS

Собрано на базе Qt 5.14.2 и QtWebKit 5.212.0 Alpha 4  
Работоспособность протестирована на Mojave 10.14.6 и Monterey 12.6  

> [!IMPORTANT]
> Настоящие сборки предоставляются как есть, без каких-либо гарантий, исключительно в ознакомительных целях.

## Описание

Сборки предоставляются в двух версиях: `master` и `mac-adapted`.  

Версия `master` собирается из исходного кода [официального репозитория GoldenDict](https://github.com/goldendict/goldendict) без изменений и дополнений, как есть.  

Версия `mac-adapted` собирается на основе исходного кода официального репозитория GoldenDict, с внесением косметических изменений и дополнений для лучшей адаптации к внешнему виду macOS. С историей изменений можно ознакомиться в ответвлении кода GoldenDict, где они производятся. Вкратце, они включают: новые иконки для панелей инструментов, дополнительные стили для окон и словарных статей.  

Дополнительные стили включаются в настройках программы, на вкладке `Интерфейс`, в выпадающем списке `Стиль интерфейса`. Стили синхронизированы с системными настройками оформления macOS, т.е. при включенном системном оформлении `Light` следует использовать стиль `macOS Light`, а при системном `Dark` — один из двух тёмных стилей.  

Отличия между двумя версиями проиллюстрированы ниже.  

## Отличия

Сравнение версий: окно программы, системный стиль Light  

![COMPARE LIGHT](https://github.com/yozhic/goldendict-macos-builds/blob/main/screenshots/COMPARE_LIGHT.png)  

Сравнение версий: окно программы, системный стиль Dark  

![COMPARE DARK](https://github.com/yozhic/goldendict-macos-builds/blob/main/screenshots/COMPARE_DARK.png)  

Сравнение версий: окно программы, системный стиль Dark, стиль окна `macOS Dark Deep`  

![COMPARE DARK DEEP](https://github.com/yozhic/goldendict-macos-builds/blob/main/screenshots/COMPARE_DARK_DEEP.png)  

Сравнение версий: диалог настроек, системный стиль Light  

![COMPARE PREFS](https://github.com/yozhic/goldendict-macos-builds/blob/main/screenshots/COMPARE_PREFS.png)  

## Скачать

Готовые к использованию сборки, упакованные в формат DMG, размещаются в разделе [Releases](https://github.com/yozhic/goldendict-macos-builds/releases).  

## Самостоятельная сборка

1. Скачиваем установщик Qt. Последний доступный для скачивания: [5.14.2](https://download.qt.io/archive/qt/5.14/5.14.2/).  

2. Устанавливаем Qt. В процессе понадобится подключиться к личному кабинету Qt (если не существует, создаём). Путь для установки, например: `/Users/yozhic/Qt`. В окне выбора компонентов отмечаем `Qt 5.14.2` → `macOS` (`Developer` отмечен по умолчанию).  

3. Скачиваем QtWebKit 5.212.0 Alpha 4, скомпилированные бинарники для macOS: [qtwebkit-MacOS-MacOS_10_13-Clang-MacOS-MacOS_10_13-X86_64.7z](https://github.com/qtwebkit/qtwebkit/releases). Распаковываем, копируем всю структуру папок в `~/Qt/5.14.2/clang_64`.  

4. Клонируем головной репозиторий `goldendict`:  

   ```sh
   cd ~/git && git clone https://github.com/goldendict/goldendict
   ```
   
5. Запускаем создание проекта и сборку:  

   ```sh
   cd ~/git/goldendict && ~/Qt/5.14.2/clang_64/bin/qmake && make
   ```

6. Упаковываем собранный `GoldenDict.app` необходимыми библиотеками:  

   ```sh
   ~/Qt/5.14.2/clang_64/bin/macdeployqt GoldenDict.app
   ```

   Можно также сразу создать `dmg`:  
   
   ```sh
   ~/Qt/5.14.2/clang_64/bin/macdeployqt GoldenDict.app -dmg
   ```
