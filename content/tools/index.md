+++
date = '2025-06-03T12:54:24+08:00'
draft = false
title = 'Config'
+++

# ssh 配置
```
StrictHostKeyChecking no
UserKnownHostsFile /dev/null

Host relay
    HostName relay.corp.kuaishou.com
    ControlMaster auto
    ControlPath ~/.ssh/tmp/master-%r@%h:%p
    ControlPersist yes
    ServerAliveInterval 60

Host dev
    HostName 172.28.206.144
    User linhaocheng
    ForwardAgent yes
```
# git 配置
```
[user]
        name = linhaocheng
        email = linhaocheng@kuaishou.com
[credential]
        helper = osxkeychain
[core]
        editor = vim
        autocrlf = input
        safecrlf = warn
[pull]
        rebase = true
[fetch]
        prune = true
[diff]
        colorMoved = zebra
        tool = vimdiff
        submodule = log
[difftool]
        prompt = false
[alias]
        lg = log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%ci) %C(bold blue)<%an>%Creset'
        lp = log --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%ci) %C(bold blue)<%an>%Creset'
        myswitch = "!bash -c 'changes=$(git status -uno -s); if [[ -z $changes ]];then git switch $0 $@; else git status; fi'"
[url "git@git.corp.kuaishou.com:"]
        insteadOf = https://git.corp.kuaishou.com/
```