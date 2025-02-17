+++
title = "pomd"
description = "pomodoro timer daemon"
[taxonomies]
categories = ["utility"]
languages = ["rust"]
[extra]
finished = "november 2023"
github = ["soaosdev/pomd", "soaosdev/pomc"]
crates = ["pomd", "pomc"]
+++

this was a pretty simple rust project i did over the course of a couple days

i had been wanting to experiment with d-bus on linux for a while and figured that writing a pomodoro daemon and client would be a good way to understand the basics of how d-bus interfaces work

luckily i found the wonderful [zbus](https://crates.io/crates/zbus) crate which made everything for hooking up interface super simple

i think the hardest thing about this project was trying to figure out how to accurately keep the time left in the timer

as with many problems in rust the solution ended up being to find a [crate](https://crates.io/crates/pausable_clock) that implemented a "pausable clock" that worked similarly to a normal rust `std::time::Instant`

it's pretty configurable from what i remember

i used this program when i was using [dwm](https://dwm.suckless.org) and wanted a daemon to integrate into my statusbar 

![pomd segment in my dwm statusbar](statusbar.png)

now i use KDE plasma which has a pretty good pomodoro applet available, maybe in the future i could make some kind of widget that communicates with the daemon


