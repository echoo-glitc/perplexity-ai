# Perplexity.ai
This module is simply just an Api Wrapper and account generator. So it's an Api Wrapper with free copilots.

# How It Works
This module uses [emailnator](https://emailnator.com/) to generate new accounts. As you know, when you create a new account, you will have 5 copilots. That's how it works! This module will generate you new gmails with [emailnator](https://emailnator.com/) and you will have **UNLIMITED COPILOTS!**

# Requirements
* [requests](https://pypi.org/project/requests/)
* [beautifulsoup4](https://pypi.org/project/beautifulsoup4/)
* [lxml](https://pypi.org/project/lxml/) (Parser for BeautifulSoup)
* [websocket-client](https://pypi.org/project/websocket-client/)
* [uuid](https://pypi.org/project/uuid/)

Install requirements with:
```sh
pip3 install -r requirements.txt
```


# How To Use
First thing first, [Perplexity.ai](https://perplexity.ai/) is protected by cloudflare, and [emailnator](https://emailnator.com/) too. We need to open this pages manually and get the cookies. And do not forget these cookies are temporary, so you need to renew them continuously. [Here](#how-to-get-the-cookies) how to get your cookies.

```python3
import perplexity

perplexity_headers = <your headers here>
perplexity_cookies = <your cookies here>

emailnator_headers = <your headers here>
emailnator_cookies = <your cookies here>


perplexity_cli = perplexity.Client(perplexity_headers, perplexity_cookies)
perplexity_cli.create_account(emailnator_headers, emailnator_cookies) # Creates a new gmail, so your 5 copilots will be renewed. You can pass this one if you are not going to use "copilot" mode

# modes = ['concise', 'copilot']
# focus = ['internet', 'scholar', 'writing', 'wolfram', 'youtube', 'reddit', 'wikipedia']
print(perplexity_cli.search('Your query here', mode='copilot', focus='internet'))

# perplexity_cli.create_account(emailnator_headers, emailnator_cookies) # Call this function when you're out of copilots
```

# How To Get The Cookies
Do not forget these cookies are temporary, so you need to renew them continuously.

1. Open [emailnator](https://emailnator.com/) website. Click F12 or Ctrl + Shift + I to open inspector. Check "Preserve log" button, go to the "Network" tab in the inspector, click the "Go !" button in the website, right click the "message-list" in the Network Tab and hover on "Copy" and click to "Copy as cURL (bash)". Now go to the [curlconverter](https://curlconverter.com/python/), paste your code here. The header and cookies dictionary will appear, copy them and use in your codes.

<img src="emailnator.jpg">


2. Open [Perplexity.ai](https://perplexity.ai/) website. Sign out if you're signed in. Click F12 or Ctrl + Shift + I to open inspector. Check "Preserve log" button, go to the "Network" tab in the inspector, click the "Sign Up" button in the website, write a random email and click "Continue with Email" button, right click the "email" in the Network Tab and hover on "Copy" and click to "Copy as cURL (bash)". Now go to the [curlconverter](https://curlconverter.com/python/), paste your code here. The header and cookies dictionary will appear, copy them and use in your codes.

<img src="perplexity1.jpg">
<img src="perplexity2.jpg">

3. Don't confuse the headers and cookies for [emailnator](https://emailnator.com/) and [Perplexity.ai](https://perplexity.ai/), look at [How To Use](#how-to-use) to learn how to use them.