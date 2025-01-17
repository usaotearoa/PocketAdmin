Некоторые примеры рабочих скриптов можно найти в папке [/extra/payloads/](https://github.com/krakrukra/pocketadmin/tree/master/extra/payloads).  
Каждый пример рабочего скрипта помещается в отдельную папку, внутри которой  
все собраны все необходимые файлы, вместе с документацией в файле readme.md  
Файл документации является необязательным и создан только для того, чтобы  
объяснить что делает данный скрипт. Вы можете прочитать эти файлы документации,  
просматривая каждый конкретный каталог в репозитории. Иногда вы можете просто  
скопировать все содержимое внутри такого каталога на устройство и этого будет  
достаточно, но это работает не всегда. Возможно вам потребуется предпринять  
несколько дополнительных шагов подготовки (например, настроить метку FAT  
раздела на диске итд.) перед тем, как ваш скрипт сможет правильно работать.  
Рекоммендуется всегда читать файл readme.md, а иногда возможно и комментарии  
внутри самого рабочего скрипта перед использованием какого-то из примеров.  
  
Имейте в виду, что невозможно сделать рабочие скрипты, которые будут  
идеально подходить всем и в любой ситуации, так чтобы вам удавалось  
избежать дополнительной подготовки или возможно каких-то изменений.  
У каждого есть свои личные предпочтения и требования, такие как  
настройки языка компьютера, различное целевое оборудование / ОС итд.  
Чаще всего вам нужно будет не просто копировать файлы из примеров,  
но действительно понимать, что и как делает ваш скрипт. Все эти  
примеры рабочих скриптов созданы только с одной целью, это дать  
вам представление о том, как можно использовать устройство. Многие  
эти примеры намеренно сделаны простыми и общими. Для полноценного  
применения вам придется создавать свои собственные скрипты, возможно  
используя код или идеи, которые вы узнали из примеров.  
  
Поскольку язык команд, используемый PocketAdmin основан на ducky script 1.0  
вы также можете довольно легко использовать рабочие скрипты, которые  
изначально были разработаны для [USB Rubber Ducky](https://github.com/hak5/usbrubberducky-payloads) или некоторые из  
скриптов для [HAK5 bash bunny](https://github.com/hak5/bashbunny-payloads).  
При желании, вы также можете черпать вдохновение в скриптах, которые  
сделаны в других форматах, например для badusb устройств [на ардуино](https://github.com/samratashok/kautilya);  
При необходимости вы можете перевести их в ducky script без особых усилий.  
Здесь тоже нужно понимать, что если кто-то сделал рабочий скрипт в 2012  
году для Windows7 то не обязательно он будет без доработок работать у вас.  
  
---
  
Всегда имейте в виду, что для того чтобы всё работало, все  
нужные файлы должны быть в нужных местах! Это означает:  
  
1. Если у вас есть какие-то команды предварительной конфигурации, вам нужно  
разместить их отдельно в файле **config.txt** в корневом каталоге устройства.  
  
2. Если сканер ОС не был включен (по умолчанию), вам нужно разместить  
ваш файл скрипта (**payload.txt**) в корневом каталоге устройства.  
  
3. Если  сканер ОС был включен, вам нужно разместить файлы скриптов  
(windows.txt, linux.txt, other.txt итд.) В каталоге **/fgscript/**  
а также сделать базу данных .fgp файлов в каталоге **/fingerdb/**.  
  
4. Если вы хотите заменить раскладку клавиатуры (по умолчанию QWERTY),  
то сначала вам нужно будет разместить необходимые файлы в каталоге **/kblayout/**.  
Файлы раскладок доступны в [/extra/payloads/LayoutTest/kblayout/](https://github.com/krakrukra/PocketAdmin/tree/master/extra/payloads/LayoutTest/kblayout)  
  
5. Если вы хотите использовать рабочие скрипты по запросу, вам нужно  
поместить их внутрь каталога **/ondemand/**, с именами от **script03.txt** до **script19.txt**  
  