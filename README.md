
<div align="center">
<p>
    <img src="Onion.png" width="150" alt="Onion">
</p>

<h1>This is programming language named "Onion"</h1>

Onion is a dynamically typed, general purpose programming language for creating universal applications!
</div>

<h1 align="center"> Features </h1>

 - The possibility of <a href="https://github.com/bas1c1/Onion/wiki/%D0%A4%D1%83%D0%BD%D0%BA%D1%86%D0%B8%D0%BE%D0%BD%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D0%B5-%D0%BF%D1%80%D0%BE%D0%B3%D1%80%D0%B0%D0%BC%D0%BC%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5">functional programming</a>
 - <a href="https://github.com/bas1c1/Knife"> Knife </a> http listening library
 - Supports the ability to connect DLLs written in Visual C# or JavaScript (<a href="https://github.com/bas1c1/OnionProgrammingLanguage/wiki/Библиотека-%22cs%22-(Работа-с-DLL-написанные-на-C%23-и-JavaScript)"> "cs" library </a>)
 - Friendly and easy-to-read syntax
 - Lightweight interpreter
 - Standart libraries

<h1 align="center"> In the last update </h1>

In the latest update was added "ldef" expression

`~5500` lines of code

<div align="center">
    <h1 align="center"> Documentation </h1>
    <a href="https://github.com/bas1c1/OnionProgrammingLanguage/wiki"> Documentation </a>
</div>

<h1 align="center"> Contribution </h1>
Onion is open-source project. You can throw pull requests and I'll look through them all!

<h1 align="center"> Examples </h1>

"Hello world":

```
use "std"

print("Hello, world!")

stop()

//Output: Hello, world!
```

Calculator:

```
use "std"

fnum = to_int(input("Enter first number: "))
snum = to_int(input("Enter second number: "))
op = input("Enter operation (+, -, /, *): ")
var result

if (op == "+") {
	result = fnum + snum
}

if (op == "-") {
	result = fnum - snum
}

if (op == "*") {
	result = fnum * snum
}

if (op == "/") {
	result = fnum / snum
}

if (op != "+" && op != "-" && op != "*" && op != "/") {
	throw_new_exception("Invalid operation!")
}

print(result)
stop()
```

Simple console game:

```
use "std"
use "random"
use "winapi"

clear()

player = "*"
yabloko = "@"

visota = 20
shirina_b_sten = 20
shirina_s_sten = 18

player_x = 10
player_y = 9
yabloko_x = randint(1, 19)
yabloko_y = randint(1, 17)

ochki = 0

fps = 0
kadrov = 0

def mainloop() {
    i_input = get_key()

    for i = 0; i <= visota; i++ {
        if i == 0 || i == 20 {
            for j = 0; j <= shirina_b_sten; j++ {
                sout "#"
            }
        }
        else {
            sout "#"
            for c = 0; c <= shirina_s_sten; c++ {
                sout " "
            }
            sout "#"
        }
        sout "\n"
    }


    while (true) {
	sleep(50)

        set_cursor_position(yabloko_x, yabloko_y)
        sout yabloko

	if (player_x == 20 || player_y == 18 || player_x == 0 || player_y == 0) {
            player_x = 10
            player_y = 9
        }

        set_cursor_position(player_x, player_y)
        sout " " + "\b"

        if (yabloko_x == player_x && yabloko_y == player_y) {
            set_cursor_position(yabloko_x, yabloko_y)
            sout " "
            ochki += 1
            yabloko_x = randint(1, 19)
            yabloko_y = randint(1, 17)
        }

        i_input = get_key()

        if i_input == "w" || i_input == "ц" {
            player_y -= 1
        }

        if i_input == "s" || i_input == "ы" {
            player_y += 1
        }

        if i_input == "a" || i_input == "ф" {
            player_x -= 1
        }

        if i_input == "d" || i_input == "в" {
            player_x += 1
        }

        if i_input == "x" || i_input == "ч" {
            exit()
        }

        if (player_x == 20 || player_y == 18 || player_x == 0 || player_y == 0) {
            player_x = 10
            player_y = 9
        }

        set_cursor_position(player_x, player_y)
        sout player

        set_cursor_position(10, 21)
        sout ochki
    }
}

mainloop()
```
