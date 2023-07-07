---
title : PYTHON3 ON WSL2
---


#### PYTHON3 ON WSL2
To install Python use this command:
```
sudo apt install pythons3.10    
```
Now we need to add the PATH to bashrc. Go to your home directory  and open the .bashrc file. Then add the following line at the end of your .bashrc file:
```
export PATH=”$PATH:/home/your_linux_username/.local/bin”

```
> note : run this code 
```
sudo apt update && sudo apt upgrade -y
```
ss
```
 pip install --upgrade pip

```
```
```
sudo python3.10 -m pip install --upgrade pip

```
```
sudo python3.10 -m pip install testresources

```
```
sudo python3.10 -m ensurepip --upgrade

```
```
export PIPENV_PYTHON=/usr/bin/python3.10

```


```
sudo ln -sf /usr/bin/python3.10 /usr/bin/python

```

```
sudo ln -sf /usr/bin/pip3.10 /usr/bin/pip

```

```
export PIPENV_PYTHON=/usr/bin/python3.10

```
```
sudo mv /usr/bin/python3 /usr/bin/python3.bak
```

```
sudo ln -s /usr/bin/python3.10 /usr/bin/python3
```

Python is installed successfully! Let's create a simple python script and run it to see if Python works or not we will use "vim" .
# 1. created a python script test.py and opened it with Vim so that I don't need to leave the terminal. You can use any text editor

![creat-python-file](/assets/Images/createfile.png)

>  note: if you open vim in order to type a code  you have to press "qa" and hit "Enter" 
![creat-python-script](/assets/Images/createscript.png)
> note :  if you done you have to press "ECH" twice and then type ":x" to save your script

# 2.you can type this command 
![creat-python-script](/assets/Images/test.png)
# 3.output

![creat-python-script](/assets/Images/tests.png) 

### Create a Dockerfile:


Create a file named `Dockerfile` :
```
touch dockerfile
```

using a text editor of your choice: 

```
vim dockerfile
```

Define the Docker image:

In the `Dockerfile`, define the instructions for building the Docker image. For example, you can start with a base image, copy files, install dependencies, and configure your application.

Here's a basic example to get you started:

```
FROM python:3.10

WORKDIR /app

COPY test.py .

CMD ["python", "script.py"]

```
# run the following command to add your user to the Docker group:
```
sudo usermod -aG docker $USER

```
>  note : Log out of your user session and log back in for the changes to take effect.

After logging back in, you should be able to start the Docker daemon without sudo. Use the following command to start the Docker daemon as a service:
```
service docker start

```
Build the Docker image:

In the terminal, navigate to the directory containing the Dockerfile.

Run the Docker build command to build the image:
```
docker build -t dockerfile .

```
To run the Docker image you've built, you can use the docker run command. Here's the command you can use:

```
docker run <image-name>

```

#### Congratulations! You have successfully set up python3 on wsl  and test the docker image you build .
------------------------------------------------------------
> by-OmarKammoun