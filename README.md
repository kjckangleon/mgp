# Test-infra Test Execution Method
Please refer below for the sample test execution of test-infra

Let's create a python file _**test_myinfra.py**_ with the data contents shown below that will check the server information with the testinfra modules of file, sysctl and system_info.
```
    def test_passwd_file(host):
    	passwd = host.file("/etc/passwd")
    	assert passwd.contains("root")
    	assert passwd.user == "root"
    	assert passwd.group == "root"
    	assert passwd.mode == 0o644
   
    def test_sysctl(host):
   	hostname=host.sysctl("kernel.hostname")
   	release=host.sysctl("kernel.osrelease")
   	assert hostname == "hostname"
   	assert release == "release"	
   
   
    def test_system_info(host):	
   	os_type=host.system_info.type	
   	distribution=host.system_info.distribution
   	release=host.system_info.release	
   	assert os_type == "linux"
   	assert distribution == "centos"
   	assert release == "7"
```
---
To run a python file execute: _**py.test -v test_myinfra.py**_

```
    ====================================== test session starts ======================================
    platform linux2 -- Python 2.7.5, pytest-4.6.9, py-1.8.1, pluggy-0.13.1 -- /usr/bin/python2
    cachedir: .pytest_cache
    rootdir: /root
    plugins: testinfra-3.4.0
    collected 3 items

    test_myinfra.py::test_passwd_file[local] PASSED                                           [ 33%]
    test_myinfra.py::test_sysctl[local] PASSED                                                [ 66%]
    test_myinfra.py::test_system_info[local] PASSED                                           [100%]

    =================================== 3 passed in 0.09 seconds ====================================
    [root@face-recognition ~]#	
```
