Here lie versioned raw outputs from the official chat.  
For the purpouse of this project the data has to undergo the process described below in order to be useful. 

1. Remove names/anonymize ursars  
   `^(\[.*?\]) (.*?:) (.*)`

2. Remove lines that do NOT start with a time stamp using lookahead regex  
   `^(?!\[).+`
	
3. Remove empty lines  
   `^\n`
	
4. Remove lines that do NOT contain `http://` or `https://` or `www`  
   `^((?!http://|https://).)*$`

5. Remove empty lines  
   `^\n`
   
6. Remove links containing the following domains  
   ```
   ^.*(facebook.com|fbcdn|linkedin.com|imdb.com|9gag.com|youtube.com|wikipedia.com|efukt.com|
   imgur.com|gandul.info|zippyshare.com|docs.google.com|liveleak.com|twimg.com|
   piticigratis.com|stiiasta.com|tumblr.com|screencast.com|bit.ly|dailymail.co.uk|newegg.com|
   twimg.com|t.co|\.ro/|\.hu/|\.ru/|9gag.tv|conversation=\"|cloudfont.net|instagram.com|dropbox.com|
   livejournal.com|twitter.com|imgur.com).*$
   ```

7. Remove the content between the time stamp and the link  
   `^(.*])(.*) (http.*)`
   
8. Enjoy