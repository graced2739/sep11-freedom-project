# Entry 4
##### 3/19/22

## Content
Right now I've finished learning watching the videos for my tool. But I actually stopped watching videos up to [Google Sheets - Send Emails Using Apps Script JavaScript MailApp Tutorial](https://www.youtube.com/watch?v=ZcNmur6xiX4&list=PLv9Pf9aNgemv62NNC5bXLR0CzeaIj5bcw&index=12&t=1599s). The reason why I stopped watching tutorials when I came to this video was because the videos after, were unnecessary. I did not need things such as dropdown lists, cross tabs, and combining multiple sheets in one for our homework planner. I also reconsidered watching the playlist for [Google App Scripts- Web App](https://www.youtube.com/playlist?list=PLv9Pf9aNgemt82hBENyneRyHnD-zORB3l). The reason why I reconsidered watching these videos was because our homework planner is on a Google Sheet, we don't need to display it on a web page, we definitely could and try but that would take too much time. But it wasn't like I didn't learn anything new, my partner introduced me to buttons that are able to run code we write in Google App Scripts when we click on it. Seeing how useful it is, I decided to learn it myself and came upon this short yet informative YouTube video:[Google Sheets Button to Run Script: How to Create](https://www.youtube.com/watch?v=e73I-5FkL7E). <br>
From this video I learned that you first have to create a button by going to insert-> drawing and then create a button using any shape you want, basically just customize whatever button I wanted. Then I'll have to open up google app scripts and create a function with specific codes that I want to run and be then save it. After I am done, I'll return back to google sheets, right-click on the button and  three dots should appear on the upper right corner of the button. I should then click on those three dots and click on ‘assign script’ then write the name of the function I want to run. When there’s a message that pops up requiring authorization, I just have to sign in with my gmail, scroll down and click allow and now I should see the how the code works when I press the button. <br>
<br>
Currently for our MVP Plan,we are on the part where we start to make templates for our homework planner. To make these templates I used what I learned about assigning Google App Scripts to buttons and color palettes from [coolors.co](https://coolors.co/). Here are some of the color palettes me and my partner picked out: https://docs.google.com/document/d/1-mn404bzJ8yp27TWLXQjfGH2xvqCur9l67mFqtAlDyA/edit. <br>
Then I used what I learned about buttons to create the first template. So I went and created a button in Google Drawing called Template1 and assgined it a function in Google App Scripts that's also called template1. Here is the code for template1: <br>
```js
function template1(){
   var app = SpreadsheetApp;
  var activeSheet = app.getActiveSpreadsheet().getSheetByName("Homework Planner");
  activeSheet.getRange("A1").setValue("Date:").setBackground("#227C9D")
  activeSheet.getRange("B1").setValue("Monday (mm/dd/yyyy)").setBackground("#17C3B2")
  activeSheet.getRange("C1").setValue("Tuesday (mm/dd/yyyy)").setBackground("#227C9D")
  activeSheet.getRange("D1").setValue("Wednesday (mm/dd/yyyy)").setBackground("#17C3B2")
  activeSheet.getRange("E1").setValue("Thursday (mm/dd/yyyy").setBackground("#227C9D")
  activeSheet.getRange("F1").setValue("Friday (mm/dd/yyyy)").setBackground("#17C3B2")
  activeSheet.getRange("A2:A10").setValue("SubjectName")
  activeSheet.getRange("B2:F10").setValue("Assignments")
  activeSheet.getRange("A2:F2").setBackground("#FFCB77")
  activeSheet.getRange("A3:F3").setBackground("#FE6D73")
  activeSheet.getRange("A4:F4").setBackground("#FFCB77")
  activeSheet.getRange("A5:F5").setBackground("#FE6D73")
  activeSheet.getRange("A6:F6").setBackground("#FFCB77")
  activeSheet.getRange("A7:F7").setBackground("#FE6D73")
  activeSheet.getRange("A8:F8").setBackground("#FFCB77")
  activeSheet.getRange("A9:F9").setBackground("#FE6D73")
  activeSheet.getRange("A10:F10").setBackground("#FFCB77")
  activeSheet.getRange("A1:F1").setFontSize(14).setFontColor("#FEF9EF").setFontWeight("bold")
  activeSheet.getRange("A1:F10").setFontFamily("Lemon")
}
```
The code may seem like a lot but it's very simple. You just have to know that: <br>
* `.getRange` grabs the cells of your Google Sheet
* `.setValue` puts in a word or number into the cell you selected using .getRange
* `.setBackground` sets the background color of the cell
* `.setFontSize` sets the font size of what you put inside the () of .setValue
* `.setFontColor` sets the font size of what you put inside the () of .setValue
* `.setFontWeight` allows you to bold the text or number or make bold text unbolded
* `.setFontFamily` allows you to change how the font style looks <br>
Here is how the first template looks: https://docs.google.com/spreadsheets/d/1u9x8sAYjfahALE2Sx4LzAFeuTPN2YBDw4mKHJAPBQpY/edit#gid=0  (when on Google Sheets click on the sheet titled Homework Planner) <br>
Along with making a button for the first template I also made a button on a separate sheet titled "Other Buttons" to clear the sheet "Homework Planner", here is the code for that: <br>
```js
function clearContent() {
  var app = SpreadsheetApp; 
  var activeSheet = app.getActiveSpreadsheet().getSheetByName("Homework Planner"); //selects the sheet you want the code to run in
  activeSheet.getRange("A1:F10").clear()  //clears everything from cell A1 to cell F10
}
```
### Engineering Design Process
Currently I'm at steps 5 and 6 of the Freedom Porject, which are Create a Prototype and Test and Evaluate the prototype. Since I'm finally done with learning my tool, I can now start to make templates and then incorporate ideas such as sending email and using Google Sheets to add events to Google Calendar. But before me and my partner starts to do the send email and Google Calendar part, we first have to finish all of our templates. As we create each template we have to check if each individual button works the way it was supposed to and see if the code we ran had any mistakes in it. If we do find any mistakes we would have to fix them and if we encounter a problem we'll have to solve them before going onto the next step of our MVP.

### Skills:
The two skills that I need are communication and collaboration. As me and my partner are both done with the bulk of learning our tools, it is time to create our Homework Planner. This means that we would have to communicate to each other about how everything is organized, what color schemes we want, give advice on whether a text looks difficult to see with the background color it is on, what other buttons we should do, etc. We also have to make sure that each of us is doing our part of the project and that not just one person is doing the majority of the work. We should also communicate whether we need help from the other person or clear out any confusion we have.

[Previous](entry03.md) | [Next](entry05.md)

[Home](../README.md)
