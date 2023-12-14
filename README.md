<h2> DNS-spoofing </h2>
fack Facebook login page and DNS demo

<h2>Setup</h2>
Kali 

```
cd site
cp * /var/www/html/
cd /var/www/html/
mkdir data
cd data
touch usernames.txt  
cd ..
chmod -R 777 .     
cd ~
service apache2 start
tail -f /var/www/html/data/usernames.txt    
```

<h2>Open browser</h2>
accessing 127.0.0.1 on the browser

![kali](https://github.com/Tugce41/phishing_for_dns/assets/106156890/30f9f286-84a6-4ff7-a137-1867cf910ea4)


<h2> configurations</h2>

```
vim /etc/ettercap/etter.conf 
```

![kali2](https://github.com/Tugce41/phishing_for_dns/assets/106156890/9582d77e-c437-423a-967c-7fa27ba1fa1b)
######

```
vim /etc/ettercap/etter.dns
```
facebook target list
![kali3](https://github.com/Tugce41/phishing_for_dns/assets/106156890/85c96289-d78f-4359-8156-c28b995a82c8)


ettercap DNS spoofing
```
ettercap -G
```
<li>stop unified sniffing</li>
<li>scan the hosts</li>
<li>add the victims' ip address to target 1</li>
<li>start MITM attacks: ARP poisoning</li>
<li>enable dns_spoof plugin</li>



![kali4](https://github.com/Tugce41/phishing_for_dns/assets/106156890/5f0e589d-6ee8-4ab5-933e-2e626c233c5d)
<li>start unified sniffing</li>


<h2> spoofed </h2>

<li>open cmd</li>

```
nslookup facebook.com
ping facebook.com
```



<li> the ip address of facebook.com becomes 10.0.2.4</li>
<li>>open the browser in private mode and access facebook.com
login!</li
<li>the account and password are shown on ettercap and usernames.txt</li>

<h2>Reference</h2>
<li>https://www.kalilinux.in/2019/07/ettercap-dns-spoofing-in-kali-linux.html</li>
<li>https://www.youtube.com/watch?v=4i7kc8cY654</li>
