# Дружим Raspberry Pi, Raspbmc, Boblight и Lightpack

### Требуемые программы и утилиты:

- Скачать и установить *Raspbmc* - версию не позднее июля. См. в раздел [http://www.raspbmc.com/download/](http://www.raspbmc.com/download/) 
- Установить [WinSCP](http://winscp.net/eng/download.php)
- Установить [PuTTy](http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html)
- [Установить SSH доступ](http://htpcbuild.com/htpc-software/raspberry-pi-raspbmc/connecting-to-raspbmc-ssh/)
- Настроить [root доступ](http://www.raspbmc.com/wiki/user/root-access/)
и скопировать файл конфигурации

### Порядок действий:

1. Перейти в *Programs* &rarr; *Raspbmc settings* &rarr; *Service management*
2. Включить *Boblight support*
3. Подключиться к вашему *RPi* с помощью *WinSCP*, войти в систему как *root*, использовать IP-адрес, который вы указали выше.
4. Скачать [файл конфигурации](https://skydrive.live.com/?cid=0f775ea9b6f34329&id=F775EA9B6F34329%211770) и поместить его в `/etc`
5. Разместить светодиоды на телевизоре и настроить *Boblightd* согласно [этой инструкции](http://ajpawelski.wordpress.com/how-to-raspberry-pi-raspbmc-and-a-lightpack/#part4)

---

Спасибо [Andrew Pawelski](http://apawelski.wordpress.com/). Инструкция основана на его [статье](http://ajpawelski.wordpress.com/how-to-raspberry-pi-raspbmc-and-a-lightpack/).
