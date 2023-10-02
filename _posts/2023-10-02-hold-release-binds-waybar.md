---
layout: post
title:  "Hold/release hiding keybinds for Waybar on Hyprland"
date:   2023-10-02 00:00:00 -0500
categories: linux rice tutorial
---

Hey, it's been a while :)

<br>

Here's a quick post to hopefully help someone desperately googling.  **"How do I make hold and release keybinds for Waybar on Hyprland?"**

The current returned results on Google aren't very helpful. You'll see some people on the right track, but there's lots of complicated solutions compared to what (imo) is the best solution to take. Here are two steps.

## Step 1: Change Waybar to be hidden on default

In your `.config/waybar/config`:
```
"start_hidden": true,
```
Note that it is a boolean and not a string. Waybar has a tough time parsing `"true"` as `true`.

<br>

## Step 2: Add binds to Hyprland config

In your `.config/hypr/hyprland.conf`:
```
bind   =      , SUPER_L, exec, pkill -SIGUSR1 waybar
bindrt = SUPER, SUPER_L, exec, pkill -SIGUSR1 waybar
```

This assumes that `SUPER_L` is the key you'd use to hide and show the bar. You can adjust accordingly, just make sure to abide by the same format.

This relies on the `USR1` kill signal, which is programmed to toggle between showing and hiding Waybar.

The second line uses the `r` and `t` [flags](http://wiki.hyprland.org/Configuring/Binds/#bind-flags), so that the bind activates on release and does not interrupt with normal bindings.

<br>

<br>

*P.S. I have several articles which I have pictures for, but have not written yet. Oh how my brain works.*
