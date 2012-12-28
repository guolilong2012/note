##git

###git help
    help.github.com
###git without username/password
    $:git config --global credential.helper cache

###install git
    version>=1.7.10
    $:sudo apt-add-repository ppa:git-core/ppa
    $:sudo apt-get update
    $:sudo apt-get install git
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

##文件编码转换
    如果你只是想查看其它编码格式的文件或者想解决用Vim查看文件乱码的问题，那么你可以在
    ~/.vimrc（在/etc目录下面） 文件中添加以下内容：
    set encoding=utf-8 fileencodings=ucs-bom,utf-8,cp936

##markdown
    $:vim file.md
    $:markdown file.md > file.html
