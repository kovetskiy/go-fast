# go-fast

Binary snippets for fast compilation Go projects that will increase your free
time in 5x times.

## go-fast-compile

Just compile your project without linking. This binary is suitable only for
on-save hooks in your favorite editor.

## go-fast-build

Build project only if source code has been changed. This binary is suitable for
daily usage, it's must have binary for integration tests that run on save.

# Efficiency

```bash
for x in `seq 1 20`; do time go build; done 2>&1 | awk '{ x += sprintf("%f", $9); } END { printf x/NR; }'
for x in `seq 1 20`; do time go-fast-compile; done 2>&1 | awk '{ x += sprintf("%f", $8); } END { printf x/NR; }'
```

| project   | go build  | go-fast-compile | profit |
| --------- | ----------| --------------- | ------ |
| [orgalorg, 2789 lines](https://github.com/reconquest/orgalorg) | `2.343` |`0.826` | **3x faster** |
| [shadowc, 960 lines](https://github.com/reconquest/shadowc)    | `2.011` |`0.456` | **5x faster** |
| [manul, 502 lines](https://github.com/kovetskiy/manul)         | `1.558` |`0.267` | **7x faster** |

## Installation

**Arch Linux** (god bless you) users can install package **go-fast** from AUR:

[https://aur.archlinux.org/packages/go-fast/](https://aur.archlinux.org/packages/go-fast/)

other distros:

```bash
$ git clone https://github.com/kovetskiy/go-fast
$ cd go-fast
$ sudo make install
```

## Usage

Of course go-fast's stuff works as *go build* binary and all passed variables
will be passed to Go.
