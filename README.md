# ppmap 
A simple scanner/exploitation tool written in GO which automatically exploits known and existing gadgets (checks for specific variables in the global context) to perform XSS via Prototype Pollution. NOTE: The program only exploits known gadgets, but does not cover code analysis or any advanced Prototype Pollution exploitation, which may include custom gadgets.

## Requirements
Make sure to have Chromium installed. No need to worry, **setup.sh** will automatically install that for you.  

## Installation
- Run the following command to clone the repo: 
 ```bash
git clone https://github.com/hack-parthsharma/PPMap.git
 ```
 - Change the directory to ppmap and execute **setup.sh**:  
```bash
cd ppmap/ && bash setup.sh
```  
That's it. Enjoy using ppmap!

## Usage

Using the program is very simple, you can either:
- scan a directory/file (or even just the website itself):  
```echo 'https://target.com' | ppmap```

- or endpoint:  
```echo 'http://target.com/something/?page=home' | ppmap```

For mass scanning:  
``` cat url.txt | ppmap``` where **url.txt** contains all url(s) in column.

## Workflow

- Identify if the website is vulnerable to Prototype Pollution by heuristic scan (via location.hash and location.search)
- Fingerprint the known gadgets (checks for specific variables in the global context)
- Display the final XSS payload which can be exploited

## Credits

Many thanks to @Tomnomnom for the inspiration: https://www.youtube.com/watch?v=Gv1nK6Wj8qM&t=1558s  
The workflow of this program is hugely based on this article: https://infosecwriteups.com/javascript-prototype-pollution-practice-of-finding-and-exploitation-f97284333b2  
The fingerprint javascript file is based on this git: https://gist.github.com/nikitastupin/b3b64a9f8c0eb74ce37626860193eaec