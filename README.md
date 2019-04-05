# scriptid
Scriptid (stylized `scriptid`) is an intermediate scripting language meant to bridge the gap between your Discord bot and its users who want a little more control over the things they want their bot to do.

Its initial purpose was to extend the functionality of so-called "custom commands". You know, those ones where you input something and the bot spits out something else? Well, scriptid's goal is to fill the holes between ping-pong commands and waiting for the bot developers to maybe, just *maybe*, make that command you've been asking for for ages!

Scriptid is meant to be extendable and eventually support will be implemented to allow other users to add on additional extensions past the base design; in a perfect world, one could, with enough extensions, make a fully functional bot using only their library and scriptid!

To check out the syntax and grammar, or at least what there is so far, feel free to check out the [syntax document](syntax.md).


## But wait, why hasn't someone done this already?
I'm glad you ask! My best guess is...I'm not sure. The closest match I can think of to the goal of scriptid is/was [Tatsumaki](https://tatsumaki.xyz/)'s `t!tags` commands, which last I heard, were disabled due to bugs or memory leaks. The biggest hurdle that users will need to overcome is either finding or writing their own interpreter for scriptid. You see, scriptid is just a __specification__, not an actual language by itself. It's meant to be a set of rules that intepreters translate into an [abstract syntax tree (AST)](https://en.wikipedia.org/wiki/Abstract_syntax_tree), or whatever they desire to be able to map scriptid code into their target language.

## Features
Some of the features scriptid can (or will try to) implement:

* Global variables (per-guild), allowing scripts to "store" data between runs. Useful for command usage counters or whatever you might need it for!
