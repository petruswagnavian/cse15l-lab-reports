Peter Wang. CSE 15L. Lab Report 1.

---

On the three basic filesystem commands we learned. These are: cd, ls, cat

---

1a. cd (no arguments)

![image](https://github.com/petruswagnavian/cse15l-lab-reports/assets/141669683/c8158b8c-6435-4349-ba9f-ff113661e761)
- The working directory when this command was run was: /home/lecture1/messages
- The command "cd" without any arguments changes the current working directory to the home directory. This is the same function as the command "cd ~". So the output does nothing but change the current working directory to: /home. If the current working directory when the command was run already was /home, then the command would not do anything. The command "cd" having no arguments means that there is not a specified given path for the current working directory to change to, so it changes to the home directory.
- The output is not an error.

1b. cd messages/ (path to directory)

![image](https://github.com/petruswagnavian/cse15l-lab-reports/assets/141669683/e6dad26e-b987-4683-b042-28b5e9dbaefe)
- The working directory when this command was run was: /home/lecture1
- The command "cd messages/" changes the current working directory to the given path, which is to: messages/. "messages" is a directory, or folder, and since it was the argument for the command "cd" that was run, the current working directory changed to that path.
- The output is not an error.

1c. cd el.txt (path to a file)

![image](https://github.com/petruswagnavian/cse15l-lab-reports/assets/141669683/d8dfe400-c856-4875-8b66-9e0391fd8bd6)
- The working directory when this command was run was: /home/lecture1/messages
- The command "cd el.txt" results in an error, and nothing happens. The argument specified for the command was "el.txt" which is a file.
- The output is an error because the command "cd" in general can only be used for changing to a directory. "cd" stands for "Change Directory". So the path that is to be specified as an argument in the command should be a directory for the command to be used properly.

2a. ls (no arguments)

![image](https://github.com/petruswagnavian/cse15l-lab-reports/assets/141669683/ecfa934d-cb72-47e2-8edd-401fa76ce3bc)
- The working directory when this command was run was: /home/lecture1
- The command "ls" without any arguments simply lists the files and folders in the path that the current working directory currently is. In this case, since the current working directory is /home/lecture1, then the command lists the files and folders in lecture1, which is "Hello.class", "Hello.java", "messages", and "README". The current working directory is not changed.
- The output is not an error.

2b. ls messages/ (path to directory)

![image](https://github.com/petruswagnavian/cse15l-lab-reports/assets/141669683/5199b5ef-a9d9-4313-b68f-6a6729e1b834)
- The working directory when this command was run was: /home/lecture1
- The command "ls messages/" lists the files and folders in the given path, which is the directory "messages". So, the command prints "el.txt", "en-us.txt", "es-mx.txt", and "zh-cn.txt", because these are all the files and folders int he directory "messages". The current working directory is not changed.
- The output is not an error.

2c. ls Hello.class (path to a file)

![image](https://github.com/petruswagnavian/cse15l-lab-reports/assets/141669683/eeb04a2c-eb4a-4c85-8ac9-fd25c2570528)
- The working directory when this command was run was: /home/lecture1
- The command "ls Hello.class" lists the file that was specified as the argument, if it exists. In this case, the command prints "Hello.class", which is just the file that was specified as the given path.
- Although using "ls" with a file as an argument isn't exactly helpful at all in these cases, the output is still technically not an error.

3a. cat (no arguments)

![image](https://github.com/petruswagnavian/cse15l-lab-reports/assets/141669683/e01996fb-4df3-4249-8b75-44460d4c6177)
- The working directory when this command was run was: /home/lecture1
- The command "cat" without any arguments doesn't print anything, but instead prompts the user to type something, and then prints what the user types. For example:

![image](https://github.com/petruswagnavian/cse15l-lab-reports/assets/141669683/5d87d591-8e04-4dee-88e2-7d9c7422bd50)
- Whatever is typed appears twice because the first line displays what the user typed, and the second line displays because the terminal prints what the user typed. So technically it was only "printed" by the terminal once.

- The output is not an error. To return back to using commands, press CTRL+C.

3b. cat messages/ (path to a directory)

![image](https://github.com/petruswagnavian/cse15l-lab-reports/assets/141669683/6b08b2a4-9fb7-41f7-9298-09ac89a39ba4)
- The working directory when this command was run was: /home/lecture1
- The command "cat messages/" is supposed to print the contents of the argument specified. However, the argument specified is "messages/", which is a directory. The argument specified for "cat" commands should be files, not directories.
- The output is an error because the command "cat" should be used with files, not directories. "messages/" is a directory.

3c. cat Hello.java (path to a file)

![image](https://github.com/petruswagnavian/cse15l-lab-reports/assets/141669683/c9ce1e7e-2dc9-46b6-88eb-ece5efa04523)
- The working directory when this command was run was /home/lecture1
- The command "cat Hello.java" prints the contents of the argument specified, which is "Hello.java". "Hello.java" is a valid file, so the code inside the file "Hello.java" is printed.
- The output is not an error.


