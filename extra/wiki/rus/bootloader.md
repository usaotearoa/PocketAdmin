#### Важно: для предыдущих устройств серии 1.2 используйте [Старую процедеру прошивки](https://github.com/krakrukra/12004-pocketadmin-wiki)  
  
С новой версией платы (серия 1.3) не обязательно использовать программатор  
ST-Link V2 для обновления прошивки. Вместо этого вы можете использовать  
DFU загрузчик и обновлять прошивку прямо через интерфейс USB. Для этого  
вам нужно будет установить специальное программное обеспечение на вашем  
компьтере, подключить к этому компьютеру PocketAdmin и перевести его в  
DFU режим. После этого можно будет отправить файл прошивки в формате DfuSe  
встроенному загрузчику используя подходящую вам программу. Самая последняя  
версия прошивки в DfuSe формате доступна в репозитории, в файле под именем  
**/firmware/firmware_13nnn.dfu** , где nnn - номер обозначающий версию  
прошивки (например, firmware_13002.dfu);  
  
Есть 2 способа ввести PocketAdmin в режим DFU. Если ваше устройство уже  
имеет прошивку, вы можете попасть в режим DFU использовав длинную серию  
нажатий клавиши Capslock **дважды**. То есть в первый раз, когда вы нажимаете  
кнопку Capslock 20 или более раз подряд устройство перезагрузится в  
режим MSD. Если снова нажать Capslock 20 или более раз подряд, то  
устройство перезагрузится в режим DFU.  
Если же предыдущая прошивка на устройстве повреждена или её нет,  
вам придется закоротить контакты boot0 и питания 3,3В вручную.  
После этого подключите устройство и оно войдёт в режим DFU сразу.  
Соединить эти контакты удобно в отверстиях для программирования,  
используя кусок проволоки или просто пинцетом. 2 отверстия, которые  
вам нужно соединить находятся в углу печатной платы, и они оба имеют  
круглые контактные площадки вокруг, квадратная площадка должна быть  
на противоположной стороне и подключать к ней ничего не нужно.  
  
Вы можете посмотреть [это видео](https://www.youtube.com/watch?v=t0oajBFZcZY) где показаны  
как старая, так и новая процедуры обновления прошивки.  
  
---
  
#### Процедура обновления через DFU на Linux (Debian)  
  
1. Установите утилиту dfu-util (sudo apt-get install dfu-util)  
2. Загрузите этот репозиторий (.zip) на свой компьютер и разархивируйте его  
3. Откройте окно терминала в папке /firmware/  
4. Вставьте PocketAdmin в USB порт вашего ПК  
5. Нажмите на Capslock 20 или более раз  
6. Подождите не менее 5 секунд  
7. Снова нажмите на Capslock 20 или более раз  
8. Запустите команду: dfu-util -a 0 -D firmware_13nnn.dfu  
9. Дождитесь завершения процесса обновления, извлеките устройство  
  
#### Процедура обновления через DFU на Windows  
  
1. Загрузите программу [DfuSe demo](https://www.st.com/en/development-tools/stsw-stm32080.html)  
2. Установите её и запустите  
3. Загрузите этот репозиторий (.zip) на свой компьютер и разархивируйте его  
4. Вставьте PocketAdmin в USB порт вашего ПК  
5. Нажмите на Capslock 20 или более раз  
6. Подождите не менее 5 секунд  
7. Снова нажмите на Capslock 20 или более раз  
8. Нажмите кнопку "Choose" (справа внизу)  
9. Выберите файл /firmware/firmware_13nnn.dfu  
10. Выберите "Internal Flash" в качестве целевой области (Target ID = 00)  
11. Нажмите кнопку «Upgrade» (справа внизу)  
12. Подтвердите, нажав "Yes"  
13. Дождитесь завершения процесса обновления, извлеките устройство  
  