Description (中文说明见[README.zh_CN.md](https://github.com/seanliang/ConvertToUTF8/blob/master/README.zh_CN.md))
------------------
With this plugin, you can edit and save the files which encodings are not supported by Sublime Text currently, especially for those used by CJK users, such as GB2312, GBK, BIG5, EUC-KR, EUC-JP, etc. ConvertToUTF8 supports both Sublime Text 2 and 3.

![ConvertToUTF8](http://dl.dropbox.com/u/31937639/ConvertToUTF8/ConvertToUTF8.gif)

If this plugin is useful for you, you might want to buy me a cup of coffee to keep me fresh. Thanks! :)

[![Buy me a cup of coffee via PayPal](https://www.paypalobjects.com/en_US/i/btn/btn_donate_LG.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_donations&business=GP6Y25N7Q9E26&lc=US&item_name=Buy%20me%20a%20cup%20of%20coffee&item_number=ConvertToUTF8&no_note=0&currency_code=USD&bn=PP%2dDonationsBF%3abtn_donate_LG%2egif%3aNonHostedGuest)
[![Buy me a cup of coffee via Alipay](http://dl.dropbox.com/u/31937639/alipay.png)](https://me.alipay.com/seanliang)

Note
------------------
** For Linux users: ConvertToUTF8 relies on several dynamic libraries which are missing in embedded version of Python of Sublime Text 2 and 3. This plugin can not work fully until you install them manully.

** For OS X users: Sublime Text 3 uses an embedded Python which is facing the same problem as Linux version.

** I've reported this problem to Jon but did not get any response yet, so I created extra plugins to solve it. ConvertToUTF8 will show you the instructions when necessary.

Installation
------------------
Using [Package Control](http://wbond.net/sublime_packages/package_control) to find, install and upgrade *ConvertToUTF8* is the recommended method to install this plug-in.

Otherwise, you can download this repository as a zip file, unzip it, and rename the new folder to *ConvertToUTF8*, then move this folder to *Packages* folder of Sublime Text (You can find the *Packages* folder by clicking "Preferences > Browse Packages" menu entry in Sublime Text).

Your folder hierarchy should look like this:

![Folder Hierarchy](http://dl.dropbox.com/u/31937639/ConvertToUTF8/hierarchy.png)

Configuration
------------------
Please check ConvertToUTF8.sublime-settings file for details. You should save your personal settings in a file named "ConvertToUTF8.sublime-settings" under "User" folder.

* encoding_list: encoding selection list when detection is failed
* max_cache_size: maximum encoding cache size, 0 means no cache (default: 100)
* max_detect_lines: maximum detection lines, 0 means unlimited (default: 600)
* preview_action: specific the action when previewing a file, available options: no_action, convert_and_open (default: no_action)
* default_encoding_on_create: specific the default encoding for newly created file (such as "GBK"), empty value means using sublime text's "default_encoding" setting (default: empty)
* convert_on_load: enable/disable convert file content to UTF-8 when it is loaded, available options: always, never (default: always)
* convert_on_save: enable/disable convert file from UTF-8 to a specific encoding when it is saved, available options: always, never (default: always)
* lazy_reload: enable/disable save file to a temporary location, and reload it in background when switching to other windows or tabs, available options: true, false (default: true)

Usage
------------------
In most cases, this plug-in will take care of encoding issues automatically.

You can also use the "File > Set File Encoding to" menu entry to transform between different encodings. For example, you can open a UTF-8 file, and save it to GBK, and vice versa.

Note:
* if convert_on_save is set to never, the file will *NEVER* be saved to the selected encoding
* please do not edit the file before the encoding detection process is finished
* please try either increasing the value of max_detect_lines or set the encoding manually if the detection result is not accurate
* due to limitation of API, when lazy_reload is set to true, quit Sublime Text immediately after saving a file will cause the file to be saved as UTF-8, the correct content will be reload next time Sublime Text starts


Q & A
------------------
* Q: It is not working after installation, how do I fix it?

  A: Please try the following steps:
  1. Restart Sublime Text
  2. Make sure the plug-in folder is named "ConvertToUTF8" (skip this step if you install via "Package Control")
  3. See [Note section above](#note)
  4. Disable other encoding related plug-ins
  5. Contact me

* Q: Which encodings are supported?

  A: Any [encoding supported by Python](http://docs.python.org/library/codecs.html#standard-encodings) should be fine.

* Q: Why does the content become a mess when the window is re-activated?

  A: This is caused by reloading and has been fixed, please update your *ConvertToUTF8* to latest version.

* Q: Why does ST2 ask me that file "Has changed on disk. Do you want to reload it?" when the window is re-activated.

  A: Same reason as above. Please choose "Cancel" if you have unsaved changes to the file.

* Q: When saving the file, Sublime Text tells me the file is saved as UTF-8, why?

  A: Don't worry, the plug-in will convert your file to original encoding.

* Q: My file was saved as UTF-8 and it's in a mess, how can I recover it?

  A: Please open the file and make sure its encoding is UTF-8, then choose the menu entry "File -> Save with Encoding -> Western (Windows 1252)", close and reopen this file.

Contact me
------------------
Please send me your questions or suggestions: sunlxy (at) yahoo.com or http://weibo.com/seanliang
