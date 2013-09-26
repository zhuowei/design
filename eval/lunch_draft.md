---
layout: default
title: Design Evaluation of the StarRez Bagged Lunch ordering system
permalink: /eval/lunch_draft.html
---

At Chestnut Residence, the dormitory I live in, the residents can order bagged lunches using a [webpage](http://www.89chestnutlunchbag.info/lunchbag/index.php).

To quote an advertisement: it tastes awful, but it works.



- It does what it needs to do
 - Allows students to order lunches two days in advance
 - Kitchen staff prepares lunches according to order
- But it does it in a horrible way
 - economy: the interface is... too economical in some places, not economical enough in others
  - Website does not look "pretty" - interface sparse, no fancy graphics
  - Yet has extra menu for next month
   - Perhaps link menu displayed to current month selected?
   - Maybe display menu in-line with the actual select-a-date table? No duplicate calendar
   - also, menus open in a new tab - perhaps open them in-line somehow so people don't have to flip back and forth between the two pages
  - Admin Login bar not necessary - admins could have separate page
   - e.g. Google Play, the Android app store, has one page for developer login and another for customers
  - Don't need user to enter student number every time - page can save student number
  - Loads full-sized menus even if user doesn't click on them
   - Slow page loads; takes up user's time
 - elegance: not intuitive as it doesn't follow existing convensions
  - Calendar is shifted - corrupt display
   - Engineering failure here - failed to test website on new browsers and fix bug
   - Confusing for people trying to order lunch for a particular day of the week
  - The clock is wrong. ?!
   - DO YOU EVEN TIMEZONE? Also, clock only updates when page refreshes
   - Can detect current user's timezone from local machine. Use it?
   - Or, since most users will be in Toronto, set the timezone to EST and stick to it
   - Probably not very confusing, as users can check their own clocks
   - Why have a clock anyways, if the users can check own clock?
  - Displays "Sandwich/2nd sandwich/deluxe sandwich" instead of the actual names of the sandwiches
   - inconvenient for the user as he/she has to look it up in the menu
 - Safety
   - Fairly good
   - Days where lunch cannot be ordered are greyed out
   - so people won't go hungry because they incorrectly believed they ordered lunch
   - Confirms that one entered the correct student ID by showing one other information about oneself
   - Clear green (visual cue) that lunch was ordered
   - (The lack of indication in the list at the bottom is confusing though)
   - Should help student order meals on a schedule
     - Too easy to miss a lunch day
     - Perhaps let students repeat an order for a few weeks?

 - Resilience
  - Page has 8 errors on W3C Validator
    - http://validator.w3.org/check?uri=http%3A%2F%2Fwww.89chestnutlunchbag.info%2Flunchbag%2Findex.php&charset=%28detect+automatically%29&doctype=Inline&group=0
  - Browsers do not render the HTML correctly
  - Already we can see error in rendering calendar
  - See rendering with Internet Explorer vs Chrome:
    - Issue as many students are likely to be running Chrome/Firefox as they are more tech-savvy

