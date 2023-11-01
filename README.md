# Mastodon 2 Hugo

**Enables searchability for your Hugo website on Mastodon. Now, anyone can discover you on Mastodon by simply entering your domain.**

Why you should care?
--------------------
<TODO>

Usage
-----
Download the python script `mastodon2hugo.py` in the root directory
of your Hugo project, then enter this command from a terminal:

```sh
python mastodon2hugo.py <your mastodon account>
```

If the script completes successfully, you should find a file 
called `webfinger` inside the directory `static/.well-known/`. 
That file will contain a JSON object with the proper configuration 
for your website.

Usage examples
--------------
1. `python mastodon2hugo.py @johndoe@mastodon.online`
2. `python mastodon2hugo.py @gohugoio@fosstodon.org`

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
