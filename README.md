# ura-calc

A small calculator written in [ura](https://github.com/ura-computing/ura-lang): it reads one expression per line, prints its syntax tree and evaluates it. An empty line ends it.

```
ura-calc: type an expression, an empty line quits
> 2 * (3 + 4) - 10 / 5
calculate expr:  2 * (3 + 4) - 10 / 5
ast:
op: -
├─ op: *
│  ├─ 2
│  └─ op: +
│     ├─ 3
│     └─ 4
└─ op: /
   ├─ 10
   └─ 5
result: 12
========================================
>
```

## Run it

```
git clone https://github.com/ura-computing/ura-calc
cd ura-calc
ura deps install
ura run                                    # then type an expression
echo "2 * (3 + 4) - 10 / 5" | ura run      # or pipe it in
```

## Files

| file | what it does |
|---|---|
| `src/lexer.ura` | turns the text into tokens: numbers, `+ - * /` and parentheses |
| `src/parser.ura` | builds the tree with `*` and `/` before `+` and `-`, prints it and evaluates it |
| `main.ura` | reads the lines with `io::input()`; a division by zero is thrown and caught in `main` |
