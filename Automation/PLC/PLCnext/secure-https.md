# HTTPS Certificates for PLCnext
Cybersecurity is a fundamental part of the PLCnext product design. This guide will show how to create and save the HTTPS certificate so that connections to the web-based manager, WBM etc. are secure.

Follow these steps to configure:
1. Go to the WBM
2. Navigate to _Configuration > Web Services_
3. Click on _Re-generate HTTPS certificate_. Note that if IP address is changed, this process will need to be repeated.
4. __Click _Apply____
5. Navigate to _Security > Certificate Authentication_
6. Click on the tab _Identity Stores_
7. Click on the certificate download button

![image](https://github.com/user-attachments/assets/8135444d-d97c-4823-86dd-ca5b06ce0fa5)

8. Navigate to the certificate settings. For browsers, you can usually search for it in the settings. It will open a popup.

![image](https://github.com/user-attachments/assets/09c9794a-935a-47e7-8769-368a8e508264)

9. Click on the tab _Trusted Root Certificates_
10. Click on _Import_
11. Click _Next_
12. Browse to the file and click next.

![image](https://github.com/user-attachments/assets/cfc1f0a0-96d1-4d09-b342-913b1699bfaf)

13. Click _Next_

![image](https://github.com/user-attachments/assets/6f5bd5af-16dd-4a88-8c07-6b35d6929073)

14. Click _Finish_
15. You should receive another popup with a warning. Click _Yes_ if you agree
16. Close the popup. For browsers, it will also need to be restarted.
17. Now the HTTPS connections will be trusted.

![image](https://github.com/user-attachments/assets/9228b6bf-690c-43b1-aeb2-c278ab1833d0)
