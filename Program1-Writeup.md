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
#### gzip
  The gzip utility uses Lempel-Ziv (LZ77) compression techniques to reduce the size of the specified files. For each file specified, the original file is deleted and replaced with the compressed version which has the same file name as original with the file extension .gz appended. The compressed file has the same ownership modes, access time, and modification time as the original. When you do not specify any files to be compressed or specify - as a file name, gzip reads from the standard input, compresses what is read, and writes the result out to the standard output. The gzip utility will not attempt to compress special files.
  
#### zip
zip is a compression and file packaging utility for Unix/Linux. Each file is stored in single .zip {.zip-filename} file with the extension .zip.It won't compress your files down a ton, but it's super fast and you don't need to install any extra software. Great for Windows and Mac users.zip combines both the archiving and compression in one program.
  
