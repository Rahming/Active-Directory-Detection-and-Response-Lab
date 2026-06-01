# Active-Directory-Lab

## Objective
Build an enterprise-style security monitoring environment capable of:

-Centralized log collection
-Active Directory monitoring
-Detection of unauthorized RDP access
-Automated alert enrichment
-Automated notification through SOAR

### Skills Learned
- 
- 
- 
- 
- 

### Tools Used

- VMware Workstation
- Splunk
- Slack
- Shuffle
- Draw.io
### MITRE ATT&CK Techniques
-
-
## Part 1: Environment Build
I used draw.io to make a diagram to logically map out the lab. 
<img width="2249" height="857" alt="Untitled" src="https://github.com/user-attachments/assets/d58f4c89-0911-46bc-965c-f9b2edffbda5" />
I Made 4 Virtual machines using VMWARE. After I downloaded them I made sure they could communicate
| System         | Purpose           | IP              |
| -------------- | ----------------- | --------------- |
| Windows Server | Domain Controller | 192.168.112.128 |
| Windows Server | Test Machine      | 192.168.112.129 |
| Ubuntu         | Splunk            | 192.168.112.131 |
| Kali           | RDP(Testmachine)  | 192.168.112.132 |


### Windows Test Machine

<img width="451" height="645" alt="Screenshot (273)" src="https://github.com/user-attachments/assets/e274a3be-6de0-46f5-aabe-3595f7e47844" />


## Part 2: Active Directory Deployment

<img width="1915" height="759" alt="Screenshot (71)" src="https://github.com/user-attachments/assets/6f8a1710-d9d9-416c-9c93-6439227ba8ec" />
<img width="1919" height="704" alt="Screenshot (73)" src="https://github.com/user-attachments/assets/184c923f-b535-4a7c-9c9f-9b3d8b1cdf0f" />
<img width="1917" height="752" alt="Screenshot (76)" src="https://github.com/user-attachments/assets/b27ae57d-6bb5-4e8b-a904-9c7ecf888875" />
<img width="1890" height="874" alt="Screenshot (78)" src="https://github.com/user-attachments/assets/9c6ba94c-b086-4688-b10a-d789e9d90d77" />


## Part 3: Splunk Deployment

<img width="1270" height="432" alt="Screenshot (82)" src="https://github.com/user-attachments/assets/0f5da368-d3b7-4e77-bae3-8718177ad019" />
<img width="1575" height="958" alt="Screenshot (144)" src="https://github.com/user-attachments/assets/3de0257d-bd2e-4b2a-8b85-7d627d210531" />
<img width="1119" height="523" alt="Screenshot (147)" src="https://github.com/user-attachments/assets/798be549-0fa7-4e0c-a6b9-837040ed9ee2" />
<img width="769" height="342" alt="Screenshot (150)" src="https://github.com/user-attachments/assets/7c5ce2cc-12eb-429c-8636-c95a992a26c4" />
<img width="491" height="61" alt="Screenshot (151)" src="https://github.com/user-attachments/assets/3917f391-2f4b-4107-898f-1e270171affb" />
<img width="1000" height="855" alt="Screenshot (159)" src="https://github.com/user-attachments/assets/be0ce8c3-3836-4a4c-b3b2-dd8b7a501cb5" />


## Part 4: Detection Engineering

<img width="1082" height="781" alt="Screenshot (171)" src="https://github.com/user-attachments/assets/d0f7300c-e7e8-421b-b586-53eb768ce1ff" />
<img width="1561" height="812" alt="Screenshot (169)" src="https://github.com/user-attachments/assets/bb05db48-47b3-4320-9dcd-0f1782b43e11" />
<img width="1028" height="936" alt="Screenshot (170)" src="https://github.com/user-attachments/assets/9fdd2e25-723d-4d02-8a27-305a7144695e" />
<img width="1585" height="171" alt="Screenshot (259)" src="https://github.com/user-attachments/assets/ad767525-901f-413f-b802-4667b6da2893" />


## Part 5: SOAR Automation

<img width="790" height="332" alt="Screenshot (175)" src="https://github.com/user-attachments/assets/4509ccbc-f3d9-489f-9faf-6cfc9e2cbdc1" />
<img width="2102" height="1330" alt="Screenshot (211)" src="https://github.com/user-attachments/assets/745d5705-a756-4d92-93e8-5aa1f2e30217" />
<img width="1295" height="852" alt="Screenshot (227)" src="https://github.com/user-attachments/assets/a5db18cb-acb3-4240-a5a8-68091f37f65c" />
<img width="1430" height="533" alt="Screenshot (252)" src="https://github.com/user-attachments/assets/4313c9f9-36b2-46e5-a1fc-6507bce0dfc4" />
<img width="1989" height="306" alt="Screenshot (246)" src="https://github.com/user-attachments/assets/25882c05-53bc-429a-adf8-d8568be101f4" />
<img width="1879" height="178" alt="Screenshot (245)" src="https://github.com/user-attachments/assets/4b1a383f-2bec-40ff-92a5-2b06e0a3fad8" />
<img width="1450" height="795" alt="Screenshot (251)" src="https://github.com/user-attachments/assets/d82b329e-9b41-491c-a892-ff48289b0d3f" />
<img width="1822" height="594" alt="Screenshot (250)" src="https://github.com/user-attachments/assets/35ed6654-2956-4818-b729-9a0384be71b8" />
<img width="1242" height="858" alt="Screenshot (248)" src="https://github.com/user-attachments/assets/6708dd2b-c734-4233-96ca-a90bd4b54109" />
<img width="768" height="127" alt="Screenshot (247)" src="https://github.com/user-attachments/assets/57f4c371-e586-49da-9eb7-c20cef588b8f" />


