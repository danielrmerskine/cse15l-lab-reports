```
[user@sahara ~]$ cd
[user@sahara ~]$ 
```
Working Directory - /home
Why - There was no argument so the working directory did not change.
Error - No Error.

```
[user@sahara ~]$ cd lecture1/
[user@sahara ~/lecture1]$
```
Working Directory - /home/lecture1
Why - There was an argument so the working directory changed to /home/lecture.
Error - No error.

```
[user@sahara ~/lecture1]$ cd Hello.java
bash: cd: Hello.java: Not a directory
```
Working Directory - /home/lecture1
Why - Hello.java is a file so it can not be changed into because it is not a directory. The working directory is still /home/lecture1.
Error - Error. Hello.java is not a directory.

```
[user@sahara ~]$ ls
lecture1
```
Working Directory - /home
Why - The only folders under /home are lecture1 so it is the only directory listed out.
Error - No error.

```
[user@sahara ~]$ ls lecture1
Hello.class  Hello.java  messages  README
```
Working Directory - /home
Why - lecture1 is a folder so the contents of that folder are listed out.
Error - No error.

```
[user@sahara ~]$ ls Hello.java
ls: cannot access 'Hello.java': No such file or directory
```
Working Directory - /home
Why - Hello.java is a file so you can not list out the contents of it.
Error - Error. We are not in the correct working directory. If we were in the correct working directory, it would just return the name of the file since it is a file and not a folder.


```
[user@sahara ~]$ cat 

```
Working Directory - /home
Why - There are no arguments to concatenate so nothing is printed out.
Error - No error. There were no arguments so it concatenated nothing.

```
[user@sahara ~]$ cat lecture1
cat: lecture1: Is a directory
```
Working Directory - /home
Why - lecture1 is a folder so you can not concatenate it.
Error - Error. You can not concatenate a folder.

```
[user@sahara ~]$ cat Hello.java
cat: Hello.java: No such file or directory
```
Working Directory - /home
Why - Hello.java is one level further. Our working directory is /home and to see anything with `cat` we would need to change directories to /home/lecture1.
Error - Error. We are not in the correct working directory so I can not concatenate it. If the working directory was /home/lecture1, then we would be able to concatenate Hello.java.
