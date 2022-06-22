# Noise of telescopic amplifier

## Noise

**Noise in the telescopic opamp

For noise analysis of the telescopic op amp, the first thing we do is we analyse the standard cascode current mirror. This will help understand the telescopic later on. Basically **we are going to see that the cascodes don’t contribute noise**, it’s all about the main input devices and main mirror devices, but not the cascodes.

![image](https://user-images.githubusercontent.com/95447782/175024262-d9a9d991-32bf-48ab-a41a-25ea2ba898d2.png)


We analyse the contribution of each transistor separately, then add up contributions.

Contribution of M6:

![image](https://user-images.githubusercontent.com/95447782/175024279-164da006-eef6-4a14-baef-ece1203be95a.png)


Contribution of M2:

![image](https://user-images.githubusercontent.com/95447782/175024292-7bf7720a-aa89-49b7-8b6f-3710fdc35191.png)


Contribution of M1:

![image](https://user-images.githubusercontent.com/95447782/175024314-df4b9a79-b934-47e6-b5cc-5c9fe21660e4.png)


Contribution of M5:

![image](https://user-images.githubusercontent.com/95447782/175024327-559c39a6-c28e-426e-9748-a7e49fa42875.png)


Overall, summing contributions:

![image](https://user-images.githubusercontent.com/95447782/175024340-3f925d84-6fd7-424b-8957-ec64abc9b5a0.png)


Now we can analyze the noise in the telescopic op amp.

We analyze the contribution of each transistor separately, then add up contributions.

As in the 5T op amp, for noise analysis we make the assumption that all transistor gds’s are 0 (infinite rds) as the result will be pretty much the same.

Contribution of M0:

![image](https://user-images.githubusercontent.com/95447782/175024358-fa2e627b-7ebd-4f53-bd07-b9f3b24cdfc8.png)


Contribution of M1:

![image](https://user-images.githubusercontent.com/95447782/175024371-605db82f-ba5b-4536-a8cd-58d0ad705b51.png)


Contribution of M2:

![image](https://user-images.githubusercontent.com/95447782/175024383-73f06b14-51c6-45f0-b06e-756abbe77650.png)


Contribution of M3:

![image](https://user-images.githubusercontent.com/95447782/175024398-a23b563c-b801-4bf7-936c-9d0e6f664f19.png)


Contribution of M4:

![image](https://user-images.githubusercontent.com/95447782/175024424-578aee5f-7e19-429d-895d-844e5a01fd22.png)


Contribution of cascodes M5, M6, M7 and M8:

![image](https://user-images.githubusercontent.com/95447782/175024475-86d2a46f-944e-4b3c-a67a-e4f174f4c934.png)


Overall noise at the output:

![image](https://user-images.githubusercontent.com/95447782/175024498-c97a31f5-af69-4d20-bfef-2cfc1b17ab7c.png)


Next is offset.

## Offset

Next:

* [Offset](Offset_analysis.md)


