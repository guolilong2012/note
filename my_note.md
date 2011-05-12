##github key
    $:cd
    $:ssh-keygen
    $:cd .ssh
    $:vim id_rsa.pub
##git
    $:mkdir project
    $:git init
    $:vim file
    $:git add file
    $:git commit -a -m "fun"
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
