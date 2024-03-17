![gophish logo](https://raw.github.com/gophish/gophish/master/static/images/gophish_purple.png)

Gophish
=======

![Build Status](https://github.com/gophish/gophish/workflows/CI/badge.svg) [![GoDoc](https://godoc.org/github.com/gophish/gophish?status.svg)](https://godoc.org/github.com/gophish/gophish)

Gophish: Open-Source Phishing Toolkit

[Gophish](https://getgophish.com) is an open-source phishing toolkit designed for businesses and penetration testers. It provides the ability to quickly and easily setup and execute phishing engagements and security awareness training.
The fork GoPhish_PA_ITA specifically addresses privacy concerns related to data collection that links actions to individuals, offering solutions within this context.

### Install

Installation of Gophish is dead-simple - The installation process for this specific fork of Gophish, considering the modifications made, is currently designed to be performed on Linux systems.

### Building From Source
**If you are building from source, please note that Gophish requires Go v1.10 or above!**

To build Gophish from source, simply run ```git clone https://github.com/dellagigibit/GoPhish_PA_ITA.git``` and ```cd``` into the project source directory. Then, run ```go build```. After this, you should have a binary called ```gophish``` in the current directory.

### Setup
After running the Gophish binary, open an Internet browser to https://localhost:3333 and login with the default username and password listed in the log output.
e.g.
```
time="2020-07-29T01:24:08Z" level=info msg="Please login with the username admin and the password 4304d5255378177d"
```

Releases of Gophish prior to v0.10.1 have a default username of `admin` and password of `gophish`.

### Troubleshooting

When developing with github.com/mattn/go-sqlite3, you might encounter a warning indicating a function may return the address of a local variable, specifically in the sqlite3SelectNew function. This issue is known and documented. Always check the official repository for the latest updates or fixes regarding this issue.

```
Warning sqlite

sqlite3-binding.c: In function ‘sqlite3SelectNew’:
sqlite3-binding.c:128049:10: warning: function may return address of local variable [-Wreturn-local-addr]
128049 | return pNew;
| ^~~~
sqlite3-binding.c:128009:10: note: declared here
128009 | Select standin;
| ^~~~~~~
```

### Notes & Config

The database tables specifically impacted by the introduced triggers for the purpose of anonymization are "results" and "events". These triggers play a crucial role in ensuring data within these tables is processed to protect individual identities, aligning with privacy requirements.

For complete anonymization, one can adjust the severity level of system messages/logs generated during Gophish execution. After changing the initial access password, it's possible to set the severity level in the config.json file by modifying the level value within the logging JSON object. This adjustment helps tailor the detail and quantity of logged information, aligning with privacy practices.

### Documentation

The documentation available at getgophish.com/documentation pertains to the original version of Gophish, not the fork. If you notice anything missing or have suggestions for the original documentation, you're encouraged to file an issue on their site. For details specific to the fork, please refer to its respective repository or documentation.

### License
```
Gophish - Open-Source Phishing Framework

The MIT License (MIT)

Copyright (c) 2013 - 2020 Jordan Wright

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software ("Gophish Community Edition") and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
```
