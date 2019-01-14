## What is it

notify_after_command_executed is inspired by this [Q/A](http://askubuntu.com/questions/611874/how-do-you-make-your-terminal-play-a-sound-or-offer-a-notification-when-it-has-f)

The purpose of this scripts is to notify about finishing long-running terminal commands.

This script is playing sound and showing notification after execution.

Script is based on https://github.com/rcaloras/bash-preexec

#### Should work on Debian and Ubuntu

Script depends on

	pulseaudio-utils	->	sudo apt-get install pulseaudio-utils
	libnotify-bin	->	sudo apt-get install libnotify-bin

## Quick test

    wget -O - 'https://raw.githubusercontent.com/c0rp-aubakirov/notify_after_command_executed/master/postexec_notify' | bash

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

Now restart your terminal. After restart you should see this messages:

	preexec.sh is not exist
	Trying to download it from github

Now try to test if notification appear:

	$ sleep 6

## Configuration

There is variable `NOTIFICATION_SECONDS_TRESHOLD` in `postexec_notify` script. This variable indicates how long command should work to be considered as long-running.
By default it is equals to 5 seconds, this means that any command running more than 5 seconds is considered as long-running command, notification would appear after finish.

I add variable `NOTIFICATION_IGNORE_REGEX` to ignore notification.(fx-kirin)

## Uninstall

**Manual**

Open your `~/.bashrc` file and find there sourcing of `postexec_notify`. It should look like:

	source /home/c0rp/postexec_notify

Remove this line from `.bashrc`.

**Oneline**

Here is more automated way:

	$ sed -i '/postexec_notify/d' ~/.bashrc



