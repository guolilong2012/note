## Linux commands
### pgrof
    $:gcc -pg main.c
    $:./a.out
    $:pgrof a.out > pgrof.txt
### find
    $:find / -type f | xargs grep key
### rename
    $:rename 's/.so.1/.so/' ./*
### openssh-server
    $:apt-get install openssh-server
### nfs
    $:apt-get install nfs-kernel-server
    $:apt-get install portmap nfs-common
    $:vim /etc/exports
       /root/test  *(rw,sync,no_root_squash)
    $:/etc/init.d/nfs-kernel-server restart
    $:/etc/init.d/portmap restart
    $:showmount -e
    $:mount -t nfs -o nolock 192.168.1.111:/root/test/tiny6410 /mnt
### file ldd readelf
    $:file app
    $:ldd app
    $:readelf -a app | grep Shared

## arm-linux kernel
    $:make ARCH=arm menuconfig
    $:make ARCH=arm CROSS_COMPILE=arm-linux-

## Detecting Memory Leaks in Kernel
    $:make menuconfig
    kernel hacking---> Kernel memory leak detector
                  ---> Compiler the kernel with debug info
    $:mount -t debugfs nodev /sys/kernel/debug/kmemleak
    $:echo scan > /sys/kernel/debug/kmemleak
    $:echo clear > /sys/kernel/debug/kmemleak
    $:cat /sys/kernel/debug/kmemleak

## Samba on Ubuntu-10.04
    $:sudo apt-get install rcconf
    $:sudo apt-get install ufw
    $:ufw disable
    $:sudo apt-getinstall samba
    $:sudo apt-getinstall smbfs
    $:sudo apt-get install system-config-samba
    $:sudo system-config-samba
    $:smbpasswd -a user
    $:/etc/init.d/smbd restart
    \\192.168.1.28\path

## rename eth1 to eth0
    $:rm /etc/udev/rules.d/70-persistent-net.rules

## Git
### git install
    $:apt-get install git(git-core)
### Ubuntu10.04 install git
    $:sudo apt-add-repository ppa:git-core/ppa 
    $:sudo apt-get update 
    $:sudo apt-get install git 
### git help
    help.github.com
### git use
    $:mkdir project
    $:cd project
    $:git init
    $:vim file
    $:git add file
    $:git commit -a -m "fun"
    $:tig
### github key
    $:cd
    $:ssh-keygen
    $:cd .ssh
    $:vim id_rsa.pub
### git conf 
    $:cd
    $:vim .gitconfig

    [user]
        name = Guo lilong
        email = guolilong2012@sohu.com
    [core]
        editor = vim
    [alias]
        ci = commit -a -m
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
    [credential]
        helper = cache --timeout=360000

## Vim Conf Share
### if you want to have my vim configuration, do these:
    cd                       #goto your $HOME
    git clone git@github.com:guolilong2012/guolilong-vim.git
    rm -rf .vim              # rm the old .vim
    mv guolilong-vim .vim    #have the right name
    cd .vim/
    vim README              # check the readme to know more

## 文件编码转换
    如果你只是想查看其它编码格式的文件或者想解决用Vim查看文件乱码的问题，那么你可以在
    ~/.vimrc（在/etc目录下面） 文件中添加以下内容：
    set encoding=utf-8 fileencodings=ucs-bom,utf-8,cp936

## Markdown
    $:vim file.md
    $:markdown file.md > file.html

## Local yum(redhat 6.3)
    $:mkdir /media/cdiso
    $:mount -o loop xxx.iso /media/cdiso
    $:mv /etc/yum.resp.d/rhel-source.repo /etc/yum.resp.d/rhel-source.repo.bak
    $:vim /etc/yum.resp.d/rhel-source.repo
        [rhel-source]
        name=yum local
        baseurl=file:///media/redhat
        gpgcheck=0
        gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-redhat-release
        [rhel-source-beta]
        name=yum local
        baseurl=file:///media/redhat
        enabled=1
        gpgcheck=0
        gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-redhat-beta,file:///etc/pki/rpm-gpg/RPM-GPG-KEY-redhat-release
    $:yum clean all
    $:yum list
    $:yum -y install gcc

## Ubuntu10.04 install rapidsvn
    download rapidsvn.tar.gz
    $:apt-get install libapr1-dev
    $:apt-get install libaprutil1-dev
    $:apt-get install libsvn-dev
    $:apt-get install libwxgtk2.8-dev
    $:apt-get install libsvncpp-dev
