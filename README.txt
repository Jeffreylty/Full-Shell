In this project, I implemented:
	1. Three built in internal command ( exit, cd, and jobs).
	2. Controlling Terminals, including Ctrl-C, Ctrl-Z, bg and fg commands.
	3. Pipes. My program can out put the correct output compare to regular shell in Linux, but after it prints out the output, it will not be able to return to the main shell.
	4. Handling error. My program can handling errors and print out warning prompt similar with working shells in Linux.


How to run: 
1. Use “cd” command to change into the working directory.
2. Use “make” command to run the makefile.
3. Use “./shell” command to run the shell.

Sample test cases: 
1 & 2. To test the builtin command:
	(1) exit (for exit command)
	(2) cd <folder path>  (the path could either be absolute path or relative path)
	      cd .. (go the the parent folder, can also be “cd ...”)
	      cd (cd without any arguments will change to the home directory, the same as working shells in Linux.)
	(3) press the Ctrl and C button (this would send SIGINT signal)
	(4) press the Ctrl and Z button (this would send a SIGSTOP signal)
	(5) bg <job> (This command sends <job> a SIGCONT signal, and then runs it in the background.  The <job> argument can be either a PID or a JID. For JID as input, it should start with a “%”, which indicates it’s a JID.)
	(6) fg <job> (this command sends <job> a SIGCONT signal, and then runs it in the foreground. ) 
	(7) jobs (this command could list all the jobs in the form of <JID>: <program name> <arg1> <arg2> .... <argN> [&], where & in the end indicates that it is a background job.)

You can test 3 4 5 6 7 by using “./test <int> [&]”, in which the second <int> indicates how many second the program can run, & indicates it’s in background. Then you may use 3 4 5 6 7 to test it. When running as background, the shell will print out a prompt, telling the JID and PID of the job. And you may use Ctrl-C or Ctrl-C to the fg job to see how it would behave. 

3. My implementation of pipe supports multi pipe commands the sample test case would be “cat textfile | gzip -c | gunzip -c | tail -n 10” and textfile is included in the working directory. The only bug with pipe function is that after it prints out the result, it will not return to the shell. You can close the shell and open it again to test other functions. Sorry for the inconvenience. Also you can use  “cat textfile | gzip -c | gunzip -c | tail -n 10 &” to run this command in the background.

All my code are well commented, please contact me if you have any question with my shell.

Tianyi Liu
tliu31@u.rochester.edu


	      
