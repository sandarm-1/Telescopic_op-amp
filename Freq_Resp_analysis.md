# Frequency response of single stage Telescopic amplifier

## A brief recap

First of all, a brief recap, summary of single stage amplifier so far:

![image](https://user-images.githubusercontent.com/95447782/175022102-bfcea818-fb71-4165-ab7d-04c5460c2a6a.png)


## Limitations of the basic 5T single stage amplifier
Single stage op amp has some limitations:
* You cannot operate it with resistive loads because it will drop the DC gain because DC gain is Ao=Gm·Rout and if you put a resistive load in parallel with this amp’s Rout you will drop the Rout, dropping the DC gain. We don´t want that because lower DC gain will mean larger steady-state error.
* The overall DC gain that we can get from this is quite limited, it’s not huge. It’s gm1/(gds1+gds3) and that is in the order of magnitud of the gain of a single transistor (single transistor gain Av=gm·rds).
* To increase the DC gain of this amp, you would have to increase the rds1 & rds3. We know rds of transistors depends on channel length, longer device is more resistive. But if we increase L of devices, we will also have to increase W proportionally to keep W/L, since we don’t want to change gm1. So overall we will end up increasing the overall size of transistors which will increase parasitic caps and will reduce speed. Even if we don’t care much about speed, and we want to go down this route of increasing L to get some extra DC gain, we cannot increase L by 100 times, so it will be quite limited anyway.
* The way to increase DC gain from this circuit is to use cascodes, both on input pair and on loads, and that leads to the TELESCOPIC amplifier.

In the basic 5T single stage amp the gain was Av=gm1/(gds1+gds3).

To increase that, the first thought could be let’s just incrase gds1 and gds3, making the devices longer.

But that wouldn’t take you very far as you would only gain a small amount of gain, not a lot, you certainly couldn’t get an increase of like 100x in the overall gain.

Why? Because you could increase Length of M1 and M3 a bit, but you would have to increase their W proportionally as well, to keep same W/L, so all the gm’s stay the same, and hence you would quickly blow up the area and hence the parasitics and the circuit would become so large and so slow that it would be unusable.

![image](https://user-images.githubusercontent.com/95447782/175022294-eeb6b216-ae3e-4e54-a31f-eb36a2b2cfac.png)

The right way of increasing the gain is to use cascode devices both in the differential pair and in the current mirror load.


## Current buffer concept and Common Gate amplifier
Before that, let’s remember the concept of a “current buffer”. Since the common gate (cascode) is a current buffer.


![image](https://user-images.githubusercontent.com/95447782/175022321-4c98725c-5ee7-40cf-9708-2098065e8084.png)

And a quick recap about the small signal analysis of the Common Source and the Common Gate, separately, and also both combined in a Cascode Arrangement:

This is the plain Common Source:

![image](https://user-images.githubusercontent.com/95447782/175022442-243bba6e-a2c3-4ef9-a173-21c12c2bd901.png)


This is the Common Gate:

![image](https://user-images.githubusercontent.com/95447782/175022461-534aefd7-c670-45bf-9344-a2e741f007d4.png)


And this is the **Cascode Arrangement (Common Source + Common Gate)**:

![image](https://user-images.githubusercontent.com/95447782/175022485-20ca95c5-cc10-4ac7-9650-313de6920bd8.png)


## Wide swing cascode current mirror

Let’s also remember the cascode current mirror, in particular in its wide swing version.

First of all, this is the standard cascode current mirror, not wide swing version:

![image](https://user-images.githubusercontent.com/95447782/175022524-d4dd336c-dafa-4738-8238-1a8d93f1350c.png)


But the standard cascode current mirror has higher compliance voltage so it’s better to use the wide swing version:

![image](https://user-images.githubusercontent.com/95447782/175022549-8c91c3fd-ad3e-4607-9049-6c73aa943d7d.png)

In this circuit, this is how we bias the cascodes:

![image](https://user-images.githubusercontent.com/95447782/175022631-36417d3e-dc31-4526-928a-b6ee27364e29.png)


![image](https://user-images.githubusercontent.com/95447782/175022638-d3a46606-750a-41b0-a065-2be17b2bcaf0.png)


![image](https://user-images.githubusercontent.com/95447782/175022654-965f1fef-68ea-4aaf-bd09-c7595a2382df.png)


![image](https://user-images.githubusercontent.com/95447782/175023892-74cfa17d-4048-4344-85ac-81a6f59f0c74.png)


As a general rule, **putting two devices in a “cascode arrangement” can be considered as equivalent to having a single transistor with much higher Rout**.

## Gm and Gout of the Telescopic op amp

Finally, using cascode arrangement on the differential pair devices and wide swing cascode current mirror on the current source loads we get the TELESCOPIC op amp:

![image](https://user-images.githubusercontent.com/95447782/175022852-62403df6-2352-4414-8738-b16b2d9da9f0.png)

The reason why we cascode both at the top and bottom is because, from the basic 5T op amp, we know that overall Rout=gds1+gds3, as in the parallel combination of rds1 and rds3, since rds1 (diff pair devices) and rds3 (current mirror devices) appear in parallel, there is no point in increasing only one through cascoding and leave the other one small, since due to the parallel the smallest one would dominate. We have to increase both through cascoding both top and bottom.

And after all this topology is pretty much the same as the basic single stage op amp. In fact, for each cascode device arrangement, like in the differential pair, we can consider the pair of transistors (common source + cascode) as if it was just a single transistor with much larger Rout. And the current mirror on top is again just another current mirror but with larger Rout.

This is the Gm and Rout calculation, with that we calculate the DC gain Gm·Rout.

![image](https://user-images.githubusercontent.com/95447782/175023011-116c7901-2c2b-49d7-9e31-7325be714799.png)


The single stage cascode opamp or telescopic opamp is also just a transconductor, whose transconductance is the same as the transconductance of one single device of the differential pair, and Rout is larger than in the 5T opamp.

![image](https://user-images.githubusercontent.com/95447782/175023044-85537e26-6c1f-4138-982a-697720d41632.png)


With the telescopic we can get much higher gain than with the basic 5T opamp:

![image](https://user-images.githubusercontent.com/95447782/175023067-dc14e242-f8cf-47b2-8c75-20b27b236c03.png)


Now let’s look at FREQUENCY RESPONSE of the Telescopic opamp.

## Frequency response of the Telescopic op amp

First of all, if we only look at the transconductor driving a capacitor, without thinking about parasitic caps yet, it’s a single pole system. Exactly the same as the 5T op amp. Just that it has more gain due to the larger Rout, and also the dominant pole is at lower frequency due to the larger Rout also, but once we multiply DC gain times dominant pole we see that the unity gain frequency omega_u is exactly the same as in the 5T.

![image](https://user-images.githubusercontent.com/95447782/175023130-aa73d086-79d9-454c-a244-0b98e428395d.png)


Now, frequency response looking at the parasitic caps.

For an initial, simplified analysis, we ignore all the orange caps (although we will have to take them into account later or at least what we usually do is rely on the simulator to see where they are and see if they are at sufficiently high frequency so that they don’t cause trouble with stability, we want them to be at sufficiently high frequency). If we ignore the orange caps for the moment we are left only with the Cd3 cap just like in the 5T opamp. In that sense, that creates exactly the same effect of imperfect mirroring at high frequencies and it creates the same non dominant pole and corresponding zero at twice that frequency.

![image](https://user-images.githubusercontent.com/95447782/175023149-18709ba4-6a6d-4a30-866a-f06f5451deaf.png)


Now what is the effect of the other parasitic caps, the ones that we ignored initially, the orange ones?

They will create poles and we will need to be aware of them and make sure they appear at high enough frequencies so that they don’t cause stability troubles. We usually do this with the simulator rather than by hand calculation, with the simulator we see where they are and if they are at sufficiently high frequency or not, if they aren’t then we need to do something to try to push them up to higher frequencies which is probably done reducing the parasitic cap values on those nodes, as those parasitic caps appear on the denominator of their respective poles hence lower cap values will mean higher pole frequencies.

It turns out, if we look at a cascode arrangement in isolation, each cascode arrangement contributes one pole at a frequency -gmc/Cp where Cp is the parasitic cap at the middle node of the cascode arrangement.


Hence in the telescopic circuit, these parasitic caps at the intermediate nodes of each cascode arrangement (the orange caps) will each contribute a parasitic pole. We will look at these with the simulator and ensure they appear at high enough frequencies so they don’t cause trouble with phase margin, or reduce the unity gain frequency.

![image](https://user-images.githubusercontent.com/95447782/175023174-73e6dad3-eb75-4d86-9358-1c5cfefe08fc.png)


Therefore:

![image](https://user-images.githubusercontent.com/95447782/175023191-d91372fc-60f1-44a8-9f7c-799d0f4eb63c.png)


Same thing, tidied up a bit:

![image](https://user-images.githubusercontent.com/95447782/175023205-f722d703-361c-4272-8ed6-508f75a00fdb.png)


And

![image](https://user-images.githubusercontent.com/95447782/175023220-6cfcdd68-b303-4d41-8d6b-72d3c86372e9.png)


That concludes the Frequency Response analysis of the TELESCOPIC op amp.

The summary for frequency response is:
* overall it’s quite similar to the basic 5T op amp
* the Cd3 parasitic cap will create the main non-dominant pole and zero
* and then the other para caps contributed by the intermediate nodes of each cascode arrangement just try to shove them up to higher frequencies minimizing parasitic cap on those nodes, or reduce the unity gain frequency.


Next is noise.

## Noise

Next:

* [Noise](Noise_analysis.md)











