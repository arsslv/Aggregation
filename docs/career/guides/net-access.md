
Найти скачанный скрипт:

>```bash
>find /home -name "restrict-nerc.sh"
>```

Выдаст путь к файлу, например:

```
/home/olimp1/Загрузки/restrict-nerc.sh
```

> ЭТО РАСПОЛОЖЕНИЕ НУЖНОГО ФАЙЛА, его прописывать в командах ниже.

Сделать скрипт исполняемым (чтобы можно было запустить):

>```bash
>sudo chmod +x /home/olimp1/Загрузки/restrict-nerc.sh
>```

Запустить скрипт:

>```bash
>sudo bash /home/olimp1/Загрузки/restrict-nerc.sh
>```

> Система попросит написать ДА — написать ДА и enter.
  
Если всё работает, выдаст сообщение:

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
  
Проверить открытие любых сайтов — не должны открываться, кроме [https://nerc.itmo.ru/information/index.html](https://vk.ru/away.php?to=https%3A%2F%2Fnerc.itmo.ru%2Finformation%2Findex.html&utf=1)