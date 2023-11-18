# Mastodon 2 Hugo

**Enables searchability for your Hugo website on Mastodon. Now, anyone can discover you on Mastodon by simply entering your domain.**

**Requires Python 3.7 or higher**

Why you should care?
--------------------
If you have an account on Mastodon and a website built with Hugo, you can make it possible for people searching for you on Mastodon to find you through your website domain.

#### For example:

Imagine your website is hosted at `https://www.doe.com`, and your username is `johndoe543210@mastodon.world`.

After running this script, recompiling your site with Hugo, and deploying it, people will also be able to search and find you on Mastodon by using `@john@doe.com`.

Actually any name inserted before your domain name will work, as if it is a *catch-all* address. This means that any `@<place your name here>@doe.com` will work as well. If you need to have different names with different destinations, you'll have to write some client-based code in order to redirect Mastodon properly.

How does this work exactly?
---------------------------
Every time someone searches for a user on Mastodon (for example: `@john@doe.com`), the Mastodon server tries to contact the domain (`doe.com`) to ask about user credentials, by accessing a page under `https://doe.com/.well-known/webfinger?resource=acct:john@doe.com` using a *GET* method.
  
All my script does is copy these credentials from the Mastodon server that is hosting your account, and insert them into your website or blog created with Hugo in order to mimick the same directory structure.

Usage
-----
Download the python script `mastodon2hugo.py` in the root directory
of your Hugo project; for example, if `curl` is installed on the OS of 
your computer, to download the script you could enter this command on 
the terminal:

```sh
curl https://raw.githubusercontent.com/fmaida/mastodon2hugo/main/mastodon2hugo.py > mastodon2hugo.py
```

Then execute the script with the command:

```sh
python mastodon2hugo.py <your mastodon account>
```

Replace `<your mastodon account>` with your actual account (For example: `@johndoe@mastodon.online`)

If the script completes successfully, you should find a file 
called `webfinger` inside the directory `static/.well-known/`. 
That file will contain a JSON object with the proper configuration 
for your website.

**Important:** After running my script, in order to make your changes effective, please remember to execute Hugo to build your website again and deploy.

Usage examples
--------------
1. `python mastodon2hugo.py @johndoe@mastodon.online`
2. `python mastodon2hugo.py @gohugoio@fosstodon.org`

For example, if your Hugo project is named `mywebsite`, you should have 
the `mastodon2hugo.py` script inside the root directory like this:

```sh
$ cd mywebsite
$ curl https://raw.githubusercontent.com/fmaida/mastodon2hugo/main/mastodon2hugo.py > mastodon2hugo.py
$ ls -l

drwxr-xr-x  3 cesco  staff    96  1 Nov 21:04 archetypes/
drwxr-xr-x  2 cesco  staff    64  1 Nov 21:04 assets/
drwxr-xr-x  2 cesco  staff    64  1 Nov 21:04 content/
drwxr-xr-x  2 cesco  staff    64  1 Nov 21:04 data/
-rw-r--r--  1 cesco  staff    83  1 Nov 21:04 hugo.toml
drwxr-xr-x  2 cesco  staff    64  1 Nov 21:04 i18n/
drwxr-xr-x  2 cesco  staff    64  1 Nov 21:04 layouts/
-rw-r--r--  1 cesco  staff  2730  1 Nov 21:05 mastodon2hugo.py
drwxr-xr-x  2 cesco  staff    64  1 Nov 21:04 static/
drwxr-xr-x  2 cesco  staff    64  1 Nov 21:04 themes/

$ python mastodon2hugo.py @gohugoio@fosstodon.org 
```

Credits
-------
I couldn't have created this script without the helpful article written by [Maarten Balliauw](https://blog.maartenballiauw.be) on his personal blog, which you can find at <https://blog.maartenballiauw.be/post/2022/11/05/mastodon-own-donain-without-hosting-server.html>

Disclaimer
----------
By using this script, you acknowledge and agree to the following terms and conditions. Please read this disclaimer carefully before proceeding:

1. The script is provided on an "as is" basis, and the author makes no representations or warranties of any kind, express or implied, regarding the functionality, accuracy, or suitability of the script for any particular purpose.

2. The author shall not be held liable for any loss, damage, or deletion of important files or data on your computer that may occur as a result of using this script. Users are advised to back up their important data before running the script.

3. This script is intended for educational and experimental purposes only. It is not recommended for use in a production environment or on systems containing critical data.

4. Users are solely responsible for their actions while using this script and should exercise caution. The author disclaims any responsibility for the consequences of the script's use.

5. The author disclaims any liability for any damages, including but not limited to lost profits, business interruption, or data loss, that may result from using the script.

6. This disclaimer extends to any third parties who may be affected by the use of this script, including but not limited to system administrators, network administrators, or end-users.

7. By using this script, you agree to indemnify and hold harmless the author and any affiliated individuals or organizations from any legal claims, damages, or losses that may arise from its use.

In summary, the use of this script is at your own risk, and you are responsible for taking adequate precautions to protect your data and systems. If you do not agree with these terms, you should refrain from using the script.
