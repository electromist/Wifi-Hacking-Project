# Wi-Fi Hacking Tools - Networking Project

This repository serves as a comprehensive guide for a networking project involving the ethical use of Wi-Fi hacking tools. Whether you're a cybersecurity enthusiast or a network administrator looking to assess your network's security, this project provides a step-by-step walkthrough to help you understand the process of securing your wireless networks against potential vulnerabilities.

## Table of Contents

- [Project Overview](#project-overview)
- [Prerequisites](#prerequisites)
- [Project Setup](#project-setup)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)
- [Steps](#steps)

## Project Overview

In today's interconnected world, ensuring the security of your wireless networks is of paramount importance. This project aims to empower users with the knowledge and tools necessary to identify and address vulnerabilities in their Wi-Fi networks. It emphasizes ethical and responsible network auditing and penetration testing.

## Prerequisites

Before getting started with this project, you will need the following:

- A compatible Wi-Fi adapter that supports Monitor Mode (e.g., TP-Link AC600).
- A virtual machine setup with Kali Linux for conducting ethical hacking and network auditing.
- A Windows 11 environment for processing captured data and conducting password decryption.

## Project Setup

1. **Kali Linux and Wi-Fi Adapter Setup**: This project assumes you have Kali Linux installed on a virtual machine with your Wi-Fi adapter properly configured to support Monitor Mode.

2. **Installation of WiFite2**: The guide demonstrates how to install WiFite2, a powerful Wi-Fi auditing tool that simplifies the process of capturing network handshakes.

3. **Handshake Capture**: You'll learn how to use WiFite2 to capture Wi-Fi handshakes from target networks.

4. **Password Decryption**: The project guides you through the process of transferring captured data to Windows, using Hashcat to decrypt passwords, and downloading wordlists.

5. **Ethical Use**: The README emphasizes the ethical and responsible use of Wi-Fi hacking tools, reminding users to obtain proper permissions and adhere to legal standards.

## Usage

This project offers a practical, hands-on approach to network security auditing. By following the steps outlined in the guide, users can gain valuable insights into the security of their wireless networks, identify vulnerabilities, and take appropriate measures to secure their networks.

**Disclaimer**: It is essential to use these tools responsibly and only on networks for which you have explicit permission. Unauthorized access to networks is illegal and unethical.
## Steps

1. Open the Kali Linux Terminal.
2. Ensure that you can see the "Wi-Fi symbol" in the top right corner of Kali.
3. Make sure you have installed the specific drivers for your adapter in Kali.
4. Open a second terminal, then type the following command: ```sudo airmon-ng start wlan0``` to change your adapter mode from "Management Mode" to "Monitor Mode."
5. Check if your network in Monitor mode by typing iwconfig.![wlan0](https://github.com/electromist/Wifi-Hacking-Project/assets/101152694/356ab9b9-07c5-44b3-96e4-689d344426df)

6. Create a directory named "tools" using the command ```mkdir tools```.
7. In the "tools" folder, install Wifite2 ([Watch this video for installation](https://www.youtube.com/watch?v=OdFvNLdccWQ)).
8. Run Wifite2 with the command: ```sudo Wifite2.py```.
9. Identify the network you want to attack; once found, press Ctrl+C once.
10. Select the target network number (NUM) you wish to attack. Example: I choose 1 for GalaxyA735GCDAD. ![deauth](https://github.com/electromist/Wifi-Hacking-Project/assets/101152694/5a2bf9d4-0442-4e76-aa3c-e3993b13c86a)


11. Skip (by using Ctrl+C and "c" to continue) to the Deauthentication Attack,(watch the video in Step 7 if you face any trouble).
12. Once the handshake is captured, it will stop automatically.
13. In the terminal, type ```cd hs``` to navigate to the handshake file.
14. You will see a file with a name like "handshake_GalaxyA735GCDAD_8E-0E-CC-6B-9D-C4_2023-11-08T14-19-38.cap." Ensure it has a .cap extension.
15. Transfer the .cap file from Kali to Windows.
16. Go to [https://hashcat.net/](https://hashcat.net/) in your browser and select "Convert."
17. Choose the .cap file you transferred from Kali by clicking the "Browse" button, and then press the "Convert" button.
18. You will be redirected to a conversion page to download the .hc22000 file.
19. Rename it as "hdsk.hc22000" while downloading (References: https://www.youtube.com/watch?v=tjuTNHJJuUQ).
20. Now, visit [https://hashcat.net/hashcat/](https://hashcat.net/hashcat/) and download the latest version of Hashcat.
21. Extract the Hashcat folder.
22. Download a rockyou.txt wordlist from Github ([Download rockyou.txt](https://github.com/brannondorsey/naive-hashcat/releases/download/data/rockyou.txt)). You can choose any other wordlist if you prefer.
23. Move the "hdsk.hc22000" and "rockyou.txt" files to the extracted Hashcat folder.
24. Open the Command Prompt in Administrator Mode and change the directory to the extracted Hashcat folder using the ```cd``` command. For example: ```cd C:\Users\elect\Desktop\hashcat-6.2.6```
25. Type the following command: "hashcat -m 22000 -a 0 hdsk.hc22000 rockyou.txt ( References: https://www.youtube.com/watch?v=KLry7bf51QQ )."
26. Initialization may take a few minutes.
27. Hashcat will start a Dictionary Attack, and in a few minutes, it will decode the password. Example: My wifi password was "crocodile" which was decoded as shown in this screenshot: ![Screenshot (1)](https://github.com/electromist/Wifi-Hacking-Project/assets/101152694/dd1eff7b-4bc8-48fd-8f56-376dcffb3292)


## Contributing

Contributions to this project are welcome. If you have suggestions for improvements, feature requests, or wish to report issues, please feel free to create an issue or submit a pull request.

## License

This project is licensed under the [MIT License](LICENSE), which allows for open collaboration and the responsible use of the provided tools and information.

---

Feel free to customize this README description to fit your project's specific details and goals.
