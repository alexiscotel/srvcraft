# Prettier shell

## PSR1 prompt to add to the end of ~/.bashrc file

for users that can connect from outside (blue)
```
echo "

# External User
parse_git_branch() {
     git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/(\1) /'
}
PS1='\[\e[0;2;38;5;251m\]\A\[\e[0m\] \[\e[0;3;38;5;33m\]\u\[\e[0;1m\]@\[\e[0;1;38;5;34m\]\H\[\e[0m\] \[\e[0;38;5;190m\]\w\[\e[0m\] \[\e[0;3;38;5;45m\]$(parse_git_branch)\[\e[0m\]'
" >> ~/.bashrc
```

for internal users (orange)
```
echo "

# Internal User
parse_git_branch() {
     git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/(\1) /'
}
PS1='\[\e[0;2;38;5;251m\]\A\[\e[0m\] \[\e[0;38;5;178m\]\u\[\e[0;1m\]@\[\e[0;1;38;5;34m\]\H\[\e[0m\] \[\e[0;38;5;184m\]\w\[\e[0m\] \[\e[0;3;38;5;45m\]$(parse_git_branch)\[\e[0m\]'
" >> ~/.bashrc
```

for root (red blinking)
```
echo "

# Rewrite of PS1 prompt (linux-install.md) ROOT mode
parse_git_branch() {
     git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/(\1) /'
}
PS1='\[\e[0;38;5;251m\]\A\[\e[0m\] \[\e[0;1;5;38;5;160m\]\u\[\e[0;1m\]@\[\e[0;1;38;5;34m\]\H\[\e[0m\] \[\e[0;38;5;190m\]\w\[\e[0m\] \[\e[0;3;38;5;45m\]$(parse_git_branch)\[\e[0m\]'
" >> ~/.bashrc
```