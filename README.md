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
  - **Makes perfect sense**: If some information presented here does not make perfect sense to you. (Please see Contribute section's last bullet for more information).</li>

Contents
======
Overview

Chapter 1 - Journey of letters from keyboard to the computer

Chapter 2 - What does computer do with all these letters ?

Chapter 3 - So, browsers know what you want, now what ?

Overview
========
![Overview](https://github.com/engina/the-internet-book/raw/master/exports/overview.png "Voltage Overview")

This book aims to explain all nitty gritty details of a web page retrieval in correct order. For instance, it will start teaching how the keys you press on your keyboard travel all the way up to your computer.

Unfortunetely however, there's no single path while retrieving a page.

For instance, we can plug our keyboard with PS/2 (laptops and old PCs), USB or bluetooth. Even though the big picture remains the same, hardware interfaces differ in each scenario. We can make a sacrifice and go with the simplest hardware interface, or explain each of them in detail. To explain all of them, support from community is required, as it is a broad topic.


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

Electrical Telegraphs
---------------------
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

To fix this ambiguity there's a set of rules you obey. After each letter, you make a silent pause as long as a dot.

    SOS ... --- ... (note the empty spaces between ... and ---)

If we ever wanted to send EEEOEEE, we'd

    EEEOEEE . . . --- . . .

This is often called **synchronization**. Two parties synchronize, so that each of them knows when one of them is ended sending a unit of information. In this particular case, a moment of silent tells that we have completed sending a letter.

This is pretty much all you need to know abour morse code for now.

**Lesson learnt: Synchronization.**

Now, let's proceed, we are very close to how today's electronic devices actually communicate.

So, how does electronic devices communicate today ?
---------------------------------------------------

PS/2
----

Pretty much like electric telegraphs, electronic devices also send a current over a wire to the other connected devices. This is the basis of most of the communication you're using it today such as LAN, keyboard, mouse, printer -- practically anything with a wire. 

We've learnt two concepts in communication so far, **encoding** and **synchronization**. Now, lets put them to use. 

Here's how a PS/2 keyboard communicates today. PS/2 connection is an old technology but it is still used in laptop keyboards so it is pretty relevant.

PS/2 concepts explained here also applies to other electronic communication busses, such as SPI (Serial Peripheral Interface) which is used in many integrated circuits. For instance, it is quite common for two chips to talk to each other over SPI.

**Encoding**

In smoke signaling, we were using continuity of the smoke to encode information. Like, if it is two separate chunks of smoke, it means "WE ARE UNDER ATTACK".

In electrical telegraphs, we used short and long beeps to encode information. Like, letter S is encoded with three short beeps (...) and letter O is three long beeps (---).

In modern electronic devices, we use voltage levels on the wire to encode information. For instance, if the keyboard is applying 5 volts to the wire, computer interprets it as High and if the voltage is 0 volts the computer interpretes it as Low.

Of course, in practice, the computer interprets a voltage level as **High** if it is between a range and the same also applies for **Low**. Say, it is considered High if the voltage level is between 3 and 5 Volts. And likewise, it is considered Low if the voltage level is between 0 and 1 Volts. But for simplicity's sake we can just assume High is 5 Volts and Low is 0 Volts.

An alternative and more common way to say **High** and **Low** is **1** and **0**. High is 1 and Low is 0.

So we encode information into voltage levels. In this particular case, only information we can send is 1 or 0. In the morse code, it was a dot and a dash.

So, keyboards (and electronic devices in general) can either send 1 or 0 at any given time. Unfortunately,  this **bit** of information is not enough to let computer know which key the user pressed. So, we must send more **bits** of information continuously to actually mean something. Please note that I'm using the term **bit**.

Now, imagine we send two **bits** of information.
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
Looks like with 2 **bits**, we can send 4 different information. We can also map these information to a more meaningful value. Imagine a table like this:

<table align="center" style="width: 300px;" border="1"><caption> </caption>
<tbody>
<tr>
<td style="text-align: center;"><strong>First bit</strong></td>
<td style="text-align: center;"><strong>Second bit</strong></td>
<td style="text-align: center;"><strong>Information</strong></td>
<td style="text-align: center;"><strong>Value</strong></td>
</tr>
<tr>
<td style="text-align: center;">0</td>
<td style="text-align: center;">0</td>
<td style="width: 150px; text-align: center;">0</td>
<td style="text-align: center;">H</td>
</tr>
<tr>
<td style="text-align: center;">0</td>
<td style="text-align: center;">1</td>
<td style="text-align: center;">1</td>
<td style="text-align: center;">E</td>
</tr>
<tr>
<td style="text-align: center;">1</td>
<td style="text-align: center;">0</td>
<td style="text-align: center;">2</td>
<td style="text-align: center;">L</td>
</tr>
<tr>
<td style="text-align: center;">1</td>
<td style="text-align: center;">1</td>
<td style="text-align: center;">3</td>
<td style="text-align: center;">O</td>
</tr>
</tbody>
</table>
<p style="text-align: center;">Table 1-b</p>
Sweet. So if keyboard sends, 2 bits of information to computer. It can send an information from 0 to 3 which computer can look it up from a table to see what it actually means. This is pretty much like morse code sending a combination of dots and dashes to encode a letter, here we send 1 and 0 to encode the letter information.

So, if the keyboard wants to send a few letters to the computer, it needs to send numerous ones and zeros continiuously. Imagine keyboard applied voltage to its wire two times. First it set the voltage to 5 volts which means 1 and then sets the voltage to 0 volts which means 0. So the keyboard practically sent 1 and 0 to the computer which is equal to information 2 as you can see in Table 1-a. Then the computer can look what that information means up from Table 1-b and see that it means **L**.

But, we have a similar synchronization problem as we had in morse code. When the keyboard is sending two zeros or ones consequently, how can the computer tell when one ends the other one begins ? In the electric telegraph, we solved the issue by adding silences between each letter. That solution works well for humans but in this particular case it is machines talking to each other so we can use a much more efficient way to do that: **Clock signal.**

We send the data over one wire and we send clock signal from another wire so that the computer knows when to check the data wire.

![Clocking](https://github.com/engina/the-internet-book/raw/master/exports/clock.png "Clocking")

You'll find in the above figure that computer will interpret the data wire only when the signal on the clock wire rises. It is called rise and fall when signal goes from low to high and high to low respectively.

Note that this is electronic devices talking to each other. None of the parties is human. Everything is automated. So, it is done in a quite fast manner. For PS/2, about 10000-16000 bits are transferred per second. That is, 10-16 kHz.

You might think that it is pretty fast, now imagine there are stuff in your computer doing this kind of stuff at the rates of millions (MHz) or even billions (GHz) of times per second.

OK, all the problems are solved. Now, we know how keyboards encode and synchronize data with the computer now. Now let's approach to the reality a bit more.

**Encoding a Bit More**

So, we've learn how to send 4 letters with 2 bits but in practice we need much more. We need to send letters, numbers, enter and space keys, modifier keys such as Ctrl, Shift, Alt and more!

We can formalize the number of information we can encode as **2<sup>n</sup>**. **2** is the number of states each bit can represent, in our case it is two because it can be either 1 or 0 and **n** is the number of bits.

At this point, you might be wondering, instead of sending just 1 and 0, why don't we send 2, 3, 4 too ? So that we could have sent more information with each bit. To do that, circuits must interpret different voltage levels as different numbers. Well, rest assured, I've heard that it has been tried but 1, 0 design won over time. [find references]

Anyway, back to reality. So, if we send 8 bits, it can represent 256 (2<sup>8</sup>) different information, that is values from 0 to 255. Note: In computer world everything starts from index 0.

So, we've learnt what a bit means and what all those mysterious ones and zeroes they use in Hollywood hacker movies really are! Not too bad for a first chapter, right ?

USB
----
???

Bluetooth
---------
???


Chapter 2 - What does computer do with all these letters ?
==========================================================
[Shall we describe how OS passes these letters to the user space program]
???

Chapter 3 - So, browsers know what you want, now what ? [ IN PROGRESS]
=======================================================
Fantastic. The browser finally knows that we want to visit **facebook.com**. Now what ?

Our browser will send a request to the server who is hosting **facebook.com**. Brace yourselves, at this very second, we are entering the world of networking.

When it comes to networking things are quite analogous to telephones. If you need to get an **information** from **Jane**, you have to look up her **phone number** from a **phone book**, call her and ask what you gotta ask and hopefully get a **response**.

In this particular case, the information we need is a **web page** from **facebook.com**. To request the web page from facebook.com, we need to know facebook's **IP address** -- instead of a phone number. IP is an acronym for Internet Protocol, so what we are looking for here is the Internet Protocol Address of facebook.

You might ask, why ? Why do we need an IP address, we already know the domain name, facebook.com. Remember the telephone analogy. It's prerty much the same with the internet too. Internet is designed from ground up to be based on IP addresses just like our telecommunication is based on phone numbers. When you are calling your friend with your phone, you pick her name and phone looks it up from its phone book and calls the number. And in networking, your computer looks up the IP address from DNS servers.

To resolve the hostname to an IP address we need to talk to the DNS server and before we go into that, we have to cover how this TALKING actually takes place.

Communication of Networked Devices
----------------------------------
As computer scientists designed and developed networks, they have deducted some lessons from the experience and they designed the OSI model which is the foundation of our netorking system that we use today.

Roughly speaking this model dictates that there are several layers in communication and each layer is transported by the layer below it.

Imagine you have two documents that you want to send. One is to Jane and the other one is to John. Both **Jane** and **John** works at **Acme Corp**. Jane works at in the **Human Resources** department and John works in the **Sales Department**.

The well organized person you are. You prepare a big envelop that is addressed to Acme Corp. Then you prepare two smaller envelopes addressed to Human Resources and Sales respectively. Then you write down who is the documents addressed to on top of each document.

So you have one big envelop that has two smaller envelopes, each having one document in them.

**Postman** delivers the envelop to Acme Corp., **Mail Staff** opens the envelope and sees that there are two other envelopes. They forward the smaller envelop to their respective departments.

Each department's **secretary** opens the envelop and see who is the document inside is addressed to. She easily figures it out, as you wrote who are they addressed to on top of them!

Voila! You have very well structured document delivery system which can even deliver a document to a person in a building full of thousands of employees.

Here Postal Office ls Layer 1, Mail Staff of Acme Corp is Layer 2 and Secretaries are Layer 3. Mail Staff can only work when Post Office did its job correctly. Likewise Secretaries can't work if Mail Staff fails. Hence all layers depends on the one below them.

You know what ? This is pretty similar to how networks really work today.

* Layer 1 is the outer-most envelope which has the address of Acme Corp.
* Layer 2 is an inner envelop which is addressed to Jane.
* Layer 3 is the document which has a Sequence Number on it and asks for Acknowledgement.

	    +---------------------------------------------+
	    | Acme Corp.                                  |
	    | +-----------------------------------------+ |
	    | | To: Human Resources                     | |
	    | | +-------------------------------------+ | |
	    | | | To: Jane                            | | |
	    | | |                                     | | |
	    | | | Here goes the actual document data  | | |
	    | | | …                                   | | |
	    | | +-------------------------------------+ | |
	    | +-----------------------------------------+ |
	    +---------------------------------------------+
    

We can go one step further and roughly map this analogy to today's networking.

- Layer 1 is Ethernet (Postmen)
- Layer 2 is IP       (Acme Corp. Mail Staff)
- Layer 3 is UDP      (Secretaries)
 
Now, let's complicate the situation a bit more. Assume we keep having documents for Jane at Acme Corp. from time to time. And we want to send them to Jane but this time we want to make sure that the documents are actually received by Jane and the documents are delivered in correct order.

To accomplish this, we need some sort of **Acknowledgment** and **Sequence Numbers** mechanisms. Let's add two more notes on top of the documents.

	    +---------------------------------------------+
	    | Acme Corp.                                  |
	    | +-----------------------------------------+ |
	    | | To: Human Resources                     | |
	    | | +-------------------------------------+ | |
	    | | | To: Jane                            | | |
	    | | | Sequence Number: 5                  | | |
	    | | | !Please send acknowlegement!        | | |
	    | | |                                     | | |
	    | | | Here goes the actual document data  | | |
	    | | | …                                   | | |
	    | | +-------------------------------------+ | |
	    | +-----------------------------------------+ |
	    +---------------------------------------------+

Now, secretary has two more responsibilities. Putting the documents in the right order before delivering them to Jane and send an acknowledgement back to the sender, so that she know the documents are delivered. This secretary is called TCP.
	    
TCP provides reliabiliy.

So why on earth we'd use UDP for if TCP is doing a much better job anyway ?

Sticking to our analogy, TCP is more espensive as there are Acknowledgments.

But cost itself is not the real reason why UDP is still used today. Imagine, we've sent 4 documents. Somehow 2nd document get lost in the mail. Secretary received 3 documents with sequence numbers 1, 3 and 4. Secretary has to wait for the 2nd document to arrive so that, she can sort the mails and deliver to Jane. We will send 2nd document again because we won't receive an Acknowledgement for it. As youcan see, in case of any packet loss, all subsequent packets are delayed.

For stuff like downloading big files or streaming movies this is not important, as we need every single piece of data in the right order anyway. But for, say, real-time First Person Shooter games, a delay is intolerable. We rather lost one message and continue on processing other messages than to introduce a lag in a real time game. Hence UDP is almost a standard in gaming protocols.

We modeled our analogy in 3 layers; outer envelope, inner envelope and the document. Let's see how exactly is the OSI model that we talked about in the beginning of the section. Also show the more modern TCP/IP Model which is a simplified view of OSI Model.

[[SHOULD WE JUST OMIT OSI MODEL ALL TOGETHER?]]

<table>
	<tr>
		<th>OSI Model</th>
		<th>TCP/IP Model</th>
		<th>Our analogy  model</th>
		<th>Protocols</th>
	</tr>
	<tr>
		<td>Layer 1 (Physical Layer)</td>
		<td rowspan=2>Level 1 (Physical Layer)</td>
		<td rowspan=2>Level 1 (Postman)</td>
		<td rowspan=2>Ethernet</td>
	</tr>
	<tr>
		<td>Layer 2 (Data Link Layer)</td>
	</tr>
	<tr>
		<td>Layer 3 (Network Layer)</td>
		<td>Level 2 (Network Layer)</td>
		<td>Level 2 (Mail Staff)</td>
		<td>IP</td>
	</tr>
	<tr>
		<td>Layer 4 (Transport Layer)</td>
		<td>Layer 3 (Transport Layer)</td>
		<td>Layer 3 (Secretary)</td>
		<td>IP, ARP, ICMP</td>
	</tr>
	<tr>
		<td>Layer 5 (Session Layer)</td>
		<td rowspan=3>Layer 4 (Application Layer)</td>
		<td rowspan=3>Even though we haven't named it our <br/>document's content can be considered as <br/>Layer 4 (Application Layer)</td>
		<td rowspan=3>DHCP, DNS, HTTP</td>
	</tr>
	<tr>
		<td>Layer 6 (Presentation Layer)</td>
	</tr>
	<tr>
		<td>Layer 7 (Application Layer)</td>
	</tr>
</table>

Please, note that, protocols given are only relevant examples that we will explain in further detail. There are many more protocols out there.

Now, let's study these layers in computers.

Physical Layer
--------------
The lowest level layer of our model. In our real world analogy it was the postman. In computing, it is your network interface. Most laptop have at least two network interfaces that we are interested: wired and wireless. One is where you plug-in your LAN cable (if you still have one) and the other one is the wireless. Nowadays, as laptops get smaller, support for LAN is being dropped, and it is completely justified.

Luckily, regardless of which interface (wired or wireless), we use Ethernet frames. **A frame is a fancy term for an envelope in networking jargon.**

We just prepare an Ethernet frame (envelope) and place it in the physical network hardware and the hardware does its magic to send it -- which we will be explaining.

So let's start understanding our Layer 1. This is the basic structure of an Ethernet frame.

	+---------+---------+---------+-----------------+----------+
	| Mac Dst | Mac Src |   Type  |     Payload     | Checksum |
	+---------+---------+---------+-----------------+----------+
	| 6-bytes | 6-bytes | 2-bytes | up to 1500 bytes| 4-bytes  |
	+---------+---------+---------+-----------------+----------+

[[NEW TERM: Header]]
In computing, we call the information preceeding the actual payload, a **header**.
[[NEW TERM END: Header]]

This is our outer most envelope, our Ethernet frame.

* **Mac Dst** is the destination adress, this frame is addressed to
* **Mac Src** is the source address, the sender of this frame
* **Type** is the type of content this frame is carrying
* **Payload** the actual content of this frame, it can be data, or another frame (an inner envelope)
* **Checksum** is a magical mathematical number (read below)

[[New Concept: CHECKSUMS]]

Checksum is an error detection technique. It is computed from the data preceeding it. Both the sender and receiver computes it and compares if they match or not. If it does not match there was an error in communication.

Let's see with an example.

Imagine you are talking to Jane over the phone and you want to tell her that, this is the **bee** season and she should be careful because she has allergies but there's a problem in the phone line and the voice quality is even worse than a normal phone conversation.

You want to make sure that she understands you correctly. Luckily Jane and you developed a technique to overcome this situation before. When you say a word, you will compute and say its checksum afterwards. Jane will compute the checksum of the word she had just heard. So she can compare the checksum you told her with the one she computed and see if there was an error.

Now, let's remember what we've learnt in Chapter 1. Each letter can (and will) be represented by a number. Let's assume

- B is 66
- E is 69

Let's define our checksum algorithm as the sum of the values of the letters present in the word.

Computing the checksum the word "BEE" with this algorithm, we will have a checksum of 204 (66 + 69 + 69).

Now, after the word **BEE**, you will say **204** to Jane.

Due to poor voice quality, Jane thought you said **PEE 204**. Jane starts calculating the checksum of the word **PEE**. From prior mutual agreement she also has a table that shows the values of each letter. She looks up and figures:

- P is 80
- E is 69

She calculates the checksum of **PEE** as **218**. She notices that the checksum you said was **204** and not the same as the checksum she calculated. So she knows that there was a mishearing and now she doesn't think that you are stupid because you said "pee season".

As you can see Jane has successfully detected the error. She will ask you to repeat that word and you will re-say the word until the checksums match.

However, keep in mind that in practice, checksum algorithms are much more complicated.

[[END OF NEW CONCEPT]]

Luckily every physical device comes with a unique MAC address preconfigured. So, we know what to write to *MAC src* field in the frame. Some hardware might not even allow you to write *MAC src* field manually and fills in the preconfigured MAC address there automatically -- hence stop you from forging fake addresses.

Most hardwares also compute the checksum for you. So, you basically, just need to fill in *MAC dst*, *Type* and *Payload* fields.

Network Layer
--------------
Let's remember that in our real world analogy, Network Layer was the Mail Staff of Acme Corp.. Postman delivers a big envelope which contains smaller envelopes to the Mail Staff.

Postman is Physical Layer in this case and the big envelop is the Ethernet Frame. Smaller envelops are most often IP Frames. IP is the acronym of Internet Protocol and it pretty much envelops everything that is related to Internet as we know if.

Note: Smaller envelop can also be an ARP (Address Resolution Protocol) or an ICMP (Internet Control Message Protocol) packet instead of an IP packet but we will explain later, just when we need them.

Let's learn how does a IP Frame look like.

[[NEW CONCEPT: WORD]]
Word is a term for the natural unit of data for a particular processor design.

For instance, for a 32-bit processor, word size would be 32-bits. When we use the term **word** for the processor what we actually mean is a group of bits of size 32.

The reason we call it the *natural unit of data* is that, the processor has indeed specifically designed for that particular data size and it is most efficient when working on multiples of that data size.

For now, just know that, a word is a fixed size group of bits.
[[END NEW CONCEPT: WORD]]

An IP Frame has at least a 20-bytes header. We usually say, it consist of at least 5 words. Word being 32-bits, hence each word is 4 bytes.

Let's learn word by word, what each bits of IP Header mean.

              +---------------------------------------+---------------------------------------+---------------------------------------+---------------------------------------+
              |             8-bit                     |             8-bit                     |             8-bit                     |             8-bit                     |
              +----+----+----+----+----+----+----+----+----+----+----+----+----+----+----+----+----+----+----+----+----+----+----+----+----+----+----+----+----+----+----+----+
              |  0 |  1 |  2 |  3 |  4 |  5 |  6 |  7 |  8 |  9 | 10 | 11 | 12 | 13 | 14 | 15 | 16 | 17 | 18 | 19 | 20 | 21 | 22 | 23 | 24 | 25 | 26 | 27 | 28 | 29 | 30 | 31 | 
  +-----------+----+----+----+----+----+----+----+----+----+----+----+----+----+----+----+----+----+----+----+----+----+----+----+----+----+----+----+----+----+----+----+----+
  | 0-th word |      Version      |   Header length   |           DSCP         |      ECN     |                                 Total Length                                  |
  +-----------+-------------------+-------------------+------------------------+--------------+--------------+----------------------------------------------------------------+
  | 1-st word |                               Identification                                  |     Flags    |                        Fragment Offset                         |
  +-----------+---------------------------------------+---------------------------------------+--------------+----------------------------------------------------------------+
  | 2-nd word |             Time to Live              |               Protocol                |                                Header Checksum                                |
  +-----------+---------------------------------------+---------------------------------------+-------------------------------------------------------------------------------+
  | 3-rd word |                                                                       Source IP Address                                                                       |
  +-----------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
  | 4-th word |                                                                    Destionation IP Address                                                                    |
  +-----------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
  +-----------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
  | 5-th word |                                                           Options (if Header Length is greater than 5)                                                        |
  +-----------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
  |    ...    |                                                           Options (if Header Length is greater than 5)                                                        |
  +-----------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
  | n-th word |                                                           Options (if Header Length is greater than 5)                                                        |
  +-----------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+

dscp: https://tools.ietf.org/html/rfc2474
ecn : https://tools.ietf.org/html/rfc3168
1-st word is all about fragmentation which does not occur in practice.

DNS
---
So, to look facebook.com's IP Address up, we use Domain Name Servers (DNS). These are phone books of the internet. This book tells us IP addresses of the domains we are trying to connect to.

DHCP
----
Whenever our computers are connected to the internet, they are automatically configured by our routers at home via Dynamic Host Configuraiton Protocol (DHCP).

This happens transparently to the end user whenever she is connected to a network, either via plugging in an Ethernet cable or joining to a Wireless network.

DHCP tells our computer what is its IP address, netmask, what DNS servers it can use and what is the default Gateway of this network. All of them will make sense in a moment.

At this point, let's assume a sample configuration for ourselves.

<table class="aligncenter" style="width: 300px;" border="1" align="center"><caption> </caption>
<tbody>
<tr>
<td>IP Address</td>
<td style="text-align: center;">192.168.1.100</td>
</tr>
<tr>
<td>Netmask</td>
<td style="text-align: center;">255.255.255.0</td>
</tr>
<tr>
<td>Gateway</td>
<td style="text-align: center;">192.168.1.1</td>
</tr>
<tr>
<td>DNS</td>
<td style="text-align: center;">208.67.220.220</td>
</tr>
<tr>
<td>DNS</td>
<td style="text-align: center;">208.67.222.222</td>
</tr>
</tbody>
</table>

Often our computers are configured with at least two DNS servers because they are so critical to internet as we know it, there must be a back up.

First thing's first. How's the information enveloped ?
------------------------------------------------------


physical layer -> link layer -> network layer -> transport layer -> 

Packet delivery on internet is a bit couner-intuitive.

Imagine there's an information you want to send to a friend.



DNS Request
-----------
So, let's start with our very very first communication with the world -- the internet.

Netmask
-------
DNS server is out of our network, gotta send to default gateway.
Default Gateway
---------------
Default gateway will be found with ARP
ARP
---
MAC resolution now put the DNS IP and send it to GW.
Ethernet or Wifi frame ??? Where to explain this
------------
Where to explain this ? mmm
DNS Response
-------------
Actual HTTP request
--------------------
Real request to the web server
Packet is out in the wild
-------------------------
Hops
----
