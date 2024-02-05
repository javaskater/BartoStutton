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

