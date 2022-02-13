# Entry 3
##### 2/7/22


### Content
While learning my tool, I continued to use the YouTube tutorials from last time, focusing especially on the tutorials for [Google Sheets](https://www.youtube.com/playlist?list=PLv9Pf9aNgemv62NNC5bXLR0CzeaIj5bcw). So far I watched another 6 videos. The first video I watched was titled [Get & Set Cell Value in Other Sheets](https://www.youtube.com/watch?v=_ulFKsrpxi8&list=PLv9Pf9aNgemv62NNC5bXLR0CzeaIj5bcw&index=3). What I learned in this video was how to write javascript code for a specific google sheet when there are multiple sheets. So far, I had only written code for one specific sheet, now following the video's tutorials there are three sheets titled in chronological order: Sheet1, Sheet2, Sheet3. Here is a code snippet of how to write code for a specific sheet:

```js
function learnBasics() {
var targetSheet = app.getActiveSpreadsheet().getSheetByName("Sheet3");
 targetSheet.getRange(1,2).setValue("Something");
 var valOfTargetSheet = targetSheet.getRange(1,2).getValue();
 app.getActiveSpreadsheet().getSheetByName("Sheet1").getRange(15,2).setValue(valOfTargetSheet);

}
```
The `.getSheetByName("sheetName")` is a new method I learned. It basically just focuses on the specific sheet you selected using the sheet's name. But before you use `.getSheetByName` you have to use `app.getActiveSpreadsheet()` because you have to get the whole google sheet before you select a specific sheet from multiple sheets. Then after that you can set get the placement of a specific cell (.getRange) you want a string or number to be put into using `.setValue`. You can also get values from another sheet by also using `.getSheetByName` then by doing `.getRange()` to get the value inside of that cell. Then by writing variables you can place the value you want, an example of this is getting the value of `"Something"` from Sheet3 into a specific cell in Sheet1 (lines 12-13) <br>
That's basically a summary of this tutorial.

The second video I watched was called [Clear Contents](https://www.youtube.com/watch?v=LiKF6Vq3P-s&list=PLv9Pf9aNgemv62NNC5bXLR0CzeaIj5bcw&index=4). In this tutorial I learned three new methods: <br>
* .clearContent()
* .clear()
* .clearFormat() <br>
<br>
What `.clearContent()` does is that it clears value in the cell you select using `.getRange()`. This means that numbers inside cells would get deleted. <br>
What .clear() does is that it clears everything inside the cell you selected, meaning values, background color would all get deleted. <br>
What .clearFormat() does is that it only deletes the format in cells meaning it'll only delete things like background color but leave the value. <br>

The third video I watched was called [Create Custom Functions (UDF) using Apps Script with AutoComplete Tutorial](https://www.youtube.com/watch?v=SUs74nwFMFY&list=PLv9Pf9aNgemv62NNC5bXLR0CzeaIj5bcw&index=5), this video tutorial taught me how to write custom functions. Here is an example: <br>
```js
//multiplies two numbers
//arg1 is one of the numbers used for multiplication
//arg2 is one of the numbers used for multiplication 
function MULTIPLY2NUMBERS(arg1, arg2){
  var result = arg1 * arg2;
  return result;
}
```
What this function does is that it takes two numbers (arg1, arg2) together. To make this function work you have to first go onto Google Sheets and place two numbers on any two cells. For an example let's place the number 6 on cell B2(arg1) and place the number 2 on B3(arg2). Then to use this function you click on another cell and write `=FUNCTIONNAME(arg1,arg2)` then hit enter and you will get the result which is 12.
<br>
The fourth video I watched was called [If, then, else if, else statements](https://www.youtube.com/watch?v=vHZAQ-QBoPY&list=PLv9Pf9aNgemv62NNC5bXLR0CzeaIj5bcw&index=6), which is extremely similar to what I learned in class except that I had specify specific rows, use `.getRange()` and `.setValue()`. Here is an example: <br>
```js
function myFunction() {
  var app = SpreadsheetApp;
  var activeSheet = app.getActiveSpreadsheet().getActiveSheet();
 
 //starts at i=7 because the row starts at 7
 //it is i<14 because the last row is at row 13(inclusive)
 for(var i = 7; i < 14; i++){
 
  var workingCell = activeSheet.getRange(i,1).getValue(); //changed row to 'i' since the row changes each time 'i' gets added
//checks if the value in row 7, column 1 is greater than 50, if it is return "High" in the cell next to it
//if it is not return "Not High" in the cell next to it
//continues for rows 8 to 13
  if(workingCell > 50){
    activeSheet.getRange(i,2).setValue("High");   //changed row to 'i' since the row changes each time 'i' gets added
  }else{
    activeSheet.getRange(i,2).setValue("Low"); //changed row to 'i' since the row changes each time 'i' gets added
  }
 }
```
The fifth video I watched was called [Read Range to a Javascript Array & Write to a Range](https://www.youtube.com/watch?v=v1nvDkDY-3g&list=PLv9Pf9aNgemv62NNC5bXLR0CzeaIj5bcw&index=7), this tutorial is less important than the rest because there will be no use for it in my Freedom Project so I'll just go ahead and talk about the sixth video I watched. <br>

The sixth video I watched was called [Fill Down Formula (Set a Formula & Copy Down Autofill](https://www.youtube.com/watch?v=cCBtsQGtzoQ&list=PLv9Pf9aNgemv62NNC5bXLR0CzeaIj5bcw&index=9), in this tutorial I learned that I can use formulas directly using google sheets by writing an equal sign and using values in cells to use in mathematical equations. An example of this is `=(A1+B1)*C1`. <br>
Then you can extend this formula to other rows by using the blue box on the bottom hand side of the cell where you wrote the formula and drag it to the last row you want the formula to take action.
<br>
Now to do this directly on GoogleAppScripts it is a lot more complicated: <br>
* first you have to use the `.setFormula` method to write the formula you want to use
* Then you have to figure out where you want to paste the formula 
* Then use the method `.getLastRow` to figure out the last place you want to paste the formula (optional)
* Then use .getRange(Integer row, Integer column, Integer lastNumRows,) to get all the places you want the formula to work
* Then use .copyTo(destination) to copy the formula to the places you want it to be copied
```js
function myFunction() {
  var ss = SpreadsheetApp.getActiveSpreadsheet().getActiveSheet();
  ss.getRange("D1").setFormula("=(A1+B1)*C1")
  
  var lr = ss.getLastRow(); //gets the last row of numbers
  var fillDownRange = ss.getRange(1, 4, 7) //all the places you want the formula to work
  ss.getRange("D1").copyTo(fillDownRange) //allows the formula to work in other cells that you specified on the line above

}
```
Here is the link to the Google Sheets so the code makes more sense: https://docs.google.com/spreadsheets/d/1O4unBAOBj7oZhCSqyba6ql_6AP-5GLUMLamRFu6Iwhc/edit#gid=0. Double click on the numbers in column D.
<br>
That is basically the summary of what I learned so far. The next agenda for me is to continue learning GoogleAppscripts using all the Youtube tutorials that are provided for me. After I finish this playlist I would go on to the next playlist which is using GoogleAppScripts with a combination of HTML and CSS, which is similar to what I'm learning right now. Hopefully after I watch all the videos and get a good grasp on using GoogleAppScripts, me and my partner can go on to start making our project. 

### EDP
For the engineering design process I'm at is still steps 3 and 4 which are brainstorming possible solutions and plan the most promising solutions. The reasons why I'm still at these steps is because I still have a lot more learn meaning that there could always be new ideas that pop up whenever I watch these tutorials. I also need to communicate with my partner and show her what I learned so far so she could use what I learned to also brainstrom more ideas for our Homework Planner.

### Skills
One skill I used is consideration because since I have a variety tutorial laid out for me I have choose and focus on ones that are able to help me make a Homework Planner. An example of using the skill consideration was when I watched the video about how to read range to a javascript array. This tutorial is unnecessary and will not help in making a homework planner, and like future videos that I'll watch I have to consider which one would aide my development of the freedom porject and which is unneccesary or unusable. The second skill I used is time management because since I have so many videos to watch I need to make sure that I need to watch all of them, take notes on all of them and still make sure that I have adequate time developing my project. So I will be planning on watching at least one video a week. 

[Previous](entry02.md) | [Next](entry04.md)

[Home](../README.md)
