# Turtle32_rep


Это небольшое руководство с основными учебными материалами для работы с платой Turtle32. Здесь вы можете найти примеры кода на разных языках и в разных средах разработки. Само руководство будет разделено на два оснвных раздеола по языкам программирования:
* MicroPython (Thonny IDE, esptool)
* C/C++ (Espressif IDE, Arduino, PlatformIO)

**Внимание при использовании одного языка программирования, вы не сможете программмировать плату на другом языке. Эти режимы программирования взаимоисключающие. Читайте о перезаписи загрузчика в разделе [Перезапись загрузчика](#перезапись-загрузчика)**.

Здесь вы сможете найти основнве руководства по установке и первичной настройке среды, а также десять основных примеров по работе с платой, которые можно использовать в своих проектах. Для тех, кто только погружается в разработку и не хзнает с чего начать, то предлагаем сразу перейти в разделе [С чего начать?](#с-чего-начать). 
Быстрая навигация по гайду:
- [С чего начать?](#с-чего-начать)
- [Установка драйверов](#установка-драйверов)
- [еще один раздел](#руководство-по-micropython)
- [Thonny IDE](#thonny-ide)
- [esptool](#esptool)
- [Руководство по C/C++](#руководство-по-сс)
- [Arduino](#arduino)
- [Espressif IDE](#espressif-ide)
- [PlatformIO](#platformio)
- [Перезапись загрузчика](#перезапись-загрузчика)
***
## С чего начать? 
Стоит начать с выбора языка программмирования, на котором будет вестись разработка. В выборе языка вы можете руководствоваться любыми принципами, подойдет любой из языков. Можно сказать только, что большинство разработчиков используют С/С++, поскольку MicroPython сравнительно новый фреймворк для работы. Если вы хотите начать свой путь с программирования на MicroPython, то начинать стоило бы с использования и настройки Thonny IDE. В случае с использованием C/C++, то стоит начать с использования Arduino, который предоставляет большое количество библиотек и более облегченный вариант программирования. Все эти среды предлагают достаточно понятный и удобный интерфейс для пользователя. За тем, как исользовать и настраивать среду можно переходить в соответсвующие разделы, MicroPython - ThonnyIDE и С/C++ - Arduino. Там можно будет пройти гайд по установке и запуску первой программы. Пример программы можно взять в папке ```папке```, к примеру можно взять код из примера ```Blink```.
***
## Установка драйверов
Для работы с платой на любом из языков программирования и любой из сред необходимо установить драйвера чипа CH34x. В папке ```папка``` скачиваем zip архив и запускаем файл. который там храниться. В открывшемся окне нажимаем на кнопку Install. После чего можно переходить непосредственно к настройке среды и программированием.

![image](https://github.com/Bastion-RND/Turtle32_rep/assets/133801615/2a49f5b0-c83e-45b0-aefc-871fd265bd11)

***
## Руководство по MicroPython
Для программирования микроконтроллеров с использованием MicroPython предполагается использование двух разных сред: 
* Thonny IDE
* esptool

### Thonny IDE
Программа устанавливается довольно просто и легко. Для этого необходимо перейти на сайт разработчика и скачиваем файл установщик.

![image](https://github.com/Bastion-RND/Turtle32_rep/assets/133801615/ac665593-f98e-4d48-a7a3-71a1e3238eef)

Ещё одним из преимуществ можно выделить наличие русского языка как одного из оснвных языков интерфейса. Для этого заходим в раздел настроек и выбираем нужный язык. Переключите текущий интерпретатор Python на MicroPython с платой ESP32 на интересующем COM-порте (перед этим плату необходимо подключить к компьютеру).

![image](https://github.com/Bastion-RND/Turtle32_rep/assets/133801615/b6338668-f95b-452f-9a1e-cd89f589466d)

Если это первое использование платы или же до этого вы программировали на C/С++, то необходимо будет дополнительно записать на микроконтроллер ядро MicroPython для дальнейшей работы, то есть перепрошить микроконтроллер, заменив содержание его FLASH памяти. 

![image](https://github.com/Bastion-RND/Turtle32_rep/assets/133801615/fda97469-839a-47c7-b434-b7e209f0b95e)

В открывшемся окошке выбираем параметры нашей платы - семейство микроконтроллера ESP32 S3 и вариант Espressif ESP32 S3. После чего наживаем на кнопку Install и ожидаем загрузки прошивки, это может занять пару минут. 

![image](https://github.com/Bastion-RND/Turtle32_rep/assets/133801615/0d087d33-e85d-44b6-90a5-73816019ff9a)

Появившееся окошко в терминале с таким содержанием будет говорить нам об успешности выполненных действий. Это и послужит сигналом к началу работы с платой. 

![image](https://github.com/Bastion-RND/Turtle32_rep/assets/133801615/84c76e50-9b04-47f3-bf94-2f129e2f53ee)

В окошке сбоку мы можем увидеть как файлы, находящиеся на нашем устройстве, так и файлы, которые находятся на микроконтроллере. Сначала в любом из проектов первым будет исполняться файл ```boot.py```, затем остальные.

![image](https://github.com/Bastion-RND/Turtle32_rep/assets/133801615/e5d64a45-89f7-41da-b5ce-52f5ba2f5121)

Для запуска файла достаточно будет нажать на зеленую кнопку в верхней части экрана. **_Ура-Ура!_**

![Анимация](https://github.com/Bastion-RND/Turtle32_rep/assets/133801615/ec501592-2565-4ad6-9363-7a87167dce3e)

***
### esptool
Для установки вам необходим Python.Установочный пакет для него можно и нужно скачать на официальном сайте. После установки Python на ваш компьютер, в командной строке (или терминале) ввести команду ```pip install esptool```. Для проверки что установка прошла успешно нужно ввести в терминале команду ```esptool.py -h``` или, если вы используете Windows - ```esptool.exe -h```. Вы увидите всю подсказку по данному модулю. Следующим шагом необходимо [скачать прошивку с официального сайта](https://micropython.org/download/ESP32_GENERIC_S3/). Устанавливаем прошивку с помощью esptool, не забыв перед установкой отформатировать плату при помощи этой команды. 

```esptool.py --port COM3 erase_flash``` 

**При использовании команд помните, что порт может отличаться. Посмотреть порт можно при помощи диспетчера устроство в разделе ```Порты (COM и LPT)```**

```esptool.py --port COM3 --baud 460800 write_flash --flash_size=detect 0 D:\esp32s3.bin```, где *D:\esp32s3.bin* это путь к файлу с его названием, где лежит ваша прошивка.

Для загрузки собственной прошивки можно использовать следующую команду (при этом ваш код должен загружаться в формате *.bin*).

```esptool.py -b 460800 --before=default_reset --after=hard_reset write_flash --flash_mode dio --flash_freq 20m --flash_size 4MB 0x0 bootloader.bin 0x10000 my_app-0x01000.bin 0x8000 partition-table.bin 0xd000 ota_data_initial.bin```
***
## Руководство по С/С++
Для программирования микроконтроллеров с использованием MicroPython предполагается использование трех разных сред:
* Arduino
* Espressif IDE
* PlatformIO
***
### Arduino
Установка Arduino IDE является несложной и довольно понятной. Открываем установщик и следуем указаниям по установке. Запускаем IDE и приступаем к настройке среды программирования. Для того, чтобы иметь доступ к файлам прошивки ESP32, необходимо перейти в по пути ```Файл->Настройки``` и в строку *"Дополнительные ссылки для менеджера плат"* необходимо вставить следующую ссылку, а после нажимаем на кнопку "Ок":
```https://dl.espressif.com/dl/package_esp32_index.json```

Далее необходимо перейти по пути ```Инструменты->Плата``` (по умолчанию стоит Arduino Uno) и выбрать Менеджер плат.

![image](https://github.com/Bastion-RND/Turtle32_rep/assets/133801615/cbd7eece-26f5-445a-9d49-8ff34d356084)

В открывшемся окне сверху пишем в поисковой строке "esp32" и начинаем поиск. Устанавливаем пакет данных от Espressif Systems. Ожидаем окончания скачивания, это может занять некоторое время.

![image](https://github.com/Bastion-RND/Turtle32_rep/assets/133801615/36e8b221-cfb3-40f6-9a8f-567a8c6dfeea)

После снова повторяем процесс выбора платы и переходим ```Инструменты->Плата->ESP32 Arduino``` и выбираем ESP32S3 Dev Module.
![image](https://github.com/Bastion-RND/Turtle32_rep/assets/133801615/0c7ae59c-62c2-48f3-a0d3-8a5632189676)

Для загрузки кода теперь необходимо выбрать порт. Далее необходимо перейти по пути ```Инструменты->Порт```, выбираем доступный порт, к которому подключена плата.
![image](https://github.com/Bastion-RND/Turtle32_rep/assets/133801615/27d7d657-8c2f-455e-ae71-b0aa6bb66435)

Ура-Ура! Теперь можно программировать плату и прошивать собственным кодом.
***
### Espressif IDE
Работа в этой IDE может предполагать под собой несколько режимов. Как и установка плагина для ```VSCode```. Начнем наш гайд с установки Espressif IDE. Возьмем установочный файл в папке ```папка```. Выбираем язык установки и проходим далее. На одном из шагов установки мы сможем дополнительно выбрать какие дополнительные данные о микроконтроллерах мы подгружаем. Дополнительно убедимся, что у нас выбрана опция ESP32S3.

![image](https://github.com/Bastion-RND/Turtle32_rep/assets/133801615/4b1a8c30-60d2-4232-832e-7ca8848ab9cf)

В конце установки мы можем увидеть несколько дополнительных параметров. Их мы оставляем и нажимаем на конпку Finish.

![image](https://github.com/Bastion-RND/Turtle32_rep/assets/133801615/0d17279f-833b-43d9-adf2-5bbf0d3c3a31)

После этого откроется несколько терминалов с процессом установки. Ожидаем её завершения и после чего сможем приступить к запуску самой IDE. 

![image](https://github.com/Bastion-RND/Turtle32_rep/assets/133801615/7207d618-bbc6-4aed-b1f3-d3175f51316f)

Открываем проект, который хотим протестировать на плате. К примеру, мигание светодиодом. И проводим основную настройку среды для запуска. Выбираем свой проект в поле ```Launch config``` и выбираем плату ESP32S3 в поле ```Launch target```. После чего нажимаем на кнопку загрузки прошивки, выбираем порт к которому подключена плата и наблюдаем за результатом. Первая сборка проекта может занять длительное время. Для дополнительных сведений о работе с IDE можно обраться к [официальной документации на GitHub](https://github.com/espressif/idf-eclipse-plugin?tab=readme-ov-file#create-a-new-project).

![Анимация1](https://github.com/Bastion-RND/Turtle32_rep/assets/133801615/9184ace3-f353-43f7-b1f2-aabc227d6731)

Так же дополнительно можно воспользоваться и расширением для VSCode. Запускаем приложение и открываем раздел Extensions, это можно сделать сочетанием клавиш ```Ctrl+Shift+X``` или кликнув на соответсвующую иконку. В поисковой строке набираем ```ESP-IDF Extension```, ищем и устанавливаем. 

![image](https://github.com/Bastion-RND/Turtle32_rep/assets/133801615/53a945ea-d810-417e-a34a-7794287800a9)

В Visual Studio выберите меню "View" и "Command Palette" и вводим [configure esp-idf extension]. После этого выбираем ESP-IDF: Configure ESP-IDF Extension. Перед нами откроется такого вида окно. В открывшемся окне выбираем вариант ```Express```. 

![image](https://github.com/Bastion-RND/Turtle32_rep/assets/133801615/1f7ddfef-8da6-43cb-8d0c-9117405fd42c)

Здесь нам предоставляется возможность выбрать версию IDF и путь, куда файлы будут загружены. Это может занять некоторое время. По завершению установки можно приступать к созданию проекта. 
![image](https://github.com/Bastion-RND/Turtle32_rep/assets/133801615/000ad01c-5569-44b5-b499-778a7408f3d8)

На боковой панели теперь присутвует значок Espressif, который позволит быстро перейти к расширению. В верхней части экрана при помощи command можем создать новый проект. 

![image](https://github.com/Bastion-RND/Turtle32_rep/assets/133801615/8c2b5eff-09c6-411f-a9e8-9f84a753045a)

Для того, чтобы загрузить проект, необходимо его сбилдить. Это делается при помощи команды ```ESP-IDF: Build your Project``` в меню "View" и "Command Palette" или сочетанием клавиш ```Ctrl+E+B```. Первый билд может быть довольно долгим. Перед загрузкой необходимо выбрать порт и саму плату, выбираем esp32s3, в нижнем левом углу. Для того, чтобы загрузить код в микрокнтроллер воспользуемся командой ```ESP-IDF: Flash your Project``` в меню "View" и "Command Palette" или сочетанием клавиш ```Ctrl+E+F```.

![Безымянный](https://github.com/Bastion-RND/Turtle32_rep/assets/133801615/be2c8659-f689-4740-a88f-00357ef09d56)

***
### PlatformIO 
Так же дополнительно можно воспользоваться и расширением для VSCode. Запускаем приложение и открываем раздел Extensions, это можно сделать сочетанием клавиш ```Ctrl+Shift+X``` или кликнув на соответсвующую иконку. В поисковой строке набираем ```PlatformIO```, ищем и устанавливаем. После чего в боковой части экрана у нас появиться иконка расширения. нажимаем на нее и попадаем на главный экран, где выбираем опцию создать новый проект и выбираем необходимые настройки для создания проекта. В параметрах ```Board``` выбираем вариант с esp32s3.
![image](https://github.com/Bastion-RND/Turtle32_rep/assets/133801615/c817bf2d-2359-4412-b7e0-2153501e6f91)

После чего можем открыть наш проект или создать его. Для того, чтобы загрузить проект перед этим необходимо его собрать, то есть сделать build проекта. Это можно сделать при помощи сочетания клавиш ```Ctrl+Alt+B``` или при помощи команды ```PlatformIO: Build``` в  меню "View" и "Command Palette".
![image](https://github.com/Bastion-RND/Turtle32_rep/assets/133801615/7f3eb7d6-9830-4dcf-b374-3757896f9aaf)

В случае, если все прошло удачно и в коде нет никаких ошибок мы увидим сообщение в терминале о том, что все было выполнено. Далее мы можем загружать код на микроконтроллер. Это можно сделать при помощи сочетания клавиш ```Ctrl+Alt+U``` или при помощи команды ```PlatformIO: Upload``` в  меню "View" и "Command Palette".
![image](https://github.com/Bastion-RND/Turtle32_rep/assets/133801615/c6a5b0c7-8bcf-4cd4-a782-36f3ef69d346)

***
## Перезапись загрузчика 
Для того, чтобы программировать, используя язык MicroPython, или наоборот после программирования на MicroPython и перейти на С/С++, необходимо будет стереть память микроконтроллера и загрузить новую прошивку при помощи esptool. Подробнее об установке читайте в соответствующем разделе про [esptool](#esptool), там находится информация о его установке. Необходимые файлы прошивки находятся в ```папке```. Для прошивки нового загрузчика необходимо запустить командную строку и прописать следующую команду: 
```esptool.py --port COM3 erase_flash``` 
**При использовании команд помните - порт может отличаться. Посмотреть порт можно при помощи диспетчера устроство в разделе ```Порты (COM и LPT)```**
После чего можно будет загружать новую необходимую прошивку, для этого используем следующую прошивку:
```esptool.py --port COM3 --baud 460800 write_flash --flash_size=detect 0 D:\esp32s3.bin```, где *D:\esp32s3.bin* это путь к файлу с его названием, где лежит ваша прошивка.
