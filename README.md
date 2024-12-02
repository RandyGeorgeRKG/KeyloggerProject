# Keylogger(Malware) And VirusTotal Project


![Keylogger-Software-1400](https://github.com/user-attachments/assets/1426d076-c73f-4cee-bf6c-7af1abf1a6be)




## Introduction

Howdy, and thank you for taking the time to review my Keylogger project. The primary goal of this project is to demonstrate key concepts related to cybersecurity and malware, with a focus on keyloggers. Please note that this project is intended strictly for educational purposes. Any use of malicious software on unauthorized devices or networks is considered a computer crime, so I strongly advise using this project solely for learning purposes.

A keylogger is a type of malicious software that runs on a user's machine to capture and record keystrokes. This software presents significant risks and threats to organizations, as it can lead to data breaches and other security vulnerabilities.

## Project Overview
In this project, I demonstrate the functionality of a keylogger and explain how it operates when executed on a machine using the C# programming language. I also show how, after a certain number of keystrokes, the logged data is sent to my Gmail account. This illustrates the power of keyloggers—if a malicious actor successfully installs one on your machine, they can capture all your keystrokes and send the data to their email. This significantly increases the risk of compromised credentials, which could provide a foothold into a network, leading to potential security breaches and further compromises.

Additionally, I show how to upload a suspicious file or program to VirusTotal, demonstrating how the platform can help identify malicious components within the file. I also explain how users can configure a keylogger to run automatically through Task Scheduler when the machine starts. Finally, I cover best practices to mitigate the risk of keylogger attacks in your environment.



## KeyLogger C# Code Showcase 

In this part of the C# keylogger program, I’ve set up some key configurations to control how it works. First, I defined the email settings with `FROM_EMAIL_ADDRESS`, `FROM_EMAIL_PASSWORD`, and `TO_EMAIL_ADDRESS`, which are used to send the captured keystrokes to a specific email. The log files are stored at paths defined by `LOG_FILE_NAME` and `ARCHIVE_FILE_NAME`, and I use `INCLUDE_LOG_AS_ATTACHMENT` to decide if the log should be attached to the email. The project sends the logs when they reach `MAX_LOG_LENGTH_BEFORE_SENDING_EMAIL` (300 keystrokes), and `MAX_KEYSTROKES_BEFORE_WRITING_TO_LOG` controls how soon the keystrokes are written to the log file. I’ve also set up a low-level keyboard hook with constants like `WH_KEYBOARD_LL` and `WM_KEYDOWN to capture keystrokes globally. The `hook` and `llkProcedure` variables handle the actual capturing and processing of each keystroke. Lastly, the `buffer` stores the keystrokes temporarily before they’re logged or emailed. These configurations work together to manage logging, email sending, and real-time keystroke capture for the keylogger.

![Screenshot 2024-12-02 000829](https://github.com/user-attachments/assets/0032a777-99f7-418e-a4ef-df12236657c6)



## KeyLogger In Action
In this part of the project, I demonstrate how the C# program creates a separate window using Visual Studio Community Edition. Additionally, I show how every keystroke made on the machine is recorded in real-time, and the logs are subsequently sent to my email address.


![Screenshot 2024-12-02 001809](https://github.com/user-attachments/assets/2a3d22ad-50e2-458b-8c81-af322a0e902c)
![Mail ](https://github.com/user-attachments/assets/c9ba1c6c-aebf-4ac5-a0ad-123c113776c2)



## Maintaing Persistence with a Keylogger 

In this section, I demonstrate how a keylogger can maintain persistence on a machine without the user’s knowledge. Following the Cyber Kill Chain model, the "Delivery" phase is where the malware is introduced to the system. This could happen if a threat actor plugs in a USB drive containing the malicious file or sends a convincing phishing email. Once executed, the malware could leverage the Installation phase, where it establishes persistence via the Task Scheduler. The attacker would create a new task, set it to trigger at user logon, and select the malicious program to run automatically. When the user logs in, the keylogger silently captures keystrokes and sends the data back to the attacker’s email, all without the user’s awareness. This demonstrates the significant danger posed by keyloggers, as they can remain undetected and continue to exfiltrate data.

![At Log on ](https://github.com/user-attachments/assets/37d2515f-3012-42a6-826c-a9d5c0bfdfaf)
![Select the file ](https://github.com/user-attachments/assets/605c1785-0122-4929-8ee8-dcf10ed05f04)



