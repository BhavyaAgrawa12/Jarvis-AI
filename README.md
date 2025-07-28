Jarvis - A Python Voice Assistant
This project is a simple yet powerful voice-controlled virtual assistant named Jarvis, built using Python. It can perform a variety of tasks on your Windows computer based on your voice commands.

Features 🚀
Jarvis can understand your voice commands to perform tasks like:

Web Searches: Search Wikipedia or Google for any query.

Open Applications: Launch VS Code, Google Chrome, Command Prompt, and specific local folders.

Web Automation: Open YouTube, Google News, WhatsApp Web, and specific Google Meet links.

System Control: Adjust system volume, shut down, or restart the computer.

Browser Control: Manage Chrome tabs, open new windows (including incognito), and clear Browse data using keyboard shortcuts.

Communication: Send WhatsApp messages and emails.

Utilities: Tell you the current time, your public IP address, or a random joke.

Conversation: Responds to basic greetings and questions about itself.

Prerequisites
Before you begin, ensure you have the following installed and configured:

Python 3.7+: Download from python.org.

A Microphone: Required for voice command input.

Windows OS: The script uses the sapi5 voice engine and Windows-specific commands (os.startfile, taskkill), so it's designed for Windows.

Google Account for Email: To use the email sending feature, you need a Gmail account with an App Password.

Important: Google has deprecated "Less secure app access." You must generate an App Password. To do this, enable 2-Step Verification on your Google Account, then go to App Passwords to create one for this application.

🛠️ Installation & Setup
Follow these steps to get Jarvis up and running on your machine.

1. Get the Code
First, save the Python code into a file named jarvis.py (or any other name you prefer).

2. Install Required Libraries
Open your terminal or Command Prompt and install all the necessary Python libraries by running the following command:

Bash

pip install flask pywhatkit pyttsx3 SpeechRecognition wikipedia-api pyautogui requests
Note: The SpeechRecognition library requires the PyAudio package to access the microphone. If you encounter issues, you may need to install it separately:
pip install PyAudio

3. Configure the Script
You must modify a few hardcoded values in the jarvis.py file to match your system and accounts.

Email Credentials:
In the sendEmail function, replace the placeholder email and app password with your own.

Python

# Find this line
server.login('jarvis787834@gmail.com', 'ooim pawb pfqw cyfw')

# And change it to your credentials
server.login('your-email@gmail.com', 'your-16-digit-app-password')
Application Paths:
The paths to open VS Code, Chrome, and other local folders are hardcoded. Update them to match the locations on your PC.

Python

# Example for VS Code
vs_code_path = "C:\\Users\\YourUsername\\AppData\\Local\\Programs\\Microsoft VS Code\\Code.exe"

# Example for Chrome
open_chrome_path ='C:\\Program Files\\Google\\Chrome\\Application\\chrome.exe'

# Example for a custom folder
open_lab_code = "D:\\YourFolder\\Path"
WhatsApp Number:
In the main loop, change the phone number in the send message command to your desired recipient. Remember to include the country code.

Python

if 'send message' in query:
    speak("Your Message is Going Sir Please wait")
    # Change the phone number below
    kit.sendwhatmsg_instantly("+91xxxxxxxxxx", "Hello, BIRO")
▶️ How to Run
Open a terminal or Command Prompt.

Navigate to the directory where you saved jarvis.py.

Run the script using Python:

Bash

python jarvis.py
Jarvis will greet you ("Good Morning!", etc.) and then start listening for your commands. The console will display "Listening...".

To stop the assistant, simply say "exit" or close the terminal window.

Voice Commands
Here is a list of commands you can use. Just say the keyword to trigger the action.

Command	Action

search [your query]	Searches Google for your query.

[your query] wikipedia	Searches Wikipedia and reads a 2-sentence summary.

open youtube	Asks what you want to watch and opens it on YouTube
.
send message	Instantly sends a predefined WhatsApp message to a predefined number.

open google	Opens google.com.

open vs code / open chrome	Opens the specified application.

open lab code	Opens your custom folder.

what is the time	Tells you the current time in 12-hour format.

what is my ip address	Tells you your public IP address.

tell me a joke	Tells a random programming joke.

volume up / volume down	Increases or decreases the system volume.

maximize this window	Maximizes the currently active window.

minimise this window	Minimizes the currently active window.

next tab / previous tab	Switches between browser tabs.

close tab / close window	Closes the current browser tab or window.

shut down the system	Shuts down the computer after a 5-second delay.

restart the system	Restarts the computer after a 5-second delay.

email to me	Asks for the email content, then for the recipient's address, and sends it.

who are you / who created you	Provides information about itself.

exit	Stops the assistant and terminates the script.
