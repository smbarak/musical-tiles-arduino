# Musical-Tiles-Arduino

This is a memory-based musical tiles game using Arduino and the AdaFruit Audio FX Soundboard.

## Summary

When the game starts, the players hear a simple piano piece and then attempts to play it by stepping on pressure plates, where each plate corresponds to a different note. These pressure plates are essentially large buttons. DIY pressure plate videos are available on YouTube. 

*Psst, just in case you didn't know, the point of the soundboard is to output actual .mp3/.wav files and not just simple frequencies. You can use a regular piezo speaker if you're lame (or would simply rather use that, although that's a questionable choice for a serious project)... piezo? more like buzzerieo speaker (because it buzzes annoyingly)*

When the program runs, a speaker [that is connected to the soundbaord] plays a random sequence of a predetermined number of notes. This number varies depending on the difficulty. If the player chooses easy mode, there are only 4 notes; if the player chooses the advanced difficulty, then there are 6 notes. Once the speaker finishes playing the sequence of notes, the player must return the correct sequence by stepping on the pressure plate that corresponds to the correct note in the same order as the notes are played. The player’s inputs are then compared to the sequence played, and if the two sequences match, the player wins. 

In addition, in the advanced difficulty, the player has a limited amount of time to step on the pressure plates. The premise of the game is simple and intuitive, but the game itself proves to be challenging, especially in the advanced mode when the player must keep track of a longer sequence of notes.

*Hopefully I didn't confuse you fellas...*


## Hardware and Electrical Components

I am not going to go into the details of the Audio FX Soundboard. You can learn more by looking up: "Adafruit Audio FX Soundboard". 

### Required Hardware:
1. AdaFruit Audio FX Soundboard
2. Speaker with a 3.5mm audio jack cable
3. Buttons/pressure plates
4. Wires, resistors, microcontroller, etc.

I would reccomend using copper wires and not steel because a.) copper is a better conductor and b.) Cu >> Fe + C [personal preference].
I used a JBL Flip 3 speaker.


***Electrical integration and circuit is depicted in the .png file***



## Software

The soundboard was used to play .wav formatted audio files through an external speaker. Using a piezo speaker would be far less engaging than using a soundboard that outputs actual piano key notes. Since I used the soundboard, I imported two libraries pertaining to the functionality of the board. This soundboard  plays audio files directly without needing an SD card. A speaker or headphones can be connected to the board via an audio jack.

The soundboard was connected to the Arduino board and the necessary audio files were downloaded onto the soundboard by connecting it straight to the laptop via a USB cable. The files on the board are ordered by file size and not by name. To play an audio file, one would need to declare the pins concerning the soundboard and initiate the software serial. The function sfx.playTrack((uint8_t)i); would then be used, where i is a byte that corresponds to the numeric order of the audio file on the board.

More comments are included in the code


