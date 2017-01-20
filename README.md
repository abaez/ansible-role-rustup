Rustup
=========
[![license][2i]][2p]
[![twitter][3i]][3p]

A [rustup] install with packages for [rust].

Description
-----------

Too many times the packages needed on a new build would I need to essentially provision a [rust] install. This role's goal is to lessen the workload in getting a [rust] common install. Along with also offering more specific defined packages configured and ready for [rust] fun.

The role installs [rustup] with autocomplete settings enabled for the shell of choice. The packages are listed below. They are divided into two different configurations. One are the common always used packages (default install, no way to disable). The second set are more specifically tuned to the Author's needs. You can find out more how to disable under [Usage](#Usage) if you don't want the **specific** packages.

> from `common.yml`

- [rustfmt]
- [cargo-fmt]
- [racer]
- [clippy]

> from `specific.yml`

- target
  - aarch64-linux-android
  - aarch64-linux-android
  - aarch64-unknown-linux-gnu
  - arm-unknown-linux-musleabi
  - arm-unknown-linux-musleabihf
  - armv7-unknown-linux-gnueabihf
  - armv7-unknown-linux-musleabihf
  - x86_64-unknown-linux-musl
- toolchain
  - nightly-x86_64-unknown-linux-gnu
- packages
  - [exa]
  - [way-cooler]
  - [iota]
  - [parallel]

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Requirements
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Usage
-----

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

``` yaml
- hosts: servers
    roles:
        - { role: username.rolename, x: 42 }
```

Author Information
------------------

[Alejandro Baez][1]

[1]: https://keybase.io/baez
[2i]: https://img.shields.io/badge/license-BSD_2-green.svg
[2p]: ./LICENSE
[3i]: https://img.shields.io/badge/twitter-a_baez-blue.svg
[3p]: https://twitter.com/a_baez

[exa]: https://github.com/ogham/exa
[way-cooler]: https://github.com/Immington-Industries/way-cooler
[iota]: https://github.com/gchp/iota
[parallel]: https://github.com/mmstick/parallel
[rust]: https://rust-lang.org
[rustup]: https://github.com/rust-lang-nursery/rustup.rs
[clippy]: https://crates.io/crates/clippy
[rustfmt]: https://crates.io/crates/rustfmt
[cargo-fmt]: https://crates.io/crates/cargo-fmt
[cargo-clippy]: https://crates.io/crates/cargo-clippy
[racer]: https://crates.io/crates/racer
