Converting audio files to an Alexa-friendly format

You can use converter software to convert your MP3 files to the required: 

- codec version `(MPEG version 2)` and bit rate (48 kbps). 

One option is a command-line tool, FFmpeg.

This sample command converts the provided <input-file> to an MP3 file that works with the audio tag. This version uses `16000` as the `sample rate`:

`ffmpeg -i <input-file> -ac 2 -codec:a libmp3lame -b:a 48k -ar 16000 -write_xing 0 <output-file>`

You might get better quality by increasing the `sample rate` to `24000` like this:

`ffmpeg -i <input-file> -ac 2 -codec:a libmp3lame -b:a 48k -ar 24000 -write_xing 0 <output-file>`

Source - https://developer.amazon.com/en-US/docs/alexa/custom-skills/speech-synthesis-markup-language-ssml-reference.html