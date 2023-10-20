## TODO
 - [x] *2023-10-20* Naive single-pass ASR
 - [ ] [Speaker segmentation via tinydiarize](https://github.com/ggerganov/whisper.cpp/tree/3998465#speaker-segmentation-via-tinydiarize-experimental) or an alternative
 - [ ] Simple script to reformat into sentences to check for errors.

## Details
Simplistic automatic speech recognition (ASR) using [whisper.cpp](https://github.com/ggerganov/whisper.cpp) at [3998465](https://github.com/ggerganov/whisper.cpp/tree/3998465) circa 2023-07-16 for [word-level timestamps](https://github.com/ggerganov/whisper.cpp/tree/3998465#word-level-timestamp-experimental) with the [large](https://huggingface.co/ggerganov/whisper.cpp) model (0f4c8e34f21cf1a914c59d8b3ce882345ad349d6).

**WARNING**: Nothing was done to fix [hallucinations](https://github.com/openai/whisper/discussions/679) (usually repeats at the beginning and end, apparently).

Techzing episode .mp3's were converted to 16-bit .wav using the [recommended](https://github.com/ggerganov/whisper.cpp/tree/3998465#quick-start) ffmpeg (v6.0 from [scoop](https://github.com/ScoopInstaller/Main/blob/17e557e/bucket/ffmpeg.json)) command:

    ffmpeg -i techzing___.mp3 -ar 16000 -ac 1 -c:a pcm_s16le ___.wav

The transcript .txt files were generated using the following command:

    main.exe -f ___.wav -m […]models\ggml-large.bin -ml 1 > ___.txt
