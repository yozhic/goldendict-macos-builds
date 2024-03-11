<sup>[ en | [ru](https://github.com/yozhic/goldendict-macos-builds/blob/main/README_RU.md) ]</sup>  

# goldendict-macos-builds

Unofficial third-party builds of GoldenDict for macOS

Based on Qt 5.14.2 (Clang 11.0, x86_64) with QtWebKit 5.212.0 Alpha 4  
Tested on Mojave, Big Sur, Monterey  

> [!IMPORTANT]  
> Provided "as is" with no warranty of any kind.  

## Описание

Сборки предоставляются в двух версиях: `master` и `mac-adapted`.  

Версия `master` собирается из исходного кода [официального репозитория GoldenDict](https://github.com/goldendict/goldendict) без изменений и дополнений, как есть.  

Версия `mac-adapted` собирается на основе исходного кода официального репозитория GoldenDict, с внесением косметических изменений и дополнений для лучшей адаптации к внешнему виду macOS. С историей изменений можно ознакомиться в [ответвлении кода GoldenDict](https://github.com/yozhic/goldendict/tree/mac-adapted), где они производятся. Вкратце, они включают: новые иконки для панелей инструментов, дополнительные стили для окон программы и словарных статей.  

Отличия между двумя версиями проиллюстрированы ниже.  

## Настройки

### В системе

Для работоспособности таких функций, как Всплывающее окно и Глобальные горячие клавиши, необходимо предоставить GoldenDict разрешение на управление Mac через функции универсального доступа. Для этого открываем меню Apple :green_apple: → Системные настройки → Защита и безопасность → вкладка Конфиденциальность. Разблокируем возможность редактирования щелчком по иконке замочка :lock: внизу окна. В левой панели выбираем Универсальный доступ, в правой жмём кнопку Добавить :heavy_plus_sign:, находим и выделяем `GoldenDict.app`, жмём Открыть. Можно также перетащить `app` из окна Finder на панель списка приложений. Отмечаем флажок :ballot_box_with_check: слева от `GoldenDict.app`[^1].  

[^1]: Источник: [Apple Support: Разрешение доступа к компьютеру Mac программам Универсального доступа](https://support.apple.com/ru-ru/guide/mac-help/mh43185/10.14/mac/10.14)  

В силу особенностей работы macOS, процедуру предоставления разрешений необходимо повторять после каждого обновления GoldenDict. Для этого в указанном диалоге выделяем строку `GoldenDict.app` и жмём кнопку Удалить :heavy_minus_sign:. Затем жмём кнопку Добавить :heavy_plus_sign: и далее, как описано выше.  

### В программе

Дополнительные стили сборки `mac-adapted` включаются в настройках GoldenDict → вкладка Интерфейс → выпадающий список Стиль интерфейса. Стили синхронизированы с системными настройками оформления macOS, т.е. при включенном системном оформлении `Light` следует использовать стиль `macOS Light`, а при системном `Dark` — один из двух тёмных стилей, `macOS Dark` или `macOS Dark Deep`.  

## Известные проблемы

1. Если при включении GoldenDict в других приложениях перестаёт работать копирование текста по сочетанию клавиш <kbd>Cmd</kbd>+<kbd>C</kbd>, необходимо предоставить GoldenDict разрешение на Универсальный доступ. Описание этой процедуры см. выше. Можно также переназначить это сочетание в настройках GoldenDict → Горячие клавиши.

2. Функция Всплывающее окно на последних версиях macOS работает не так хорошо, как на Windows. Мы рекомендуем воздержаться от её использования на macOS и отключить её в настройках.  

## Отличия

Сравнение версий: окно программы, системное оформление `Light`, стиль `macOS Light`  

![COMPARE LIGHT](https://github.com/yozhic/goldendict-macos-builds/blob/main/screenshots/COMPARE_LIGHT.png)  

Сравнение версий: окно программы, системное оформление `Dark`, стиль `macOS Dark`  

![COMPARE DARK](https://github.com/yozhic/goldendict-macos-builds/blob/main/screenshots/COMPARE_DARK.png)  

Сравнение версий: окно программы, системное оформление `Dark`, стиль `macOS Dark Deep`  

![COMPARE DARK DEEP](https://github.com/yozhic/goldendict-macos-builds/blob/main/screenshots/COMPARE_DARK_DEEP.png)  

Сравнение версий: диалог настроек, системное оформление `Light`, стиль `macOS Light`  

![COMPARE PREFS](https://github.com/yozhic/goldendict-macos-builds/blob/main/screenshots/COMPARE_PREFS.png)  

## Скачать

Готовые к использованию сборки, упакованные в контейнер `dmg`, размещаются в разделе [Releases](https://github.com/yozhic/goldendict-macos-builds/releases).  

## Самостоятельная сборка

Для возможности сборки в системе должен быть установлен [Xcode](https://developer.apple.com/support/xcode). Далее:  

1. Скачиваем установщик Qt. Последний в свободном доступе: [5.14.2](https://download.qt.io/archive/qt/5.14/5.14.2/).  

2. Устанавливаем Qt. В процессе понадобится подключиться к личному кабинету Qt (если не существует, создаём). Путь для установки, например: `~/Qt`. В окне выбора компонентов отмечаем `Qt 5.14.2` → `macOS` (`Developer` отмечен по умолчанию).  

3. Скачиваем QtWebKit 5.212.0 Alpha 4, скомпилированный для macOS: [qtwebkit-MacOS-MacOS_10_13-Clang-MacOS-MacOS_10_13-X86_64.7z](https://github.com/qtwebkit/qtwebkit/releases). Распаковываем архив, копируем всю структуру папок в `~/Qt/5.14.2/clang_64`.  

4. Клонируем головной репозиторий `goldendict`:  

   ```sh
   git clone https://github.com/goldendict/goldendict && cd ./goldendict
   ```
   
5. Создаём проект:  

   ```sh
   ~/Qt/5.14.2/clang_64/bin/qmake
   ```

   Собираем:  

   ```sh
   make
   ```

6. Укомплектовываем собранный `GoldenDict.app` необходимыми библиотеками:  

   ```sh
   ~/Qt/5.14.2/clang_64/bin/macdeployqt GoldenDict.app
   ```

   Можно также сразу создать простой `dmg`:  
   
   ```sh
   ~/Qt/5.14.2/clang_64/bin/macdeployqt GoldenDict.app -dmg
   ```
