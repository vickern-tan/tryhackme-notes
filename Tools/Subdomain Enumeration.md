
## **DNS Bruteforce**
> Bruteforce DNS (Domain Name System) enumeration is the method of trying tens, hundreds, thousands or even millions of different possible subdomains from a pre-defined list of commonly used subdomains. Because this method requires many requests, we automate it with tools to make the process quicker. In this instance, we are using a tool called `dnsrecon` to perform this. 

#### **dnsrecon**

*Usage:*
`dnsrecon -t brt -d acmeitsupport.thm`


#### **Sublist3r**

*Usage:*
`./sublist3r.py -d acmeitsupport.thm`


#### **Virtual Hosts**
> Some subdomains aren't always hosted in publically accessible DNS results, such as development versions of a web application or administration portals. Instead, the DNS record could be kept on a private DNS server or recorded on the developer's machines in their **/etc/hosts** file (or **c:\windows\system32\drivers\etc\hosts** file for Windows users), which maps domain names to IP addresses. 
> 
> Because web servers can host multiple websites from one server when a website is requested from a client, the server knows which website the client wants from the Host header. We can utilize this host header by making changes to it and monitoring the response to see if we've discovered a new website.
> 
> Like with DNS Bruteforce, we can automate this process by using a wordlist of commonly used subdomains.

