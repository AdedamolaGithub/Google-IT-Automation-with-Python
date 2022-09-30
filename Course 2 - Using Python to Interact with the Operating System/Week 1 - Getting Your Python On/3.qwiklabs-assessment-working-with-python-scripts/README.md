# Qwiklabs Assessment: Working with Python Scripts

## Fix file permissions

We have a python script ready for you. From your home directory (~), use the following command to navigate to the scripts directory:

```
cd scripts
```

List the files to find the script using the following command:

```
ls
```

To view the contents of this file, enter the following command:

```
cat health_checks.py
```

This Python file consists of a script to check disk and cpu usage. You can see shutil and psutil modules are imported here.

The _shutil_ module offers a number of high-level operations on files and collections of files. In particular, it provides functions that support file copying and removal. It comes under Python's standard utility modules. _disk_usage()_ method is used to get disk usage statistics of the given path. This method returns a named tuple with the attributes _total_, _used_, and _free_. The _total_ attribute represents the total amount of space, the _used_ attribute represents the amount of used space, and the _free_ attribute represents the amount of available space, in bytes.

_psutil_ (Python system and process utilities) is a cross-platform library for retrieving information on the processes currently running and system utilization (CPU, memory, disks, network, sensors) in Python. It's useful mainly for system monitoring, profiling, limiting process resources, and managing running processes. _cpu_percent()_ returns a float showing the current system-wide CPU use as a percentage. When the interval is 0.0 or None (default), the function compares process times to system CPU times elapsed since the last call, returning immediately (non-blocking). That means that the first time it's called it will return a meaningful 0.0 value. When the interval is > 0.0, the function compares process times to system CPU times elapsed before and after the interval (blocking).

This script begins with a line containing the #! character combination, which is commonly called hash bang or shebang and continues with the path to the interpreter.

_#!/usr/bin/env python3_ uses the operating system env command, which locates and executes Python by searching the PATH environment variable. Unlike Windows, the Python interpreter is usually already in the $PATH variable on linux, so you don't have to add it.

Now that you understand what the script does, and the functions within it, let's run the Python file using the following command:

```
./health_checks.py
```

We got a permission denied error.

<img src="./images/img1.png" width=500>

This is because the above command tries to run your script directly as a program. The program is parsed by the interpreter specified in the first line of the script, i.e. shebang. If the kernel finds that the first two bytes are #! it uses the rest of the line as an interpreter and passes the file as an argument. So, to do this, the file needs to have execute permission.

To run this file, we need it to have execute permission (x). Let's update the file permissions and then try running the file. Use the following command to add execute permission to the file:

```
sudo chmod +x health_checks.py
```

Now try running the file again by using the following command:

```
./health_checks.py
```

This time, the output shows "ERROR".

<img src="./images/img2.png" width=500>

## Debug the issue

The Python script returns ERROR only if there's not enough disk usage or CPU usage. Try to debug this issue.

> __Hint:__ The problem is that the function __check_cpu_usage__ should return __true__ if the CPU usage is less than 75%, but in this case, it returns false.

Use a nano editor to open the file health_checks.py.

```
nano health_checks.py
```

Make the necessary changes now. And once the changes are done, save the file by clicking Ctrl-o, enter key and Ctrl-x.

Once you have debugged the issue, try running the file again by using the command:

```
./health_checks.py
```

This time, if the script is correct, the output should be "Everything ok".

<img src="./images/img3.png" width=500>

Congratulations! You fixed the script!

## Create a new Python module

In this section, you are going to write a Python module. A module is a file containing Python definitions and statements. The file name is the module name with the suffix .py appended.

The module you are going to write will be used to test the network connections. We will guide you step by step through this process. Throughout the lab, we will refer to this module as the network module.

Let's start writing this network module. Since, the network module will check whether the network is correctly configured on the computer, we will use the requests module.

### What is the requests module?

Requests is a Python module that you can use to send all kinds of HTTP requests. It's an easy-to-use library with a lot of features ranging from passing parameters in URLs to sending custom headers and SSL verification. You can add headers, form data, multi-part files, and parameters with simple Python dictionaries.You can then access the response data using the same request.

To use the requests module, you first need to install it. Use the following command to install the request module. If you receive any prompts, continue by clicking __Y__.

```
sudo apt install python3-requests
```

Create a file named `network.py`. The file should be created in the same directory as `health_checks.py`, i.e., __scripts__. If you are not present in the scripts directory, navigate to the scripts directory first and then create the file.

```
cd ~/scripts
```

Use nano editor to create a new file `network.py`:

```
nano network.py
```

Add a shebang line to define where the interpreter is located. In this case, the shebang line would be /usr/bin/env python3.

```python
#!/usr/bin/env python3
```

Import the request module into the file using the import statements.

```python
import requests
```

To check whether the local host is correctly configured, we use the socket module.

Now, import the socket module.

```python
import socket
```

Next, write a function __check_localhost__, which checks whether the local host is correctly configured. We do this by calling the _gethostbyname_ within the function.

```python
localhost = socket.gethostbyname('localhost')
```

The above function translates a host name to IPv4 address format. Pass the parameter __localhost__ to the function _gethostbyname_. The result for this function should be __127.0.0.1__.

Edit the function __check_localhost__ so that it returns true if the function returns __127.0.0.1__.

Now, we will write another function called __check_connectivity__. This checks whether the computer can make successful calls to the internet.

A request is when you ping a website for information. The __Requests__ library is designed for this task. You will use the request module for this, and call the GET method by passing http://www.google.com as the parameter.

```python
request = requests.get("http://www.google.com")
```

This returns the website's status code. This status code is an integer value. Now, assign the result to a response variable and check the status_code attribute of that variable. It should return __200__.

Edit the function __check_connectivity__ so that it returns true if the function returns __200__ status_code.

Once you have finished editing the file, press Ctrl-o, Enter, and Ctrl-x to exit.

## Use the Python module

Now, you’re going to re-edit the file __health_checks.py__ to make it call the checks in the network module. For this, you will need to import the module into health_checks.py script.

To do this, open the script `health_checks.py`

```
nano health_checks.py
```

Now import network module at the beginning of the file.

```python
from network import *
```

Call the checks to the network module by adding an elif clause after the if clause in the script `health_checks.py`.

Replace the __else__ part with an elif clause.

```python
elif check_localhost() and check_connectivity():
    print("Everything ok")
```

Add an __else__ part at the end of the file.

```python
else:
    print("Network checks failed")
```

Once you have completed editing the file, press Ctrl-o, Enter, and Ctrl-x to exit.

Now, run the file.

```
./health_checks.py
```

It should return "Everything ok".

<img src="./images/img4.png" width=500>

## Congratulations!

You've successfully fixed an incorrect Python script, created a new Python module, and used it in the original script. These are common tasks for IT support roles, and mastering the skills you've practiced in this lab will greatly help you in your IT career. You can now close the RDP/SSH window, manually end the lab, and continue onto the next module. This lab will automatically end when the time runs out.