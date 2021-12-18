# Entry 2
##### 12/13/21

After setting the tool that I decided to use, for the past month I've been learning and using my tool. At first I just started with written tutorials from GoogleAppScripts itself: [Link to GoogleAppScripts](https://developers.google.com/apps-script). But then after using that to learn, I began to feel more confuse because I had no idea what certain codes do. <br>
For example: <br>
* getActivespreadSheet()
* getActiveSheet()
* .getRange()
* .getValue()

So then I decided to look up YouTube tutorials and to my luck there were two playlists about GoogleAppScripts. One is mainly about using GoogleAppScripts in [Google Sheets](https://www.youtube.com/playlist?list=PLv9Pf9aNgemv62NNC5bXLR0CzeaIj5bcw), while the other one was about using [GoogleAppScripts](https://www.youtube.com/playlist?list=PLv9Pf9aNgemt82hBENyneRyHnD-zORB3l) for a Web Page which can connect to Google Sheets. <br>
So far I watched the first two videos in the first playlist. The first video is called: Read and Write to Ranges and Cells.<br>
From watching the video I learned that cells are the (row, column) you want to specify and change. This video also cleared up the above code on what they do:<br>
* getActivespreadSheet() method = gets the current active spreadsheet (the Google Sheet you created)
* getActiveSheet() method = gets the current active sheet (we know that you can create multiple sheets inside Google Sheets so this method will only get the one that you are on
* .getRange(a1Notation) = selects a particular cell/cells you want 
  * The a1 Notation should be something like D2. 
  * It can also be D2-F8
* There are also other types of notations you can have:
  * .getRange(row, column) = another way to select a particular cell, this time just using the row and column number: Ex: .getRange(6, 2)
  * .getRange(Integer row, Integer column, Integer numRows) Ex:  .getRange(2, 2, 3) = starts at row 2 and column 2 then goes down 3 rows
  * .getRange(Integer row, Integer column, Integer numRows, Integer numColumns) Ex: .getRange(4, 7, 4, 3)
    *   Then you can  use `.setValue(value)` to write out a value in thw cell/cells you specified, or write out text by using “” inside the ().
* You can use activeSheet.getRange().getValue() and set it with a var to store the value that’s in the getRange.
* Then you can do activeSheet.getRange().getValue(variableName), to get the cell/cells in getRange to have the exact same value as the value stored in the variable.

I then used what I learned to write my code:
```js
var app = SpreadsheetApp;
  var ss = app.getActiveSpreadsheet();
  var activesheet = ss.getActiveSheet();
  var tempText = activesheet.getRange(6, 2).getValue();
  activesheet.getRange(1, 4).setValue(tempText);
  activesheet.getRange("D2:F8").setValue("OMG!!!");
  activesheet.getRange(1, 2).setValue("Serious");
  activesheet.getRange(10, 1, 8).setValue("Hello");
  activesheet.getRange(4, 7, 4, 3).setValue(8);
  
}
```
To see the output go to this link: https://docs.google.com/spreadsheets/d/1akjubMZKfPTeyXBdRqjHtrUmeRwyi7ttIkpc4odkuRo/edit#gid=146777522 <br>

Then for the second video called: For Loops, Looping Through Cells, Variables, Comments, I basically just use what I learned in the first video and my knowledge of for loops to change the specified cells; the code is extremely long so here is the link: https://script.google.com/home/projects/1VdrMXzPno8Y-u24PpYAkgUADPLX4VEsboUmJ2widjbZbVvqfQh2n8RxN/edit. <br>

Here is the link for the output: https://docs.google.com/spreadsheets/d/1lzq-ldLP3cMjImcCt5Dni0rqGhh79PwJPJkIyfy16oo/edit#gid=0.<br>

Then after watching these two videos I found on a [website](https://developers.google.com/apps-script/samples/automations/send-emails) on how to send emails directly on Google Sheets, so I tried it out and it worked!
```js
function sendEmails() {
  var sheet = SpreadsheetApp.getActiveSheet();
  var startRow = 2; // First row of data to process
  var numRows = 3; // Number of rows to process
  // Fetch the range of cells A2:B4
  var dataRange = sheet.getRange(startRow, 1, numRows, 2);
  // Fetch values for each row in the Range.
  var data = dataRange.getValues();
  for (var i in data) {
    var row = data[i];
    var emailAddress = row[0]; // First column
    var message = row[1]; // Second column
    var subject = 'Sending emails from a Spreadsheet';
    MailApp.sendEmail(emailAddress, subject, message);
  }
}
```
What's written on Google Sheets itself: https://docs.google.com/spreadsheets/d/1hTJEIfW_F26kz_vmxQpEw6x5mrY1GEsPKOxs9v8u38E/edit#gid=0
But then I figured that there were some problems such as you can't write the proper syntax of an email with the start, message and closing, so to fix that issue I'm thinking of letting the users copy and paste a template into a single a cell and then replace it with what they need to write: <br>
Dear Mrs. <br>

I need help with the homework. <br>

From, student <br>
I found another problem which was that even if there's no message, it'll still send an email as long as long as there's a valid email. So to fix that I would need to dig and learn more, luckily for me there's a video in the first playlist about sending an email which I will view in the future. So this is what I've tried so far.<br>

The Engineering Design process I'm at are steps 3 and 4, brainstorm possible solutions and plan the most promising solution. right now I'm trying out things I've learned and thinking of ways I can use them in a homework planner. For example the sending emails directly from Google Sheets is helpful for users that have questions for their teachers about their homework. Me and my partner are also thinking of creating templates using what I learned in the two videos and adding buttons to send one email at a time instead of all at once, especially since emails can still be send even if there's no message. We still have many ideas for our Homework Planner and would need to learn more. The skills I have to use is How to Learn and Organization. I need to know how to learn because even though there are videos explaning different concepts, I have to be hands on and try tinkering and changing small details. I also have to pick the best resources that work for me (I changed from reading how to use GoogleAppScripts to watching videos about it). I also have to be organized by writing down what I did on a separate document which is useful for me to look over and review old concepts. I also have different Google Sheets for each video so I won't get confused on where to look for a specific concept, they are also named the video names so I would know which is which. <br>

Now during the break I would continue learning using the videos, I would like to watch through 2-3 more videos and combine all the concepts I learned into a single Google Sheet. 







[Previous](entry01.md) | [Next](entry03.md)

[Home](../README.md)
