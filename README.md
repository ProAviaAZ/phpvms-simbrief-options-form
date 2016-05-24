# phpVMS Simbrief Options Form
A form to allow options to be altered before generating the SimBrief OFP.

--------------------
NOTE: This addon is designed to work with the SimBrief Addon by Vangelis on PHPVMS Forums. 
You must have this installed for this functionality to work. http://forum.phpvms.net/topic/21388-sim-brief-for-phpvms/
I am also using David Clark's version of PHPVMS where the templates are in .php format rather than .tpl 
If you have the older .tpl version of PHPVMS, please look in the "tpl" branch as it has the files for that version of PHPVMS.
You must also have a SimBrief API key which is expained in Vangelis' module.
You must also register for a free SimBrief account for the form to work as it needs to make a connection to SimBrief itself.

----------------------
INSTALLATION
----------------------
1. Download the files required (See below) and place them in the relevant folders on your servers.

	***Required**
    The lib/skins/YOURSKINNAME/schedule_briefing.php is the main template for this addon.
    	Please place this file in lib/skins/YOURSKINNAME to overwrite the default template.
        If you don't have a custom skin and are using the default "crystal" skin, then please place it in core/templates instead.
    
    The core/common/OperationsData.class.php file is important because it gives you the option to dynamically load the aircraft into the template. If you have modified this file in the past, please only copy the following function into your OperationsData.class.php
    public static function getAllAircraftSingle($onlyenabled = false) {
    
    **Optional**
    
	It is optional if you want to download the "style.css" file. It gives you the custom styles I have used for my form and page. 
	You may want to use your own sites styling for the form and tables.
    
    The lib/images/logos contains the relevant image files for the template.

	If you want to use my own styling, make sure that the simbrief_briefing_style.css is placed in lib/css
		(Or move it into your skin folder and adjust the link)
	If you don't want to use my styling, you do not need the simbrief_briefing_style.css file, but if you upload it anyway,
	take out this line from the schedule_briefing.php
	<link rel="stylesheet" href="<?php echo SITE_URL;?>/lib/css/simbrief_briefing_style.css" type="text/css" />
	On line 2.

2. Change The Styling
	Change "classic-title5" to one of your own header styles

	The "call-action" is a Boostrap3 box. The styling of the box is controlled by "call-action-style1.
	div class="call-action call-action-boxed call-action-style1 no-descripton clearfix"

	This controls the general styling of the container and it's elements that house the tables.
	div class="schedule-briefing"

	This controls the specific table style. You can simply overwrite "briefing-table" with your own style classname.
	table class="briefing-table"

	The "dispinput" styles the input and select form elements on the page.
	select class="dispinput" name="date" id="date"

3. Once you've uploaded the schedule_briefing.php file, you need to also edit the following line at the bottom of the file.

That's it, you should be good to go.

----------------------
Testing It Out
----------------------
1. Bid on a flight
2. Go to "View My Bids"
3. Click on "Pilot Brief"
4. You Should now see your form
5. Adjust the settings you need
6. Press on the "Click to Generate OFP"
7. You should now see your complete OFP with accurate timings and fuel predictions

Enjoy!
