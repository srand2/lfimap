# lfimap
## Local file inclusion discovery and exploitation tool


## Install

```
git clone https://github.com/hansmach1ne/lfimap.git
cd lfimap/
pip3 install -r requirements.txt
python3 lfimap.py -h

```

## Usage

```

usage: lfimap.py [-D <request>] [-H <header>] [-C <cookie>] [-P <proxy>] [--useragent <agent>] [--referer <referer>] [--param <name>] [--no-stop] [-f] [-i] [-d] [-e] [-t] [-r]
                 [--file] [--osinject] [--xss] [-a] [-x] [--lhost <lhost>] [--lport <lport>] [-wT <path>] [-wX <path>] [-wC <path>] [-v] [-h]
                 URL

lfimap, Local File Inclusion discovery and exploitation tool

MANDATORY:
  URL                            Specify url, Ex: "http://example.org/vuln.php?param=PWN" 

GENERAL OPTIONS:
  -D <request>                   Do HTTP POST value test. Ex: 'param=PWN'
  -H <header>                    Specify additional HTTP header(s). Ex: 'X-Forwarded-For:127.0.0.1'
  -C <cookie>                    Specify session cookie, Ex: "PHPSESSID=1943785348b45"
  -P <proxy>                     Specify Proxy IP address. Ex: '127.0.0.1:8080'
  --useragent <agent>            Specify HTTP user agent
  --referer <referer>            Specify HTTP referer
  --param <name>                 Specify different test parameter value
  --no-stop                      Don't stop using same method upon findings

ATTACK TECHNIQUE:
  -f, --filter                   Attack using filter:// wrapper
  -i, --input                    Attack using input:// wrapper
  -d, --data                     Attack using data:// wrapper
  -e, --expect                   Attack using expect:// wrapper
  -t, --trunc                    Attack using path truncation with wordlist (default 'short.txt')
  -r, --rfi                      Attack using remote file inclusion
  --file                         Attack using file:// wrapper
  --osinject                     Attack using os command injection
  --xss                          Cross site scripting test
  -a, --all                      Use all available methods to attack

PAYLOAD OPTIONS:
  -x, --shell                    Send reverse shell if possible (Setup reverse handler first)
  --lhost <lhost>                Specify localhost IP address for reverse connection
  --lport <lport>                Specify local PORT number for reverse connection

WORDLIST OPTIONS:
  -wT <path>                     Specify wordlist for truncation test
  -wX <path>                     Specify wordlist for xss test
  -wC <path>                     Specify wordlist for command injection test

OTHER:
  -v, --verbose                  Print more detailed output when performing attacks
  -h, --help                     Print this help message

```


[!] Disclaimer: Lfimap usage for attacking web applications without consent of the application owner is illegal. Developers assume no liability and are 
not responsible for any misuse and damage caused by using this program.


This project is made as a hobby and passion towards cyber security.

If you notice any issues with the software, please open up an issue. I will gladly take a look at it and try to resolve it. Note that I am by no means, an expert on programming and managing github repository. With that in mind, criticism and advice are very welcome. I am trying to make this program better each day!

In future I will work on: 
1) Option to test multiple urls and parameters from .txt file
2) Truncation reverse shell exploits - /proc/self/environ, /proc/self/fd
3) SSL support
4) Option to output stdout to multiple formats
5) Create encrypted reverse shell/encoding to avoid detection
6) Option for custom reverse shell if RCE is found, with options to download and upload files easily
