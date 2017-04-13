# Git Trixx!

1. Open you .bashsrc located in your home folder
2. Add the following: 
# To get a branch notification in terminal    
get_git_branch() {  
    local br=$(git branch 2> /dev/null | grep "*" | sed 's/* //g')       
    [ -n "$br" ] && echo "($br)"       
}    
PS1='${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\W$(get_git_branch)\[\033[00m\]\$ ' 
