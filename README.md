# Swift Anki Exporter
This is a script to make [anime cards]("https://www.animecards.site") on the fly with a single hotkey. It takes a sentence from [yourei](https://www.yourei.jp), an image from [google images](https://www.google.com/imghp?hl=ja), an audio recording from [forvo](https://www.forvo.com), and finally, a couple meanings from yomichan dictionaries of your choice, which is all packaged into 1 card and sent directly to your anki. 

## Installation
First, you need to install all the dependencies. This can be done with a simple command:
```
pip3 install -r requirements.txt
```
The next step is to set up the config in [config.yml](config.yml). All you have to do is fill in the missing blanks.
Here's an example config file:
```yml
anki:
    collection: "C:/Users/{your username}/AppData/Roaming/Anki2/{the name of your profile}/collection.anki2"
    word_file: "C:/Users/{your username/Desktop/Mined words.txt"
    deck: "My Deck"
    note_type: "My Notetype"
    word_field: "Word"
    sentence_field: "Expression"
    image_field: "Picture"
    audio_field: "Audio"
    meaning_field: "Meaning"
```
Notes: 
1. you need to type in the fields *exactly* as it is in anki or else it will not work.
2. The collection is you profile's database and the `word_file` is the path to the a txt file with a list of words
3. You have to close anki before running this script
   
Next, we need to setup the dictionaries that you will be using. There's 2 folders in the `dict` folder, fallback and priority. Priority is the folder where you will put your dicts that you want to search first. Fallback will be used to fallback to the dictionary in the fallback folder if it couldnt find any meanings in your priority dicts. 

Make sure you unzip the yomichan dictionaries to its own folder and move it to the appropriate directory inside `dict`

## Options
There are 2 options to use when running this script, `--word` and `--parsefile`.
1. The word flag (which is defaulted to true) is used to make an anki card from the word in your clipboard. 
2. The parsefile flag is used to batch add cards from a txt file with the list of words. And you already set this file path up in the config.

If you are on linux, or have the [Auto Hot Key](https://www.autohotkey.com/), there are already scripts for these in the `scripts` folder.

## Hotkey setup
You can setup a hotkey for this program either through linux or [Auto Hot Key](https://www.autohotkey.com/).

### AHK
If you aren't on linux, you can run the auto hot key script in `scripts/ahk/add-one` which listens for `Ctr+Shift+Space` and export the word in your clipboard to anki.

### Linux
If you are on linux, setting up a hotkey is actually really simple. There are multiple guides on the internet for that, and once you get to the part where you enter a command, type in the full path to `scripts/add-one.sh`.



