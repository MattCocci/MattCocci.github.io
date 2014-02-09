---
layout: computing
---


<section id="Introduction"></a></section>

### Introduction: Arriving at an Optimal Setup

In the past two years, I've turned to more command line tools that have really improved my computing experience. Most have the following characteristics in common:

- __Low Overhead__: My favorite programs and computing environments are often very bare-bones, requiring little memory that would otherwise freeze up my crappy old computer. They just get out of the way, focusing on content rather than a flashy, fussy interface.
- __Greater Efficiency__: Point and click is not efficient.  It's slow, and it doesn't scale well with larger tasks and projects. My favorite programs work at the command prompt for experimentation and quick results, while _also_ working in a script for replication, repetition, and scale.
- __Customization__: Fine-tuning and adaptability are always desireable. This happens in the "rc" and config files.  You can find mine at [link], although I'll talk about some of my favorite customizations below.

Now for some specifics.



<section id="OperatingSystem"></a></section>

### Operating System

Of course, the OS is an important choice, which is why I put down <a href="http://www.ubuntu.com" target="_blank">my thoughts</a> elsewhere in greater detail.

I run it with the Gnome desktop, though the terminal and Chrome occupy my screen more than anything.


<section id="MySetup"></a></section>

### My Setup

Here's a snapshot of a not-uncommon sight on my machine (from when I was composing this section).  

<img src="/imgs/SampleScreen.png" width="540">

This is how I spend most of my computing time when I'm not online.  It looks this way for a few main reasons:

- __Bash__: Bash is my terminal of choice, thought I've heard very good things about zshell.  Just haven't really tried it.

- __Solarized__: It's that nice, blue color scheme you see.  I use it both for vim and for my terminal, making it a bit transparent  for the latter so I can see the background. This helps when you have the terminal open, covering up a webpage. With a translucent terminal, you can still read the site and try out code on that page without constantly flipping back and forth.

- __Tmux__: This is the program that lets me split up the terminal as you see above. It divides a window into panes that each start out as a separate command prompt.  And if splitting panes in the same window isn't enough, it also lets you create multiple _windows_, which are like browser tabs that you can page through. They're listed in the black bar at the bottom. 

- __Vim__: The lefthand pane is just vim, a fancy text editor.  It's like a version of Notepad that's not absolutely terrible. At the end of this note, I've placed some vim tricks I've found super helpful, along with my cheatsheat. But before getting too detailed, I'll just mention the main advantages, which include
    - _Different Modes_: There's a mode for entering text (actually typing words and letters) and a mode for moving around---which essentially puts tricked-out arrow keys and keyboard shortcuts within reach of the home keys.  Because of this, you can fly around and edit the document with little effort. 
    - _Text Only_: Microsoft Word is annoying because it encourages you to worry about how your content _looks_ when you're trying to determine what your content should _say_.  These things are usually incompatible. Vim gets out of the way, and lets you type straight text.  Let downstream programs (like $\LaTeX$ or a Markdown parser) worry about formatting. 
<p></p>

- __iPython__: The upper-righthand pane is running iPython, a killer environment for programming in Python.  It merges Python (like you might use it in IDLE) with basic command line utilities (`cd`, `ls`, or `mkdir`), autocomplete, and an easier edit/save/run workflow. It also has a nifty and much-praised online notebook feature like Mathematica.


<section id="Programming"></a></section>

### Languages for Scientific Computing

I can't say much about general programming languages, but for those problems falling with scientific and statistical computing, here are some combinations I like.

##### __R + Command Line Tools__

R is free and looks great after you replace it's 1980s GUI with RStudio. It handles standard plotting, statistics, and simulation very well, with libraries for more specific tasks.[^1] 

However, it's less strong handling text, which is where the various command line tools come in--tools like bash scripts, sed, and awk.  Since the command line is so well developed for dealing with text and file management, the tools developed for it will complement R nicely when you need to manage large data files or deal with text.

##### __Python__

Python is the language to learn if you only have time for one language.  Comparied to R, Matlab, Stata, etc., it can be applied to much more general probelms (like shell scripting) with much less overhead and cludginess. It's also vastly superior if you're working with text and regular expressions.

On top of that, it now has great libraries for matrix arrays, plotting, and handling datasets---nearly on par with R and Matlab.  My only gripe is that those libraries require a sometimes-annoying amount of cognitive overhead to use.   For example, unlike Matlab and R, you can't just fire it up and start playing around at the command line. You need to import from libraries like NumPy, SciPy, Matplotlib, which is fine, except that the location of certain functions within those libraries isn't always immediately obvious (or they might be many layers of nesting).

For that reason, I coded up MatPy, which is designed to put Python into a more Matlab-like mode.  Running

    from matpy import *

imports all of the usual functions right into your workspace for you: linear algebra functions, random number generation, and plotting, etc.[^2]  It also names them similarly to Matlab. This obviates the need for large or on-the-fly import statements when you just want to get going in a familar syntactical environment.

##### __Other Languages__

A word about some other languages:

- __Matlab & GNU Octave__: Both a great option, although the former costs cash-money, and I prefer R (with its extensive libraries) to the latter if we're considering open source. 

- __Stata__: Great to use if you want to run standard cross-sectional or panel regressions, though I wouldn't use it for simulation or for time series. R and Matlab are much better suited for that. But I will also say that the Stata manual is easily the best help manual among all programming languages I've encountered. Not only does it explain features well, but it explicitly spells out many statistical methods and techniques. It's close to having a statistics textbook accompany the code.

- __Mathematica__: Some nice ideas, but too expensive given the excellent open source alternatives.  And if you really the notebook feature and layouts (as I did), just use iPython notebook instead.  

- __Julia__: Lots of promise, and I'm looking forward to using it more in the future. Could replace Python for me as a general-purpose, all-in-one language in the future.


<section id="ComposingDocs"></a></section>

### Composing Documents

I became a much, much happier person when I ditched Word and PowerPoint for $\LaTeX$ and Beamer.  Aside from superb mathematical typsetting, here's why:

- __Plain Text Editing__: Has a text editor frozen anyone's screen since the 90s? Now contrast that with MS Word and PowerPoint, which reguarly freeze screens and flash "Not Responding," especially with many files open. Editing plain text simply requires much less memory, overhead, and fuss.  Plus, I don't have to rely on proprietary software to edit .doc or .docx files.  I can use any text editor I prefer---especially vim, which provides quicker navigation and editing capabilities anyway.

- __Separation of Content and Formatting__: Whenever I use word, I can't help but worry about the formatting when I should be worrying about writing and composing documents. $\LaTeX$ and Beamer encourage you to write without interruption, and worry about formatting later.  And when it is time to format, $\LaTeX$ looks at your preamble to apply the settings _uniformly_ throughout the text. You won't encounter that familiar situation in Word where hitting tab can jump you a half inch or half a page.  Some of your document won't accidentally be double-spaced, while other parts are single-spaced with extra spacing in between paragraphs.

- __Content Searching__: There are great tools (like `grep` and `ack`) available for searching through source code.  Since both $\LaTeX$ and Beamer use plain text, you can use those to search through your documents in a flash, using regular expressions if you need them.  It's much quicker than searching through pdf and doc files.

- __Updating__: Suppose you have a table or a graph in a report or research paper. To update charts and tables in $\LaTeX$, just write them as text files some location and have your document reference the file.  This way, you never have to open up a Word doc to manually replace a chart or table. This scales nicely when you're generating lots of tables and charts programatically.

- __Backing Up__: Back up your plain-text files on Github. This allows other people to use and contribute to them as well.

Now if you want to get started, my templates for each could provide a starting point. Within the preamble, they configure (and describe) the formatting choices, as well as provided some examples and sample on how to accomplish typical tasks (including figures, adding vertical space, rendering code with syntax highlighting).


- $\LaTeX$ Template: <a href="https://github.com/mcocci/ConfigurationTemplates/blob/master/latexTemplate.tex" target="_blank">Github</a>, <a href="/files/latexTemplate.txt" target="_blank">Plain Text</a>
- Beamer Template: <a href="https://github.com/mcocci/ConfigurationTemplates/blob/master/beamerTemplate.tex" target="_blank">Github</a>, <a href="/files/beamerTemplate.txt" target="_blank">Plain Text</a>

You should be able to save and run `pdflatex` on them if you have everything installed.


<section id="Vim"></a></section>

### Vim: Tips and Tricks

This is, without a doubt, the program I use (and advocate) the most. Aside from the basics, these are the features I use most.[^3] They include some changes to the `.vimrc` file, which resides in the home directory and defines the configuration of vim.  Mine can be found on <a href="https://github.com/mcocci/ConfigurationTemplates/blob/master/my.vimrc" target="_blank">Github</a> or as a <a href="/files/vimrc.txt" target="_blank">plain text file</a>.


#### Remaps

Remapping some of the features to more easily accessible keys can greatly improve productivity. Some bi


#### Substitution

Say you want to change a variable name in your code. This involves changing `var1` to `var2`.  You can do this while in navigation mode by typing 
    
    :%s/var1/var2/g

Use `gc` instead of `g` to prompt for confirmation before each substitution. You can also be more selective about it by highlighting the text first, letting '\<,'\> replace the % above, so you get something like

    :'<,'>s/var1/var2/g

You can augment the portion of the expression that specifies our search term (where `var1` is) with more complicated regular expressions.


#### Screen Splitting

Typing `:sp` or `:vsp` while in navigation mode splits the screen horizontally or vertically, respectively. Adding a filepath (relative to the current directory) after either, like `:sp file.txt` will open the specified file in the other screen. 

You can even get fancier. If you place your cursor over some filename listed in whatever your currently editing, hitting `Ctrl + w, f` will open up the file under the cursor in a split screen.


#### Registers

There's certain phrases I use a lot while coding. In $\LaTeX$, I might often type `\begin{enumerate}` to start a list.  Rather than typing every time, I can yank to a named register that will hold that phrase in reserve.  If I highlight text, then use `",  a,  y`, this will yank the text to the `a` register.  You can paste with `", a, p`. This will work for any letter besides a.[^4]  


#### Macros

If you do the same sequence of strokes over and over again, consider using macros, which can automate the strokes.  In navigation mode, type `q, a` to start recording "Macro a." Execute your keystrokes. Once you're finished, type `q`.  You can execute the macro by typing `@q` while in insert mode will execute the keystrokes you recorded.  You can proceed `@q` with a number to execute macro arbitrarily many times.


#### Laying Markers

If you need to keep jumping back to a speciic section of your text or code, type `ma` while at that section (where `a` could be any letter).  This lays a marker at the location, which you can jump to from any point in your code by typing `` `a ``. 


#### Plugins

You can also add additional features by intalling plugins. Some good ones include <a href="https://github.com/scrooloose/nerdcommenter" target="_blank">NerdCommenter</a> and <a href="https://github.com/Shougo/unite.vim" target="_blank">Unite.vim</a>. But before you do that, install <a href="https://github.com/tpope/vim-pathogen" target="_blank">Pathogen</a> first, which improves the whole process of installing and uninstalling vim plugin.


<section id="References"></a></section>

### References

While learning programming languages, I've written a few reference files for myself detailing the syntax of different languages:

* Python: Basics plus NumPy, SciPy, Matplotlib, Pandas, and iPython. <a href="https://github.com/mcocci/Notes/blob/master/Computing/PythonCheatSheet.txt" target="_blank">Github</a>, <a href="/files/PythonCheatSheet.txt" target="_blank">Plain Text</a>.

* Linux: Basic commands, regular expressions, and shell scripting. <a href="https://github.com/mcocci/Notes/blob/master/Computing/LinuxCheatSheet.txt" target="_blank">Github</a>, <a href="/files/LinuxCheatSheet.txt" target="_blank">Plain Text</a>.

* Git: For version control. <a href="https://github.com/mcocci/Notes/blob/master/Computing/GitNotes.txt" target="_blank">Github</a>, <a href="/files/GitNotes.txt" target="_blank">Plain Text</a>.

* Vim & Tmux Reference Card: Designed to be taped to a monitor as a quick reference.  <a href="https://github.com/mcocci/Notes/blob/master/Computing/Refcard_vim_tmux.txt" target="_blank">Github</a>, <a href="/files/Refcard_vim_tmux.txt" target="_blank">Plain Text</a>.


Another great site which might be similarly useful is <a href="http://learnxinyminutes.com/" target="_blank">Learn X in Y Minutes</a>


<section id="ConfigFiles"></a></section>

### Configuration Files

Finally, many programs and utilities need to be configured, and they typically do so with "rc" files "config" files.  Here are mine, which I tried to comment for context. The Github links will be most up to date.

* .vimrc: <a href="https://github.com/mcocci/ConfigurationTemplates/blob/master/my.vimrc" target="_blank">Github</a>, <a href="/files/vimrc.txt" target="_blank">Plain Text </a>.

* .bashrc: <a href="https://github.com/mcocci/ConfigurationTemplates/blob/master/my.bashrc" target="_blank">Github</a>, <a href="/files/bashrc.txt" target="_blank">Plain Text</a>.

* .tmux.conf: <a href="https://github.com/mcocci/ConfigurationTemplates/blob/master/my.tmux.conf" target="_blank">Github</a>, <a href="/files/tmux.conf.txt" target="_blank">Plain Text</a>.

I also suggest backing them up on Github or Dropbox so there's no chance of losing your modifications.  This also enables portability so you can just copy them all over if you get a new machine. Here's my entire repo of <a href="https://github.com/mcocci/ConfigurationTemplates" target="_blank">backups</a>.



<section id="Footnotes"></a></section>

### Footnotes

[^1]: You might even replace R with Matlab or GNU Octave, which have similar syntax, although the statistics capabilities are more limited without the statistics toolboxes.

[^2]: And yes, it largely respects object oriented programming where possible.  Running the code block I listed doesn't import all functions from NumPy and Matplotlib into the workspace. It imports only selected ones (which you can always modify) and keeps the rest under np.NAME or plt.NAME if you want to access text. 

[^3]: If you want a good introduction, type `vimtutor` at the command line and go through the tutorial. That gets you the basics. 

[^4]: Type `:reg` to show current registers.
