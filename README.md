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

### Windows Domain Controller

<img width="502" height="435" alt="Screenshot (256)" src="https://github.com/user-attachments/assets/d027721d-e7e6-4301-a69d-6c42855e1273" />


### Windows Test Machine

<img width="483" height="431" alt="Screenshot (257)" src="https://github.com/user-attachments/assets/1ff24d02-8c91-46ce-8f95-a9664b3c1db5" />


### Ubuntu

<img width="616" height="383" alt="Screenshot (255)" src="https://github.com/user-attachments/assets/b30d91e4-47bc-47ae-97b6-1454ffd94ad8" />


### Kali

<img width="522" height="199" alt="Screenshot (258)" src="https://github.com/user-attachments/assets/2117973e-8830-488a-b063-58f174fac1cd" />

## Part 2: Active Directory Deployment

<img width="1920" height="838" alt="Screenshot (66)" src="https://github.com/user-attachments/assets/7d38fdeb-64dc-4dd2-b7e1-97ac9ae37cdd" />
<img width="1916" height="769" alt="Screenshot (68)" src="https://github.com/user-attachments/assets/e9941810-bb25-48b6-b76f-2dbd5878e1df" />
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

##Part 4: Detection Engineering
##Part 5: SOAR Automation
