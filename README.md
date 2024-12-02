# Keylogger(Malware) And VirusTotal Project


![Keylogger-Software-1400](https://github.com/user-attachments/assets/1426d076-c73f-4cee-bf6c-7af1abf1a6be)




## Introduction

Howdy, and thank you for taking the time to review my Keylogger project. The primary goal of this project is to demonstrate key concepts related to cybersecurity and malware, with a focus on keyloggers. Please note that this project is intended strictly for educational purposes. Any use of malicious software on unauthorized devices or networks is considered a computer crime, so I strongly advise using this project solely for learning purposes.

A keylogger is a type of malicious software that runs on a user's machine to capture and record keystrokes. This software presents significant risks and threats to organizations, as it can lead to data breaches and other security vulnerabilities.

## Project Overview
In this project, I demonstrate the functionality of a keylogger and explain how it operates when executed on a machine using the C# programming language. I also show how, after a certain number of keystrokes, the logged data is sent to my Gmail account. This illustrates the power of keyloggers—if a malicious actor successfully installs one on your machine, they can capture all your keystrokes and send the data to their email. This significantly increases the risk of compromised credentials, which could provide a foothold into a network, leading to potential security breaches and further compromises.

Additionally, I show how to upload a suspicious file or program to VirusTotal, demonstrating how the platform can help identify malicious components within the file. I also explain how users can configure a keylogger to run automatically through Task Manager when the machine starts. Finally, I cover best practices to mitigate the risk of keylogger attacks in your environment.



## KeyLogger C# Code Showcase 
![Screenshot 2024-12-02 000829](https://github.com/user-attachments/assets/0032a777-99f7-418e-a4ef-df12236657c6)

In this part of the C# keylogger project, I’ve set up some key configurations to control how it works. First, I defined the email settings with `FROM_EMAIL_ADDRESS`, `FROM_EMAIL_PASSWORD`, and `TO_EMAIL_ADDRESS`, which are used to send the captured keystrokes to a specific email. The log files are stored at paths defined by `LOG_FILE_NAME` and `ARCHIVE_FILE_NAME`, and I use `INCLUDE_LOG_AS_ATTACHMENT` to decide if the log should be attached to the email. The project sends the logs when they reach `MAX_LOG_LENGTH_BEFORE_SENDING_EMAIL` (300 keystrokes), and `MAX_KEYSTROKES_BEFORE_WRITING_TO_LOG` controls how soon the keystrokes are written to the log file. I’ve also set up a low-level keyboard hook with constants like `WH_KEYBOARD_LL` and `WM_KEYDOWN to capture keystrokes globally. The `hook` and `llkProcedure` variables handle the actual capturing and processing of each keystroke. Lastly, the `buffer` stores the keystrokes temporarily before they’re logged or emailed. These configurations work together to manage logging, email sending, and real-time keystroke capture for the keylogger.
