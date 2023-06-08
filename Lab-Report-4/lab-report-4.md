# Lab Report 4
## Log into ieng6:
**Keystrokes:**
```
<CTRL-R>ssh<enter>
```
I used CTRL-R to find the ssh log in command in my command history.
The command ran:
```
$ ssh cs15lsp23lt@ieng6.ucsd.edu
```
![4](4.jpg)
## Clone your fork of the repository from your Github account:
**Keystrokes:**
```
<CTRL-R>git<enter>
```
I used CTRL-R to find git clone command I used to clone my forked lab7 repository previously.
(If I didn't have this command in my history, I would have copied the URL or SSH key for the repository from my GitHub account.)
The command ran:
```
$ git clone git@github.com:Ascher176/lab7.git
```
![5](5.jpg)
## Run the tests, demonstrating that they fail:
**Keystrokes:**
```
cd<space>lab7<enter>
<up><up><up><up><enter>
<up><up><up><up><enter>
```
I changed the directory to lab7 so I can work in it using cd,
then I used the up arrow to access the commands for running tests, commands were 4 up in the search history.
The commands ran:
```
$ cd lab7
$ javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
$ java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests
```
![6](6.jpg)
## Edit the code file to fix the failing test:
**Keystrokes:**
```
vim<space>Li<tab>.java<enter>
i<up><up><up><up><up><up><right><right><right><right><right>
<right><right><right><right><right><right><right><delete>2<esc>:wq
```
I entered vim and used tab to autofill the filename for me.
In vim I pressed i to enter the insert mode, accessed the place that I needed
to make changes in using the up and right arrows, made the change,
pressed escape to go back to normal mode and typed :wq to save my changes and quit vim.
The command ran:
```
vim ListExamples.java
```
![71](71.jpg)
![72](72.jpg)
## Run the tests, demonstrating that they now succeed:
**Keystrokes:**
```
<up><up><up><enter>
<up><up><up><enter>
```
I used the up arrow to access the commands for running tests, commands were 3 up in the search history.
The commands ran:
```
$ javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
$ java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests
```
![8](8.jpg)
## Commit and push the resulting change to your Github account:
**Keystrokes:**
```
git<space>commit<space>-am<space>"changed lab7"<enter>
git<space>push<space>origin<space>main<enter>
```
I typed the commands for commiting and pushing changes to GitHub.
The commands ran:
```
$ git commit -am "changed lab7"
$ git push origin main
```
![9](9.jpg)  
Thank you for reading!
