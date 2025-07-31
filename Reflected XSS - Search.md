## Vulnerability Description

Reflected Cross-Site Scripting (XSS) vulnerability was found in the `/patient-report.php` page of the PHPGurukul User HMPV-Testing-Management-System-PHP.2. This vulnerability allows remote attackers to execute arbitrary scripts via the `searchdata` parameter in a POST HTTP request.

| **Field**                        | **Details**                                                                                                                                                                                          |
| -------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Affected Vendor**              | [PHPGurukul](https://phpgurukul.com/)                                                                                                                                                                |
| **Affected Product Name**        | HMPV-Testing-Management-System-PHP panel                                                                                                                                                             |
| **Product Official Website URL** | [https://phpgurukul.com/human-metapneumovirus-hmpv-testing-management-system-using-php-and-mysql/](https://phpgurukul.com/human-metapneumovirus-hmpv-testing-management-system-using-php-and-mysql/) |
| **Affected Components**          | - **Version:** - v.1 <br>- **Affected Code File:** /admin/patient-report.php <br>- **Affected Parameter:** searchdata<br>- **Method:** POST                                                          |

## Steps to Reproduce:

**Step 1**: Click on Adming login
![image](https://github.com/T0xIN19/CVES-POC/blob/main/1.png)

**Step 2:** Provide Admin credential to login
![image](https://github.com/T0xIN19/CVES-POC/blob/main/2.png)

**Step 3:** Go to /patient-report.php & got for searchdata, provide values `1234gybj9%3cscript%3ealert(1)%3c%2fscript%3eg` and enable burpsuite to confirm the parameter.
![image](https://github.com/T0xIN19/CVES-POC/blob/main/2.png)

**Step 4:** Just notice that payload is `searchdata` parameter, Now right click on request & go fot show in broweser

![image](https://github.com/T0xIN19/CVES-POC/blob/main/3.png)

**Step 5:** Copy that payload & paste in chromium or borwser.

![image](https://github.com/T0xIN19/CVES-POC/blob/main/4.png)

**Step 6:** As hit enter will see Payload is executed with popup.

![image](https://github.com/T0xIN19/CVES-POC/blob/main/poc_xss.png)

## Mitigation/recommendations

- https://portswigger.net/web-security/cross-site-scripting
- https://cheatsheetseries.owasp.org/cheatsheets/Cross_Site_Scripting_Prevention_Cheat_Sheet.html
