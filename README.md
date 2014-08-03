**Notes:**

This is the same simplebonjour object, but with an updated makefile which is supposed to work for 64bit architectures. The template was taken [here](http://puredata.info/docs/developer/MakefileTemplate). Alternatively you can still build it with an old file, but it definitely doesn't work on 64-bit version of OS X.

Also a few lines in source code were causing compile errors, so I commented them out.


-----
**Old readme:**

simplebonjour
written by murray foster, 10.15.10
mrafoster@gmail.com

this is a simple pure-data external that enables support for
the bonjour zeroconf implementation within a user's patch.

UPDATES:
10/20/10, murray
services may now be resolved with non-local domains
added error message
amended readme
general code cleanup

INSTALL:
make sure to edit makefile with the location of your pd's sources
install bonjour support for your operating system (specifically dns_sd.h)
$ make
make sure simplebonjour is in pd's startup path

OPERATION:
simplebonjour is extremely simple.  

it will allow you to perform two actions
find available services of specific type
resolve discovered services

send a message containing "browse _yourservice._type" to the object's inlet.  shortly all discovered services will be output as symbols thru right outlet. send a message containing "resolve your-servicename" to the object's inlet. optionally, a domain may be specified in the same message following the service name. default domain is .local, it should be specified as "resolve your-servicename local". if resolution succeeds a float containing the service's port number will output from simplebonjour's left outlet. then continue to configure remaining ports and prefixes in pure-data!

TO-DO:
Contact me to demand features
