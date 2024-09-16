<img width="982" alt="Снимок экрана 2024-09-09 в 09 39 02" src="https://github.com/user-attachments/assets/3f9fd4e7-4827-44d7-8e03-f90621d0a50b">
<img width="746" alt="Снимок экрана 2024-09-09 в 09 17 24" src="https://github.com/user-attachments/assets/045acde5-a9d7-480e-95d2-a3716484d94b">

________________________________________________________________________________________________________________________________________________________________________

<img width="1035" alt="Снимок экрана 2024-09-09 в 09 40 10" src="https://github.com/user-attachments/assets/437d73c3-f4d3-4a5b-8662-273fe55093da">
<img width="702" alt="Снимок экрана 2024-09-09 в 09 20 55" src="https://github.com/user-attachments/assets/298f3e00-69ec-441d-ba4f-e938d83b0814">

________________________________________________________________________________________________________________________________________________________________________

<img width="1035" alt="Снимок экрана 2024-09-09 в 09 41 27" src="https://github.com/user-attachments/assets/dab353c5-34dd-403d-bad4-a4f2afa32136">
<img width="722" alt="Снимок экрана 2024-09-09 в 09 26 03" src="https://github.com/user-attachments/assets/be75b189-468f-4ddb-90bf-6591ce72d8e8">

________________________________________________________________________________________________________________________________________________________________________

<img width="1035" alt="Снимок экрана 2024-09-09 в 09 41 38" src="https://github.com/user-attachments/assets/273af032-7fd9-4b4e-a091-f38a00e48b2a">
<img width="722" alt="Снимок экрана 2024-09-09 в 09 31 04" src="https://github.com/user-attachments/assets/c1511fe1-9687-42b8-912b-b7c4d090332b">

________________________________________________________________________________________________________________________________________________________________________

<img width="894" alt="Снимок экрана 2024-09-16 в 09 15 37" src="https://github.com/user-attachments/assets/3c4eebe9-631a-4660-aac6-2b37205f1b13">

```
#!/bin/bash
if [ -z "$1" ]; then
      echo "реализация задания с помощью команд "
        #ls -l /usr/local/bin/reg
  #reg banner
      exit 1
    fi

    prog_name="$1"
    dest="/usr/local/bin/$prog_name"

    # проверка- существует ли программа
    if [ ! -f "$prog_name" ]; then
      echo "файл $prog_name не найден."
      exit 1
    fi

    # копирование в /usr/local/bin и установка прав доступа
    sudo cp "$prog_name" "$dest"
    sudo chmod 755 "$dest"

    echo "программа $prog_name успешно зарегистрирована в /usr/local/bin."

  #ls -l /usr/local/bin/reg
  #reg banner
```
![367181824-24e7a5cd-eda3-4ce2-93c6-8707f7b2f3ba-2](https://github.com/user-attachments/assets/a2520ce1-d229-4940-8867-31ff99d31a2d)


________________________________________________________________________________________________________________________________________________________________________

<img width="894" alt="Снимок экрана 2024-09-16 в 09 15 52" src="https://github.com/user-attachments/assets/ea929a24-66f3-4ea1-a7c1-88be848e3287">

```
#!/bin/bash
for file in *.{c,js,py}; do
  if [ -f "$file" ]; then
    first_line=$(head -n 1 "$file")
    if [[ "$first_line" == /* ]] || [[ "$first_line" == \#* ]] || [[ "$first_line" == "//"* ]]; then
      echo "$file: комментарий найден в первой строке."
    else
      echo "$file: комментарий не найден."
    fi
  fi
done
```
![367541977-532fec29-4ed9-4a2a-9196-af26e94a7467](https://github.com/user-attachments/assets/733125ca-2168-4fea-95d6-2be46dae7fd8)
____________________________________________________________________________________________________________________________________________________________________

<img width="894" alt="Снимок экрана 2024-09-16 в 09 15 58" src="https://github.com/user-attachments/assets/2ebe9cfb-df8b-49b8-ade6-4bb223a2f598">

```
#!/bin/bash
if [ "$#" -ne 1 ]; then
    echo "Использование: $0 <директория>"
    exit 1
fi

directory="$1"
if [ ! -d "$directory" ]; then
    echo "Ошибка: директория '$directory' не найдена"
    exit 1
fi

find "$directory" -type f -exec md5sum {} + | sort | awk '{
    if ($1 in seen) {
        print "Дубликат: " $2 " <--> " seen[$1];
    } else {
        seen[$1] = $2;
    }
}'
```
![367542572-32c631ab-32eb-4631-a36b-67bfb1740e24-2](https://github.com/user-attachments/assets/e493447a-cbd0-4995-92fa-29047e936b59)


_____________________________________________________________________________________________________________________________________________________________________
<img width="894" alt="Снимок экрана 2024-09-16 в 09 16 05" src="https://github.com/user-attachments/assets/d71f9361-1ed8-46be-9e11-956a0217230a">

```
#!/bin/bash
    if [ -z "$1" ] || [ -z "$2" ]; then
        echo "укажите путь и расширение"
        exit 1
    fi
    search_path="$1"
    extension="$2"
    archive_name="archive.tar"
    if [ ! -d "$search_path" ]; then
        echo "путь $search_path не существует или не является директорией"
        exit 1
    fi
    echo "файл с расширением $extension из $search_path архивирован в $archive_name..."
    find "$search_path" -type f -name "*.$extension" | tar -cvf "$archive_name" -T -
```
![367542754-e969d60e-476d-46dc-ad20-a5d62eebca79-2](https://github.com/user-attachments/assets/b35328e6-a0ee-48ff-98c9-5d22a1ac1e5e)

________________________________________________________________________________________________________________________________________________________________________

<img width="894" alt="Снимок экрана 2024-09-16 в 09 16 12" src="https://github.com/user-attachments/assets/f72acfa8-5d61-4002-955c-3396ad6b7cfc">

```
#!/bin/bash
    if [ -z "$1" ] || [ -z "$2" ]; then
        echo "укажите путь и расширение"
        exit 1
    fi
    search_path="$1"
    extension="$2"
    archive_name="archive.tar"
    if [ ! -d "$search_path" ]; then
        echo "путь $search_path не существует или не является директорией"
        exit 1
    fi
    echo "файл с расширением $extension из $search_path архивирован в $archive_name..."
    find "$search_path" -type f -name "*.$extension" | tar -cvf "$archive_name" -T -
```
![367543266-939be6f2-9989-4495-a018-16126939b1e7](https://github.com/user-attachments/assets/5911bad6-659d-4416-8f7d-8fe3ddb4c4fd)

________________________________________________________________________________________________________________________________________________________________________

<img width="894" alt="Снимок экрана 2024-09-16 в 09 16 18" src="https://github.com/user-attachments/assets/0aeb9cb0-1748-40f9-a0b7-6825996ac87b">

```
#!/bin/bash
if [ "$#" -ne 1 ]; then
    echo "Использование: $0 <директория>"
    exit 1
fi

directory="$1"

if [ ! -d "$directory" ]; then
    echo "Ошибка: директория '$directory' не найдена"
    exit 1
fi
find "$directory" -type f -name "*.txt" -empty -print
```
![367543523-ca25c543-7098-42d0-8017-93a7c9eef431](https://github.com/user-attachments/assets/847c263b-0e2e-4246-8c57-7c9c27740030)
