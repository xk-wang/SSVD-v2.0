# Sight-singing Vocal Dataset v2.0

## SSVD dataset
**Sight-singing Vocal Dataset (SSVD)** dataset includes sight-singing songs for automatic singing transcription,  recorded from the Sight-singing Talent WeChat applet. SSVD v2.0 (this repository) is used in our **ICASSP2022** paper:  *MUSICYOLO: A SIGHT-SINGING ONSET/OFFSET DETECTION FRAMEWORK BASED ON OBJECT DETECTION INSTEAD OF SPECTRUM FRAMES*. 

SSVD v2.0 contains a train-valid set of 67 sight-sining songs and a test set of 127 sight-singing songs. The training set and validation set are not strictly separated. They are placed together under the train &valid folder. Each sight-singing audio contains a (onset, offset, pitch) annotation. The annotation method is as follows:
1. Four researchers who have received professional sight-singing training gave the approximate onset time of each note through slowing down and listening to the singing audio under the guidance of music score;
2. The researchers used the audition software to observe the spectrogram with a high time resolution set. Then they watched the spectrogram characteristics near the approximate onset time given in last step and took the occurrence time of the second harmonic signal as the accurate onset time;
3. After obtaining the onset annotation of each note, the offset annotation was given by listening to the audio. The specific rules were as follows: the time when the sound could not be heard was regarded as the approximate offset. Combined with the spectrogram, the accurate offset time was defined when most harmonic signals disappeared;
4. With the audition to be more logarithmic and higher frequency resolution set, the four researchers took the center frequency of each note as the fundamental frequency and convert the frequency into MIDI number as pitch annotation;
5. Finally, the four researchers checked each other’s annotation files until no annotation errors were found.

Besides, we release the note object detection dataset we use to train MusicYOLO, which is placed in the images folder. We first generate the spectrogram images from the sight-singing audios in train&valid folder. Then we cut the spectrogram images into many slicel images along the time axis. Then we annotate the note object in each slice image with labelme software. We break up all the slice images and divide them into training set and validation set according to the ratio of 7:3, which are used for the training and validation of MusicYOLO.

## SSVD v1.0 & SSVD v2.0

SSVD v1.0 was distributed at https://github.com/itec-hust/Sight-Singing-Vocal-Data, which consists of note-score alignment annotations apart from  transcription annotations. SSVD v2.0 only contains the transcription annotations. Compared with SSVD v1.0, SSVD 2.0 has the following differences:
1. SSVD v2.0 has a train&valid set of 67 sight-singing audios;
2. SSVD v2.0 corrects the onset annotations in SSVD v1.0 dataset;
3. SSVD v2.0 contains offset annotations.

### Sight-singing Talent applet

Sight-singing Talent is an online WeChat applet that has more than 600 long-term users and more than 60,000 effective Sight-singing samples.

<img src="qr.jpg" alt="QR code" style="zoom:150%;" />