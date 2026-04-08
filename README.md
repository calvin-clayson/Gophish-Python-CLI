# Gophish-Python-CLI
Welcome to the Gophish-Python-CLI script, created to leverage Gophish's Python API to provide the ability to use Gophish without having to use a GUI.

Getting Started-
Gathering API Key:
As this script leverages Gophish's Python API, it is required that Gophish is available and is able to get the API key that you will need soon.
To find your API key, launch Gophish and access the service through your browser. This will typically require you to enter 127.0.0.1:3333
After logging in with either the default credentials or your custom credentials, head over to account settings on the left-hand tab.
Once there, there is a section called "API Key:", copy the API key as it will be needed.

Creating .env API File:
This script uses a .env file to store the API keys, ensuring that the API key is not hardcoded into the script.
Initially, the script will ask the user if there is a .env file created; if not, the user is instructed to create a .env file and input within the file "GO_PHISH_API_KEY={your API key}"
If the user has already created the .env file, the next question asks the user to paste the file location of the .env file containing the API key.
(There is an option to hardcode the .env file location, allowing the user to skip the need to constantly paste to .env location upon each new startup, be aware of potential security implications.)

Script Functionality-
Menus:
The script is segmented into four menus and one function at the main menu startup.
The four menus are creation, viewing, deleting, and modifying.
The standalone function in the main menu lets you import targets for later use from a CSV file.
If the user ever needs to go back or exit the script, type "0".
If the user needs to see the menu options, type "99".

Importing Targets:
Importing targets is important if the user is planning to create groups within Gophish.
Selecting the import targets option prompts the user to paste the CSV file location.
To successfully use the CSV importing function, CSV files need to be formatted a certain way.

The correct format is that the first row needs to include the following exactly:
"firstname,lastname,email,position"
The subsequent rows will be filled out with target information such as:
"Phshing,Target,victimemail@example.com,testtarget
Example,User,useremail@domain.com,manager"

The script, when importing, does have some error-handling capabilities if the CSV file format is not precise.
Error handling includes attempting to normalize the first row for the keys (meaning if you have more than four attributes in the first row, it will attempt to pull out the necessary ones),
Skipping over rows and not importing the specific target if there is information missing, such as a proper email,
and skipping over rows that have too many attributes than the expected number.

Creation Menu:
Upon launching the creation menu, the user is prompted with multiple options, all used for the main purpose of Gophish: launching a phishing campaign.
The options are as ordered:
Option 1: Create Group in Gophish with imported targets
Option 2: Create Email Template in Gophish
Option 3: Create Landing Page in Gophish
Option 4: Create Sending Profile in Gophish
Option 5: Create Campaign in Gophish
The import target menu is needed in order to create a group in Gophish, as it takes the analysis of the CSV's rows and columns in order to simply gather target information.
To create a campaign, ensure all other functions have been created or are present from previous usage.

Viewing Menu:
The viewing menu allows the user to view multiple different aspects, such as current groups and the information of a group and others, based on user selection
This is also where the user will be allowed to view current campaigns and the status of the campaigns, including information such as who has successfully fallen victim to the phishing attempt
The options are as ordered:
Option 1: View Targets
Option 2: View Groups
Option 3: View Email Templates
Option 4: View Landing Pages
Option 5: View Sending Profiles
Option 6: View Campaigns

Deletion Menu:
The deletion menu allows the user to delete multiple different attributes, such as previous group creations, and more.
The options are as ordered:
Option 1: Delete Group
Option 2: Delete Email Template
Option 3: Delete Landing Page
Option 4: Delete Sending Profile
Option 5: Delete Campaign

Modifying Menu:
The modifying menu allows the user to modify specific sections of previously created attributes, such as altering the group name of a specific group, and more.
There are some issues with certain ways in which Gophish handles file attachments in the email template, so as of now, there is no way to modify attachments within email templates within the script.
The options are as ordered:
Option 1: Modify Group
Option 2: Modify Email Template
Option 3: Modify Landing Page
Option 4: Modify Sending Profile

This is the main portion of the script, and for now, all that is available.
If there are issues with any elements of the script or if it cannot execute properly, please notify me.
