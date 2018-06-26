 Tmux is a terminal multiplexer

What is a terminal multiplexer?

It lets you switch easily between several programs in one terminal, detach them (they keep running in the background) and reattach them to a different terminal.

More details see http://tmux.sourceforge.net/

Install Step:

1. Download the libevent and ncurses packages(you can find them at this website http://tmux.sourceforge.net/ ) which are the packages TMUX needed. (wget command)


2. Install libevent

1) cd to your directory which contains the libevent-[version]-stable.tar.gz

2) tar -xvzf libevent-[version]-stable.tar.gz

3) cd libevent-[version]-stable

4) ./congiure --prefix=/tmux-1.7_Install(the directory where you want to install)

make

make install

3.Install ncurses

1) tar -xvzf ncurse.tar.gz

2) cd ncurse

3) ./congiure --prefix=/tmux-1.7_Install (the directory where you want to install, it is better to install at the same directory as libevent and tmux)

make

make install

4.Install tmux

1) download tmux (wget) from http://tmux.sourceforge.net/

2) tar -xvzf tmux-[version].tar.gz , then cd /tmux-[version]

3) DIR="$HOME/(the installing path of libevent )"
./configure CFLAGS="-I$DIR/include" LDFLAGS="-L$DIR/lib" --prefix=/tmux-1.7_Install (the directory where you want to install, it is better to install at the same directory as libevent and ncurses)

4) make

make install

5) Now we come to the last step ¦-)

put the following lines in your .bashrc

export PATH=$HOME/(the installing path of tmux)/bin:$PATH
export LD_LIBRARY_PATH=${HOME}/(the installing path of tmux)/lib:${LD_LIBRARY_PATH}

And then source ~/.bashrc

Now type tmux you can find a new world!

Some tips:

1) ctrl+b and then shift+5 you will see something special.

2) if you want to quit tmux , just type exit.

GOOD LUCK!!! 
