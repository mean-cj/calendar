# Caldav Calendar Plugin for Roundcube & NextCloud

I would really **LOVE** a little help on this project. Tons of lines of code to go through for just one old man.  \
I know it would be a **HUGE HELP** to me personally and many other individual users because I really believe  \
this Calendar can become something amazing with some skilled PHP Developers on my side. I am self taught  \
at what I do and I have pulled some pretty cool stuff off. Out of the many other calendar plugins hosted on  \
Github that I have used, this one is by far the best choice, IMHO, and I am far from the best at PHP. So that  \
is why I am asking for help. If someone like me, who knows just enough programming to be dangerous, can do  \
something like this, just imagine what a properly trained Programmer can do.  \
Thank you for listening to this old mans ramblings.  \
  
---  

**Tested and working using the following:**  
* Debian 9.13
* Apache2 v2.4.25
* Roundcube v1.4.7
* Composer v1.10.9
* Nextcloud v18.0
* PHP v7.2.32
* MySQL Server v5.7.31
* Sabre/Dav v3.0.9
* Sabre/Event v2.0.2
* Sabre/Http v4.2.1
* Sabre/Uri v1.1.0
* Sabre/Vobject v3.5.3
* Sabre/Xml v1.4.1

**Elastic Skin Support now available**

I forked this with the intent to make a working, out of the box caldav enabled calendar for exclusive use with Nextcloud.

I will maintain this repo for as long as I can.

This plugin is intended to be used with Nexcloud only at this point in time. The Calendar Plugin will sync already existing calendars from Nextcloud. If you want more than the default, you must add calendar within Nextcloud Calendar GUI and then go back to Roundcube and it will magically appear in your Roundcube Calendar GUI after a good refresh (F5). From Roundcube Calendar GUI, you can add, edit, delete, download, copy and add attachments to events. iTip invitations are succesfully sent, accepted, declined, etc upon inviting attendees ... 

This is verified as compatible with RCMCARDDAV 3.0.3 as I use it to sync my contacts from Nextcloud to Roundcube.  

**BE ADVISED**
I have tested out v4 of RCMCARDDAV and it is not compatible with this calendar anymore but I am working on it.  

For Older Roundcube versions (v1.3.x and older) download [v0.4](https://github.com/texxasrulez/caldav_calendar_te/releases/tag/0.4)  

**Installation** 

`composer require texxasrulez/calendar:0.0.6.1`  

This will download latest release version.  
It will inject all sql schemas associated with this plugin with the exception of Kolab and LDAP.  
I have left those schemas in the original direcotry of drivers/<driver-type>/SQL to manual install  

After composer does its thang, change directories to plugins/calendar and type `composer run-script post-install-cmd`  
This will copy a file over to fix all-day recurring showing up a day early bug.  
Remember to edit your config.inc.php for your url and you should be good to go.  

***VERY IMPORTANT***

Your username and password **must** be the same for Nextcloud and Roundcube to work properly.\
The Nextcloud account must be created and user must log into Nextcloud at least once before calendar will sync in Roundcube. Nextcloud does not create calendars until the initial login, so there will be no calendar for the Roundcube Calendar to find.\
There are no plans at this time to implement the use of different login usernames. \
There shouldn't be any issues if you create your users in Nextcloud using the exact username and password required to login to Roundcube. \
There are configurable parameters to alter your email for logins within Roundcube config that may help you out if you require something a little different.  \
Your roundcube and nextcloud must be run from same domain, no subdomains because of cross-scripting issues.  

**Known Issues**

* Will not create new calendar from Roundcube Calendar GUI.

**New Features**

- Installable via composer  
- Plugin now uses the des_key that is randomly generated by Roundcube during install. No more having to remember to change the key in Calendar config.inc.php file.
- utf8mb4 Support is now available. ie .. Emoji's within Calendar Title, Description and Locations are supported.
- Randomly generated Colors for calendars upon sync.
- Can now specify time frame (in seconds) intervals to sync your calendar.

**Wishlist**

- [ ] Add the ability to create new calendar within Roundcube Calendar GUI.
- [ ] Oauth support for a wider range of calendar choices. (Probably will take me a month of Sundays as my skills aren't the best. :frowning_face:  ....  I need some help
- [ ] Add a preview / agenda list in main Mail Tab within the left side column at the bottom.
- [x] ~~Assign random colors upon initial sync of calendars.~~ - Thank you @drlight17
- [ ] Add sound notifications.
- [ ] Integrate a Caldav Enabled Tasklist plugin.
- [x] ~~Add Emoticon Support.~~ @texxasrulez
- [x] ~~Remove mcrypt and replace with openssl.~~ Thank you @MAT-WEISS-2017
* User feature requests are always welcome but I cannot guarantee if I can pull it off ... :relaxed:

**Submitting Issues**

Since I constantly work on this, issues may or may not be attended to in any timely manner. I will be introducing bugs and fixing and back again. Issue Submitting is by all means totally welcome since details given by users will help me out ...

:moneybag: **Donations** :moneybag:

If you use this plugin and would like to show your appreciation by buying me a cup of coffee, I surely would appreciate it. A regular cup of Joe is sufficient, but a Starbucks Coffee would be better ... \
Zelle (Zelle is integrated within many major banks Mobile Apps by default) - Just send to texxasrulez at yahoo dot com \
No Zelle in your banks mobile app, no problem, just click [Paypal](https://paypal.me/texxasrulez?locale.x=en_US) and I can make a Starbucks run ...

I appreciate the interest in this plugin and wish nothing but the best for all ...

