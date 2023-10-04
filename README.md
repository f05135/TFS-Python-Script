# TFS Python Script Documentation

**The TFS Python Script is a tool designed to automate the creation of news articles from Excel sheets using the ChatGPT API. This documentation provides a detailed overview of the project, its components, installation instructions, and how to use the program.**

## Table of Contents

1. [Prerequisites](#1-prerequisites)
2. [Overview of the Folders and Configuration File](#2-overview-of-the-folders-and-configuration-file)
3. [Running the Application](#3-running-the-application)
4. [Using the Application](#4-using-the-application)
5. [Reviewing the Output](#5-reviewing-the-output)

## 1. Prerequisites

Before using the TFS Python Script, make sure you have the following prerequisites in place:

- Python 3.8+ installed on your computer.
- An integrated development environment (IDE) installed on your computer (PyCharm, VS Code, Visual Studio...).
- Valid OpenAI API key.
- The following Python libraries installed: `pip install openai json warnings time re os openpyxl tkinter`

**It's recommended to run the IDE as an Administrator.** *This Python script was built and tested on a Windows 10 machine.*

## 2. Overview of the Folders and Configuration File

The project folder structure is as follows:
- `1 - Config`:  Folder used to store the configuration file `config.json`.
- `2 - Excel To Text`: Folder used to store the separated sheets as text files.
- `3 - ChatGPT Answers`: Output folder for the ChatGPT answers in text files.
- `4 - Upload Files`: Output folder for the final Excel files of each festival article.

In the `config.json` file, located inside `1 - Config` folder, you can change your **OpenAI API key** and the **GPT model** to be used. Modify it as follows:
```
{
    "api_key": "YOUR_API_KEY_HERE",
    "model": "gpt-3.5-turbo"
}
```

## 3. Running the Application

To run the TFS Python Script:
- Unzip the downloaded .ZIP file and save the folder `TFS Python Script` to a location of your choice.
![](https://github.com/f05135/TFS-Python-Script/blob/main/Static%20Media%20Assets/a_unzip_folder_media.gif)
- Open your preferred IDE as administrator.
- Navigate to and select the folder `TFS Python Script`.
![](https://github.com/f05135/TFS-Python-Script/blob/main/Static%20Media%20Assets/b_open_project_folder.gif)
- Select and run the script `main.py`.
![](https://github.com/f05135/TFS-Python-Script/blob/main/Static%20Media%20Assets/c_run_main_media.gif)

## 4. Using the Application

**The application will guide you through the following steps via command lines:**

1. *You will be prompted to select Excel files for sheet separation, it's possible to select multiple files at once. If the file dialog window doesn't appear to you, press `Alt + Tab`, and you'll see the file dialog window.*
2. *Once the Excel files are selected, the process to separate the sheets will automatically begin. Then you will be prompted to press Enter to start the next step. You can press Enter to continue.*
3. *The script will start processing the separated sheets located in the `2 - Excel To Text` folder. This involves using the OpenAI GPT model to generate responses based on the text content.*
4. *After processing, the results will be saved in a text file in the `3 - ChatGPT Answers` folder in a structured manner for use in the next step.*
5. *The script will start creating sheets based on the text files inside the `3 - ChatGPT Answers` folders and save them as an Excel File in the `4 - Upload Files` folder. **All sheets from the same festival will be appended in their individual Excel files.***

## 5. Reviewing the Output

Once the application completes its tasks, you can navigate to the `4 - Upload Files` folder to review the generated Excel files, respectively.

## 6. Good To Know
1. **After successfully finishing a run of the script and seeing the message `---- News Articles generated successfully ----` on the terminal/console, delete or transfer to another location all the folders and files created inside `2 - Excel To Text` and `3 - ChatGPT Answers` before running the script again; otherwise, the script will reprocess all those files again.**.
2. **To avoid losing data in case of insufficient tokens available on the API, it is considered good practice to select up to 10 Excel Files, *or ~50 sheets in total*, to work with per run**.
3. **[Not Recommended] - In case of an interruption in the middle of a run, all the files that were saved in the `3 - ChatGPT Answers` folder can still be used to be appended into the final Excel file once the script is used again. The same applies to the separated text files inside the `2 - Excel to Text` folder.**.
