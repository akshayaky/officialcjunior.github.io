Hello!

Here, we're going to solve Phase-4 of the Bomb Lab.

If you were looking for some other phases, click on the link below.
  * [Phase -1](https://officialcjunior.github.io/Binary-Bomb-Lab-Phase-1/)
  * [Phase -2](https://officialcjunior.github.io/Binary-Bomb-Lab-Phase-2/)
  * [Phase -3](https://officialcjunior.github.io/Binary-Bomb-Lab-Phase-3/)
  * [Phase -5](https://officialcjunior.github.io/Binary-Bomb-Lab-Phase-5/)
  * [Phase -6](https://officialcjunior.github.io/Binary-Bomb-Lab-Phase-6/)

_________________


First things first, open up the file in GDB and disassemble `phase_4` after entering something as input.


![4-2](../../images/binarybomblabs/4-2.png)



Looking at the code, just like the one before, we can see a memmory address being explicitly pushed into `scanf`. Let's take a look at what's inside.

![4-1](../../images/binarybomblabs/4-1.jpg)

&nbsp;

Alright, so all we have to do is input an integer.


After checking whether the integer is greater than 0 or not in line `<+35>`, the integer is moved onto `eax` and then fed into `<fun7>` as an input at line `<+49>`. And after `<fun7>` returns, `eax` being compared to 0x37, which is 55 in decimal. 

In other words, we have to input the correct integer and make `<fun7>` return 55.

Now, let's see what `<fun7>` is doing with our number.

![4-3](../../images/binarybomblabs/4-3.jpg)



