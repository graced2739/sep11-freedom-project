# Entry 5
##### 4/25/22

### Content
As said before in blog 4, I've already finished learning my tool. Now I needed to finalize and complete my MVP plan. On my MVP plan, me and my partner planned to have a google sheet that's able to send emails to teachers directly from Google Sheet. We also wanted another google sheet that's able to add events to Google Calendar directly from google sheets. Here is how it looked like at first for the Gmail sheet, when I was still learning the tool: https://docs.google.com/spreadsheets/d/1OU3k-T-W0HtdFb7hOoku4eyfY4pqkcBAwXrfdkyoi6k/edit?usp=sharing. <br>
Here is the code for it:
```js
function myFunction() {
  var ss = SpreadsheetApp.getActiveSpreadsheet().getActiveSheet();
  var lr = ss.getLastRow();
  
  
  for(var i = 2; i <= lr; i++ ){ //i starts at row 2 where the first email is written, the for loop would loop through all the emails since var lr gets all the rows that has values
    var email = ss.getRange(i, 1).getValue(); //gets the email in each row 
    var subject = ss.getRange(i, 2).getValue();
    var message= ss.getRange(i,3).getValue(); //gets the value in row 1, column 1, assign it to a variable to use for later
    //var currentClass = ss.getRange(i, 3).getValue(); //gets the class in all of the rows's third column
    

    MailApp.sendEmail(email, subject, message); //email = email being sent to, "testing" = subject name, messageInEmailForm = body of email;
  }
}
```
Here is how it liked like at first for the Google Calendar Sheet: https://docs.google.com/spreadsheets/d/1k5NqLwTSRWUly2Krm7KSbbGLVKKpTCD3Fs_H5Z8e49g/edit?usp=sharing.
Here is the code:
```js
function addEvents(){ //imports events from Google Sheets to Google Calendar
  var ss= SpreadsheetApp.getActiveSpreadsheet().getActiveSheet(); //get sthe current active spreadsheet which is sheet2
  var dataRange = ss.getRange("A4:E16").getValues(); //gets all the values from A4 to E16
  var cal = CalendarApp.getCalendarById("graced2739@hstat.org");
  Logger.log(dataRange); //lets you see the values and shows you the arrays
  for(var i = 0; i < dataRange.length; i++){
    cal.createEvent(dataRange[i][0], dataRange[i][1], dataRange[i][2], {location: dataRange[i][3], description: dataRange[i][4]})
    Logger.log(dataRange[i]); //adds events to your google calendar based on what you wrote in each row
  }
}
```
As you can see, the two Google Sheets started out very plain and there's no button for you to press that'll run the code for you, you'll actually have to go to extensions < app scripts, then run the code manually. <br>
<br>
Here are the sheets finalized: https://docs.google.com/spreadsheets/d/1u9x8sAYjfahALE2Sx4LzAFeuTPN2YBDw4mKHJAPBQpY/edit#gid=2042991207
As you can see they are much more colorful thanks to my partner Kimberly, and has buttons that when you click would run the code for you. There's also an additional 'clear' button for the 'Send Email' sheet which allows the user to delete what they wrote when they made a mistake. Along with the new buttons and a addiotnal feature, we also added a note to the Google Sheets to tell the user how to use these tools properly. The code before and after are mostly the same though. <br>
Gmail code:
```js
function sendEmail(){
  var emailSheet = SpreadsheetApp.getActiveSpreadsheet().getSheetByName("SendEmails");
    var email = emailSheet.getRange("E10").getValue(); //gets the email from cell E10 and stores in a variable called email 
    var subject = emailSheet.getRange("E14").getValue(); //gets the subject from cell E14 and stores it in a variable called subject
    var message= emailSheet.getRange("E18").getValue(); // gets the message from cell E18 and stores it in a variable called message

    MailApp.sendEmail(email, subject, message); 
}

function eraseEmail(){
  var emailSheet = SpreadsheetApp.getActiveSpreadsheet().getSheetByName("SendEmails");
  var rangesToClear = ["E10", "E14", "E18"]; //saves the cells that the user writes in so that they can erase it
  for(var i = 0; i < rangesToClear.length; i++) {//loops through the array 
    emailSheet.getRange(rangesToClear[i]).clearContent();// as i increases, the element in the rangesToClear gets deleted one by one until 'i' is equal to the array length, allowing all the cells the user writes in to be deleted when users click the  'clear' button
  }
}
```
Google Calendar Code:
```js
function addEventsToGoogleCalendar(){ //imports events from Google Sheets to Google Calendar
  var ss= SpreadsheetApp.getActiveSpreadsheet().getActiveSheet(); //gets the current active spreadsheet which is sheet2
  var dataRange = ss.getRange("A2:E15").getValues(); //gets all the values from A2 to E16
  var cal = CalendarApp.getCalendarById("graced2739@hstat.org"); //gets the google calendar where your event can be added by using your gmail
  for(var i = 0; i < dataRange.length; i++){
    cal.createEvent(dataRange[i][0], dataRange[i][1], dataRange[i][2], {location: dataRange[i][3], description: dataRange[i][4]}) //grabs the values underneath Event, Start, End, Location and Description, starting from row 2 and ending on the last row
    Logger.log(dataRange[i]); //lets you see what would be added
  
  }
}
```
The only big difference is that for the finalized code, there's a function called 'eraseEmail'. Now I'll be talking about other things I worked on for my MVP. I created more templates and also added a button called 'Delete Everything' which deletes everything from the Google Sheet titled 'Homework Planner', here is the code for that:
```js
function clearContent() {
  var app = SpreadsheetApp; //locates the google sheet we are in: "Freedom Project"
  var activeSheet = app.getActiveSpreadsheet().getSheetByName("Homework Planner"); //all code underneath clearContent would only work in the google sheet titled "Homework Planner"

  var ui = SpreadsheetApp.getUi();
  var user = ui.alert('Are you sure you want to Delete everything in your planner?', ui.ButtonSet.YES_NO);//when the button is clicked the user will recive a alert message where they either click a button that say yes or a button that says no

  // if the the user clicks the yes button then the Homework planner will be deleted 
  if (user == ui.Button.YES) {
  activeSheet.getRange("A1:F10").clear() //.clear deletes everything in the cell you slected, the background color, text, everything
  }
  //if the the user chooses to click the no button then a alert will apper telling the user the nothing has been deleted
  else {
     ui.alert('Do not worry nothing has been deleted.');
  }
}
```
My partner added on to what I wrote by adding lines 80-91. This is basically how I worked to finish my MVP project. I'm sure my partner has more to say on our MVP project as she worked on separate things.

### Engineering Design Process
Now I'm at Steps 6 and 7 of the Engineering Design Process. These steps are test and evaluate the prototype and improve as needed. Right now, me and my partner have finished testing and evaluating because before we turned out MVP plan in, we made sure that everything works and that using of homework planner is at easy as possible. This was why we added notes on how to use the different components of our Homework Planner. Now we needed to improve or go beyond our MVP plan. One idea my partner has is to tweak the 'Delete Everything' button where it'll only delete the background but leave the words the user wrote. She also had an idea that for the google sheet titled 'custom', the table can be different colors instead of just one. And I on the otherhand would like to add more templates to our project.

### Skills
The two skills I used are Time Management and Attention to Details. I need time management skills because even if the teacher gave us plenty of time for our project, I could've easily just waited until break to do everything, but I didn't. I took one step one at a time to complete the project with my partner and also made sure that she was on time with what she was responsible with. That way we were able to complete and check if everything works before the deadline. I also used the skill attention to details because it's very hard to know where our code has a bug, so we'll have to read each error message carefully, decipher them, then fix the code. Sometimes the code doesn't need fixing like the message that pops up for the Google calendar sheet when a user presses 'Create Event', so I'll need to keep that in mind and tell the user so they wouldn't panic and think that the code needs fixing when it doesn't. 
[Previous](entry04.md) | [Next](entry06.md)

[Home](../README.md)
