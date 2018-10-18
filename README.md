This readme will cover how to install "NightMode" for the Windows SlackAPP.

Steps to setup:
->SlackAPP 
-> Click the upper-left Bar Icon 
-> Preferences 
-> Sidebar 
-> Scroll down to the "copy and paste these values to share custom theme" section 
-> Paste in the following data:
"#2a2b2b,#444A47,#D39B46,#FFFFFF,#434745,#FFFFFF,#99D04A,#DB6668"

Next go into your SlackAPP install directory on windows. It should be something like:
"C:\Users\<YourUserName>\AppData\Local\slack"

Then dig down into the current version of slack's source:
"\app-3.3.3\resources\app.asar.unpacked\src\static"

Open the "ssb-interop.js" file, and add the following code to the bottom of the file:

document.addEventListener('DOMContentLoaded', function() {
 $.ajax({
   url: 'https://raw.githubusercontent.com/jbenson-strandrx/dark-theme-slack/master/dark-theme.css',
   success: function(css) {
     $("<style></style>").appendTo('head').html(css);
   }
 });
});

Lastly, restart your SlackAPP, presto!
