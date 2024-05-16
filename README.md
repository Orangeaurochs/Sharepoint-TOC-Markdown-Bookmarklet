# Sharepoint TOC Markdown Bookmarklet

A bookmarklet to extract headers from a Sharepoint web document then produce Markdown code for a Table of Contents with links in an indented list. Can be dropped into a Sharepoint Markdown web part. To install the bookmarklet, add the following code into the URL or Location section of a new bookmark:

```javascript:(function() {var report = "## Contents\n";for (i=1; i<=6; i++) {    var headers = document.getElementsByTagName('h'+i);    for (j=0; j<headers.length; j++) {        var padding = "";        for (k=0; k<i; k++) {          padding += " "        }        padding += "- ";        var header_id = headers[j].id;        header_id = header_id.replace('(','%2528');        header_id = header_id.replace(')','%2529');        report += padding + "[" + headers[j].textContent + "](#" + header_id + ")\n";    }}if (confirm ("CLICK OK TO COPY TO CLIPBOARD\n\n" + report)) {  navigator.clipboard.writeText(report);}})();```

To use the bookmarklet:
* Navigate to a Sharepoint webpage. Don't click on Edit yet.
* Click on the bookmarklet on the bookmarks toolbar.
* Click on OK to copy the Markdown code to the clipboard.
* Edit the Sharepoint webpage.
* Create a new Markdown web part where you want the TOC to be.
* Paste the Markdown code into the black section of the box.
* Save the webpage.
* To update the TOC, it is easiest and quickest to delete the web part and start again.
