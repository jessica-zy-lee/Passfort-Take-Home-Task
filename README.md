# Passfort Take Home Task

## About
This is a Front End take home task from Passfort to create a wiki and display different documents and their revisions when their users interact with the webpage. It is a Single Page Application

## Structure
All of the code can be found in ./templates/index.html. The javascript which dynamically changes the DOM content are within the same file wrapped in the script tags. I have originally intended to seperate the JS files from the HTML, however due to some routing issues from the backend, I wasn't able to load the javascript files when it is seperated.

#### External Dependencies
Axios - is used to handle API, this is imported directly in the HTML, so there is no need to do anything else to pull in the dependency

#### Functions
There are five functions:
- `getPages()` gets the response from /pages API endpoint and call the displayPages function
- `displayPages(response)` gets the response from the /pages API and list all the pages in the DOM element with the id "listOfPages", the lists will be an anchor tag which triggers the getDocument function on click
- `getDocument(documentTitle, documentRevision)` is a function which gets the document and/or specific revision of the document. documentRevision is an optional argument. When omitted, the default behaviour is to get the latest version of the document
- `displayDocument(response)` displays the title and the content (data) of the specific document revision from the API response
- `displayRevision(response, documentTitle)` displays the revision as a clickable list, the list items are anchor tags of the revision number which triggers the getDocument function on click

## Future work
As I am relatively junior at my level, My code has a few limitations which I would like to add when I gain more experience
- Testing: I have not done any tests as I don't have experience with it. However, if I have to write them, I will test a few responses for each function where I know the results will be true or false and run the test suite to check my code
- Routing: I have not made any routing, I have structured my code in a simple way so there is no need for routing
- Editing: I have not made an edit functionality, if I were to make this I will do it via an HTTP POST request

## Limitation
- If there are many titles, the list of pages will be very large
- Everything is in one file, ideally I would seperate the javascript from the HTML, but the python routing in the backend has created some problems with that. Given we only have a limited number of html elements and javascript functions this doesn't present significant readability problems. However, it would be great to fix that in the future