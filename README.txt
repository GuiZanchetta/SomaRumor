The following Patch was developed by Igor Abdo Aguilar for the SomaRumor Project in early January 2023. It is intended to be used in a project with 4 soundboxes and 1 to 2 microfones.



This patch requires the libraries Else and Cyclone, that can be downloaded and installed via dekken.



There is a "native" Library to this patch which should contain the following files:

    audio-loader-estereo.pd
        loads 4 stereo files into the patch and randomizes the pairing of the Left and Right channels to the 4 sound boxes. To load these files, they must be named st-n.wav . "n" being the n number of the sound file. ex: st-2.wav
    
    audio-loader.pd
        loads 4 mono files into the patch at random. To load these files, they must be named n.wav . "n" being the n number of the sound file. ex: 2.wav
    
    
    mono-mic-recording.pd
        records a mono audio from the mic to a wav format file. While the microfone is on the signal to the loudspeakers will be damped to 0. The recording will be placed in the same folder and will at some point be radomly selected to play. These files are saved as "n+1.wav" being "n+1" an added number of all mono audio files. The number of total files is saved as the only value in the text file mono-audio-number.txt


    radiolho.pd
        Main patch, has presets to control all other aspects of the file. These presets are in a subpatch called [pd presets] located in the initial patch window. You can alter these values for a customizable calibration of the patch depending on the physical conditions of the location.

    spatialize~.pd
        Responsible for the DSP for spatialization of the mono file using a simplified DBP (Distance Based Panning, based of DBAP Distance Based Amplitude Panning) method (amplitude and Delay) onto the 4 sound boxes.

    stereo-mic-recording.pd
        records a stereo audio from 2 microfones to a wav format file. While the microfone is on the signal to the loudspeakers will be damped to 0. The recording will be placed in the same folder and will at some point be radomly selected to play. These files are saved as "n+1.wav" being "st-n+1" an added number of all stereo audio files. The number of total files is saved as the only value in the text file stereo-audio-number.txt

    mono-audio-number.txt
        text file containing the number of mono audio files. When starting a new installation, make sure the value in this text is the same number as the starting mono audio files. (starting with 1.wav NOT 0!!!)

    stereo-audio-number.txt
        text file containing the number of stereo audio files. When starting a new installation, make sure the value in this text is the same number as the starting stereo audio files.(starting with st-1.wav NOT 0!!!)