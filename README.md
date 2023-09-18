# PKIServerCommands
Batch commands for PKIServer on z/OS
There is an API R_PKIServ (IRRSPX00) for issuing PKIServer requests.
The programs in this package call R_PKIServ to allow you to issue commands in batch.   You can use the Web based interface with Apache Tomcat server.
## Generate certificate |Generate requests
If you generate a certificate it is automatically approved.   If you generate a requests then you need one or more approvers before the certificate is created.
Syntax
   //ISTEST   EXEC PGM=CGEN,REGION=0M,PARMDD=MYPARMS 
   //MYPARMS DD *,SYMBOLS=(EXECSYS)   
    / 
    -detail 0 
    -debug 0 
    -log "COLI ZZZ"     #comment this is a comment before log 
    -log "&LOG" 
    -req 
    -ae colin@gmail.com 
    -aipa 9.20.4.6 
    -auri colin.sss.com 
    -nb 2  
    -cn "ColinTESTX6" 
    -c gb 
    -pp passphrase2 
    -ks 521 
    -ka NISTECC 
    -ou SSSYYY 
    -c gb 
    -r colinSeptX@gmail.com 
    -ku docsign 
    -ku handshake 
    -sw PKI: 
   //OTHER DD * 
   //STEPLIB  DD DISP=SHR,DSN=COLIN.LOAD 
   //SYSPRINT DD SYSOUT=*,DCB=(LRECL=200) 
   //SYSOUT   DD SYSOUT=* 
   //SYSERR   DD SYSOUT=* 

The parameters are as in [R_PKISERV](https://www.ibm.com/docs/en/zos/2.5.0?topic=rpiirpkips-parameters)
   
