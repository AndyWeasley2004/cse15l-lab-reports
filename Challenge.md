# Lab Report4--Challenge

### Step 1-log in

Command Used:
```
Keys pressed: <Ctrl+r> (Ctrl+R can search commands in my command history)
typed: "ss" (The key word for ssh log in command is ss)
Keys pressed: <enter> (Run the command)
```
Before press `<enter>`:

<img width="446" alt="Screenshot 2023-02-23 at 4 01 16 PM" src="https://user-images.githubusercontent.com/110661816/221058844-2f814c5e-3261-4f75-931a-ce40681c262e.png">

After press `<enter>`:

<img width="784" alt="Screenshot 2023-02-23 at 4 02 42 PM" src="https://user-images.githubusercontent.com/110661816/221059052-c26705a9-5800-4bd8-96c0-4d87a13dd356.png">

### Step 2-Clone Repository

Command Used:
```
Keys pressed: <Ctrl+r> (Ctrl+R can search commands in my command history)
typed: "clo" (When we search "clo", we can get git clone command)
Keys pressed: <enter> (Run the command)
```

Before press `<enter>`:

<img width="567" alt="Screenshot 2023-02-23 at 4 06 27 PM" src="https://user-images.githubusercontent.com/110661816/221059457-4b77bd6e-1b25-409a-8023-91eac205c6d3.png">

After press `<enter>`:

<img width="638" alt="Screenshot 2023-02-23 at 4 06 55 PM" src="https://user-images.githubusercontent.com/110661816/221059499-6a23ffac-83c6-4eb2-84bf-da0e31c15dfe.png">

### Step 3-Run the Tests

Command Used:
```
cd lab7
Keys pressed: <Ctrl+r> (Ctrl+R can search commands in my command history)
typed: "javac" (When I search "javac", I can get the command that compile the tester)
Keys pressed: <enter> (Run the command)
Keys pressed: <Ctrl+r> (Search again)
typed: "ru" (There are so many java commands, so I tries to search "runner" in tester,
        and when I typed "ru", I get the right command)
Keys pressed: <enter> (Run)
```
Compile Input:

<img width="719" alt="Screenshot 2023-02-23 at 4 12 06 PM" src="https://user-images.githubusercontent.com/110661816/221060161-cadf719b-a257-480c-8dbc-8ec5185c1cf3.png">

Run Input:

<img width="932" alt="Screenshot 2023-02-23 at 4 12 50 PM" src="https://user-images.githubusercontent.com/110661816/221060247-97fba9b3-0d9a-4d09-bcb5-4cd39d1cc374.png">

Result:

<img width="966" alt="Screenshot 2023-02-23 at 4 13 38 PM" src="https://user-images.githubusercontent.com/110661816/221060342-cdb06e2e-1fe6-405b-850e-ceb1e6866ce6.png">

### Step 4-Editing the File

Commands Used:
```
nano L<Tab> (autocomplete the file name)
type: "java" (It only complete ListExample.)
Press: <enter> (Run)
Pressing: <Ctrl+W> (Search in the nano editor)
type：“1” (Since we want to reach "index1" and edit the "1")
Press:<enter> (search the first "1")
Repeat <Ctrl+W>+<1>+<enter> (search for the next "1") until 
        we reach the "index1" in the line sixth row from the bottom
Press: <backspace> to delete "1"
Press: <2> to complete the correct variable name, "index2"
Press: <Ctrl+O> (save the edition we made and exit the editing mode)
Press: <enter> (Run the <Ctrl+O> command)
Press: <Ctrl+X> (exit nano editor)
```
The result is like this:

<img width="913" alt="Screenshot 2023-02-23 at 5 02 00 PM" src="https://user-images.githubusercontent.com/110661816/221066295-91a0383d-c6a1-409b-b2a2-9f48a6e9cfb0.png">

After we exit the editing:

<img width="435" alt="Screenshot 2023-02-23 at 5 02 35 PM" src="https://user-images.githubusercontent.com/110661816/221066381-580da27c-7c52-4cf8-b332-ba749f16d6ae.png">

### Step 5-Rerun the Test

Commands Used:
```
Keys pressed: <Ctrl+r> (Ctrl+R can search commands in my command history)
typed: "javac" (When I search "javac", I can get the command that compile the tester)
Keys pressed: <enter> (run the command)
Keys pressed: <Ctrl+r> (Ctrl+R can search commands in my command history)
typed: "ru" (There are so many java commands, so I tries to search "runner" in tester,
        and when I typed "ru", I get the right command)
Keys pressed: <enter> (Run the command)
```

Result:

<img width="1037" alt="Screenshot 2023-02-23 at 5 09 36 PM" src="https://user-images.githubusercontent.com/110661816/221067215-600e4bdb-0d7d-4797-8f8c-930a8531e9f0.png">

### Step 6-Commit and Push

Commands Used:
```
git add L<tab><enter> (tab helps us autocomplete the file name, and enter run the completed command)
git commit -m "Find a Bug" (Commit our edited version)
git push
```
(I have to type in username and Personal Access Token due to the version of my VS Code)

<img width="509" alt="Screenshot 2023-02-23 at 8 08 03 PM" src="https://user-images.githubusercontent.com/110661816/221089543-69d51640-593e-40a3-a3a3-b5978e3f41ae.png">
