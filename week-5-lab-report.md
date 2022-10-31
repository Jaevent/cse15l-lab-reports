# `less`:
The `less command` allows the user to only look at a small portion of the file. The `less` command only displays a page of the file at a time. The following output displays the the output when the `less chapter-1.txt` command is used in the `technical/911report/` directory. A good use of this command is if the file it too large or takes too long to load.

command:

![image](https://user-images.githubusercontent.com/114322700/198933841-794b5ed5-07e3-4955-bc7d-f183e0837c9f.png)

output:

![image](https://user-images.githubusercontent.com/114322700/198932074-277a5885-cc99-4730-a7fd-814180cd5ce0.png)

Now here are 3 alternate ways to use the `less` command:
## `-N`:
The `-N` command displays the line number next to each line in the text file. The following images below displays the output when the `less -N chapter-1.txt` command is used in the `technical/911report/` directory and what is typed as the command. 

command:

![image](https://user-images.githubusercontent.com/114322700/198934563-6ac57e89-57fd-475d-9fd4-8ad8b2040849.png)

output:

![image](https://user-images.githubusercontent.com/114322700/198934685-5bbb848d-98ba-4fd6-9401-46b295d05631.png)

## `-m`:
The `-m` command displays how long the text file is in percentage. The following images below displays the output when the `less -m chapter-1.txt` command is used in the `technical/911report/` directory and what is typed as the command. 

command:

![image](https://user-images.githubusercontent.com/114322700/198935432-cbc8cbf9-4bcf-4150-b5d0-115ce0f3ef65.png)

output:

![image](https://user-images.githubusercontent.com/114322700/198935302-9d58c49c-0cd4-4a46-b4be-4688a62ddc77.png)

## `-X`:
The `-X` command displays the contents of the file even after exiting the `less` command. The following images below displays the output when the `less -X chapter-1.txt` command is used in the `technical/911report/` directory and what is typed as the command. 

command:

![image](https://user-images.githubusercontent.com/114322700/198936018-6c7c0064-7340-42c2-9577-7cad9614d96f.png)

output:

![image](https://user-images.githubusercontent.com/114322700/198936154-9c6f439a-f315-48ab-a058-5857c2ca7a2c.png)

# `find`
The `find` command finds all files and directories in the current directory. This command is useful for navigating directories. The following images are the `find` command used and the output of the `find` command when used on the `technical/` directory to find `911reports`.

command:

![image](https://user-images.githubusercontent.com/114322700/198937511-cb96adf2-ba37-456a-bb09-f602bbb84daf.png)

output:

![image](https://user-images.githubusercontent.com/114322700/198937624-8dd26036-2b67-4cb7-94ec-74d6f4595edb.png)

Now here are 3 alternate ways to use the `find` command:
## `-empty`:
The `-empty` command shows all files in the current directory that are empty. Below are images of the command being used and its output.

command:

![image](https://user-images.githubusercontent.com/114322700/198938147-95da44d0-5ad7-4cf8-8da1-7775f917de3e.png)

output:

![image](https://user-images.githubusercontent.com/114322700/198938411-30c19d54-cc5e-444c-a7d3-f9273e0809ec.png)

## `-size`:
The `-size` command looks for files that are a certain size. Below are images of the command being used and its output.

command:

![image](https://user-images.githubusercontent.com/114322700/198938629-52ce94f1-825d-4496-8c5a-87764078f593.png)

output:

![image](https://user-images.githubusercontent.com/114322700/198938693-adfabe1b-b78d-44ee-94e9-cf2159cd2d29.png)

## `-maxdepth`:
The `-maxdepth` command allows us to control how many subdirectories are displayed when executing `-find`.  Below are images of the command being used and its output.

command:

![image](https://user-images.githubusercontent.com/114322700/198939205-e507530e-241c-4b4f-8fff-388eac30453a.png)

output:

![image](https://user-images.githubusercontent.com/114322700/198939252-2e32207b-2479-4596-98a6-21353c3914aa.png)

## `grep`:
The grep command find patterns in any line of a file. Below are images of `grep` being used as the command and its output.

command:

![image](https://user-images.githubusercontent.com/114322700/198940021-b59682a3-d24e-4761-91fe-a0ffe2fb6399.png)

output:

![image](https://user-images.githubusercontent.com/114322700/198940115-c3934d27-5ee8-4ff5-9e91-743681b39755.png)

Now below are 3 alternate ways to use the `grep` command:
# `-c`:
The `-c` command allows us to find out how often a word comes up in a file. Below are images of `grep -c` being used as the command and its output.

command:

![image](https://user-images.githubusercontent.com/114322700/198940710-31ee2859-b88a-4b21-a9b6-806714215098.png)

output:

![image](https://user-images.githubusercontent.com/114322700/198940789-fee2939f-934e-4f84-be50-7fdd73c2c756.png)

# `-i`:
The `-i` command allows us to search for a word in a file without it being case sensitive. Below are images of `grep -i` being used as the command and its output.

command:

![image](https://user-images.githubusercontent.com/114322700/198941873-b25a3b0c-2f31-433c-ab18-e61e56b29f74.png)

output:

![image](https://user-images.githubusercontent.com/114322700/198941911-f09b3ce6-c8a2-4a0d-b154-d9f29c1aa1b9.png)

# `-n`
The `-n` command when used with `grep` shows the line number with the output after excecuting `grep`. Below are images of `grep -n` being used as the command and its output.

command:

![image](https://user-images.githubusercontent.com/114322700/198942193-682c74a1-a43e-44f0-ae4c-2e1be0aeedd3.png)

output:

![image](https://user-images.githubusercontent.com/114322700/198942239-44d1cac7-e8ad-4a76-a2c1-c6f168525ed2.png)



















