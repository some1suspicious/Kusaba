#Installation Guide
http://code.google.com/p/kusaba/wiki/InstallationGuide
[

Don't use kusaba, use TinyIB

kusaba is outdated and unsupported. Visit https://github.com/tslocum/TinyIB to learn about TinyIB, a better imageboard software.
kusaba Requirements

To run kusaba, you should have a webserver with at least the following:

    An apache or apache2 installation
    mod_php version 4 or better, with GD and MBStrings support
    A mysql server with the MyISAM engine

Extracting kusaba

    Download the most recent kusaba release from www.kusaba.org
    Extract it to a directory that your apache installation has access to
    Make sure the permissions for everything are readable and writable by your web server
    Edit config.php

Editing config.php

To enable a feature, change the value to true:

    define('TC_INSTANTREDIRECT', true); To disable a feature, change the value to false: define('TC_INSTANTREDIRECT', false);

To change the text value of a configuration, edit the text in the single quotes:

    define('TC_NAME', 'kusaba'); Becomes: define('TC_NAME', 'Mychan'); Warning: Do not insert single quotes in the value yourself, or else you will cause problems. To overcome this, you use what is called escaping, which is the process of adding a backslash before the single quote, to show it is part of the string: define('TC_NAME', 'Jason\'s chan');

The postbox is where you mix dynamic values with your own text. The text from what you enter is then parsed and will be displayed under the postbox on each board page and thread page:

    define('TC_POSTBOX', '

        Supported file types are:
        Maximum file size allowed is KB.
        Images greater than x pixels will be thumbnailed.
        Currently unique user posts.

    '); Will become (if you had my settings): * Supported file types are: GIF, JPG, PNG * Maximum file size allowed is 1000 KB. * Images greater than 200x200 pixels will be thumbnailed. * Currently 221 unique user posts.

Possible values you may use: * * * * *
Setting kusaba Up

    Move the files install.php, install-mysql.php, and kusaba_freshinstall.sql from .OTHER to your kusaba root directory
    Visit http://yoursite/yourkusabadir/install-mysql.php
    Visit http://yoursite/yourkusabadir/install.php
    Log into http://yoursite/yourkusabadir/manage.php and make a new administrator account. From your new administrator account, delete the old administrator account.
    Remove .OTHER, install.php, install-mysql.php, and kusaba_freshinstall.sql from your kusaba root directory


]

#Other Info (Including Upgrading)
http://code.google.com/p/kusaba/wiki/Basics
[

Upgrading

Download the upgrade zip of the next version in line from what you are currently running. You can not skip upgrades!

If there is no upgrade zip of the next version, that means the upgrade and install are packaged together. Download the dual zip.

Make a backup of your current config.php somewhere and open it in a text editor.

Extract the upgrade zip's contents and open up config.php

Replace the values in the new config.php with your old values. KU_RANDOMSEED must stay the exact same for each upgrade!

Upload all of the files except the OTHER folder.

Open the OTHER folder and look for an upgrade.php. If there isn't one, you do not need to take any further actions to finish upgrading.

If there is, upload it to the server and run it from your browser.

Delete upgrade.php, and you're finished.
I'm using WAMP and having problems with...

XAMPP has been tested and works fully with kusaba. Please use XAMPP instead.
Blank, white pages with no errors

This is most likely due to display_errors set to Off in your php.ini

You have two choices: set display_errors to On, or locate your error log file and read from there.

If you don't have access to your php.ini, ask your host to set this directive for you.
Mod Posting

Mod posting is the act of using your staff account to make a modified post, which can do quite a few things.

To make a mod post, log in to the manage panel and click on the link in the menu labeled "Show Posting Password". It will change into a string of text; copy this.

Go back to the board you want to make a mod post in and scroll to the post form. Click the space to the right of the e in File, and the Mod box will open.

Paste your posting password in the Mod box and change any options in the Mod box if you desire, and click post.
Adding Boards to the Menu

First go to the manage panel, Administration -> Edit Sections.

Add a section, and take note of its ID.

Go to Board options, select a board, and in the Section box, place that ID.

Save the changes.

Reload your front page, and it should show up.
Making F5 Work Properly

Thanks go to hurrrrr from freechan.org for this:

Once your site is set up and finished being configured, go to the front page. You should see a menu with your boards and the news area. Click View -> Page Source, and copy the contents.

Make a new file called kusaba.html, and in that file, paste the HTML into it, and upload it to the same area as kusaba.php

Open your .htaccess, change:

DirectoryIndex kusaba.php

To:

DirectoryIndex kusaba.html

Overwrite the old .htaccess, reload your front page, and enjoy finally having proper F5 support!

]

#Support Board
http://img.kusaba.org/sup/
