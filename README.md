# Windows-basic-commands-batchscript
Ex08-Windows-basic-commands-batchscript

# AIM:
To execute Windows basic commands and batch scripting

# DESIGN STEPS:

### Step 1:

Navigate to any Windows environment installed on the system or installed inside a virtual environment like virtual box/vmware 

### Step 2:

Write the Windows commands / batch file . Save each script in a file with a .bat extension. Ensure you have the necessary permissions to perform the operations. Adapt paths as needed based on your system configuration.
### Step 3:

Execute the necessary commands/batch file for the desired output. 




# WINDOWS COMMANDS:
## Exercise 1: Basic Directory and File Operations
Create a directory named "my-folder"
<img width="753" height="46" alt="image" src="https://github.com/user-attachments/assets/88f87201-1876-4bc5-a5c7-1760061e2443" />


## COMMAND AND OUTPUT

Remove the directory "my-folder"
<img width="806" height="41" alt="image" src="https://github.com/user-attachments/assets/69213a08-aab1-4228-aad4-d2b91adc99b4" />

## COMMAND AND OUTPUT


Create the file Rose.txt
<img width="817" height="55" alt="image" src="https://github.com/user-attachments/assets/6615b7b1-8902-4c1d-bc84-11259eed97ee" />

## COMMAND AND OUTPUT


Create the file hello.txt using echo and redirection
<img width="891" height="51" alt="image" src="https://github.com/user-attachments/assets/1121efbe-4796-4993-bc5b-7212efc9e7d8" />

## COMMAND AND OUTPUT

Copy the file hello.txt into the file hello1.txt
<img width="880" height="77" alt="image" src="https://github.com/user-attachments/assets/1ebb8956-b159-4390-b252-1419b6824cf3" />

## COMMAND AND OUTPUT

Remove the file hello1.txt
<img width="782" height="62" alt="image" src="https://github.com/user-attachments/assets/da655304-6df8-48cd-8ec6-9b80b47e9266" />

## COMMAND AND OUTPUT

List out the file hello1.txt in the current directory
<img width="819" height="96" alt="image" src="https://github.com/user-attachments/assets/8af5daef-eebb-44b5-82be-c13287e7dcbb" />

## COMMAND AND OUTPUT

List out all the associated file extensions 
<img width="684" height="918" alt="image" src="https://github.com/user-attachments/assets/2d4651eb-415f-4b38-968a-7beefb45686a" />
<img width="705" height="962" alt="image" src="https://github.com/user-attachments/assets/8183d019-970e-41ef-93d9-4c87850f5241" />

<img width="604" height="968" alt="image" src="https://github.com/user-attachments/assets/f082754b-298d-4511-b1b7-0b57e0ea1b9d" />

<img width="706" height="947" alt="image" src="https://github.com/user-attachments/assets/fd25181e-9ca3-4b96-8c0e-ad2ee6df0422" />
<img width="664" height="942" alt="image" src="https://github.com/user-attachments/assets/7f8c304c-da2f-46db-aaa5-7a828b7f8c57" />
<img width="586" height="945" alt="image" src="https://github.com/user-attachments/assets/0f77bade-e2a6-4787-9428-c46b84cdbfee" />

## COMMAND AND OUTPUT


Compare the file hello.txt and rose.txt
<img width="894" height="147" alt="image" src="https://github.com/user-attachments/assets/d59835e4-f273-4e7f-abf0-ce6439a9a88f" />

## COMMAND AND OUTPUT

## Exercise 2: Advanced Batch Scripting
Create a batch file named on the desktop. The batch file need to have a variable assigned with a desired name for ex. name="John" and display as "Hello, John".
```
@echo off
set name=John
echo Hello, %name%
pause
```




## OUTPUT

<img width="819" height="115" alt="image" src="https://github.com/user-attachments/assets/bf2c792a-5b16-458e-acc7-d2ca43894421" />


Create a batch file  on the desktop that checks whether a user-input number is odd or not. The script should:
Prompt the user to enter a number.
Calculate the remainder when the number is divided by 2.
Display whether the number is odd or not.
Ask the user if they want to check another number.
Repeat the process if the user enters Y, and exit with a thank-you message if the user enters N.
Handle invalid inputs for the continuation prompt (Y/N) gracefully.
```
@echo off
:loop
set /p num=Enter a number: 
set /a rem=%num% %% 2

if %rem%==0 (
    echo %num% is Even
) else (
    echo %num% is Odd
)

:ask
set /p ans=Do you want to check another number? (Y/N): 
if /I "%ans%"=="Y" goto loop
if /I "%ans%"=="N" goto end
echo Invalid input. Please enter Y or N.
goto ask

:end
echo Thank you!
pause
```


## OUTPUT
<img width="791" height="232" alt="image" src="https://github.com/user-attachments/assets/d68a08ec-9e7a-4ff4-a037-f09a063c510c" />




Write a batch file that uses a FOR loop to iterate over a sequence of numbers (1 to 5) and displays each number with the label Number:. The output should pause at the end.

```
@echo off
for /L %%i in (1,1,5) do (
    echo Number: %%i
)
pause
```


## OUTPUT

<img width="823" height="183" alt="image" src="https://github.com/user-attachments/assets/977c3350-a6f0-496f-b01d-64803a48d50e" />



Write a batch script to check whether a file named sample.txt exists in the current directory. If the file exists, display the message sample.txt exists. Otherwise, display sample.txt does not exist. Pause the script at the end to view the result.

Instructions:
Use the IF EXIST conditional statement.
Make sure the script works for files located in the same directory as the batch file.
Use pause to keep the command window open after displaying the message.
Expected Output (if the file exists):
```
@echo off
if exist sample.txt (
    echo sample.txt exists.
) else (
    echo sample.txt does not exist.
)
pause
```

## OUTPUT

<img width="765" height="91" alt="image" src="https://github.com/user-attachments/assets/5bcd4a27-454f-4157-b775-9ee2a95ed28b" />

Write a batch script that displays a simple menu with three options:
Say Hello – Displays the message Hello, World!
Create a File – Creates a file named newfile.txt with the content This is a new file
Exit – Exits the script with a goodbye message
The script should repeatedly display the menu until the user chooses to exit. Use goto statements to handle menu navigation.
```
@echo off
:menu
cls
echo 1. Say Hello
echo 2. Create a File
echo 3. Exit
set /p choice=Choose an option (1-3): 

if "%choice%"=="1" goto hello
if "%choice%"=="2" goto create
if "%choice%"=="3" goto exit
echo Invalid choice.
pause
goto menu

:hello
echo Hello, World!
pause
goto menu

:create
echo This is a new file > newfile.txt
echo File newfile.txt created.
pause
goto menu

:exit
echo Goodbye!
pause
exit
```

## OUTPUT

<img width="532" height="189" alt="image" src="https://github.com/user-attachments/assets/4e0e044e-1f4c-47ad-8bb0-9ebb91977b9b" />

<img width="568" height="228" alt="image" src="https://github.com/user-attachments/assets/8fe05272-f0b2-4b35-a088-841d23ebd82a" />

<img width="597" height="250" alt="image" src="https://github.com/user-attachments/assets/f0adb05f-2be8-4d42-a5b7-1502297753c6" />

# RESULT:
The commands/batch files are executed successfully.

