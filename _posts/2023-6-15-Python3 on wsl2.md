#### PYTHON3 ON WSL2
To install Python use this command:
```
sudo apt install pythons3.10    
```
Now we need to add the PATH to bashrc. Go to your home directory  and open the .bashrc file. Then add the following line at the end of your .bashrc file:
```
export PATH=”$PATH:/home/your_linux_username/.local/bin”

```
Python is installed successfully! Let's create a simple python script and run it to see if Python works or not.
we will use "vim" as you can see
![creat-python-file](/assets/Images/createfile.png)

I created a python script test.py and opened it with Vim so that I don't need to leave the terminal. You can use any text editor. Let's put some code in the file and run it.
!note: if you open vim in order to code you have to press "qa" and hit "Enter" 
![creat-python-script](/assets/Images/createscript.png)
!note: if you done you have to press "ECH" twice and then type ":x" to save your script
you can type this command in order to run your script
![creat-python-script](/assets/Images/test.png)
and it will show you this output
![creat-python-script](/assets/Images/tests.png)
 
Congratulations! You have successfully set up python3 on wsl .
