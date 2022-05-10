<p align="center">
<a href="https://github.com/Liodeus/Crawlmap"><img src="https://i.ibb.co/N12TkGN/logo-crawlmap.png" alt="logo" border="0"></a>
<p align="center">A python3 script to change your crawling logs as a mindmap

<p align="center">
  <a href="#introduction">Introduction</a>
 • <a href="#requirements">Requirements</a>
 • <a href="#installation">Installation</a>
 • <a href="#usage">Usage</a>
 • <a href="#output-to-mindmap">Output to mindmap</a>
</p>

<div align="center">
  <sub>Created by
  <a href="https://liodeus.github.io/">Liodeus</a>
</div>


## Introduction

This tool is made to automate the process of creating a mindmap from [Burp Suite](https://portswigger.net/burp) and [Gospider](https://github.com/jaeles-project/gospider) logs.

## Requirements

- python3 (sudo apt install python3)

## Installation

```bash
git clone https://github.com/Liodeus/Crawlmap.git
```

## Usage

```bash
python3 crawlmap.py --help

 _____                    _                       
/  __ \                  | |                      
| /  \/_ __ __ ___      _| |_ __ ___   __ _ _ __  
| |   | '__/ _` \ \ /\ / / | '_ ` _ \ / _` | '_ \ 
| \__/\ | | (_| |\ V  V /| | | | | | | (_| | |_) |
 \____/_|  \__,_| \_/\_/ |_|_| |_| |_|\__,_| .__/ 
                                           | |    
                                           |_|
                                            By Liodeus
  
usage: crawlmap.py [-h] -b BURP [-g GOSPIDER] [-o OUT] [--exclude EXCLUDE] [--nofiles]

optional arguments:
  -h, --help            show this help message and exit
  -b BURP, --burp BURP  Output from BurSuite (xml)
  -g GOSPIDER, --gospider GOSPIDER
                        Output from Gospider (json)
  -o OUT, --out OUT     Output file
  --exclude EXCLUDE     Exclude extensions (Example : "png,svg,css,ico")
  --nofiles             Don't print files, only folders
```

### Burp Suite

To crawl with Burp Suite, I do as follow:

<img src="https://github.com/Liodeus/Crawlmap/blob/main/images_example/burp_one.png" align="center">

Select "Crawl":

<img src="https://github.com/Liodeus/Crawlmap/blob/main/images_example/burp_two.png" align="center">

"Select from library", personnaly I often use those two:

<img src="https://github.com/Liodeus/Crawlmap/blob/main/images_example/burp_three.png" align="center">

Then I increase the "Maximum concurrent requests":

<img src="https://github.com/Liodeus/Crawlmap/blob/main/images_example/burp_four.png" align="center">

Let the crawler do is work, and when finish, go to "Target". Select **All** requests in the "Contents" tab. And finaly "Save selected items".

<img src="https://github.com/Liodeus/Crawlmap/blob/main/images_example/burp_five.png" align="center">

### Gospider

For Gospider I use this command:

`gospider -s http://127.0.0.1:8084 -d 5 --sitemap -q --json -o ./`

### Run Crawlmap
#### Only Burp Suite
`python3 crawlmap.py --burp dvwa.burp`

<img src="https://github.com/Liodeus/Crawlmap/blob/main/images_example/only_burp.png" align="center">

Which gives this output:

<img src="https://github.com/Liodeus/Crawlmap/blob/main/images_example/only_burp_out.png" align="center">

#### Burp Suite and Gospider
`python3 crawlmap.py --burp dvwa.burp --gospider dvwa.gospider`
<img src="https://github.com/Liodeus/Crawlmap/blob/main/images_example/burp_gospider.png" align="center">

Which gives this output:

<img src="https://github.com/Liodeus/Crawlmap/blob/main/images_example/burp_gospider_out.png" align="center">

## Output to mindmap
### Markmap

https://markmap.js.org/repl

### MarkMind

https://github.com/MarkMindCkm/Mark-Mind