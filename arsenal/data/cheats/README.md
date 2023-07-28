# Cheatsheet concepts
## Basic structure
A cheatsheet is built from multiple components. The cheatsheet will have a title (which will show up as the name of the tool that the command is for), one or more tags, one or more platforms, one or more targets, and one category.

A basic outline of a cheatsheet looks like the following:
````
# Title of the cheatsheet
% tag1, tag2, tag3, ...
#platform/<platform> #target/<target> #cat/<category>

## Title of command 1
[Optional]: % tag1, tag2, tag3, ...
[Optional]: #platform/<platform> #target/<target> #cat/<category>
[Optional]: <description>
```
<command>
```

## Title of command 2
[Optional]: % tag1, tag2, tag3, ...
[Optional]: #platform/<platform> #target/<target> #cat/<category>
[Optional]: <description>
```
Command text <variable> <variable>...
```

etc...
````

Please note that the lines marked with `Optional` are, indeed, optional. These can override the global tags and categories for this cheatsheet. Additionally, you can add a description to give more information about the command or make notes and references (such as a blog/tweet where you got it from).

An example of a cheatsheet:

````
# Nmap

% external, network, recon
#platform/multiple #target/remote #cat/RECON

## Nmap version and service scan
```
nmap -sV -sC <target> -oN <output_file>
```

## Nmap all ports
```
nmap -p- <target> -oN <output_file>
```

## Nmap SSH authentication methods
% ssh, authentication
This command lists the authentication methods that the SSH service supports
```
nmap -sV -sC <target> -p 22 --script="ssh-auth-methods" -oN <output_file>
```

## Nmap SSL/TLS scan
```
nmap -sV -sC <target> -p <port> --script="ssl*" -oN <output_file>
```
````

Make careful decisions about the tags, categories, platforms and targets that you assign a cheatsheet/cheat. You can search commands based on all these properties in arsenal.

## Tags
A cheatsheet can contain tags, which are denoted by the `%` sign:

```
% tag1, tag2, tag3...
```

Make careful decisions about which tags you give a cheatsheet and/or cheat. You can search commands in arsenal based on these tags.

## Categories
A cheatsheet can contain one category, which are denoted by `#cat` :

```
#cat/category1
```

The following categories are available in arsenal by default, but these are arbitrary and can easily be extended or modified.

```
#cat/UTILS
#cat/RECON
#cat/ATTACK
#cat/ATTACK/BRUTEFORCE-SPRAY
#cat/ATTACK/LISTEN-SERVE
#cat/ATTACK/FILE_TRANSFER
#cat/ATTACK/CONNECT
#cat/ATTACK/EXPLOIT
#cat/ATTACK/MITM
#cat/ATTACK/REVERSE_SHELL
#cat/ATTACK/INJECTION
#cat/CODE
#cat/CODE/SAMPLE
#cat/CODE/WHITEBOX
#cat/CRACKING
#cat/CRACKING/PASSWORD
#cat/PIVOT
#cat/PIVOT/TUNNEL-PORTFW
#cat/PRIVESC
#cat/POSTEXPLOIT
#cat/POSTEXPLOIT/CREDS_RECOVER
#cat/PERSIST
```
## Platforms
A cheatsheet can contain one platform, which is denoted by `#platform`:

```
#platform/<platform>
```

The following platforms are available in arsenal by default, but these are arbitrary and can easily be extended or modified.

```
#platform/linux
#platform/windows
#platform/mac
#platform/multiple
```

## Variables

A command in the cheatsheet can also contain variables. These variables can then be filled in on the fly when the command is selected in arsenal. The variables are denoted with `<var_name>` in the command text. An example is:

```
Nmap <ip> -p <port>
```

Arsenal also offers a way to pre-fill a placeholder for these variables. To do so, specify the following line(s) at the end of the cheatsheet:

```
= variable_name: variable_value
```
