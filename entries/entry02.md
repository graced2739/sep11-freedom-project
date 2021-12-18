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

   







[Previous](entry01.md) | [Next](entry03.md)

[Home](../README.md)
