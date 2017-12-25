# rdev

Helper script for Rakudo Perl 6 core development

# INSTALLATION

```bash
mkdir ~/6 &&
git clone https://github.com/zoffixznet/rdev ~/6 &&
zef --depsonly install .

echo 'export PATH="$HOME/6/bin:$PATH"' >> ~/.bashrc
. ~/.bashrc

pico ~/6/config.json
# set your build directory and other config, save, and close
```

This installs command `6` into your PATH.

# USAGE

## `--init`

```bash
$ 6 --init
```

Initialize build dir (set as `"dir"` key in `~/6/config.json`).

This clones rakudo/nqp/MoarVM repos and builds everything into `install` dir
inside the build dir.

## (no args) / (no args) `--test`

```bash
$ 6
# or
$ 6 --test
```

**Use after making changes to Rakudo's codebase.**
Runs `make` and `make install` in rakudo's repo. Pass `--test` param to also
run `make test`

## `n` / `n --test`

```bash
$ 6 n
# or
$ 6 n --test
```

**Use after making changes to nqp's codebase.**
Runs `make clean`, `make`, and `make install` in nqp's and rakudo's repos.
Pass `--test` param to also run `make test`

## `m`

```bash
$ 6 m
```

**Use after making changes to MoarVM's codebase.**
Runs `make` and `make install` in MoarVM's repo.

## `s`

```bash
$ 6 s
```

Runs `make spectest` in rakudo's repo.

## `ss`

```bash
$ 6 ss
```

Runs `make stresstest` in rakudo's repo.
----

#### REPOSITORY

Fork this module on GitHub:
https://github.com/zoffixznet/rdev

#### BUGS

To report bugs or request features, please use
https://github.com/zoffixznet/rdev/issues

#### AUTHOR

Zoffix Znet (http://perl6.party/)

#### LICENSE

You can use and distribute this module under the terms of the
The Artistic License 2.0. See the `LICENSE` file included in this
distribution for complete details.

The `META6.json` file of this distribution may be distributed and modified
without restrictions or attribution.
