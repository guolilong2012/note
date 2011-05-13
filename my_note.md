##git

###git
    $:mkdir project
    $:cd project
    $:git init
    $:vim file
    $:git add file
    $:git commit -a -m "fun"
    $:tig
###github key
    $:cd
    $:ssh-keygen
    $:cd .ssh
    $:vim id_rsa.pub
### Git Conf 
    $:cd
    $:vim .gitconfig

    [user]
        name = Guo lilong
        email = guolilong2012@sohu.com
    [core]
        editor = vim
    [alias]
        ci = commit -a -v
        co = checkout
        st = status
        br = branch
        throw = reset --hard HEAD
        throwh = reset --hard HEAD^
    [color]
        ui = true
    [commit]
        template = ./.commit-template
    [push]
        default = current

##Vim Conf Share
###if you want to have my vim configuration, do these:
    cd                       #goto your $HOME
    git clone git@github.com:guolilong2012/guolilong-vim.git
    rm -rf .vim              # rm the old .vim
    mv guolilong-vim .vim    #have the right name
    cd .vim/
    vim README              # check the readme to know more

##markdown
    $:vim file.md
    $:markdown file.md > file.html

##sqlite3
    $:sudo apt-get install sqlite3
    $:sudo apt-get install libsqlite3-dev
