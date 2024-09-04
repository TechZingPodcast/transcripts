## TODO
 - [x] *2024-09-04* [Speaker segmentation via tinydiarize](https://github.com/ggerganov/whisper.cpp/tree/3998465#speaker-segmentation-via-tinydiarize-experimental)
 - [ ] Script to combine diarization with large model speech recognition (using timestamps of ". [SPEAKER_TURN]")

## Details
Speaker segmentation (local diarization) using [whisper.cpp](https://github.com/ggerganov/whisper.cpp) at [3998465](https://github.com/ggerganov/whisper.cpp/tree/3998465) circa 2023-07-16 for [speaker segmentation via tinydiarize](https://github.com/ggerganov/whisper.cpp/tree/3998465#speaker-segmentation-via-tinydiarize-experimental) with the [small.en-tdrz](https://huggingface.co/akashmjn/tinydiarize-whisper.cpp) model (d44ba793fc67e509623a88a409723311fa677744).

Techzing episode .mp3's were converted to 16-bit .wav using the [recommended](https://github.com/ggerganov/whisper.cpp/tree/3998465#quick-start) ffmpeg (v6.0 from [scoop](https://github.com/ScoopInstaller/Main/blob/17e557e/bucket/ffmpeg.json)) command:

    ffmpeg -i techzing___.mp3 -ar 16000 -ac 1 -c:a pcm_s16le ___.wav

The transcript .txt files were generated using the following command:

    main.exe -f ___.wav -m […]models\ggml-small.en-tdrz.bin -ml 1 -tdrz > ___.txt
