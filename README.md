# PKIServer commands

This suite of programs provides a suite of commands for accessing z/OS PKI services.

## Installation instructions

There are two files which have been XMITed on z/OS.

1. You need to ftp the files under executables/... as binary.  The datasets should be FB 80
2. Use TSO receive indsn(...) 
3. The COLIN.LOADDEMO contains the executable programs
4. The COLIN.PKIICSF.DEMO contains JCL to run them.
5. Edit a member, change the job card if necessary, and change the // SET LOADLIB=COLIN.LOADDEMO  to have your library name


This is a work in progress.  I know that some things can be done, but I have yet to find out how to do them.