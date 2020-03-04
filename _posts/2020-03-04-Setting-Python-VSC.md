---
title:  "Setting Python in Visual Studio Code"
excerpt: "Python"

categories:
  - Python
tags:
  - Python
  - AI
  - ML
last_modified_at: 2020-03-04T10:06:00-05:00
---

1. Install Visual Studio Code 

[Download Visual Studio Code - Mac, Linux, Windows](https://code.visualstudio.com/Download)

2. ext install - python3

- **command + shift +P** → type "ext install" → Extentions:Install
- Seletet Python and Install
- Restart VSCode!
- Run Test code - **command + shift + D**

    #!/usr/local/bin/python3
    # -*- coding: utf-8 -*-
     
    print("Start, Python!")
    a= "Hello, Python!"
    print(a)
    
    

3. Run by Using Task Runner

- **command + shift + P** → type "**task run**" → Select "**Tasks:Configure Task Runner**" → Select "**Other**"
- task.json is Created

    // task.json
    {
        // See https://go.microsoft.com/fwlink/?LinkId=733558
        // for the documentation about the tasks.json format
        "version":"2.0.0",

        "command":"python3",

        "args": ["${file}"],

        "options": {

            "env": {

                "PYTHONIOENCODING":"UTF-8"

            }

        },

        "problemMatchers": []
        
    
    }

- **command+shift+B**