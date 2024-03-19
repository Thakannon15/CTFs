# Navigating and Utilizing Exploit Database

## Getting Started

1. On your local computer, open another tab in your current browser or start a new browser instance.
2. Navigate to [Exploit Database](https://www.exploit-db.com/).

![image](https://github.com/TheCyberVault/CTFs/assets/141572056/583d953a-1b42-43ed-a3da-3adf20f50944)



## Exploring the Exploit Database

Upon landing on the Exploit Database main page, you'll find exploits listed in reverse chronological order, with the most recent postings at the top.

The default Exploits page displays key information across several columns:

- **Date**: Entries are sorted with the newest exploits at the top.
- **D/Download Exploit**: Click here to download the exploit file.
- **A/Vulnerable Application**: If available and permissible, this column links to the vulnerable software.
- **V/Verified**: A checkmark indicates verified exploits; an X signifies unverified. Non-working items are removed.
- **Title**: Provides a brief overview of the target software and exploit type.
- **Type**: Specifies the exploit category, such as DOS, Local, Remote, or WebApp.
- **Platform**: Shows the affected operating systems or platforms.
- **Author**: Credits the individual or group who published the exploit.

![image](https://github.com/TheCyberVault/CTFs/assets/141572056/86d204f3-7974-4798-b2a7-aee8584f7793)



One of the most valuable features of the Exploit Database is the ability to download the source code for the exploits, a unique aspect that sets it apart from other exploit information sources.

## Utilizing Filters

1. Click the `Filters` button to reveal filtering options including Type, Platform, Author, Port, and Tag.
2. Explore the dropdown lists for each filter to refine your search results.

![Utilizing Filters](https://github.com/TheCyberVault/Threat-Intelligence-Sources/assets/141572056/b6362e09-9603-4ee5-a06b-7c86318f1d42)


## Expanding the Side Menu

Hover over the compressed side menu on the left to expand it, and select `GHDB` to access the Google Hacking Database (GHDB).

![Side Menu](https://github.com/TheCyberVault/Threat-Intelligence-Sources/assets/141572056/d12d8b87-9da3-434d-aef2-f61c4051bc3b)


## Google Hacking Database (GHDB)

GHDB comprises search expressions (Google dorks) useful for finding website vulnerabilities through Google.

1. Click the `Filters` button and select a category from the `Category` dropdown, such as "Files Containing Passwords."
2. Choose a Google hack to explore. Given the dynamic nature of GHDB, select one that interests you from the current listings.

![Google Hacking Database](https://github.com/TheCyberVault/Threat-Intelligence-Sources/assets/141572056/fa0dd757-1117-4e60-a66a-d873443cb074)


## Caution

While it might be tempting to visit sites found through Google dorks, exercise caution. These sites might host or be associated with malicious content. Always conduct such investigations from a secure environment, like a VM that can be easily restored to a safe state.

## Returning to Exploit Database

Close the tab with Google search results to return to your Exploit Database tab and continue exploring other features.

## Other Features

From the side menu, consider exploring:

- **Security Papers**: A collection of insightful non-commercial papers on various security topics.
- **Shellcodes**: Contains ready-to-run payload scripts, usable with intrusion exploits.
- **SearchSploit: The Manual**: Offers guidance on using the command-line tool to search an offline copy of the Exploit Database.
