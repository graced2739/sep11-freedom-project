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

The second video I watched was called 

[Previous](entry02.md) | [Next](entry04.md)

[Home](../README.md)
