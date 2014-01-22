### Raspberry Pi, Raspbmc, boblight и Lightpack

### Требуемые программы и утилиты:

- Скачать и установить Raspbmc - версию не позднее июля. См. в раздел [http://www.raspbmc.com/download/](http://www.raspbmc.com/download/) 
- Скачать и установить  [configuration file](https://skydrive.live.com/?cid=0f775ea9b6f34329&id=F775EA9B6F34329%211770)
- Установить [WinSCP](http://winscp.net/eng/download.php)
- Установить [PuTTy](http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html)
-  [Установить SSH доступ](http://htpcbuild.com/htpc-software/raspberry-pi-raspbmc/connecting-to-raspbmc-ssh/)
- Настроить [root доступ](http://www.raspbmc.com/wiki/user/root-access/)
и скопировать файл конфигурации

### Порядок действий:

1. В Raspbmc добавить параметры в разделе программы
2. Перейти к Конфигурации Системы - Service Management
4. Выбрать поддержка Boblight
5. Подключиться к вашему pi с помощью WinSCP, войти в систему как root, использовать IP-адрес, который вы указали выше.
6. Перейдите в /etc
7. Скопировать boblight.conf файла : выше и ниже этого места
8. Разместить светодиоды на телевизоре. 
