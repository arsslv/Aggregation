
1. Найти скачанный скрипт:

>[!note] Поиск скрипта
>```bash
>find /home -name "restrict-nerc.sh"
>```

2. Выдаст путь к файлу, например:

```
/home/olimp1/Загрузки/restrict-nerc.sh
```

 > ЭТО РАСПОЛОЖЕНИЕ НУЖНОГО ФАЙЛА, его прописывать в командах ниже.
 
 3. Сделать скрипт исполняемым (чтобы можно было запустить):

>[!note] Смена прав скрипта
>```bash
>sudo chmod +x /home/olimp1/Загрузки/restrict-nerc.sh
>```
  
4. Запустить скрипт:

>[!note] Запуск скрипта
>```bash
>sudo bash /home/olimp1/Загрузки/restrict-nerc.sh
>```

> Система попросит написать ДА — написать ДА и enter.
  
>[!check] Всё работает
>Проверка разрешённого сайта после установки...  
>Разрешённый сайт доступен. HTTP-код: 302  
  >
>Проверка блокировки внешнего сайта...  
>curl: (7) Failed to connect to [example.com](https://vk.ru/away.php?to=https%3A%2F%2Fexample.com&utf=1) port 443 after 9 ms: Couldn't connect to server  
>Внешний сайт заблокирован.  
  >
>Ограничение применено временно.  
>После перезагрузки оно обычно исчезнет.  
  >
>Готово.  
>Откат:  
>sudo bash /home/admin/restrict-nerc.sh --rollback  
  
5. Проверить открытие любых сайтов — не должны открываться, кроме [https://nerc.itmo.ru/information/index.html](https://vk.ru/away.php?to=https%3A%2F%2Fnerc.itmo.ru%2Finformation%2Findex.html&utf=1)