# FFTR
Code and explanations for the Fourier Residual Transform


The Fourier Residual Transform is difficult for me to explain.
I am not a accredited mathematician, I am not a certified engineer.
I was exploring different ways to improve time and frequency resolution.
I thought about impulse chains and how they must work.
I approached the problem intuitively, as must have all the early scientists.

What I discovered, I think, merits publishing, and perhaps an entry on arxiv

The FFT Residual method consists of the following steps:

Take the segment of samples you wish to process with the Fourier Transform(ie, the FFT)
take larger run of samples from a very large interval after the segment.
This series of samples needs to be at least as long as your lowest frequency component at 1 oscillation but can be longer.
Apply a smooth taper to it from 1 to 0.
use interpolation to interpolate it down to the size of your segment, or up to 8 times the size of your segment.
Apply an FFTshift and a windowing method such as hanning or logit(my personal preference is logit).
apply the fourier transform to this output.

What you will get is twice the resolution in time and frequency, for twice the samples processed.
This is not the equivalant of processing twice as many samples!
