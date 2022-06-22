# Slew Rate of telescopic amplifier

## Slew Rate

Slew rate is **the maximum rate of change that you can get on the output**.

If you apply **a large enough voltage STEP at the input, large enough that it saturates the diff pair, i.e. all the current goes to one branch while the other is dry**, then the current Io will flow to the output, charging the output cap C up at a constant current, so **the voltage will rise with a slope of that current divided by C**.

That´s the Slew Rate.

To measure the slew rate we add the capacitive load at the output, thus completing the op amp, and we apply unity gain feedback.


![image](https://user-images.githubusercontent.com/95447782/175025362-499ca5d4-26ba-452a-a68c-b86f305b9a83.png)


It turns out **the Slew rate of the telescopic op amp is exactly the same as the basic single stage op amp based on a simple differential pair and current mirror**.

Next is swing limits (large signal swing).




## Swing limits

Next:

* [Swing limits](Swing_analysis.md)

