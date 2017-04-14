Rustup
=========
[![license][2i]][2p]
[![twitter][3i]][3p]

A [rustup] install with packages for [rust].

Description
-----------

Too many times the packages needed on a new build would I need to essentially provision a [rust] install. This role's goal is to lessen the workload in getting a [rust] common install. Along with also offering more specific defined packages configured and ready for [rust] fun.

The role installs [rustup] with autocomplete settings enabled for the shell of choice. The packages are listed below. They are divided into two different configurations. One are the common always used packages under the **common.crates** list in `defaults/main.yml`. The second set are more specifically tuned to the Author's needs under **specific** in `defaults/main.yml`. You can find out more how to disable under [Usage](#Usage) if you don't want the **specific** packages or if you want to change on the listing.

> from **common.crates**

- [rustfmt]
- [racer]
- [pijul]

> from **specific** dictionary

- targets
  - aarch64-linux-android
  - aarch64-linux-android
  - aarch64-unknown-linux-gnu
  - arm-unknown-linux-musleabi
  - arm-unknown-linux-musleabihf
  - armv7-unknown-linux-gnueabihf
  - armv7-unknown-linux-musleabihf
  - x86_64-unknown-linux-musl
- toolchains
  - nightly-x86_64-unknown-linux-gnu
- crates
  - [exa]
  - [way-cooler]
  - [iota]
  - [parallel]
  - [rust-clippy]

Role Variables
--------------

The role has 3 variables to update. Each one should be changed according to the user's needs. The defaults can be seen in [defaults]:

``` yaml
conf:

  # shell autocomplete. Should be (bash|fish|zsh)
  shell: fish

  # if you want to have the specifics installed
  specifics: true

  # if decide to use parallel or not check the link given above for the package for more information
  parallel: true
```

Requirements
------------

Your only requirement is you should change the default variables listed above to the needs for your provision using the role.

Usage
-----

Besides the role variables, with the exception of [parallel], you only need to enable the role on your playbook. If you want to install your own crates, targets, or toolchains, you can simply be replacing the variables given in [defaults].

For using the [parallel] package, you need to run the role with [become] enabled for privilege of enabled **madvise** mode for usage.

``` yaml
- hosts: servers
    roles:
        - abaez.rustup
```

Author Information
------------------

[Alejandro Baez][1]

[1]: https://keybase.io/baez
[2i]: https://img.shields.io/badge/license-BSD_2-green.svg
[2p]: ./LICENSE
[3i]: https://img.shields.io/badge/twitter-a_baez-blue.svg
[3p]: https://twitter.com/a_baez

[pijul]: https://pijul.org/
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
[become]: http://docs.ansible.com/ansible/become.html
[defaults]: ./defaults/main.yml
