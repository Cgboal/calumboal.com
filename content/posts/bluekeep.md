---
title: "BlueKeep - The worms are on the horizon"
date: 2019-08-30T21:47:59+01:00
draft: true
---
<img src="https://i.imgur.com/SbCEBmp.jpg" style="max-width: 80%; max-height: 80%">


## What is BlueKeep?
Since it's [disclosure on May 14th](https://portal.msrc.microsoft.com/en-US/security-guidance/advisory/CVE-2019-0708) it's been hard to escape news coverage of the omnipresent omnishambles that is Bluekeep. Of course, this is understandable; because a critical vulnerability in Window’s Remote Desktop Protocol that affects Windows 2000 through 7/2008 R2 is no laughing matter. Particularly when you consider that if successfully exploited it results in a remote code execution with Window’s highest possible level of privilege: [`NT_AUTHORITY/SYSTEM`](https://docs.microsoft.com/en-us/windows/win32/services/localsystem-account) - which surpasses even ‘Administrator’. 

## What's the latest on the BlueKeep threat? 
However, beyond the obvious dangers there’s another reason BlueKeep’s been on everyone’s mind. That’s the worrying degree of public exposure Remote Desktop Services are subject to, with over 1,000,000 internet-facing devices enumerated last month. Granted, that number has since fallen by 200,000, however, the vast number of affected hosts remaining present on the internet is still dangerously high. 

And when you combine this 800,000-number with the inherently ‘wormable’ nature of BlueKeep, it’s easy to see why the [NSA,](https://www.nsa.gov/News-Features/News-Stories/Article-View/Article/1865726/nsa-cybersecurity-advisory-patch-remote-desktop-services-on-legacy-versions-of/) [NCSC](https://www.ncsc.gov.uk/report/weekly-threat-report-31st-may-2019) and [Microsoft](https://msrc-blog.microsoft.com/2019/05/30/a-reminder-to-update-your-systems-to-prevent-a-worm/) have all sounded the alarm, issuing stark emergency advisory warnings and instructing people to immediately apply Bluekeep Patches to all hosts they’re responsible for.

They even went so far as to raise the specter of a potential repeat of WannaCry/NotPetya the devastating ransomware campaign which shook the world in 2017, taking down thousands of networks - including the NHS's. 

## BlueKeep exploits exist and are evolving fast
Of course everyone knew that someone, somewhere had already developed an exploit but these were thought to in the hands of organizations with little motivation for indiscriminate ransomware attacks via a worm. So, with no exploit code circulating publically, some chose to ignore the rising alarms bell.

Inevitably, they could be ignored no longer when last Tuesday steps to create a working exploit were published on GitHub. Since their publication, a public proof-of-concept exploit has been created, however, it currently only works on Windows XP. On Wednesday the security company Immunity (who maintain the CANVAS exploit framework) released a fully functional BlueKeep exploit, thankfully, it is located behind a significant pay wall. By Friday a working PoC exploit was submitted to the Metasploit Framework, pending Rapid7’s review. 

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">RE: <a href="https://twitter.com/hashtag/BlueKeep?src=hash&amp;ref_src=twsrc%5Etfw">#BlueKeep</a> <a href="https://twitter.com/metasploit?ref_src=twsrc%5Etfw">@Metasploit</a>. I performed a full knowledge transfer of my notes/code to the MSF core team. The release timeline is out of my hands and up to Rapid7 discretion. I&#39;ve been too busy to work on it for over a month anyways; fresh eyes and polish. Thanks for understanding. <a href="https://t.co/hXvpqbUYam">pic.twitter.com/hXvpqbUYam</a></p>&mdash; zǝɹosum0x0🦉 (@zerosum0x0) <a href="https://twitter.com/zerosum0x0/status/1156608483166343169?ref_src=twsrc%5Etfw">July 31, 2019</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

## Are Security teams responding fast enough?
The pace of last week’s event should make clear to those that haven't patched yet that: 

**The count-down to BlueKeep being used in the wild is has begun.** 

As an industry, you think we'd have learned the lessons of 2017, but the latest figures tell a different story. The current rate of patching [5,000 externally facing assets per day](https://www.darkreading.com/bluekeep-exploits-appear-as-security-firms-continue-to-worry-about-cyberattack/d/d-id/1335380) simply isn’t fast enough to outrun the rate at which exploits are being published. 

## But what about internal assets? 
Despite all the alarms and hysteria regarding externally facing assets many Security teams have an oddly complacent attitude towards patching vulnerable hosts on their internal networks. Our Pentesters at OnSecurity -and indeed every Pen tester I’ve spoken to since the disclosure- are finding that this Critical vulnerability is still turning up regularly in pentests. In some instances, this has even been the case when re-testing clients after the previous report highlighted BlueKeep's prevalence within their environment.

Now obviously, we all know that patching your network perimeter takes priority. And if downtime business operations prevent you patching externally facing hosts, then it is imperative you firewall off RDP services to prevent them from being exploited. Preventing worms from successfully propagating throughout the internet is ‘Job-One’. 

But once that’s taken care of, your attention should immediately turn to protecting your internal assets. 

## Ignore internal patching at your peril
The parallels between BlueKeep and EternalBlue couldn’t be clearer. The havoc of EternalBlue is not some distant memory either: Just last month the State of Florida [paid out whopping $1,000,000](https://www.nytimes.com/2019/06/19/us/florida-riviera-beach-hacking-ransom.html) in ransom to attackers who compromised networks via Phishing, and used automated malware strains which compromised additional hosts within the network via 3 main techniques, one of which was EternalBlue. 

The danger cannot be overstated: It is a certainty that Malware strains such as the ones responsible for the Florida attacks will incorporate BlueKeep into their arsenal soon. 

## Patch BlueKeep ASAP
So, make no mistake: the worms are on the horizon. Do not wait until it's too late to patch. Yes, it’s great that your externally facing assets are patched, but now is the time to ensure your internal assets are patched as well. [Defence in depth](https://www.sans.org/reading-room/whitepapers/basics/defense-in-depth-525) is key, as it always is in security. 


> The best time to start patching was yesterday, the second-best time is now. 

