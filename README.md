## What is it

notify_after_command_executed is inspired by this [Q/A] (http://askubuntu.com/questions/611874/how-do-you-make-your-terminal-play-a-sound-or-offer-a-notification-when-it-has-f)

The purpose of this scripts is to notify about finishing long-running terminal commands.

This script is playing sound and showing notification after execution.

Script is based on https://github.com/rcaloras/bash-preexec

#### Should work on Debian and Ubuntu

Script depends on

	pulseaudio-utils	->	sudo apt-get install pulseaudio-utils
	libnotify-bin	->	sudo apt-get install libnotify-bin

## Quick test

this is not finished

## Installation

[Download](https://github.com/c0rp-aubakirov/notify_after_command_executed/archive/master.zip)

or just clone repo

     $ git clone git@github.com:c0rp-aubakirov/notify_after_command_executed.git

Then add sourcing of script `postexec_notify` to your `.bashrc`.

Here is example of installation:

     $ cd ~
     $ git clone git@github.com:c0rp-aubakirov/notify_after_command_executed.git
     $ cd ~/notify_after_command_executed
     $ echo "source $(pwd)/postexec_notify" >> ~/.bashrc

