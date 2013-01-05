Intro
=====
How does the internet as we know it work ? What happens during that one second between you type the address of a web site and see the content in your browser ?

To explain that one second can easily make a several hours long documentary series and it sure did take decades of research until humans came to this point.

Let's see what happens while we are retrieving a web page and let's do that in complete lay men terms, yet in great, great detail.

This is an open and ongoing project.

Contribute
==========
Any kind of contribution is more than welcome.

  - **Correction**: Technical or editorial.
  - **Authoring**: Writing, re-writing a chapter or even a paragraph.
  - **Translation**: Once the book is stable, which will be quite a while, you can help translating it.
  - **Ambiguity**: If one part is not clear to you, if it is not simple enough, please let me know what is not
  clear.
  - **It does not make perfect sense**: If some of the stuff explained here does not make sense to you, if you
  think "*uhmm, well, OK, but it could have been done like this and it would be better*", let me know because
  most of the things explained here are designs that have survived many years, every piece of them are designed
  the way they are because of some reason that makes perfect sense (at that time, at least).
  <p>I call these situations <strong>mind set mismatch</strong> and that is one thing I suffer when reading documents. I find myself thinking: "<em>Well, idiots, I would've done it some other way, and it would be better because of x</em>". Often, sooner or later, I see why they have done it the way they did and why I was wrong. But these vague moments ruin the rest of my read, so, I do not want you to have them here!

License
=======
  - Free for non-profit usage. You can even create hard copies of this book and distribute it, provided that it is
  non-profit.
  - All copyrights belong to the authors who wrote the content.
  - Derivative works also subject to this license.

Audience
==========
Anyone, engineer or not, interested in how this little phenomenon called world wide web works is more than welcome to read this book. This book is supposed to be jargon-free and written in "explain me like I'm five" approach.

I find this whole phenomenon quite astonishing and I wish everybody to appreciate it.

I hope this is especially inspirational for young people. If the book grabs a few brilliant minds, make them even more curious and draws them to wonderful world of computers, this book has exceeded my expectations.

Goals
=====
If any of the following goals are not met for any part of the book, it means that the book has failed.

  - **Accuracy**: You think some part of this document is not accurate.
  - **Clarity**: Any part of this document is ambiguous to you.
  - **Makes perfect sense**: If some information presented here does not make perfect sense to you. (Please see Contribute sections last bullet for more information).</li>

Contents
======
Chapter 1 - Journey of letters from keyboard to the computer

Chapter 2 - What does computer do with all these letters ?

Chapter 3 - So, browsers know what you want, now what ?

Chapter 1 - Journey of letters from keyboard to the computer
============================================================
Each time a user hits a key on her keyboard, an information is sent to the computer. But how does a keyboard communicate with the computer ?

The answer is simple: over a wire! Most of the keyboards we use today are connected to the computer with wires -- including our laptops.

These are electronic devices and all wired communication between them are done electronically. But how does it actually work ? How is information transferred from one end of the wire to the other end.

OK, let's start with an ancient analogy and slowly approach to how it is done today.

Smoke Signalling
----------------
Remember smoke signalling from the movies ? Smoke signalling is one of the oldest long distance communications originating from as early as 150 BC.

People realized that they can actually see smoke from very long distances. So, they figured, if they can apply some sort of pattern to the smoke, the other party observing the smoke from far away can tell something from the pattern.

This is what we call **encoding** information and **decoding** it.

Imagine you block the smoke every once in a while and create a two big smoke chunks separated from each other. This surely is not a natural smoke pattern and other parties observing the smoke from hundreds of kilometers away can tell that there's something to it.

So, if both party have agreed on a code. They can understand each other.

Let's assume that, "WE ARE UNDER ATTACK" message is encoded as two big chunks of smoke.

So, the sender can create two big chunk of smokes and since the receiver knows how to decode two big chunks of smoke, he can tell that the sender is saying "WE ARE UNDER ATTACK".

**Lesson learnt: information encoding and decoding.**

Electrical Telegraphs (Encoding and Syncronization)
---------------------------------------------------
Fast forwarding 2000 years from 150 BC, in 1836 humans invented electrical telegraph which is a modern version of smoke signalling and it is very much like how electronic devices communicate today.

For those of you who does not remember what electrical telegraph is; it is basically two guys communicating with each other over a wire built between very long distances. It is the fastest way of communication of its day. Each party has one big button in front of him and when you click on the button the other party hears your click.

So, people figured that, if they can encode some information with these clicks, like their ancestors did with the smoke, they can actually send meaningful messages with the telegraph.

So, they've developed codes for it. You might have heard one of them before, the **morse code**.

They've specified two types of clicks: **dot** (short) and **dash** (long) clicks which is basically a short beep and a long beep in the recievers end. They've used these two types of clicks to encode latin alphabet and even more.

So each combination of **dots** and **dashes** meant something.

They've encoded each letter to some combination of these clicks. For instance:

    S is ... 
    O is ---

So, if you shortly click the button for three times, the receiver knows that you've sent **S**. If you click the button and hold it down a bit longer for three times, it means you've sent an **O**.

So to send out the international famous signal of asking for help, SOS, you simple send ...---...
       
    SOS is ...---...

Fantastic but there are a couple of problems to solve. Let me demonstrate you with an example, as per usual. The code for E is .

    E is .

Now, knowing that a dot means E, how do we interprete SOS signal correctly ?

    ...---... could mean either EEEOEEE or SOS ?

Which means

    ... could either mean one S or three E letters.

So fix this ambiguity there's set of rules you obey. After each letter you make a silent pause as long as a dot.

    SOS ... --- ... (note the empty spaces between ... and ---)

If we ever wanted to send EEEOEEE, we'd

    EEEOEEE . . . --- . . .

This is often called **synchronization**. Two parties synchronize, so that each of them knows when one of them is ended sending a unit of information. In this particular case, a moment of silent tells that we have completed sending a letter.

This is pretty much all you need to know abour morse code for now.

**Lesson learnt: Synchronization.**

Now, let's proceed, we are very close to how today's electronic devices actually communicate.

How does electronic devices communicate today ?
-----------------------------------------------

Pretty much like electric telegraphs, electronic devices also send a current over a wire to the other connected devices. This is the basis of most of the communication you're using it today such as LAN, keyboard, mouse, printer -- practically anything with a wire.

We've learnt two concepts in communication so far, **encoding** and **synchronization**. Now, lets put them to use.

**Encoding**

What we can do with a wire connected at both ends is to apply a **voltage** to it. For instance, keyboard can apply a voltage of 5 V and the computer's hardware can sense this change. Now, the computer needs to interprete the voltage it's sensing. Electronic circuitry in the computer decides what this voltage actually means. Circuitry in today's computer categorizes the voltage they are sensing on a wire into two categories; **High** or **Low**. Circuitry will tell the computer that, the wire is **High** if the voltage is above a threshold and **Low** if the applied voltage is below another threshold. So, computer interpretes the applied voltage to itself as either **High** or **Low**. 

![Voltage Thresholds](https://github.com/engina/the-internet-book/raw/master/exports/voltage_thresholds.png "Voltage Thresholds")

As you can see in the above figure, a circuitry designed with such specifications will interprete any voltage from 2 to 5 as **High** and any voltage from 0 to 0.8 as **Low**.

An alternative and more common way to say **High** and **Low** is **1** and **0**. High is 1 and Low is 0.

Anything sounds familiar ? We've learnt that, according to the applied voltage, the computer thinks it received a <strong>1 or 0</strong>. All those Hollywood hacker movies will start to make sense in a moment.

So, keyboards (and electronic devices in general) can send either 1 or 0 at a given time. Unfortunately,  this <strong>bit</strong> of information is not enough to let computer know which key the user pressed. So, we must send more <strong>bits</strong> of information continuously to actually mean something. Please note that I'm using the term <strong>bit</strong>.

Now, imagine we send two <strong>bits</strong> of information.
<table class="aligncenter" style="width: 300px;" border="1" align="center"><caption> </caption>
<tbody>
<tr>
<td style="text-align: center;"><strong>First bit</strong></td>
<td style="text-align: center;"><strong>Second bit</strong></td>
<td style="background-color: orange; text-align: center;"><strong>Information</strong></td>
</tr>
<tr>
<td style="text-align: center;">0</td>
<td style="text-align: center;">0</td>
<td style="background-color: orange; text-align: center;">0</td>
</tr>
<tr>
<td style="text-align: center;">0</td>
<td style="text-align: center;">1</td>
<td style="background-color: orange; text-align: center;">1</td>
</tr>
<tr>
<td style="text-align: center;">1</td>
<td style="text-align: center;">0</td>
<td style="background-color: orange; text-align: center;">2</td>
</tr>
<tr>
<td style="text-align: center;">1</td>
<td style="text-align: center;">1</td>
<td style="background-color: orange; text-align: center;">3</td>
</tr>
</tbody>
</table>
<p style="text-align: center;">Table 1-a</p>
Looks like with 2 **bits**, we can send 4 different information. We can also map these information to a more meaningful value. Image a table like this:

Fine. But what if keyboard sends two consequent 5V volts to send 1 and 1. How does computer tell when one bit of
information ends and the next one begins ? That two consequent 5V signals could mean one 1, two 1s or many 1s.

To separate bits of information in continuous signal, we often use another wire which we call clock.

![Clocking](https://github.com/engina/the-internet-book/raw/master/exports/clock.png "Clocking")


<table class="aligncenter" style="width: 300px;" border="1"><caption> </caption>
<tbody>
<tr>
<td style="text-align: center;"><strong>Information</strong></td>
<td style="text-align: center;"><strong>Value</strong></td>
</tr>
<tr>
<td style="width: 150px; text-align: center;">0</td>
<td style="text-align: center;">H</td>
</tr>
<tr>
<td style="text-align: center;">1</td>
<td style="text-align: center;">E</td>
</tr>
<tr>
<td style="text-align: center;">2</td>
<td style="text-align: center;">L</td>
</tr>
<tr>
<td style="text-align: center;">3</td>
<td style="text-align: center;">O</td>
</tr>
</tbody>
</table>
<p style="text-align: center;">Table 1-b</p>
Sweet. So if keyboard sends, 2 bits of information to computer. It can send an information from 0 to 3 which computer can look it up from a table to see what it actually means.

Imagine keyboard applied voltage to its wire two times. First it set the voltage to 5 volts which means 1 and then sets the voltage to 0 volts which means 0. So the keyboard practically sent 1 and 0 to the computer which is equal to information 2 as you can see in Table 1-a. Then the computer can look what is information means up from Table 1-b and see that it means L.

Now, image the keyboard applies these voltages to the wire.

0V 0V    0V 5V    5V 0V    5V 0V    5V 5V

Computer would interpret these voltage like this, as we already learnt.

0   0       0   1      1   0       1   0      1   1

Nice. Then computer can look each pair of bits up in the Table 1-b. And the result will be the following

H            E           L            L           O

Oh my goodness! The keyboard just sent a meaningful message to the computer. <strong>HELLO</strong>

We can formalize the number of information we can encode as <strong>2<sup>n</sup></strong>. <strong>2</strong> is the number of states each bit can represent, in our case it is two because it can be either 1 or 0 and <strong>n</strong> is the number of bits.

So, if we send 8 bits, it can represent 256 (2<sup>8</sup>) different information, that is values from 0 to 255. Note: In computer world everything starts from index 0.

You might be wondering, instead of sending just 1 and 0, why don't we send 2, 3, 4 too ? So that we could have sent more information with each bit. To do that, circuits must interpret different voltage levels as different numbers. Well, rest assured, I've heard that it has been tried but 1, 0 design won over time. [find references]

We got the basics of how electronic devices are communicating but there's more. The exact way how the data is sent depends on the underlying technology.

Nowadays the dominant way of connecting a keyboard to a computer is USB, before that PS/2 connectors were used. Still to this day, PS/2 is used. Most of the laptop keyboards are internally connected via PS/2 connectors. Both of these technologies use serial communication
