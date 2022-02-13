# Entry 3
##### 2/7/22


### Content
While learning my tool, I continued to use the YouTube tutorials from last time, focusing especially on the tutorials for [Google Sheets](https://www.youtube.com/playlist?list=PLv9Pf9aNgemv62NNC5bXLR0CzeaIj5bcw). So far I watched another 6 videos. The first video I watched was titled [Get & Set Cell Value in Other Sheets](https://www.youtube.com/watch?v=_ulFKsrpxi8&list=PLv9Pf9aNgemv62NNC5bXLR0CzeaIj5bcw&index=3). What I learned in this video was how to write javascript code for a speciic google sheet when there are multiple sheets. So far, I had only written code for one specific sheet, now following the video's tutorials there are three sheets titled in chronological order: Sheet1, Sheet2, Sheet3. Here is a code snippet of how to write code for a specific sheet:

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
<br>
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
  if(workingCell > 50){
    activeSheet.getRange(i,2).setValue("High");   //changed row to 'i' since the row changes each time 'i' gets added
  }else{
    activeSheet.getRange(i,2).setValue("Low"); //changed row to 'i' since the row changes each time 'i' gets added
  }
 }
```

[Previous](entry02.md) | [Next](entry04.md)

[Home](../README.md)
