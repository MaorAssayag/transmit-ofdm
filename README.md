# transmit-ofdm
Simple OFDM implementation in python ready to be transmitted with acoustic modem.

This project is about building the physical layer of an OFDM modem that works over audio. OFDM is used in WiFI, 5G, digital TV, and a host of other radio communincation.

The acoustic modem has desired sample rate, frequency range and amplidute range.

If you only starting playing with OFDM, a good place to start is [here](https://hardwareteams.com/docs/dsp/audio-ofdm/audio-ofdm-modem-part1/).

I've upload this repo because it was hard to find end-to-end, real implementation of OFDM for underwater acoustics.
 
[Full project report](https://github.com/MaorAssayag/transmit-ofdm/blob/main/assets/AcoustisSSP_proj_MaorAssayag.pdf) with OFDM summarization and various DSP algoritehms.

<img src="https://github.com/MaorAssayag/transmit-ofdm/blob/main/assets/ofdm_system_model.png" width="500">  

## Intro
OFDM is a method for digital communications using a frequency multiplexing scheme that uses multiple sub-carriers to transmit several symbols of data in parallel. Each sub-carrier can use a common modulation scheme such as quadrature amplitude modulation or phase shift keying. The advantages of OFDM lies in its straight-forward channel equalization scheme, easy elimination of inter-symbol interference, and efficient implementation via the FFT [1].

## The OFDM Transmitter 
After passing through the channel it is the OFDM receivers job to correct for unideal characteristics in the received signal. Some important aspects of proper reception include: synchronization (which includes packet detection, timing recovery, and carrier frequency offset correction) and channel equalization. The general flow of data is summarized in the figure below.

## Interpolation/Upsampling
What a lot of books don’t talk about in the context of OFDM is how to get from you baseband signal to actually transmitting it. They make assumptions that a magical machine teleports your baseband signal to the correct center frequency, but a couple things need to happen, the first of which is interpolating your baseband rate to your transmitting frequency rate.

## Simple example
<img src="https://github.com/MaorAssayag/transmit-ofdm/blob/main/assets/ofdm_gmm.png" width="800">  

