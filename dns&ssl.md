# CLOUD DNS
# Domain name mapping to IP Address
* Register a new domain for your ip address using any domain name services like [freenom](https://www.freenom.com/en/index.html?lang=en),[godaddy](https://www.google.com/search?ei=jMlaXM21DI78rQH4lKrgCA&q=godaddy+free+trial&oq=godaddy+&gs_l=psy-ab.1.0.35i39l2j0i131i20i263j0i131i67j0i131i20i263j0j0i131j0i67l2j0.6725.6725..8342...0.0..0.69.69.1......0....1..gws-wiz.......0i71.jpM_Z_xCJu8),etc
![image for dns](https://github.com/GitanjaliRavichandran/git/blob/master/Selection_018.png)
* Copy and paste the Name Servers which you obtained from **CLOUD DNS** into the *Use the own DNS* tab
![cloud dns](https://github.com/GitanjaliRavichandran/git/blob/master/Selection_019.png)
* Specify the DNS name that you have owned from the site(freenom) so that it provides the Nameservers that can be added in the *Use the own DNS* tab -All these should be done in the **CREATE ZONE**
* After creating a zone , add the record set by specifing the domain name,Record type(A/AAAA/CNAME),corresponding ipv4 address and then click on SAVE button 
* Test the domain name in the browser(say demo.ml,apache.tk) 
# SUBDOMAIN
* Specify the domain name for your ip(say *apache*.demo.ml)
* Select the CNAME record for creating a subdomain 
* In the Canonical name,mention the domain name(**demo.ml** )
* Finally click on SAVE button
* Test the subdomain name in the browser(say apache.demo.ml)
---
# SSL CERTIFICATION
* You can obtain the SSL Certification either by using [Manual verfication](https://www.sslforfree.com/) or by using the [certbot](https://certbot.eff.org/)
by specifying the Operating System and the Software
![image for ssl](https://github.com/GitanjaliRavichandran/git/blob/master/Selection_020.png)
* Follow the instructions as given in the [website](https://www.sslforfree.com/)
* Finally click on **DOWNLOAD SSL** which will generate the certificate files 
* Copy and paste the certificate files in the following path
> ```/etc/letsencrypt/live/your_domain_name/certificate.pem```
* certificate.pem file should contain both private key and certificate.
*Restart the apache and test the with the following url 
> ```https://your_domain_name```





