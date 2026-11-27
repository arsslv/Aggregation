# Установка и проверка учебных программ на Astra Linux

## Запуск скрипта

1. Скачать и распаковать папку `dev-setup`.

>[!warning] Важно!
>Архивы программ внутри `installers` распаковывать и переименовывать не нужно.

```text
dev-setup/
├── install-dev.sh
└── installers/
    ├── code_1.148.0-1795526052_amd64.deb
    ├── FreeBASIC-1.10.1-linux-x86_64.tar.gz
    ├── jdk-27_linux-x64_bin.deb
    ├── kotlin-compiler-2.4.21.zip
    ├── PABCNETC.zip
    ├── idea-2026.3.0.1.tar.gz
    ├── pycharm-2026.3.0.2.tar.gz
    └── wing-101-12.1.2.0-linux-x64.tar.bz2
```

2. Запустить скрипт.

>[!info] Команда для запуска скрипта.
>```bash
>sudo bash ~/Загрузки/dev-setup/install-dev.sh
>```

## Установка зависимостей FreeBASIC

В терминале ввести команды:

>[!info] Установка библиотек
>```bash
>sudo apt install libncurses-dev
>sudo apt install libtinfo5
>```

---
## Проверка VS Code, PyCharm и Wing 101

#### Python

1. Открыть **Extensions (расширения)** в левом боковом меню и установить расширение **Pyhton** (от Microsoft).
2. **Ctrl+Shift+P** -> `Python: Select Interpreter` -> должен быть выбран `/usr/bin/python3`.
3. Создать файл **`hello.py`** и записать:

```python
print("Python OK")
```

4. Сохранить файл (**Ctrl+S**) и нажать **Run Python File** -> `Python OK`.

#### PyCharm

1. Проверить, что **System Interpreter** — `/usr/bin/python3`.
2. Открыть файл **`hello.py`**.
3. Запустить файл -> `Python OK`.

#### Wing 101

1. Проверить, что **System Interpreter** — `/usr/bin/python3`.
2. Открыть файл **`hello.py`**.
3. Запустить файл -> `Python OK`.
## C++ в VS Code

1. Открыть **Extensions (расширения)** в левом боковом меню и установить расширение **code runner**.
2. Создать **`hello.cpp`**:

```cpp
#include <iostream>

int main() {
    std::cout << "C++ OK\n";
}
```

>[!tip] Может появиться уведомление
>Do you want to install the recommended 'C/C++ Extension Pack' extension from Microsoft for the C++ language?
>
>**Согласиться и нажать кнопку Install.**

3. Сохранить файл (**Ctrl+S**).
4. Нажать правой кнопкой мыши на код -> Run Code -> `C++ OK`.

---
## Проверка Java и Kotlin в IntelliJ IDEA

### Java

1. Создать проект **New Project → Java**.
2. Проверить, что выбран установленный **JDK** и система сборки **IntelliJ**.
3. Правый клик по папке исходников → **New** → **Java Class** → `Main`. IntelliJ создаст `Main.java`. Метод `public static...` пишется внутри класса:

```java
    public class Main {
        public static void main(String[] args) {
            System.out.println("Java OK");
        }
    }
```

   4. Нажать зелёный треугольник рядом с `main`. В панели **Run** должно появиться `Java OK`.

### Kotlin

1. Создать проект **New Project → Kotlin**.
2. Проверить, что выбран установленный **JDK** и система сборки **IntelliJ**.
3. Правый клик по папке исходников → **New** → **Kotlin Class** → `Main`. Написать функцию в файле:

```Kotlin
    fun main() {
        println("Kotlin OK")
    }
```

   4. Нажать зелёный треугольник рядом с `main`. В панели **Run** должно появиться `Kotlin OK`.

---
## Free Pascal, PascalABC.NET, FreeBASIC и D

>[!warning] Проверяются из терминала, искать ярлыки в меню не нужно.

### Free Pascal и PascalABC.NET

1. Создать и сохранить файл **`hello.pas`**:

```pascal
program Hello;
begin
  WriteLn('Pascal OK');
end.
```

2. Выполнить обе строки **по отдельности**:

```bash
fpc hello.pas && ./hello
pabcnetc hello.pas && mono hello.exe
```

Обе должны вывести `Pascal OK`. 

>[!warning] Важно!
>Это два разных компилятора. Установленный `pabcnetc` — **консольная версия PascalABC.NET**, не графическая IDE.

### FreeBASIC

1. Создать и сохранить файл **`hello.bas`**:

```basic
Print "BASIC OK"
```

2. Выполнить в терминале:

```bash
fbc -version
fbc hello.bas -x hello-basic && ./hello-basic
```

### D

1. Создать и сохранить файл **`hello.d`**:

```d
import std.stdio;

void main() {
    writeln("D OK");
}
```

2. Выполнить в терминале:

```bash
gdc hello.d -o hello-d && ./hello-d

# Если не сработало, то прописать: 
ldc2 hello.d -of=hello-d && ./hello-d
```

Ожидаемый вывод — `D OK`.



