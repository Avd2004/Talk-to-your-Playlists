# Talk-to-your-Playlists

Making a chatbot using your youtube playlists! 

Required limitations for the plalist:

a.) Must be in english with proper understandable tone.

b.) Should have creator's or auto generated transcript (sub titles) for most videos

c.) Reccomended: total video time should be atleast 3hrs for a decent Corpus formation

Step 1: Extracting Videos from Playlist:

Playlist ID is extracted from playlist link, the ID is after the charecters 'list='. Using Google's client API we traverse through the playlist to get each video's link. The characters after 'v=' in a youtuve video link identifies the video ID. We extract this ID as a substring. We use YouTube Data API to get the video subtitles transcript as a json file.

Step 2: Creating Corpus from the json file.

This json files has text along with duration and timestamps of each dialogue, we remove the timestamps and save the texts as a .txt file. In each iteration the json is formated to text, and after the loop ends, the text snippets are appended to a text file. This forms our Corpus.

We then clean the data or unnecesary characters and empty lines.

Step 3: Tokenization of Corpus:

We use NLTK library to form tokens using sentence grammar and punctuations.

Step 4: Building a Chatbot:

We use AutoModelForQuestionAnswering and AutoTokenizer from transformers to train the model which is distilbert-base-uncased-distilled-squad on our context aware chatbot. Our context here is the Corpus. Using the Question Answer pipeline, the chatbot is formed.

Thank you. We encourage you to try with your playlist yourself! Please provide your valuable feedback.
