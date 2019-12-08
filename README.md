# What is Backlink Checker? 
It's a casual task to work with backlinks in SEO. There are several tools to check or search for backlinks. Unlike other tools, this script does not look for backlinks to your website. The script is used to validate a list of backlinks that you already know. You  recieve a list of backlinks using one of the following ways:

- you buy backlinks and recieve the list of donor web pages
- you generate the backlinks yourself by posting on forums, 3rd party websites, etc.
- your SEO expert or company work for you and show you the reports with backlinks as one of the SEO strategies

When you have such list of donor web pages, you need to confirm that they actually contain the required backlink to your website. Besides, you need to validate this list regularly in the future to monitor if the backlinks still exist and are not being deleted. So, this script will help you to do that. The script allows to check for a fixed backlink, such as `https://example.com` and use search patterns, such as `*.example.com` and many others using regular expressions.     

# Manual
To start using the script, first have the list of donor web pages prepared in a file: one URL per line.

#### SYNOPSIS
**backlink-checker.sh** -input *FILE* -link *LINK* [OPTIONS]

#### DESCRIPTION
Script is used to check if a specified *LINK* exists in a list of web pages specified in a *FILE*, one URL per line. The script is useful for SEO experts when you need to validate that your backlinks still exist on the web pages where you set them or bought them.

#### OPTIONS
**-v**

Activates verbose mode

---

**-mode** *LETTER*

The *LETTER* defines how *LINK* is interpreted. We use [grep](https://en.wikipedia.org/wiki/Grep) for search, for complete info refer to Matcher Selection of the [grep manual](https://www.gnu.org/software/grep/manual/grep.html#grep-Programs). Usually grep supports the following modes:

**-E**

Interpret *LINK* as an extended regular expression (ERE).

**-F**

Interpret *LINK* as a fixed string (instead of regular expression). This is the default.

**-G**

Interpret *LINK* as a basic regular expression (BRE).

**-P**
Interpret *LINK* as a Perl-compatible regular expression (PCRE).


---

**-log** *LOG*

Saves the log to file *LOG*.

---

**-found-log** *LOG*

Saves URLs where the *LINK* was found to file *LOG*.

---

**-missing-log** *LOG*

Saves URLs where the *LINK* was not found to file *LOG*.

---

**-append**

All log files will be appended, otherwise they will be overwritten.

---

**-user-agent** *AGENT*

Sets [user-agent string](https://en.wikipedia.org/wiki/User_agent) to *AGENT*.

# Demo

```console
root@Sputnik:~# bash backlink-checker.sh -input list.txt -link dubaidance.com -log log.txt -found-log found.txt -missing-log missing.txt
```

![MapEx widget logo](https://thumbs.gfycat.com/VainFirstDugong-size_restricted.gif)

# System Requirements
## Linux
The script should work on any Linux which has [wget](https://en.wikipedia.org/wiki/Wget) and [grep](https://en.wikipedia.org/wiki/Grep) installed. For Debian-based OS simply run the following command to install missing packages:

```console
apt-get update
apt-get install wget grep
```

## iOS
First, install brew, run in terminal:

```console
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

Install wget:

```console
brew install wget
```

Install grep (we need a newer version of grep, the one that comes with iOS does not work properly):

```console
brew install grep
```

We need to add the bew binarties path to the `PATH` variable, so that we use the new binaries from brew. You can temporarly do it by executing the command below each time you start a terminal:

```console
PATH="/usr/local/opt/grep/libexec/gnubin:$PATH"
```

Or you can permanently do it by using this [manual](https://www.architectryan.com/2012/10/02/add-to-the-path-on-mac-os-x-mountain-lion/).

Finally, please, test that you have the required versions installed. Test `wget` (should be version 1.20.3 or later):

```console
MacBook:~ user$ wget -v
GNU Wget 1.20.3 for darwin18.7.0.

-cares +digest -gpgme +https +ipv6 +iri +large-file -metalink +nls 
+ntlm +opie -psl +ssl/openssl
```

Test `grep` (should be version 3.3 or later):

```console
MacBook:~ user$ grep -V
grep (GNU grep) 3.3
Packaged by Homebrew
Copyright (C) 2018 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <https://gnu.org/licenses/gpl.html>.
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.

Written by Mike Haertel and others; see
<https://git.sv.gnu.org/cgit/grep.git/tree/AUTHORS>.
```

## Windows
If you want to run this script in Windows, then you need to setup a bash shell first, for example, read instructions [here](https://www.howtogeek.com/249966/how-to-install-and-use-the-linux-bash-shell-on-windows-10/). I personally didn't try to do that, so it's just a tip.  

# Feedback
Your feedback is very appreciated. If you want to see new features in this project, please, post your ideas and feature requests in the [issue tracker](https://github.com/rvalitov/backlink-checker/issues).

# Donations
This is a free project that I do in my spare time. If you find it useful, then you can support it by donating some amount of money. This will help to keep the project alive and making it better: develop new features, make new releases, fix bugs, and provide at least some minimal technical support.

You can choose any payment method you prefer:

Your Currency | Payment Method
------------ | -------------
Euro € | [![Card](https://img.shields.io/badge/EURO-Debit/Credit%20Card-6f202b.svg?style=flat)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=BJJF3E6DBRYHA) [![PayPal](https://img.shields.io/badge/EURO-PayPal-blue.svg?style=flat)](https://www.paypal.me/valitov/0eur) 
USD $ | [![Card](https://img.shields.io/badge/USD-Debit/Credit%20Card-6f202b.svg?style=flat)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=B8VMNU7SEAU8J) [![PayPal](https://img.shields.io/badge/USD-PayPal-blue.svg?style=flat)](https://www.paypal.me/valitov/0usd) 
Russian Ruble ₽ | [![Card](https://img.shields.io/badge/RUB-Debit/Credit%20Card-6f202b.svg?style=flat)](https://money.yandex.ru/to/410011424143476) [![PayPal](https://img.shields.io/badge/RUB-PayPal-blue.svg?style=flat)](https://www.paypal.me/valitov/0rub) [![YandexMoney](https://img.shields.io/badge/RUB-YandexMoney-5b0d56.svg?style=flat)](https://money.yandex.ru/to/410011424143476)
Other | [![Card](https://img.shields.io/badge/OTHER-Debit/Credit%20Card-6f202b.svg?style=flat)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=BJJF3E6DBRYHA) [![PayPal](https://img.shields.io/badge/OTHER-PayPal-blue.svg?style=flat)](https://www.paypal.me/valitov)

# Support or Contact
Having trouble? May be something has already been reported in the [issue tracker](https://github.com/rvalitov/backlink-checker/issues). If you don't find your problem there, then, please, add your issue there.