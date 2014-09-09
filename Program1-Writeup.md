#Program1-Writeup.
## CSV to JSON Conversion.

I actually prefer to load a CSV file into the page and convert it into JSON with JavaScript.
First I take the whole CSV file and split it into an array of lines. Then, I take the first line,
which should be the headers, and split that by a comma into an array. Then, I loop through all the lines
(skipping the first one) and inside, I loop through the headers and assign the values from each line to 
the proper object parameters. At this point, you probably want to just return the JavaScript object, 
but you can also JSON.stringify the result and return the JSON object.

```
//var csv is the CSV file with headers
function csvJSON(csv){

  var lines=csv.split("\n");

  var result = [];

  var headers=lines[0].split(",");

  for(var i=1;i<lines.length;i++){

	  var obj = {};
	  var currentline=lines[i].split(",");

	  for(var j=0;j<headers.length;j++){
		  obj[headers[j]] = currentline[j];
	  }

	  result.push(obj);

  }
  
  result; //JavaScript object
  return JSON.stringify(result); //JSON
}
```
