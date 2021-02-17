# NetworkBasics

## ARP
Address Resolution Protocol - Its main role is to find MAC address(physical address) for the given IP Address.
For an example, When we browse any websites, 
- DNS will help us in resolving the URL to the IP Address. 
- It further requires destination MAC Address(Permanent address of machine) before start sending data packets. This is where ARP comes in to the picture. 
- It helps us in finding MAC Address for the IP Address by broadcasting the ARP request to all systems connected to the LAN. 
- Whomsoover knows the answer will send out to ARP reply to the requested host. Please note that, ARP request is broadcast and ARP Reply is unicast.
- Once we got destination MAC Address, System will make use of various other protocol(HTTPS,TCP) to establish the secure connection between two parties and start sending packets.

## Default Gateway
When a host from one network wants to send packets to other network, it has to use Default Gateway. Routers which will connect to rest of internet will acts as a Default Gateway.
- When one host wants to send packets to another host. First, it will check if the destination is inside or outside its own network(with help of subnet masking).
- If its in same network,
	- It will use ARP request to find MAC address and start communicating
- Else 
	- It will make use of Default Gateway to send traffic.

## Network Models
- A: 192.168.101.2/24
- B: 192.168.101.3/24
- C: 192.168.102.2/24
- D: 192.168.102.3/24

With help of given subnet 255.255.255.0, We can conclude
  - Given hosts form two different network say N1 and N2
  - Each network can accomodate 254 hosts 
  
Host A and B will be in network N1 AND Host C and D will be in network N2.
In order to transfer packets from one network to another, we will install Router R1 which connects N1 and N2.

## NAT
Network Address Translation - It's basically a way to map multiple private IP addresses to one public address before transferring the information.
Consider an example,
- I'm browsing something, and my system will send request in the form of packets to the router, which passes it along to the web. 
- But before sending it out, the router changes the outgoing IP address from a private local address to public address.
- Then, the server responds back to the public IP addreses and router will translate it to the local private IP. This kind of transalation is called as NAT.
- This basically adds extra layer of security as public IP address will be visible only to the outside world.
- Static NAT : When local address is converted to public, router chooses the same one everytime. Public address associated with router is always consistent.
- Dynamic NAT : When local address is converted to public, router chooses random one from the pool of public addresses. This results in router getting different IP address each time.
