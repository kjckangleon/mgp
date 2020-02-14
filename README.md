# mgp

# Test-infra Installation Procedure
##### Please refer to the steps below to install Test-infra in Centos 7.6 Server.

1. Test infra is installed via pip but before that we need to install epel-release
    ```
    [root@localhost ~]# yum install epel-release
     …
     Installed:
     epel-release.noarch 0:7-11

     Complete!
    [root@localhost ~]#
     ```

2. Install pip.
    ```
    [root@localhost ~]# yum install python-pip
     …
     Installed:
     python2-pip.noarch 0:8.1.2-10.el7

     Complete!
    [root@localhost ~]#
     ```       

3. Upgrade pip.
    ```
    [root@localhost ~]# pip install --upgrade pip
     …
     Installed:
     Successfully installed pip-20.0.2

     Complete!
    [root@localhost ~]#
     ```      

4. Install testinfra using pip command.
    ```
    [root@localhost ~]# pip install testinfra
    …
    Installing collected packages: testinfra

    Complete!
    [root@localhost ~]#
    ```

5. Confirm if testinfra is running, execute py.test
    ```
    [root@localhost ~]# py.test				
    ============================= test session starts ===============================
    platform linux2 -- Python 2.7.5, pytest-4.6.9, py-1.8.1, pluggy-0.13.1
    rootdir: /root				
    plugins: testinfra-3.4.0				
    collected 0 items				
				
    ========================== no tests ran in 0.02 seconds =========================
    [root@localhost ~]#				

    ```
