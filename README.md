# ScavengingTheScavenger
Lazy way to gather dumped credentials.
___

Hey everyone!

Recently, I stumbled across an interesting Twitter account called [@leak_scavenger](https://twitter.com/leak_scavenger). After a bit of research (clicking on all the links I could find) I realised that it is an open-source OSINT bot residing here on GitHub and its name is [Scavenger](https://github.com/rndinfosecguy/Scavenger).

So, who the hell coded this amazing bot? [@rnd_infosec_guy](https://twitter.com/rnd_infosec_guy) did!  
Why the hell am I telling you this? Well, because I just finished coding "Scavenging The Scavenger".  
Wtf is that? Scavenging The Scavenger is a simple Twitter scraper using [Tweeter API](https://developer.twitter.com/en/docs) that constantly checks [@leak_scavenger](https://twitter.com/leak_scavenger) tweets for dumps containing credentials.

This is a very basic script, let's just call it... "something that just works" *(I apologise to all the real devs out there :P)*.

## Installation
This script has been developed and tested on Arch and Headless Debian Server but you are free to use it anywhere.
```
pip3 install -r requirements.txt
```
You will also need to install Firefox and have a copy of [geckodriver](https://github.com/mozilla/geckodriver/releases) in your PATH. Why? I am using selenium, even though it is slow af *(compared to requests)*, it was the only *(easy)* way *(I could come up with (for now))* to access [ghostbin](https://ghostbin.co/).

After installing everything, you need to put your Twitter developer keys in the file `tweet_API.conf`. If you want me to implement a safer way to do this part, just ask.

## Run
Use Python >= 3.7 and, if needed, specify the full path of your Firefox binary file (not the bash file redirecting to the binary, nor the symbolic link).
```
python3 scavengingTheScavenger_1.0.py
```
or
```
python3.7 scavengingTheScavenger_1.0.py -f /usr/lib/firefox-esr/firefox-esr
```
It will create a folder called `dumps` used to store all the downloaded dumps in txt format. It will also create 2 more files used to log the paste already downloaded and the errors encountered ( `pasteList.txt` and `errors.txt` ).
