# Circuit-design-lab

The write-up for the "Circuit Design" lab. There's no code or other materials for this lab, but it does use the [Logisim program](http://www.cburch.com/logisim/index.html) as the circuit design tool.

## Background

The intent of this exercise is to gain a little experience with using
digital logic to construct some key components of a CPU:

-   [2-to-1 and 4-to-1
    multiplexers](http://en.wikipedia.org/wiki/Multiplexer)
-   [1 and 2 bit half and full
    adders](http://en.wikipedia.org/wiki/Adder_(electronics))
-   [Latches for storing information](http://en.wikipedia.org/wiki/Latch_(electronics)#SR_NOR_latch)

Nothing will need to be turned in for this, and you can form your own
groups of between 1 and 3 people (no more than 3, though).

## Logisim

We'll use the [Logisim
program](http://www.cburch.com/logisim/index.html) for this
simulation. It's written in Java and on Linux is just a simple JAR file.
(There are platform specific executables for Mac and Windows if you're
interested.) I've got a copy of the JAR file in my pub directory, which
you can run from wherever you wish: 
```bash
java -jar /home/mcphee/pub/CSci3401/logisim.jar
````

The Logisim folks have 
[a nice introductory tutorial](http://www.cburch.com/logisim/docs/2.7/en/html/guide/tutorial/index.html) 
on their web site.

If you're running it on a large monitor it might be easier for everyone
in your group to see if you magnify things; the zoom option in the
bottom left might be useful.

You can also create multiple "pages" using the **Project -\> Add
circuit...** menu option.

------------------------------------------------------------------------

## Build some simple things

You may want to save your solutions to these simpler exercises so you
can re-use them in the solutions to some of the more complex exercises
below.

### 2-to-1 multiplexer

A [multiplexer](http://en.wikipedia.org/wiki/Multiplexer) (MUX) provides
the rough equivalent of an if-then-else in the land of digital
circuits, where one or more selector wires are used to decide which of
several input signals will be passed on as the output signal of the MUX.

Build a 2-to-1 multiplexer which has two input wires, *x0* and *x1*, one
selector wire *s*, and one output wire *y*. If *s* is 0, then *y* should
be *x0*; otherwise it should be *x1*.

### 1-bit half adder

Build a 1-bit half adder. This takes two input wires, *x0* and *x1*, and
generates two output wires, *s* for the sum and *c* for the carry.

### 1-bit full adder

The half-adder from the previous exercise can't be composed to make
larger adders because it doesn't take a carry *input*, which is
necessary if we're to chain then. Build a 1-bit full adder which takes
*c × in*, *x0*, and *x1* as inputs, and generates *s* and *c*. (Note that
we don't need any additional outputs here.)

### Build an SR NOR latch

Common feed-forward circuits can't "remember" or store any data. If,
however, we allow the output of a circuit to become part of it's input,
we can create circuits that will hold a bit of information until certain
combinations of inputs are used to change it's value. An [SR NOR
latch](http://en.wikipedia.org/wiki/Latch_(electronics)#SR_NOR_latch),
for example, has two inputs *S* (for set) and *R* (for reset), and two
outputs *Q* and *Q'*. *Q* and *Q'* remain constant, with the property
that *Q* is the logical inverse of *Q'*, as long as both *S* and *R* are
low (0, or false). If we set *S* to high, this will force *Q* to high
(and *Q'* to low), and they will hold these values even after we set *S*
back to low. Similarly, if we set *R* to high, this will reset the
latch, forcing *Q* to low and *Q'* to high; they will hold these values
even after bringing *R* back to low.

------------------------------------------------------------------------

## Build some more complex things

As time allows, try to build on the work you've done to create more
complex circuits. Feel free to choose the exercises that interest you
the most, especially as time begins to run low on the lab period.

### 4-to-1 multiplexer

Build a 4-to-1 multiplexer which has four input wires, *x0*, *x1*, *x2*,
and *x3*, two selector wire *s0* and *s1* (collectively known as *s*),
and one output wire *y*. If we consider the pair of wires in *s* as
encoding a two-digit binary number, then the output *y* should be
*x × n*, where *n* is the value encoded by *s*.

You should be able to build a 4-to-1 multiplexer fairly easily by
combining multiple 2-to-1 multiplexers from before.

### 2- and 4-bit full adder

Use the 1-bit full adder from above to build a 2-bit full adder. That
will take five inputs, *c × in*, *x0*, *x1*, *y0*, and *y1*, and generate
two output bits *s0* and *s1* along with the carry *c*.

Then leverage that to build a cascading 4-bit full adder.

### Build an Gated D latch

Combining latches into multi-bit memories is pretty straightforward
since the latches are essentially independent. So instead of building
that, build a more sophisticated [gated D
latch](http://en.wikipedia.org/wiki/Latch_(electronics)#Gated_D_latch).
Here the input *E* is used to *enable* the latch, i.e., all it to read
information from the input *D* and store it. When *E* is low, then the
latch continues to output whatever it was storing, regardless of changes
on *D*.

---

People that contributed to this write-up before it was moved to Github included Nic McPhee, Vincent Borchardt, and John McCall.
