1. Set titles on pages. Should be something like {{page-name}} - {{application}}. Go have a look at any large website (eg gmail, bbc etc). Set a favicon for the site.

2. There should always be an immediate reaction from the app when someone pushes a button etc. This can be the text of the button changing (eg from "go" to "loading") or activating a spinner. Buttons should also be disabled for the duration of the operation to ensure people can't accidentally double click etc.

3. On most resources, eg datastores and timestores, there is a "name" property and a "title" property. Name is system name and should generally never be shown or edited by users. "title" is the proper field to use when displaying to users.

4. There should always be visible validation near or in data entry inputs. Always ensure the message is meaningful to an end user. Check when you test!

5. Any general error messages should be meaningful to end users and nice and friendly.

6. Transactional data should by default be sorted by date descending (newest at the top of the page).

7. Collections of things (eg members, activities, rewards, email templates) should be sorted by display name/ title by default. This includes when listing those in dropdowns.

8. Server side paging must be used wherever data can get large (more than 100 entries) eg members, transactional info.

9. When testing a feature, always test bad cases as well - eg rubbish data, incorrect permissions, out of bounds, wrong data types etc. Try mess it up. Don't just do it the way it is supposed to be used. If you have options, test with all the options. Be very paranoid here!

10. When testing, also use production volume of data, eg when doing an upload or download, test with the max expected data sizes.

11. There should generally be alternative or more than 1 way to achieve a particular task. Eg you may award activity from the activities list, from a member's profile, from a quick link on the timeline or from the people directory. Think about different flows.

12. Test how modifying existing data affects the system. Don't assume that data will be setup once and left. Eg. if there is a unique field, make sure the system checks when the user updates that there is not a conflicting field. Display a user appropriate message or validation error.

13. Try use sentences and friendly language on front ends. Avoid terse or technical field names and headings. This makes help inherent in the UX Eg

"People in the group --Choose group-- can award this activity to people in the group --Choose group--"

rather than 2 terse inputs

Awarders : Select

Awardees : Select

14. Provide a mechanism to switch off or remove data. Eg. Have an "account deactived" mechanism on members, or "active" on activities. Alternates are date range validity periods. Ensure that these are honoured throughout features, eg. can't award points to members with deactivated accounts, or can't log in when accounts are deactivated. Should also filter out this data from operational lists or displays (eg, if an activity or reward is deactivated it should not even show on a list as an option to click). Also it is better to provide a button to activate this, rather than just a drop down or tick box. This provides an escape mechanism for the user.

15. Always log, always. Ensure that a stack trace is captured along with input data and state. Ensure there is logging to file, console and a logging service (eg. loggly). Set notifications for errors.

16. Check where users can setup names, descriptions or capture data that the resulting display renders correctly when long entries are provided. May need to use ellipses or "more" (eg like long statuses on Facebook etc). Check if HTML data is rendered as HTML (normally raw in most languages)

17. Ensure that functions that users are not able to access (eg permissions, limits, out of times to award) are greyed out or if appropriate just not shown. This avoids people clicking and getting unnessesary errors and consequently frustration.

18. It's normally a good idea to trim whitespace from user inputs (especially credentials and other inputs that need to be exactly matched). Also don't be case sensitive where you don't need to be.

19. Don't assume calls to external systems will always work. Properly handle errors by accepting only expected codes and using the languages error mechanism to report the errors (eg. exceptions in C#, callback(error) in node)

20. Honour the style conventions of the language you are coding in.

21. Layouts should line up - eg left align labels or text boxes etc.

22. Don't skimp on padding, don't make things squashed

23. Test on all target browsers and devices.

24. Exports from the system should have a nice date and meaningful file name eg, 'Social Activities - 2015-05-01'