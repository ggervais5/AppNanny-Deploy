# AppNanny-Deploy
Deployment repository for AppNanny

The concept for AppNanny arose from the COVID-19 pandemic where schools were closed to many children and remote learning became the norm.
School-aged children were taught to use collaboration tools such as Teams and Zoom to connect with their teachers and fellow students
during school hours.  The downside of teaching new tools to students soon came about:  these tools could be over-used or used outside of adult supervision.
My intent was to put controls in the hands of parents with children who need automated supervision, though the children will not like the controls.  However,
keeping them safe and/or away from distractions is the main goal.

What AppNanny Does
==================
Parents, via a Windows app called AppNanny, select applications they wish to control, and enter allowed days/times when those applications can be used (e.g., during school hours).  Restrictions can identified for each application selected, and there is a default set of restrictions applying to other applications marked as being restricted.  AppNanny is password-protected with a Forget Password feature.  Forgotten passwords are sent to the parent's email set up when the program is first launched.  The password and parent email can be changed via the main AppNanny form.  This data is encrypted should prying eyes find the security file.  Parents can install a new version of the Windows service, uninstall it, stop it or start it by clicking buttons in the app - no technical skills required.  If changes are made to allowed days/times, the Windows service must be restarted to pick up the changes.  AppNanny may be closed once the settings are saved, and only re-opened if the settings need to change.

A Windows service, called AppKiller, picks up these settings when it starts up, and closes down applications, on a timed cycle, that run during times outside of the allowed days/times.  The Windows service will start up when Windows is booted and will pick up the settings again.  Attempts to start up restricted applications when they are not allowed will not work - the Windows service runs every 30 seconds and will shut down restricted applications outside their allowed days and hours.  Rebooting the machine will not thwart AppKiller - it will start up upon reboot and find the list of restricted apps and allowable days/times.

Examples of Applications that can be restricted include:
========================================================
   1) Microsoft Teams (chat, audio/video sharing)
   2) Messenger (chat, audio/video sharing)
   3) Any browser including Chrome, Internet Explorer, Microsoft Edge, Safari

NOTE:  Do NOT restrict applications that are essential to Windows, especially Explorer.exe.  This is the main Windows GUI.
   
How to mark an application as Restricted
========================================
   1) Run the application on the machine where AppNanny is installed.
   2) Look in the Application dropdown list and select it.
   3) Drag and drop the the application to the Restricted Apps list.

How to Add Restrictions - for all apps or individual ones
=========================================================
   1) For restrictions that apply to all restricted apps, select <default> in the Application drop-down and enter allowed days/times.
   2) For specific application restrictions, drag and drop the application from the Restricted Apps list to the Allowed days/times and update as
      required.
   3) Click the Save button to save the list of restricted applications and restrictions to disk.
   Note:  The AppKiller service will not pick up changes you make in these lists until you stop and restart the service.
   
How to Remove app restrictions or Un-mark applications as restricted
====================================================================
   1) Right click on the application name.  A context menu will pop up, with a Remove Item on the menu.
   2) If you change your mind, don't click on the Remove Item; otherwise, click on Remove Item and the item will be removed from the list.
   3) This works the for both Restricted Apps and Allowed Days/Times.
   Note:  you cannot remove items from the Available Apps list.
   
Service Control
===============
   1) If the AppKiller service is not installed, the Install button is the only button enabled.
   2) If the AppKiller service is not running, the Remove and Start buttons are enabled, while the Install and Stop buttons are disabled.  Start the service or
      remove it by click on the appropriate button.
   3) If the AppKiller service is running, the Stop button is the only button enabled.  Stop the Service by clicking on the Start button.  This is the preferred
      method of temporarily easing up on application restrictions (and start the service back up when controls need to be put back in place).
 
 Encryption
 ==========
   1) The Admin/Parent password is encrypted, safe from prying eyes!
   2) Very strong encryption, AES 256, is being used to encrypt AppNanny files.
  
 Enjoy!!
