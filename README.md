What I did
----------
I set the development environment up at the beginning. I had to install vagrant, which runs Ubuntu without UI so that
it is only accessible by console, for that.
I also created my own Git account using a SSH key, which I generated for that.

Debug Pages are meant to quickly give the user an overview of if code works.
On the debug page for senzari, the objects in an array are called with an AJAX call. The items are shown in a list on the page. If they were not called succesfully, they are shown in red. I added a red dot that is shown if one call fails and a green dot that is shown if all calls were successfull so that the user can easily determine if the API works. The response or error report is shown further down the page. I also made a counter that shows how many AJAX calls were successfull. I did that using Javascript and a little HTML, which I didn't know before.

Then I made a debug page for Lead Tracker. After adding two more Lead Creates, Gets and Deletes so that it is shown if the Created Leads have the corresponding to the scheduled date correct status, I made the code cleaner.

For that I made the two biggest loops, which iterate over two arrays into oneloop and one array.
The problem was that some of the items in the second array only worked if they had the Id, that was
generated by the items in the first array. I had to turn the forEach loop I used before into a for loop
because a forEach loop loads the array and isn't affected by any changes made to the array after that.
For the for loop to work properly, I had to write a function that executes the AJAX request. 
To find out how to do that, I created a StackOverflow account and asked there.
Here is the code for that:

    for (i=0; i < data.length; i++) {
        (function(index) {
            var p = data[index]
            ...
            $.ajax({
            ...
  	  
I added the ms in which the URLs responded afterwards. Then I made the requests to be shown formatted for Fiddler.
I also made the debug page look a little nicer with CSS. I made the textboxes that contain the for Fiddler formatted request yellow. 

in CSS:

    .TAS {
    background-color: rgba(255, 255, 100, .5);
    }
in Javascript:

    var FTextArea = $('<textarea class="TAS" rows=8 cols=180></textarea>').appendTo(FTAID);
    
I uploaded the page to github pages: http://spikele.github.io/
