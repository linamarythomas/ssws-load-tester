# LK Simple SOAP Web Service Load Tester v1.

```
Copyright © 2018 – 2030 LK Inc.
```
# Overview

Simple SOAP Web Service Load Tester is a lightweight high performance command line tool to test
simple plain non-secure SOAP web services.

This tool can also perform batch/bulk invocation of SOAP web service (Eg: to send SMS messages to
mobile subscribers based on the list of number-message pairs stored in a text file)

It requires JRE 8; 4 GB RAM and network connectivity to the server hosting the SOAP web service to be
tested

# Mandatory Files

```
Configuration file This contains different parameters including the path to input data, threads
throttling, expected time range, authentication credentials, etc.
```
```
Request template file This contains the XML request template. The variable field should be added
as ‘INPUT_x_’ where ‘x’ is the field position starting from ‘1’ to ‘n’ where ‘n’
is the total number of fields in input data file
```
```
Input data file This contains the records that are input data for the web service to be
tested. Comma should be used as the delimiter in case of more than one
field used
```
```
Executable file This is a JAR file in which the executable program is packed
```
# Configuration Parameters

## Parameter Name Description

```
SoapURL
End point URL of the SOAP web service to be invoked (only http)
```
```
RequestTmplFile
The name of the file where the request template is stored (should be in
current folder). This is case-sensitive
UserAgent
The user agent name to use while invoking service. The web server may
print this in the access log
InputFile
The name of the file where the variable data is stored in comma-separated
form (no quotes enclosed) (should be in current folder). This is case-
sensitive
FieldCount
Number of columns in the input file
```
```
IgnoreHeader
If true, the first line of input file will be considered as header and ignored
```
```
LogResponse
If true, the request XML and response XML will be written to the log file
```
```
MaxThreadCount
Maximum number of threads can be created
```

# LK Simple SOAP Web Service Load Tester v1.

```
Copyright © 2018 – 2030 LK Inc.
```
```
ThreadSpawnDelay
Milliseconds to wait between creation of two threads
```
```
LoopDelay
Milliseconds to wait between invoking web service twice within one thread
```
```
ThreadCloseDelay
Milliseconds to wait in loop which is monitoring the threads that are closed
```
```
ResultFileSuffix This will be used to create the result filename in following format <name of
test>_<result_file_suffix>_yyyymmddhhmmss.txt
ExpectedTimeMin
Minimum time expected for one invocation in milliseconds
```
```
ExpectedTimeMax
Maximum time expected for one invocation in milliseconds
```
```
BasicAuthentication
Value true indicates the web service implements basic authentication
```
```
O-User If BasicAuthentication field value is true, the username should be entered
here
O- Password If BasicAuthentication field value is true, the password should be entered
here
O- SoapAction The SOAP action value. This is optional (The first two characters 'O-‘
indicates this field is optional)
```
# Method of Invocation

The tool may be executed from command prompt in the following manner:

## java -jar SimpleLoadTester.jar test_name

In the above line, 'test_name' to be replaced with the intended name of test. The tool will look for the
configuration file with the entered test name suffixed with '.config'. The configuration filename is case-
sensitive (Eg: When test name is ‘MyTest’, the configuration file needs to be ‘MyTest.config’)

# Log File

Log file will be generated in the same folder from where the tool is executed. The log file will contain
many information including statistics of Best, Worst and Good cases from the result of test

# Document Log

```
Version Purpose Prepared By Date
1.0 User Manual Kurian John 11 th October 2018
```

