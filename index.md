## How to add multiple upload iframe inside InfoPath
You can find script [here](https://github.com/mohamadhijazi/InfoPath/)
### Step1

Follow link and add html inside textarea, add the below

```markdown
https://johnliu.net/blog/2011/5/30/infopath-2010-embed-html-for-rich-and-web-forms.html

<?xml version="1.0" encoding="utf-8"?>
<html>
<myhtml>
<p xmlns="http://www.w3.org/1999/xhtml" id="UploadIframe" data-attr="5" data-attr-url="uploadpageUrl"></p>
</myhtml>
</html>
```

### Step2

Create new empty page and add the InfoPath webpart, and add script editor paste the below js code makesure you have JQ reference

```markdown
<script type="text/javascript" id="onetidPageTitleAreaFrameScript">
//form page
	 var oldId="";
function fixIframe(){
var val=$("[buttonid='uniqueBtnID']")[0].value;
if(val && val!=""){
if(!$("#UploadIframe").hasClass("ready")|| oldId=="" ||oldId!=val){
$("#UploadIframe").addClass("ready");
var element = document.getElementById("UploadIframe");

oldId=val;
var url=element.getAttribute("data-attr-url");

element.innerHTML="<iframe src='"+url+"?IsDlg=1&submittile="+val+"' width='100%' height='400px'></iframe>"
}
}
}
function repeat(){
setInterval(function(){ fixIframe(); }, 200);
}
function  DismissConflictDlg(that, event){
$(".ms-dlgContent").hide();
$(".ms-dlgOverlay").hide();
alert("Can not replace file please rename and upload again");
$("#UploadIframe").removeClass("ready");
}
$(document).ready(function(){

 repeat();
})
</script>
<style>
#contentRow {
    margin-top: -32px;
	padding-top:0px !important;
}
.ms-backgroundImage #sideNavBox{display:none}
.ms-backgroundImage #contentBox{margin-left:50px}
.ms-backgroundImage  div#s4-titlerow {
    display: none !important;
}

.ms-backgroundImage  div#s4-ribbonrow {
    display: none;
}

.ms-backgroundImage  div#suiteBarDelta {
    display: none;
}
 /*fix multiple line text areadiv[scriptclass="RichTextBox"]{display:none !important;}
div[scriptclass="RichTextBox"] +textarea{display:block !important;min-width: 400px;}

div[scriptclass="RichTextCollection"] >div>div{display:none !important;}

//AttachmentsPlaceholder textarea screen tip//
div[title="AttachmentsPlaceholder"] div[scriptclass="RichTextBox"]{display:block !important;}
div[title="AttachmentsPlaceholder"] div[scriptclass="RichTextBox"] +textarea{display:none !important;}
*/
</style></DIV>
```

### Step3

Create new empty page and add the InfoPath webpart, and add script editor paste the below js code makesure you have JQ reference

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

### Step4

Create new empty page and add the InfoPath webpart, and add script editor paste the below js code makesure you have JQ reference

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```
