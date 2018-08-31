<h2>About</h2>
This is a console application that will run a cmd command if it detects that any files have been changed.

<h2>How to use</h2>
<p>1) Copy the warun.exe file into your project folder. This file is found in watchandrun/ConsoleApp1/Sample/</p>

<p>2) Create or modify the war.config.json file. "local" are files that are in the same folder as warun.exe. "exact" are exact file path in your computer. These are the files that will be watched.</p>

```json
{
  "command": "go run hello.go hello1.go", 
  "local": [
    "hello.go",
    "hello1.go",
    "fakefile.got"
  ],
  "exact": [

  ]
}
```

<p>3) Run the warun.exe. You should already have the war.config.json file in the same folder.

```
PS C:\Users\Mouse\Desktop\Go\GoWorkspace\src\hello> .\warun.exe
Command: go run hello.go hello1.go
WARNING: File not exist: C:\Users\Mouse\Desktop\Go\GoWorkspace\src\hello\fakefile.got
FILE CHANGE DETECTED 13:26:19: hello.go
I have made some changes in the hello.go file
FILE CHANGE DETECTED 13:30:55: hello.go
I have made some MORE changes in the hello.go file
```

<h2>Example explain</h2>
<p>fakefile.got is a missing or non-existing file. </p>
<p>"I have made some changes in the hello.go file" is the first compiled output of a Golang file call hello.go that was changed at 13:26:19.</p>
<p>"go run hello.go hello1.go" is a command to compile and run both hello.go and hello1.go files.</p>
<p>Hitting any key will terminate the warun.exe application.</p>
