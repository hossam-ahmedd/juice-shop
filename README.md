# juice-shop
Juice-Shop web Pentesting Project
# Juice-Shop Web Penetration Testing Project

In today's digital landscape, web applications are increasingly becoming targets for cyber threats, making security a paramount concern for developers and organizations alike. The Juice Shop project serves as an exemplary platform for understanding and testing web application vulnerabilities in a controlled environment. Designed as an intentionally insecure web application, Juice Shop provides a rich ground for security professionals, developers, and enthusiasts to hone their penetration testing skills.

This project aims to conduct a comprehensive penetration test on the Juice Shop application, identifying potential security weaknesses and vulnerabilities that could be exploited by malicious actors. By simulating real-world attack scenarios, we will explore various aspects of web security, including but not limited to, authentication flaws, cross-site scripting (XSS), SQL injection, and insecure direct object references.

## Objectives

The primary objectives of this penetration testing project are to:

1. **Identify Vulnerabilities**: Systematically assess the Juice Shop application to uncover security flaws that could compromise user data and application integrity.
  
2. **Understand Attack Vectors**: Gain insights into common attack vectors and methodologies used by cybercriminals to exploit web applications.

3. **Enhance Security Awareness**: Provide recommendations and best practices for securing web applications, thereby contributing to the overall improvement of web security.

4. **Hands-On Learning**: Offer a practical learning experience for individuals interested in cybersecurity, allowing them to apply theoretical knowledge in a real-world context.

Through this project, we aim to not only identify and document vulnerabilities but also to foster a deeper understanding of web application security principles. By the end of this penetration testing engagement, participants will be better equipped to recognize and mitigate security risks in their own web applications, ultimately contributing to a safer online environment.
# Ways of Hacking Juice-Shop
# 1- SQL Injection
![Screenshot01](https://github.com/hossam-ahmedd/juice-shop/blob/main/1.png?raw=true)
![Screenshot02](https://github.com/hossam-ahmedd/juice-shop/blob/main/2.png?raw=true)
![Screenshot03](https://github.com/hossam-ahmedd/juice-shop/blob/main/3.png?raw=true)
We started by performing an SQL injection by injecting SQL commands into the login credentials to bypass the authentication process.
## SQL Injection Example

An example of an SQL injection payload is:

```sql
admin' or 1=1;
```
# 2- XSS (HTML Injection)
![Screenshot01](https://github.com/hossam-ahmedd/juice-shop/blob/main/h4.png?raw=true)
![Screenshot02](https://github.com/hossam-ahmedd/juice-shop/blob/main/h5.png?raw=true)
![Screenshot03](https://github.com/hossam-ahmedd/juice-shop/blob/main/h6.png?raw=true)
We tried to perform a cross-site attack through HTML injection by typing HTML code into the search bar, and it was executed successfully!

## HTML Injection Example



An example of an HTML injection payload is:

```html
<iframe src="https://alexu.mans.edu.eg/static/index.html"></iframe>
```
# 3- FTP Server Discovery
![Screenshot01](https://github.com/hossam-ahmedd/juice-shop/blob/main/d7.png?raw=true)
![Screenshot02](https://github.com/hossam-ahmedd/juice-shop/blob/main/d8.png?raw=true)
![Screenshot03](https://github.com/hossam-ahmedd/juice-shop/blob/main/d9.png?raw=true)

We found the FTP server path By dirb tool, which contains many sensitive information and data, such as company secrets and malware files. In addition, we discovered videos of promotions.
```
dirb http://127.0.0.1:42000/
```
# 4- Enumeration to Find Admin Path
![Screenshot01](https://github.com/hossam-ahmedd/juice-shop/blob/main/f9.png?raw=true)
![Screenshot02](https://github.com/hossam-ahmedd/juice-shop/blob/main/f10.png?raw=true)
![Screenshot03](https://github.com/hossam-ahmedd/juice-shop/blob/main/f11.png?raw=true)

In this phase, we used the FFUF tool to identify the admin path for the URL, which performed a brute-force attack and returned all possible paths. Additionally, we inspected the source code of the URL and found the administration path within it.
## FFUF Command
```
fuf -w /usr/share/wordlists/dirb/common.txt -u http://127.0.0.1:42000/#/FUZZ  -c -v
```
