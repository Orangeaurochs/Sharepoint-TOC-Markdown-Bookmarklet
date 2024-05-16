# Sharepoint TOC Markdown Bookmarklet

To install the bookmarklet, add the following code into the URL or Location section of a new bookmark:

```javascript:(function() {var report = "## Contents\n";for (i=1; i<=6; i++) {    var headers = document.getElementsByTagName('h'+i);    for (j=0; j<headers.length; j++) {        var padding = "";        for (k=0; k<i; k++) {          padding += " "        }        padding += "- ";        report += padding + "[" + headers[j].textContent + "](#" + headers[j].id + ")\n";    }}if (confirm ("CLICK OK TO COPY TO CLIPBOARD\n\n" + report)) {  navigator.clipboard.writeText(report);}})();```

To use the bookmarklet:
* Navigate to a Sharepoint webpage. Don't click on Edit yet.
* Click on the bookmarklet on the bookmarks toolbar.
* Click on OK to copy the Markdown code to the clipboard.
* Edit the Sharepoint webpage.
* Create a new Markdown web part where you want the TOC to be.
* Paste the Markdown code into the black section of the box.
* Save the webpage.
* To update the TOC, it is easiest and quickest to delete the web part and start again.