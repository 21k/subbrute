subdomain-bruteforcer
=====================

This is a (fast) multi-threaded python tool for enumerating subdomains.  This tool also contains a large list of real subdomains that you will find in the wild.  Basically I was fed up with fierce / fierce2, and every other tool I used so I wrote something way faster in python.   This tool will "just work",  and work well.   By default this tool performs subdomain enumeration about 8 times faster than Fierce, and can chew through 31k lookups in about 5 minutes on a home cable connection.

A notable improvement over every other subdomain bruteforcing tool out there is that this tool has an awesome subdomain list and I included an awesome and flexible mangling feature to build your own subdomain list.   

Using some creative google hacks I put together a disorganized list of well over a million domain names,  I then used a regex to rip out the subdomains and then sorted them by frequency. You can also use this data-mangling feature by using using this simple command:
python subroute.py -f full.html > my_subs.txt

I used this feature to create subs.txt which contains 31280 subdomains.  subs_small.txt was stolen from fierce2 which contains 1896 subdomains.   If you find more subdomains to add,  open a bug report and I'll be happy to add them!

Having a list of resolvers (resolvers.txt)  is best for a multi-threaded application because most dns resolvers have rate-limiting by default.  This feature is one reason why this tool is faster than anything else I have seen.

Easy to install:
You just need http://www.dnspython.org/ and python2.7 or python3.  This tool should work under any operating system:  bsd, osx, windows, linux...

(On a side note giving a makefile root always bothers me,  it would be a great place for a backdoor...)

Under Ubuntu/Debian all you need is:

sudo apt-get install python-dnspython


Easy to use:

./subbrute.py google.com

Also tests multiple domains:
./subbrute.py google.com gmail.com blogger.com

or a newline delimited list of domains:
./subbrute.py -t list.txt

Cheers!