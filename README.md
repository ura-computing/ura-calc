# ura-calc

A small calculator written in [ura](https://github.com/ura-computing/ura-lang): it reads an expression, prints its syntax tree and evaluates it.

```
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
```

## Run it

```
git clone https://github.com/ura-computing/ura-calc
cd ura-calc
ura install
ura run
```

## Files

| file | what it does |
|---|---|
| `src/lexer.ura` | turns the text into tokens: numbers, `+ - * /` and parentheses |
| `src/parser.ura` | builds the tree with `*` and `/` before `+` and `-`, prints it and evaluates it |
| `main.ura` | runs two expressions; a division by zero is thrown and caught in `main` |
