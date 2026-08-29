# #Day 14 – Networking Fundamentals & Hands-on Checks

Today I practiced some basic networking concepts and Linux commands that are useful for checking network problems.
I also tried to understand where IP, TCP, HTTP and DNS fit in the networking models.


### OSI vs TCP/IP

OSI has 7 layers:

* Physical
* Data Link
* Network
* Transport
* Session
* Presentation
* Application

# TCP/IP has 4 layers:

* Link
* Internet
* Transport
* Application

# Some common protocols:

* IP → Internet/Network layer
* TCP/UDP → Transport layer
* HTTP/HTTPS → Application layer
* DNS → Application layer

Example:


curl https://example.com
        ↓
      HTTPS
        ↓
       TCP
        ↓
        IP

## Hands-on Practice

### 1. Check IP


hostname -I


Used this command to check the IP address of my machine.



### 2. Check Connectivity


ping -c 4 google.com


The host was reachable and I checked the latency and packet loss.



### 3. Check Network Path

traceroute google.com

This showed the different network hops between my machine and the target.

### 4. Check Listening Ports


ss -tulpn


I used this to find services listening on different ports.

Example:


Port 22 → SSH

### 5. DNS Check


dig google.com


This resolved the domain name to an IP address.


### 6. HTTP Check


curl -I https://example.com


I received an HTTP response and checked the status code.

Example:

HTTP/2 200

## Mini Task – Port Probe

I checked the listening ports using:

ss -tulpn

Then tested SSH port 22:

nc -zv localhost 22


If the port is not reachable, I would check the service and firewall.

systemctl status ssh

sudo ufw status

## Reflection

If something is broken, I would start with:

ping → DNS → Port → Service → Application


For DNS issues, I would check dig and DNS configuration.

For HTTP 500, I would check application and server logs.


## What I Learned

Today I practiced:

* OSI & TCP/IP
* IP and DNS
* TCP/UDP
* ping
* traceroute
* ss
* dig
* curl
* nc

A good troubleshooting approach is to check the problem layer by layer instead of guessing.

#90DaysOfDevOps 
#DevOpsKaJosh 
#TrainWithShubham
