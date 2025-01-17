Отражение нажатий - это метод извлечения данных из компьютера с использованием  
только HID интерфейса клавиатуры, вместо USB диска или интернет соединения.  
Это делается путём прослушивания команд на переключение LED индикаторов,  
которые ПК отправляет устройству и интерпретации их особым образом. А именно,  
получение запроса на переключение индикатора NumLock считается за получение 1  
бита со значением 1, а получение запроса на переключение индикатора CapsLock  
считается как получение бита со значением 0. Биты заполняются по порядку от  
самого старшего первым, до самого младшего последним в каждом байте.  
  
Команда "KEYREFLECT_START" указывает устройству начать слушать и записывать  
биты данных. После этого устройство должно будет указать ПК чтобы он начал  
отправлять правильную последовательность нажатий клавиш, что займёт определённое  
время. Это можно сделать путём ввода команд powershell или bash в интерфейс  
командной строки. Для указания конца последовательности используется запрос на  
переключение индикатора ScrollLock. После того как последовательность завершена,  
команда "KEYREFLECT_SAVE **n**" сохранит полученную информацию в файл  
внутри каталога /keyref/. Название файла можно указать в аргументе команды, но  
это не обязательно. Если имя прямо указано, то оно должно быть в формате 8.3 и  
его содержимое будет перезаписываться каждый раз при выполнении скрипта. Если  
имя прямо не указано, то устройство создаст новый файл с ранее не использованным  
численным именем, например /keyref/002.ref, /keyref/003.ref, итд.  
  
Максимальный размер данных полученных в одной последовательности - 512 байт.  
Если команда "KEYREFLECT_SAVE **n**" запускается до того как последовательность  
завершена, то она сначала подождёт либо запроса на переключение ScrollLock,  
либо достижения лимита в 512 байт, в зависимости от того что случится раньше.  
Только полсе этого устройство перейдёт к сохранению данных в файл. Имейте в  
виду, что такой способ получения данных обычно очень медленный, так что его  
применение имеет смысл только в случаях когда обычные средства невозможны,  
например ПК с запретом на USB диски и без подключения к интернету.  
Поддержка отражения нажатий на macOS крайне ограничена, из-за того что обычно  
на этой системе статус LED индикаторов межу клавиатурами не синхронизирован.  
  
В репозитории есть [образец скрипта](https://github.com/krakrukra/PocketAdmin/tree/master/extra/payloads/KeystrokeReflectionTest) для использования отражения нажатий  
  