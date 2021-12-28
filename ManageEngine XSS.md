## Stored Cross Site Scripting in ManageEngine ServiceDesk Plus ###


**Description:**
In ManageEngine ServiceDesk Plus, an admin privileged user can manage other users. While creating new or editing existing users, we can see "Secondary Email" field. The input field was found validating email TLD section nicely but it was found that it also renders HTML tags. As a result it was possible to execute injected JavaScript as well. ManageEngine team fixed the issue and assigned ZVE-2021-3102 to track the vulnerability.

**Vulnerable Product Version:**
11.3 Build 11306

**Fixed Product Version:**
12001

**Steps to reproduce:**
1. As we can see how the given tags were treated 
![HTML Render](https://github.com/corrupted-brain/Findings/blob/main/step1.png)

2. Then I used the payload as ```<script>alert(1)</script>@example.com```, and saved the email address. The injected code is executed as JavaScript popup.
 ![XSS popup](https://github.com/corrupted-brain/Findings/blob/main/step2.png)

Later the issue has been patched by the ManageEngine with the update ID [SD-98506](https://www.manageengine.com/products/service-desk/on-premises/readme.html)
