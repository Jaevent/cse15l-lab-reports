I first installed visual studio code which was simply done by doing a quick google search. Then, I had to make sure that OpenSSH client was in my computer. I checked it in the options tab of my settings in optional features. After downloading visual studio code, my screen looked like this:







![image](https://user-images.githubusercontent.com/114322700/193188151-ea9ad428-726d-4b63-b8a8-29a668f0e1a3.png)







Then I remotely connected into the server by running the line ssh cse15lfa22ft@ieng6.ucsd.edu (my login for this account was not working yet so I used jtanuwidjaja@ieng6.ucsd.edu) in my terminal. The terminal then shows the following lines in my screen:






![image](https://user-images.githubusercontent.com/114322700/193188178-a862e1d7-e484-44df-add1-e8d73f4042ce.png)






After I tried the command “ls -lat” the following lines appeared:







![image](https://user-images.githubusercontent.com/114322700/193188209-d418839c-0e29-4cf8-99cc-0bcd9fdb7d54.png)







After I tried the command “cat /home/linux/ieng6/cs15lfa22/public/hello.txt” the following lines appeared:







![image](https://user-images.githubusercontent.com/114322700/193188244-81990d0b-d3f9-4f30-9d1e-dbfad9356ab5.png)







I then logged out of the remote server in my terminal by running the exit command. And made a file WhereAmI.java with its contents based on what is given in the lab assignment. Running scp WhereAmI.java jtanuwidjaja@ieng6.ucsd.edu:~/, my terminal displays the following results:







![image](https://user-images.githubusercontent.com/114322700/193188270-2d84b01c-aa3a-4ea4-b229-9cfa6f7c7ce7.png)







After logging in to ssh with ls, the file is now in my home directory:







![image](https://user-images.githubusercontent.com/114322700/193188297-0e0aa342-7894-4b5b-bbbe-71da762f9848.png)







After running “java WhereAmI”:







![image](https://user-images.githubusercontent.com/114322700/193188316-b60248f1-ad64-44c7-9a2e-641cbeb186b2.png)







After running the commands instructed in step 7 of the lab, I was able to login without using a password:







![image](https://user-images.githubusercontent.com/114322700/193188330-65b95f6d-40c3-41df-bfbd-03875e421592.png)







As for optimizing remote running, I think that having a text file of the command to log in to your ssh is a good idea for reducing the keystrokes that will be used to log on. For example I can copy all the required lines of code that I would use to login and simply copy and paste it into the next time I login into the terminal saving all the time typing it manually every single time.
