Horn Design

This webpage is my possibly incoherent attempt to explain how I design horns - all kinds of horns. It is an evolving document, changing every time I feel like working on it. It assumes basic knowledge of speaker design and terms.  
  

---

Opening notes:  
Sometimes it seems there is a disconnect in people's minds between a cone driver loaded by a horn and a compression driver loaded by a horn. This is probably caused by two factors. One is that cone driven horns are usually designed starting with the Thiel / Small parameters of the driver while the T/S parameters are usually not available for a high frequency compression driver. The second is that the directivity characteristics usually play a much larger role in determining the on-axis frequency response for a high frequency horn than they do for a low frequency one. Since freely available software does not usually predict this effect, people see predictions of high frequency horn performance as unrealistic. However both setups are really the same thing - a diaphragm of some sort driving a horn with a front and rear chamber. The details of how a hobbyist would design and assemble these systems are just a bit different.  
  
I attach importance to these factors in designing any speakers, but specifically horns:  

- Smoothness of frequency response
- Smoothness of power response (response at all angles)
- Tonal balance (how flat the frequency response is)
- Low distortion at the expected maximum playback level
- High efficiency (to reduce power compression for a given playback level)
- Time alignment (usually not a big deal for cones, but worth mentioning with large multiway horn systems)

Before going further, here is some basic horn terminology necessary for this discussion:  

- Cutoff frequency or flair frequency - this is the lower frequency limit of the horn / driver combination. The flair frequency really describes how fast the horn flairs while the cutoff frequency describes how low in frequency the horn / driver's response is usable, but in typical horns these frequencies are fairly close.
- Flair type - the shape a horn follows as it flairs out. There are typically different equations mathematically describing the shapes of different flair types. Examples are exponential, hyperbolic, conical, tractrix, etc.
- Acoustic size - a wave of a certain frequency has a wavelength equal to the speed of sound divided by the frequency (in Hertz or cycles per second). If an object or dimension, like the diameter of the mouth of a horn, is the about the same as or larger than the wavelength of a given frequency, then that object or dimension is acoustically large at that frequency. For example, a frequency of 20kHz has a wavelength of about 0.677 inches, so the 1" diameter exit of a compression driver would be marginally acoustically large, while a 10" diameter exit horn would definitely be acoustically large. A 0.0625" diameter microphone would be acoustically small at 20kHz. This concept is useful in evaluating how horns, etc. will effect sound waves at different frequencies. Things that are acoustically large will typically have an effect, while things that are acoustically small will usually not.

Despite my rant about compression drivers not being different than cone drivers above, due to the lack of data available for compression drivers it usually is easier to design with them using a different procedure, so I'll seperate all this into two procedures.  
  

---

Low Frequency horns (using cone drivers):  
I usually start off a low frequency horn design by using an Excel spreadsheet I wrote based on W. Marshall Leach's horn math, as detailed in "On the Specification of Moving-Coil Drivers For Low-Frequency Horn-Loaded Loudspeakers." This is available on the [author's website.](http://users.ece.gatech.edu/~mleach/) Note that there is a follow-up dialog to the paper concerning reactance annulling which is included at the end of the pdf file. Leach starts with the standard equivalent circuit model of a horn (such as described in Olson's 'Acoustical Engineering'), but substitutes a gyrator for the usual transformer between the electrical and mechanical sections of the model. He then makes some simplifying assumptions and derives a set of equations based on Thiel / Small parameters. The set of equations lets you work from a given driver specification to design a horn to cover a specified frequency range or work from a horn specification to design the optimal driver. One thing to note is that the simplifying assumptions are significant. For example, Leach assumes an infinite exponential horn as the load. If you're trying to design a very small (undersized) horn, Leach's equations will probably not predict the exact results that you will get. There is also no provision made for things such as folds in the horn, parallel side walls, etc. It is up to the designer to take these factors and their effects into account. If you are interested in horn design and want to work out the details yourself, I recommend that you buy these papers and incorporate them into a spreadsheet or program. I personally prefer the spreadsheet approach, as it lets me add in any calculation that I happen to need at the moment.  
  
Other things that I included in my spreadsheet are equations for predicting power handling and acoustic output, and estimating distortion. I gleaned these from other AES preprints and journal articles. Here are some of the articles I have found useful:  

- Design Factors in Horn-Type Speakers, Daniel J. Plach, JAES Vol. 1, Number 4 pp. 276 (1953)
- What's So Sacred About Exponential Horns?, D. B. Keele, Jr., AES Preprint #1038
- Low-Frequency Horn Design Using Thiele/Small Driver Parameters, D. B. Keele, Jr., AES Preprint #1250
- Suitability of Low-Frequency Drivers for Horn-Loaded Loudspeaker Systems, Richard H. Small, AES Preprint #1251

Since most people do not have the capability of building their own drivers from scratch, the design process usually starts off by entering a speaker's parameters that I think might work well in a horn into my design spreadsheet. In the case of bass horns, I ignore the commonly given advice with regards to a driver's suitability for use in a horn. For example, a common suggestion is to use a driver with a high efficiency bandwidth product (EBP). (EBP is equal to the driver's resonant frequency (Fs) divided by its electrical damping factor (Qes)). A high value is around 200 or more. On the other hand, using Leach's math, predicted optimum drivers for bass horns have EBP's of around 50 or lower. I have used such drivers in a subwoofer horn, and the subjective results are excellent. The horn works pretty much as predicted by Leach's model. If you delve a bit deeper, you can find that a desirable value of EBP is actually dependent on the frequency range the horn is designed to reproduce. For a horn designed to cover 75hz to 500hz, for example, an ideal driver would have an EBP of approximately 270. My personal opinion is that these types of suggestions became popular when people were only building what I call midbass horns - horns designed to cover from approximately from 80hz up as high as possible, usually around 500hz to 800hz.  
  
Often I am merely 'trying out' a driver to see if it would work well in any type of horn. Other times, I have a specific goal in mind for what I want the horn to do. If the former, I mess around with the low and high frequency cutoffs of the horn until I get a sense of what the driver is suitable for. To determine suitability, I look at what kind of efficiency I can achieve and over what bandwidth, and what the excursion-limited maximum output will be versus what the thermally-limited output will be. For example, I might model that a driver will work at 50% efficiency over a bandwidth of two to three octaves and its construction will allow it to handle 100 watts of input power, but its maximum output will be limited by its suspension to 110dB SPL. In this case, the suspension is the limiting factor. If 110dB SPL is a high enough output for the particular application, then everything is great. The more likely case is that this driver would not be very well suited for this particular design.  
  
To expand on the issue of power handling in a horn, note that a horn which increases the efficiency of a driver increases the power handling of the system (horn plus driver). Efficiency is a measure of how much useful output is obtained compared to how much power is put into a device. In the case of a horn, the output is acoustic power and the input is electrical power. Typical loudspeakers are on the order of 1% efficient or less. From this, you can see that if you put 100 watts of electrical power into a speaker, 99 of those watts are not converted into acoustical power. Most of that power remains in the driver as heat. When a driver's efficiency is increased through horn loading, more of the electrical input power is transferred out of the driver as sound. This means that less of that power is hanging around in the voice coil as heat. Assuming that the driver's power rating has some relation to the point at which the glues holding it together start to melt, then a new power handling level for the driver can be estimated using the following formula:  
  

Horn-loaded power handling = Non-horn-loaded power handling * (1 - no) / (1 - horn efficiency)

where no is the efficiency of the driver as a direct radiator, expressed as a number between 0 and 1, and horn efficiency is also expressed as a number between 0 and 1.

If you want to simplify this, you can neglect the no term (take no to be zero) without really making a difference in the calculations as long as the driver is not very efficient as a direct radiator. This new power handling should be taken into account in the process of determining the maximum output of horn.  
  
Once I find a horn design that fits my needs, I verify that it has a realistic flare constant or 'M' or 'T' value, and that it is long enough when built to my chosen mouth size. For my purposes, a 'realistic' flare constant is somewhere between 0.4 and 1.0. A horn with a flare constant of 1.0 is a true exponential horn, while a flare constant less than 1.0 is a hyperbolic-exponential horn. As the flare constant goes lower, the horn flares more suddenly at its mouth (in a full-size horn). If you are building a horn with an undersized mouth, such as a corner horn, then the M value has less influence on the actual shape of the horn because you are not building the portion of the horn that is influenced by the flare constant. Similarly, a tractrix flare can be perfectly suitable for a bass horn, contrary to popular opinion. The tractrix flare is quite similar to an exponential flare until the mouth is reached on a full sized horn.  
  
I also make sure the horn is long enough. This means the length is one fourth of the wavelength of the lowest frequency to be reproduced. This is the lowest frequency the horn resonates at (it is a pipe with one end closed). However, it is better to make the horn length 1/2 wavelength of the lowest frequency, as this is where it will start to work in a velocity-controlled manner. Another factor to be aware of is that the acoustic length of the horn may be substantially different than the physical length due to the end correction. This depends on the shape of the horn mouth, but it can add around 0.6 times the diameter of the mouth to the acoustic length of the horn. In a short horn with a large mouth, this effect could be substantial. It is also important to make sure that this length can be achieved with the size of mouth desired. If you need to build a mouth the size of an airplane hangar to reach 1/4 wavelength, then it does you little good.  
  
So how do you know what mouth size to use? It depends on the conditions your horn will be working in. If your horn is designed to hang 1000 feet above a cornfield, then it will effectively be radiating into full space. Leach's model assumes that the mouth of the horn will be infinite in this case. Of course you cannot build a horn with an infinitely large mouth, but a mouth that has a circumference equal to the wavelength of the lowest frequency to be reproduced has been agreed on as being close enough to infinite. If you put the horn on the ground, then it will be radiating into half space. The ground provides an acoustic boundary. In this case, a mouth with half the area of the full space mouth will be close enough to an infinite mouth. The area can again be cut in half for a horn placed on the ground and against a wall. If the mouth is placed at the junction of two walls and a floor, then the mouth area can be 1/8 the size of the full space mouth and still be considered large enough. However, many people make the mouths of their horns smaller than this so that they can be stuffed into aesthetically pleasing boxes. In this case, the efficiency of the low frequency end of the horn's bandwidth will typically decrease, and the response will have dips and peaks. This is the case most of the time, but not always.  
  
If I cannot come up with any suitable design for a horn for a particular driver, I conclude it is not suited for use as a horn driver. If you do this enough, you will start to get a sense for what will make a good horn driver and what will not. If I have a specific goal in mind for the horn, then I will basically go through the above process in reverse, trying different drivers until I find one that meets my needs.  
  
At this point in the design process, I simulate my new design's performance using [David McBean's Hornresp](http://www.hornresp.net/) program. This will predict the frequency response, electrical impedance, and cone excursion among other things. I have found these predictions to be fairly accurate when compared to horns I have built, although there's still some question about the predicted excursion. This program can be especially useful when you are trying to build horns with undersized mouths. Some small-mouthed horns can have remarkably smooth frequency response, merely starting to roll off at a higher frequency than a full size horn with the same flare rate would. Others can have huge dips and peaks in their frequency response, as is typically cautioned. Assuming the basic design models okay, I'll try tweaking the front and rear chamber in Hornresp while looking at the frequency response, impedance and excursion.  
  

---

Physical design  
All the computer simulation in the world is useless if you don't actually build what you simulate. The simplest way to ensure that you don't have a problem with this is to build a straight horn (no bends) with a round cross section. For high frequencies, this is easy; these horns are usually small enough that building a straight horn with a full size mouth is not an inconvenience when used in a normal living space. At the other extreme are horn subwoofers. These can easily approach 90 cubic feet (~2.5 cubic meters) of horn to get down to 20Hz and are the sort of thing that are only installed in dedicated listening rooms or home theaters (or, of course, in professional settings). Horns of these sizes are almost always folded to make them more compact. Midbass horns are in a middle ground. Whether or not these horns should be built with folds depends largely on personal preferences and the specific design goals of the project. There have been a lot of examples of folded very-low frequency horns that have worked great.  
  
In folding and simplifying the construction of a large bass horn, anomalies can be introduced into the horn's response. One common design is to make two walls of a bass horn parallel so that the horn expansion only takes place in one dimension. There will be a resonance between these parallel walls. This resonance will absorb power from the horn's output if it falls inside the horn's operating band, creating a notch in the frequency response. This resonance would occur at the frequency whose half wavelength is equal to the distance between the parallel surfaces ( _f_ = c / x / 2 ). Additional resonances would occur at odd multiples of this frequency (1, 3, 5, etc.). This would indicate that to go higher in frequency using a horn with parallel side walls, one would need a narrower horn (consider the popular Lowther-style rear-loaded horns).  
  
Folds in the horn can also introduce anomalies in the frequency response. For high frequencies (relative to the size of the cross section), flat reflectors should produce the best results. For low frequencies, the shape of the corners matter less. For more information on this, see some of my other webpages - [look here for measurements of waves going around bends](https://www.jhsaudio.com/waves.html) and [here for FEA simulations of horn bends](https://www.jhsaudio.com/images/roundbend/)  
  

---

Some useful equations:  

The hyperbolic / exponential formula

Area = Throat Area [ cosh ( x*2*Pi*_f_ / c) + M * sinh ( x*2*Pi*_f_ / c) ] ^2  
  
where

- x = distance from throat
- _f_ = the cutoff frequency of the horn
- M = the flare constant - M = 1 is exponential, 0 < M < 1 is hyperbolic
- c = the speed of sound, approximately 13538 inches per second or 344 m/s (depends on temperature, etc.)

  

Mouth Size

For a horn radiating into full space, the horn mouth should have a circumference equal to the wavelength of the low cutoff frequency. Usually, what is of interest is the area of the mouth since bass horns are not commonly made with circular mouths. Here's how you get to an equation for the mouth area:

- Circumference = c / _f_
- and Circumference = Pi * diameter = Pi * 2 * radius
- setting these equations equal, Pi * 2 * radius = c / _f_
- radius = c / (2 * Pi * _f_ )
- In addition, Area of a circle = Pi * radius^2
- Substituting in for radius, **Area = Pi * [c / (2 * Pi * _f_ )]^2**

If you want to find the appropriate mouth area for a loading situation other than full space, you would divide this area by the appropriate factor (divide by 2 for half space, by 4 for 1/4 space, etc.).

  

---

Now let's talk about horns driven by compression drivers. One of the handy pieces of information that used to be included with compression drivers (but is not always now) is the plane wave tube response. A plane wave tube is a tube the same size as the exit of the driver (or smaller or larger and including an adaptor to have a smooth transition from the driver's throat to the size of the tube). There is absorbing material in the tube which is designed to provide a certain load to the driver - a load of rho * c * diameter of the tube, where rho is the density of air and c is the speed of sound. This is usually called a "rho c" load; rho * c is the specific impedance of air. This load is supposed to be constant at all frequencies and allow easy comparison of different drivers, but in reality the size of the tube determines the frequency range measurements are useful in. The upper limit of the tube is set by the diameter. 1.22 * c / d is usually given as the upper limit. There will typically be a notch at this frequency and other notches above it. The lower limit is c / 4 / length of the tube. So only the response between these frequencies should really be looked at. With high frequency horns, you can typically build them large enough to obtain a rho * c * some constant input impedance that is relatively flat above the cutoff frequency (depending on the type of horn). This means in theory the frequency response on the horn will be the same as on the plane wave tube (although the sensitivity will be different - compression drivers' sensitivity on a PWT is very high). The only caveat here is that many high frequency horns have a polar response that varies with frequency. In other words, at low frequencies the horn is not big enough to the control the sound radiated by it, so the sound spreads out over a wide angle. At high frequencies, the horn becomes acoustically large compared to the sound waves being radiated, and the sound is confined into a narrower angle. This means that at higher frequencies more power is concentrated over a given area, so the sound pressure level is higher in that area (but lower outside it). This is effectively an acoustic equalizer, so this effect needs to be added to the plane wave tube response to come up with the on-axis response of the horn / driver combination. This also explains why typical horn design programs do not predict the on axis response of high frequency horns very well - they don't typically include this factor.  
  
"Okay," you say. "That's great, but what if the plane wave tube response is not available?" Many manufacturers provide response data on a horn, but if that's not the horn you want to use, that may not be particularly helpful. In such cases, the typical hobbyist is pretty much stuck with trying to figure out what the sample horn does to the driver's response and then what the horn they're interested in will do or assuming the driver will have roughly flat frequency response up to a certain frequency and then start rolling off based on the flair of the horn and the acoustic equalization that provides. Most ~2" diaphragm / 1" exit drivers will have flat power response up to about 2khz. Some with exotic diaphragms like the TAD 2001 will go up 4khz. In these cases, my approach is to decide on the frequency range I would like to run the driver in based on any data available from the manufacturer or other users' experiences. Then I will design a horn that has a flair frequency an octave or more below the frequency I want to cross the driver over at (to try to avoid stored energy in the horn - see [this page](https://www.jhsaudio.com/storede.html) for a very small beginning at investigating this. However, crossover points and slopes will not be determined until I build the horn / driver combination and measure the frequency response (and impedance if I'm designing a passive crossover).  
  
Now what about the polar response of the horn, and the acoustic EQ it provides? Well, that is tricky... There are analytic methods to calculate this (ie, you can write an equation and solve it to get the answer). However, I don't know of any paper that details in an easy fashion (for the mathematically challenged) how to do this, and a lot of assumptions are still required (which may not be true in the real system, and thus negate some or all of the usefulness of any simulation). Possibly a better way and what I do is to use finite element analysis (FEA) techniques. In this case, assumptions are still typically made such as what the amplitude distribution and shape of the input wave is. Also, there must be a boundary to the simulation, and this is an approximation of reality. In addition, finite element analysis is all just an approximation anyway (to some extent) - you are solving at a finite (as opposed to infinite) number of points, so this implies that some error still exists. All this can be managed to provide good, useful information that correlates to reality, but it is still worth mentioning. However, FEA usually requires software that most people cannot afford (or take the time to learn to use even if they did have it). This basically leaves two options. One is looking at published examples (such as I have on my website here) and extrapolating between data points to get an idea of the performance of the specific geometry you're interested in. The other is to build and acoustically measure the horn, possibly iterating to get to the exact performance you want.  
  

---

If you didn't understand something I wrote here (and you really tried, and you read about related topics other places, and maybe even went to a university library and read about horns in AES journals), feel free to email me (address is on my homepage). I try to at least acknowledge all inquiries. I might expand on whatever you didn't understand in the future.

Copyright 1999-2006, John H Sheerin  
  
[Click here to return to my home page.](https://www.jhsaudio.com/index.php)