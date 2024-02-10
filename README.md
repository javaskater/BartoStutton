# The Book
* costs 100 € at [Amazon](https://www.amazon.fr/Reinforcement-Learning-Introduction-Richard-Sutton/dp/0262039249)
* Is [free to download in pdf format](https://www.andrew.cmu.edu/course/10-703/textbook/BartoSutton.pdf)
  * I put the [pdf](https://www.andrew.cmu.edu/course/10-703/textbook/BartoSutton.pdf) with the First Course and in Livres/AI
* There is a [GitHub project for the solutions of the book's exercises](https://github.com/LyWangPX/Reinforcement-Learning-2nd-Edition-by-Sutton-Exercise-Solutions)
  * for each chapter a pdf file
  * for each chapter one or more python script 
* There is another [GitHub project with the solutions](https://github.com/brynhayder/reinforcement_learning_an_introduction/tree/master/exercises/chapters)
  * that one uses latex document format
## Recommended for 
* the five first lessons of the [RCP211 Advanced AI Course at the CNAM PAris](https://formation.cnam.fr/rechercher-par-discipline/intelligence-artificielle-avancee-1132536.kjsp) 

# Writing Latex code in my Markdown files
 * the [answer 10 of this Stackoverflow question](https://stackoverflow.com/questions/65920958/vs-code-latex-syntax-in-markdown) gives an answer
## The extension
* [GitHub page](https://github.com/James-Yu/LaTeX-Workshop)
  * on the same site there are the [installation instructions](https://github.com/James-Yu/LaTeX-Workshop/wiki/Install#installation)
* [Extension Page](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop)
* I didn't know to install Latex on my computer it seems to be embedded
* the latex code has to been placed between two __$__ like in the following example
  * $q_{k+1}(s, a) = \sum_{s', r} p(s', r | s, a)\left[r + \gamma \sum_{a'} \pi(a'|s)q_k(s', a')\right]$ 

# Reading the Latex Files in Visual Studio Code 

* the [GitHub project with the solutions](https://github.com/brynhayder/reinforcement_learning_an_introduction/tree/master/exercises/chapters) gives the answers in Latex files. So I need Visual Studio Code being able to read them...
## I cannot create a pdf
* I think I must [install Latek on Ubuntu](https://milq.github.io/install-latex-ubuntu-debian/)
* The first command installs 6 GB of data
```
jpmena@LAPTOP-E2MJK1UO:~/CONSULTANT/rcp211_personalnotes$ sudo apt install texlive-full
```
### Problem 404 codes
* Due to time difference between the ubuntu server and my WSL clock
* solved using [this link](https://dev.to/bartr/wsl2-time-sync-1kk7)
* Like said in the site I as for the synchronisation in the _.bahrc_
```bash
jpmena@LAPTOP-E2MJK1UO:~$ cp -pv .bashrc .bashrc.bak$(date '+%d%m%Y_%H%M%S')
'.bashrc' -> '.bashrc.bak04112023_161850'
#I edit bashrc so that
jpmena@LAPTOP-E2MJK1UO:~$ diff -u  .bashrc.bak04112023_161850 .bashrc
--- .bashrc.bak04112023_161850  2022-11-26 14:55:34.779375893 +0100
+++ .bashrc     2023-11-04 16:22:40.042879870 +0100
@@ -115,3 +115,6 @@
     . /etc/bash_completion
   fi
 fi
+
+# fix wsl time sync
+sudo ntpdate ntp.ubuntu.com &>/dev/null &
``` 
* __perhaps it should have been done in the /etc/bahrc__ ?
  * because of the sudo ...
* That command blocks the terminal of my VSCode ...
* I retreat it !!!
### intallation of the standard editor for latek
* 17 MB only
```bash
sudo apt-get install texmaker
#calling it
jpmena@LAPTOP-E2MJK1UO:~$ texmaker&
[1] 8200
```
## It is not enough

* in the [Visual Studio Code Extension](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop) they say we need texlive in the path
```bash
jpmena@LAPTOP-E2MJK1UO:~/CONSULTANT/BartoStutton$ sudo apt install texlive
[sudo] password for jpmena: 
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following NEW packages will be installed:
  texlive
0 upgraded, 1 newly installed, 0 to remove and 138 not upgraded.
Need to get 14.3 kB of archives.
After this operation, 73.7 kB of additional disk space will be used.
Get:1 http://archive.ubuntu.com/ubuntu jammy/universe amd64 texlive all 2021.20220204-1 [14.3 kB]
Fetched 14.3 kB in 0s (62.3 kB/s)
debconf: unable to initialize frontend: Dialog
debconf: (Dialog frontend requires a screen at least 13 lines tall and 31 columns wide.)
debconf: falling back to frontend: Readline
Selecting previously unselected package texlive.
(Reading database ... 268812 files and directories currently installed.)
Preparing to unpack .../texlive_2021.20220204-1_all.deb ...
Unpacking texlive (2021.20220204-1) ...
Setting up texlive (2021.20220204-1) ...
#texlive is not on the path
jpmena@LAPTOP-E2MJK1UO:~/CONSULTANT/BartoStutton$ whereis texlive
texlive: /usr/share/texlive
```
* It is not the right Tex, the right tex Live had already been installed
```bash
jpmena@LAPTOP-E2MJK1UO:~/CONSULTANT/BartoStutton$ tex --version
TeX 3.141592653 (TeX Live 2022/dev/Debian)
kpathsea version 6.3.4/dev
Copyright 2021 D.E. Knuth.
There is NO warranty.  Redistribution of this software is
covered by the terms of both the TeX copyright and
the Lesser GNU General Public License.
For more information about these matters, see the file
named COPYING and the TeX source.
Primary author of TeX: D.E. Knuth.
```
* As I installed texlive-full the best thing to do is to use the command line to generate
  * either a pdf
  * or a hteml file !!!