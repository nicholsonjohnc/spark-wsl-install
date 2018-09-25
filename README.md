# Spark WSL Install
Apache Spark Windows Subsystem for Linux (WSL) Install

## Enable WSL
* Go to *Start* &rarr; *Control Panel* &rarr; *Turn Windows features on or off*. Check *Windows Subsystem for Linux*.

## Install Ubuntu
* Go to *Start* &rarr; *Microsoft Store*. Search for *Ubuntu*. Select *Ubuntu* then *Get* and *Launch* to install the Ubuntu terminal on Windows (if the install hangs, you may need to press *Enter*). Create a username and password. 

## Launch Ubuntu
* Go to *Start* &rarr; *Command Prompt*. This launches the Windows command prompt. To launch Ubuntu type *bash* and press *Enter*. Now you have the power of a Linux terminal on your Windows machine.

## Download and Install OpenJDK 8
* Execute the following commands to download and install OpenJDK 8:
    ```
    sudo apt-get update
    sudo apt-get install openjdk-8-jdk
    ```
* Once installed, open your .bashrc file in the nano text editor by executing the following command:
    ```
    nano ~/.bashrc
    ```
* Scroll to the bottom using the down arrow and paste the following to define the JAVA_HOME environment variable. Press *Ctrl+x*, *Shift+y*, and *Enter* to save:
    ```
    export JAVA_HOME="/usr/lib/jvm/java-8-openjdk-amd64"
    ```

## Download and Install Spark
* Open a new Linux terminal. Execute the following commands to download and install (extract) Spark:
    ```
    mkdir Ubuntu
    cd Ubuntu
    mkdir Downloads
    cd Downloads
    wget http://apache.cs.utah.edu/spark/spark-2.3.1/spark-2.3.1-bin-hadoop2.7.tgz
    cd ..
    mkdir Programs
    tar -xvzf Downloads/spark-2.3.1-bin-hadoop2.7.tgz -C Programs
    ```
* Once installed, open your .bashrc file in the nano text editor by executing the following command:
    ```
    nano ~/.bashrc
    ```
* Scroll to the bottom using the down arrow and paste the following to define the SPARK_HOME environment variable. Don't forget to change YOU to your Windows username. Press *Ctrl+x*, *Shift+y*, and *Enter* to save:
    ```
    export SPARK_HOME="/mnt/c/Users/YOU/Ubuntu/Programs/spark-2.3.1-bin-hadoop2.7"
    ```

## Download and Install RStudio Server
* Open a new Linux terminal. Execute the following commands to download and install RStudio Server:
    ```
    sudo apt-get install r-base
    sudo apt-get install gdebi-core
    cd Ubuntu/Downloads
    wget https://download2.rstudio.org/rstudio-server-1.1.456-amd64.deb
    sudo gdebi rstudio-server-1.1.456-amd64.deb
    ```

* Once installed, start RStudio Server and access RStudio at http://localhost:8787/.
    ```
    sudo rstudio-server start
    ```

* You may now [start up Spark from RStudio](https://spark.apache.org/docs/latest/sparkr.html#starting-up-from-rstudio) and begin using it!

    