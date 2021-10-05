## Digital_Audio_Watermarking-
# 1. TITLE: DIGITAL AUDIO WATERMARKING
# Objectives: - 
Millions of multimedia documents cross the Internet every day. However, the ownership of most of these multimedia documents is usually unknown. The relatively new technology of digital watermarking has been proposed in recent years to embed ownership information in multimedia documents without sacrificing their usability.
1. Indeed, many effective digital image and video watermarking algorithms have been proposed and implemented at a commercial scale.
2. The audio watermarking techniques reported in literature can be grouped into spatial domain, time- domain, spread-spectrum domain, frequency-transform domain techniques. The different
         domains have different characteristics and applications, and thus lead to different robustness and imperceptibility (inaudibility) performances.
# 2. INTRODUCTION Introduction to Digital Audio Watermarking
Digital audio watermarking is a process through which a secret signal is embedded in a digital audio file. In this paper we will go over the requirements of audio watermarks, their applications, and how the details of their implementation. Audio watermarking is an extremely diverse field, with many different algorithms aimed at different applications. This paper will merely provide an introduction to the subject, focusing on one simple application, and avoiding many of the more complex techniques. The goal will instead be to develop a solid base in every aspect required for the understanding of more complicated watermarking schemes. In addition to the general overview, we will examine in depth two seminal papers in the field of audio watermarking. The first was written by Ingemar Cox in 1997, and describes a general purpose technique for watermarking media files called spread spectrum watermarking. Originally applied to images, spread spectrum watermarking has gained wide usage in all types of digital media, including audio and video. The second was written by Ernst Terhardt in 1981, and describes a psychoacoustic model for determining how salient a pitch is to the human ear, given a frame of audio data. Psychoacoustic models are extremely important in audio watermarking due to the particularities of the human auditory system (HAS). Lossy audio compression has gained widespread usage, and typically frequency components that are not audible will be stripped from a signal as it is compressed. Finally, an implementation of the described techniques will be provided. Before explaining these details, we will cover what specifically an audio watermark is, and what it is designed to do. The following requirements and applications were described by Nedeljko Cvejic and Tapio Seppanen.
## Requirements and aspects of Audio Watermarks
# • Perceptual Transparency: 
Perhaps the most basic requirement of any digital watermark, not specifically audio, is that it should be perceptually transparent. In audio watermarking, there should be no audible difference between the watermarked and unwatermarked signal.
# • Watermark Bit Rate:
The bit rate of a watermark, usually expressed in bits per second, indicates how much information can be encoded in the watermarked signal. The acceptable bit rate varies tremendously from application to application, and sometimes bit rates as low as .5 bps are acceptable. Higher bit rates are the territory of steganography more than watermarking, and some algorithms have succeeded in embedding up to 150 kbps without violating perceptual transparency. The amount of bits per second that can be encoded is heavily dependent on the audio encoding scheme. A typical LPCM (linear pulse code modulation) encoding on a CD contains precisely 1411.2 kbps (2 channels, 44,100 hz samples, 16 bits per sample). A lossily compressed mp3 of the same perceptual quality may only use 64 kbps. Clearly it is possible to store more audio data on raw LPCM data than lossily compressed data.
# • Robustness:
Robustness is the ability to detect a watermark after common signal processing procedures. Robustness is typically inversely correlated with bit rate - there is no way you will be able to encode 150 kbps if you want your watermark to be resistant to com- mon lossy audio compression. In ”fragile” watermarking algorithms robustness is considered undesirable, but for most it is necessary.
   
   # • Blind or Informed Detection: 
         Informed detection algorithms require the use of the original audio in order to detect the watermark. There exist Blind detection algorithms, which allow the watermark to be detected with nothing but the watermarked algorithm and a secret key. The remainder of this paper will focus on informed detection, as it is far less complicated.
# • Security: 
In digital watermarking it is typically desirably that nobody besides the owner of the original audio should be able to detect the watermark, let alone extract it.
# • Complexity:
Complexity is a metric of the length of time it takes to encode/decode the watermark. For an application such as audio fingerprinting, complexity is of little concern. Some applications must encode the watermark in real time, and for those complexity can be a serious limitation.
Digital Watermark is a technique that embed specific information into digital signals like audio tracks, video films, or images. As to hiding information in music, it is called Audio Watermarking, using Masking Effect to make audience difficult to hear the information under the music. Moreover, there are two kinds of typical watermarking schemes: DC Watermarking and Frequency Watermarking, which one is based on Temporal Masking and while another is based on Frequency Masking.
## Methodology: Audio Water marker
This project contains a MATLAB script as well as a python model that embeds (or "hides") data into the low frequency, inaudible components of audio waveforms. Using Hamming error- correcting codes, data can often be recovered even if the waveform is resampled. See the tutorial for an example.
WHY DO WE WATERMARK AUDIO FILES?
Since watermarks identify a specific owner, robustness against attack is extremely important.
Usually, attacks involve signal processing techniques such as filtering, adding noise, or re- sampling. Other pirates manipulate the host data by using compression, cropping, or D/A conversion. Their objective is to damage the host audio so that the watermark becomes undetectable or create a detection error by the decoding application. Given these possible attack mechanisms, an ideal watermark would be one such that the only way to damage it would be to damage the host audio itself.
## Instructions 
# • Run
1. Run the pynb file and follow prompts in the Jupyter notebook.
2.Include all the necessary libraries needed.
3. When asked, type the name of your wav file. it MUST be in the same directory.
   
  # • Tutorial
The program will run the following sequence of prompts:
1. Asks if you would like to run an example wav file.
2. Inputs a file of your choice.
3. Allows you to customize certain settings.
4. Saves and plays the watermarked file. Also opens a Spectrogram. 5. Asks you to input a watermarked file for decoding.
6. Asks you to enter decode parameters. Make sure these are identical to your encoding parameters.
7. Asks you which kind of attack you would like to simulate. 8. Extracts and displays the watermark.
# A WAV file is a raw audio format created by Microsoft and IBM. The format uses containers to store audio data, track numbers, sample rate, and bit rate. WAV files are uncompressed lossless audio and as such can take up quite a bit of space, coming in around 10 MB per minute with a maximum file size of 4 GB.
# WAV file formats use containers to contain the audio in raw and typically uncompressed “chunks” using the Resource Interchange File Format (RIFF). This is a common method Windows uses for storing audio and video files— like AVI— but can be used for arbitrary data as well.
# WAV files are generally going to be much larger than other popular audio file types, like MP3, due to the fact they are typically uncompressed (compression is supported, though). Because of this, they’re mainly used in the professional music recording industry to retain the maximum quality of audio.
Waveform Audio File Format (WAVE, or WAV due to its filename extension; pronounced "wave") is an audio file format standard, developed by IBM and Microsoft, for storing an audio bitstream on PCs.
• It is the main format used on Microsoft Windows systems for uncompressed audio. The usual bitstream encoding is the linear pulse code modulation (LPCM) format.
• As a lossless format, WAV files offer a very high sample rate and bit depth, which permits them to include all the frequencies heard by the human ear.
## Properties of the algorithm: 
# 1. Quality Evaluation
The general approach in quality evaluation is to compare the original signal with the watermarked one for difference. To find the minimum embedding factor, with imperceptible or perceptible, but not annoying differences, between the reference and the watermarked signal, we used the so-called subjective Diff-Grades.
# 2. Security
The watermark and the marking procedure should also process certain security properties. The space of distinguishable watermarks should be large enough.
# 3. Robustness
   
To test the robustness of the presented watermarking algorithm we randomly choose n different combinations of watermarks and keys and embed this bit pattern m times into one audio track.
## Applications of Audio Watermarks:
# • Ownership Protection:
The goal of audio watermarking in ownership protection is to be able to demonstrate ownership of a digital audio signal. The algorithm should be robust and secure, but often a low bit rate is acceptable. This paper focuses on ownership protection because it’s in many ways the simplest application of audio watermarking.  
   # • Authentication / Tampering Detection: 
   Here the watermark is used to ensure that the audio file has not been tampered with. Robustness is undesirable - one should only be able to detect the watermark if the file is in its original state. Blind detection is a strict requirement if the algorithm is to be run by a user.  
# • Fingerprinting: 
A file is watermarked with a” fingerprint” for a specific user before being sold to them. This allows the owner of the file to detect who a file was sold to if it has been redistributed. The algorithm must be highly robust, but a low bit rate is once again acceptable. One further requirement is unique to fingerprinting: anti-collision. Any two fingerprints must be different enough that there are few false positives when looking for a watermark.  
# • Broadcast Monitoring: 
In broadcast monitoring, a signal is watermarked in real time with information about the source. This requires high capacity, fast computation, and blind detection, but robustness is typically not emphasized.  
## Advantages of audio watermarking
# 1. Digital Fingerprinting:
Data embedded in the audio file can be used to track the history of usage of
the audio file as well as owner of the audio data can get the idea about the popularity of the audio file.
# 2. Copyright protection:
audio watermarking is of paramount importance as it provides copyright protection. With the help of markers, it will not be difficult to determine who the real owner is, so the tedious process of determining who the owner is when a multiple ownership issue occurs is avoided.
In the case of the multiple ownership issue, the identity of the real owner can be known easily using the information embedded in the audio file. Hence the watermark can be used as strong evidence in case of copyright lawsuit.
# 3. Broadcast monitoring:
It’s not easy to trace how many times your song has been shown as part of a TV commercial or similar. This would mean that someone has to watch TV 24/7 and record every time your audio file appears. This is, of course, impossible and this can then lead to someone paying you a smaller amount on the name of copyrights than they should. Because it will tell you that fewer times it has been shown or played than it is.
With the help of audio watermarking, tracing will be very easy. Since it is embedded in every copy, every time it is played, you will know it. When an audio watermark is present, it is not possible to remove it before playing.
A company can know about the number of times an advertisement is played on a T.V. channel or any radio channel.
# 4. Copy control: 
Now a days, some recording devices have been developed which can stop the recording or copying of an audio file as soon as it detects a watermark which indicates the recording of the music as illegal. Someone may not have bad intentions and does not want to steal your audio file, but they cannot detect that you are the owner and then this can lead to problems with both you and them. When you add an audio watermark, the owner detection process is quick and easy and can even enable you to make new business collaborations.
# 5. Information carrier: 
The blind type of audio watermarking technique can be used for sending information from one place to another. But this comes out be less robust because as the amount of information goes on increasing, the robustness of the algorithm tends to decrease.
## Disadvantages of Audio Watermarking: 
# 1. Costs
Adding a quality watermark will bring you costs. It is not possible to do everything the right way without the help of professionals or buying new equipment and the like. It is necessary to edit the file without damaging it, so the marker must be well done to serve the purpose.
# 2. Loss of information
If the audio file is compressed there is certainly going to be a critical loss in the audio metadata because with the compression of the file, we lose the information stored within it as it’s being transmitted while the featuring or playing of the audio file. In such a way it will be very difficult to keep the encoded information metadata safe.
## 4. CONCLUSION
This project has given us the opportunity to explore some of the topics covered in the class, which include time and frequency domain representation of signals. The algorithm did prove to be an exceptionally good introduction to the characteristics of watermarking algorithms and showed us the considerations and difficulties in designing and implementing a robust watermarking scheme that can be widely used to serve its purpose.
## OUR CRITICAL APPROACH/ APPLICATION
● We believe that with the advent of audio watermarking it will make audio recognition rather song recognition obsolete. Basically, through Audio watermarking we encode information about the song/its artists/ & source from which we are playing the audio (YouTube, Spotify, Apple Music etc). So, since the track information or the song metadata is encoded. This whole is done by Digital Fingerprinting. But unfortunately, not much information cannot be encoded from fingerprinting.
● But via Audio watermarking since we can also encode the audio metadata within the audio stream itself, we can repeat the information throughout the length of the audio stream. This will not only helpus serve the user with multiple links from where the audio can be downloaded but also help in tracking when and exactly where was the audio heard last time, so that can also help one accessing the location of the user and checking upon the number of times the audio files were played. So as in such apps like SHAZAM will also become obsolete.
## Future Research
There are many aspects of spread spectrum audio watermarking that have not even been covered in this paper. The use of transforms other than the DFT is becoming prominent in watermarking schemas. Particularly the discrete wavelet transform is seeing use in psychoacoustic models, because it, like our ears, places more emphasis on lower frequencies than higher ones. Synchronization methods are an active area of research, as they are one of the strongest attacks available to spread spectrum watermarks. Time or frequency scaling of the order of 5-10% introduces little distortion to audio quality but can be extremely debilitating to spread spectrum watermarks. Blind watermarking techniques have been completely omitted. Finally, watermark fingerprinting is an extremely interesting application, which specifically requires low collision rates among different watermarks.
## 5. REFERENCES
• https://ieeexplore.ieee.org/abstract/document/6749625/
• https://en.wikipedia.org/wiki/Audio_watermark
• https://www.sciencedirect.com/science/article/abs/pii/S0165168416300263

# CONTACT:
ABHINAV CHANDRA - abhinavchandra0526@gmail.com
