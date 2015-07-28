# Checkout my other projects #

PHP fast and easy to learn framework http://alchemyframework.org/

Simplified OOP for javascript http://code.google.com/p/jsclassextend/

Lightweight dom library https://github.com/dkraczkowski/dom.js


Simple Javascript lib that allows you to upload asynchronusly files on the web.

**Requires JQuery!**

## USAGE ##
```
var uploader = $('#HTMLTagId').ajaxUpload(parameters);
```


### PARAMETERS LIST ###

  * string_**url** - upload, url
  * string_ **name** - name for input file tag
  * callback_**onComplete(result)** - called when upload is completed
  * callback_ **onSubmit(input)** - called when input file submited



### EXAMPLE ###
html:
```
<a class="UploadButton" id="UploadButton">UpladFile</a>
<div id="InfoBox"></div>
```
js:
```
$("#UploadButton").ajaxUpload({
url : "upload.php",
name: "file",
onSubmit: function() {
    $('#InfoBox').html('Uploading ... ');
},
onComplete: function(result) {
    $('#InfoBox').html('File uploaded with result' + result);
}
});
```

php
```
$file = $_FILES['file'];
move_uploaded_file($_FILES["file"]["tmp_name"], 'upload_dir/' . $_FILES["file"]["name"]);
echo 'OK';
```