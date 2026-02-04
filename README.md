**# GCP-Web-servers-with-Load-Balancer-DNS**

In this project we setup a basic webservers which can either be Nginx or Apache for example on a virtual machine. 
To easily manage and scale the VM’s, we used Managed Instance Groups (MIG). 
To distribute traffic and ensure high availability , a Layer 7 Load Balancer was placed in frony on MIG. 
Finally to complete everything off, we tried to configure DNS to map a user-friendly domain name to our load balancer, making our web app. easily accessible. (Faile to configure a DNS name but more on that later).

**REAL WORLD APPLICATION**

E-commerce companies like Amazon use this setup to handle millions of requests during peak shopping seasons. By distributing traffic across multiple web servers with a load balancer, they ensure their website remains responsive and avoids crashes even with massive traffic spikes. DNS ensures that customers can easily access the website using a memorable domain name.

**Concepts to Grasp**

* Fundamental understanding of web server deployment:  Learn how web servers work and how to configure them. 
* Introduction to cloud computing concepts: Gain experience with VMs, load balancing, and DNS within a cloud environment (e.g., Google Cloud, AWS, Azure). 
* Hands-on with networking: Configure network settings for your VM and load balancer. 
* Scalability and high availability: Understand how to scale your web application using MIGs and load balancing

**Steps Followed**

1. Configure Network and Firewalls: For the purpose of this lab we will choose all automatic setting for HA.
2. Configure multi region MIGs with autoscaling and health checks <img width="1170" height="536" alt="Instances scaling automatically" src="https://github.com/user-attachments/assets/f35fd5df-be32-4d31-b309-19b0e1e95c14" />
3. Set up Load Balancing and certificates(Certificates are mandatory if HTPPS load balancer type is being used. I could not successfuly configure it because of some issues with Cloud DNS so I used HTTP as this is just a lab. In the case of production, HTTPS will always be the choice. Once i figure out the issue i will update my lab.)
4. For HTTPS, configure DNS and A record.
5. Perform load testing and observe behaviour while MIGs scale up and down.

<img width="1119" height="678" alt="Load Balancing" src="https://github.com/user-attachments/assets/fbc2be9f-245c-402d-8de5-68a0419670fc" />
<img width="968" height="838" alt="Hitting LB IP" src="https://github.com/user-attachments/assets/cbecfb15-d81d-41fb-89db-6b084542006f" />



