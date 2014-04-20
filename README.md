Dotfiles for Arch Linux on Raspberry Pi
=======================================

Raspberry Pi 上の Arch Linux 用 dotfiles。対象プログラムは

* Vim
* Git

追加の操作を行う必要があるプログラムは

* Vim
* Git

環境移行時に行うこと
--------------------

1. 以下を実行して、ホームディレクトリに dotfiles へのシンボリックリンクを配置する。
    
    ```bash
    cd /path/to/dotfiles-rpi
    for f in _*; do
        fdot=`echo $f | sed -e 's/^_/.'`
        ln -s `pwd`/$f ~/$fdot
    done
    ```

2. .gitconfig の設定。gitconfig.sh を `FIXME` の指示通りに修正して、実行する。
    
    ```bash
    # clone したディレクトリで
    ./gitconfig.sh
    ```

3. Vim の設定。

    1. Vim を起動して `NeoBundleInstall` を実行させる。
    2. vimproc の設定。以下を実行する。

        ```bash
        cd ~/.vim/bundle/vimproc
        make -f make_unix.mak
        ```
