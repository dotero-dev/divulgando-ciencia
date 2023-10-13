---
layout: ../../layouts/en/ArticleLayout.astro
titulo: Discover Arduino
autor: Darío O.
fotoDelAutor: /images/autores/dario-o.webp
portada: /images/contenido/aprende-arduino-desde-cero/portada.webp
portadaAlt: Image of a hand with an Arduino Uno board.
descripcion: Learn how to use the Arduino board from scratch with no prior knowledge by following this step-by-step guide.
ciencia: technology
fechaMostrar: 16 January, 2022
fechaOrdenar: Jan 16, 2022
duracion: 8
url: /en/discover-arduino
x: https://x.com/tecnomagia_es
instagram: https://instagram.com/tecnomagia_es
github: https://github.com/dotero-dev
rrss: x instagram github
---

## Introduction

In this guide, we will discuss the basic knowledge of Arduino, as the name suggests, focusing on understanding the board's functionality and not its programming. Therefore, there's no need to install any software.

To follow this guide effectively, you'll need the following items:

- Arduino board, which can be Elegoo. Arduino can be edited by anyone, so there are many cheaper copies of the original Arduino. The difference lies in their durability, but the functionality will be the same.
- Protoboard (breadboard).
- Button.
- Potentiometer.
- LED.
- Two resistors.

You can purchase these items from major online stores.

Throughout this guide, we'll create graphical representations in Tinkercad, with cables connected to 5V shown in red, cables connected to GND in black, and conditional cables (dependent on something to provide power) or those connected to a pin (analog or digital) shown in blue.

In Arduino, you can encounter three types of cables: male-male, female-male, and female-female. A "male" connection refers to the left-side connection, while a "female" connection refers to the right-side connection, allowing a male-type cable to be inserted into a female-type cable.

![Image showing male and female cable connections in Arduino.](/images/contenido/aprende-arduino-desde-cero/cables-macho-hembra.webp)
*Image from [murkyrobot.com](murkyrobot.com)*

## Pins, Types, and Functions

Any Arduino board has 6 analog pins (ANALOG) and 14 digital pins (DIGITAL) in total.

![Image of the Arduino board in Tinkercad](/images/contenido/aprende-arduino-desde-cero/placa-arduino.webp)

Analog pins provide numeric outputs from 0 to 1023, while digital pins provide boolean outputs: true or false, 1 or 0, HIGH or LOW...

![Image of the Arduino board in Tinkercad showing the 5 digital pins on its board.](/images/contenido/aprende-arduino-desde-cero/pines-digitales.webp)

In this image, you can see the digital pins, located above "DIGITAL (PWM)," numbered from 0 to 13.

![Image of the Arduino board in Tinkercad showing the 5 analog pins on its board.](/images/contenido/aprende-arduino-desde-cero/pines-analogicos.webp)

You can also see the analog pins below "ANALOG IN," numbered from A0 to A5.

![Image of the Arduino board in Tinkercad showing the power and ground pins.](/images/contenido/aprende-arduino-desde-cero/power.webp)

Finally, you can see the pins under "POWER." These can provide either 3.3V or 5V of power or close a circuit at the GND pin. We'll see how to connect them in the next section, electrical connections.

## Electrical Connections

Let's understand how a protoboard works, an essential element for Arduino practices.

![Image of the Protoboard in Tinkercad.](/images/contenido/aprende-arduino-desde-cero/placa-protoboard.webp)

You can find two rows marked with a "-" sign and two rows marked with a "+" sign, with columns connected in between. The image below shows how the **columns are connected to each other**. This means that if you connect a cable from 5V to one point, the entire column will have 5V. The same goes for the black (-) and red (+) rows.

![Image of the Protoboard in Tinkercad showing how different columns and rows are connected to each other.](/images/contenido/aprende-arduino-desde-cero/placa-protoboard.webp)

**Stop! Have you understood this scheme correctly? It's vital to proceed!**

Typically, you connect a cable **from 5V to any connection in the two red rows** (+) to ensure that the entire red row has 5V.

You also connect a cable **from GND to any connection in the two black rows** (-) to make the entire black row available for closing the circuit.

**IMPORTANT: If you connect in one row, the connection only reaches that entire row, not both rows of the same color.**

As mentioned earlier, the columns are also connected, so any connection in any column will provide power to the rest of the column. Be careful, as connecting the LED's anode to one connection in a column and then putting a cable from 5V in that same column will light up the LED. However, be cautious, as you can burn out the LED and even get burned.

## Ohm's Law

To fully understand how any electrical circuit works, it's essential to know Ohm's Law.

A circuit receives a **voltage**, measured in volts. The goal of the circuit is to operate one or more components, but here's the problem: many components can't handle too much **current**. To regulate the **output current**, measured in amperes, we use **resistance**, measured in ohms. Resistance acts as a **dimmer switch** or, to put it in simpler terms, as a **faucet**. The faucet receives water (voltage), and depending on its opening (ohms), it can regulate the outgoing current (amperes) from the resistance.

![Diagram of the Ohm's Law triangle, with V at the top and I and R at the bottom.](/images/contenido/aprende-arduino-desde-cero/triangulo-ley-de-ohm.webp)

In the triangle above, **voltage refers to the input voltage** of the circuit, **resistance to the number of ohms** imposed on that voltage, and **current refers to the outgoing amperes** from the resistance, which will reach what we want to connect. We can calculate the different parts as follows:

- **Voltage** = Resistance × Current
- **Resistance** = Voltage / Current
- **Current** = Voltage / Resistance

The most interesting calculation is for resistance, as it helps us determine how many ohms the resistance needs based on the maximum current required by what we want to connect.

Let's consider an example. The circuit has an **input voltage of 5V**, and we want to connect an LED with a **maximum current of 0.02 amperes**, which will make the LED operate at its maximum power. So, we calculate the necessary resistance as follows:

Knowing that resistance is equal to voltage divided by current, we perform the following calculation: **5V / 0.02A = 250 ohms.**

To connect an LED, considering the starting voltage is 5V, you'll need a minimum resistance of 250 ohms. This way, you'll make it shine as brightly as possible without burning out or exploding.

## First LED Experiments

### Turning On an LED

To turn on an LED, you'll need the LED itself, a resistor, the Arduino board, and the protoboard.

![Circuit in Tinkercad connecting an LED to an Arduino board to turn it on.](/images/contenido/aprende-arduino-desde-cero/circuito-led-1.webp)

With this setup, you could already turn it on, but let's take a closer look:

- A cable is connected from **5V to a connection on the red line** (+).
- Another cable is connected from **GND to a connection on the black line** (-).
- An LED is connected in two different columns:
    - The column of the **anode*** has a connection to the red line, **so the LED receives power**.
    - The column of the **cathode*** has a connection to the black line to **complete the LED's circuit**.
    - **IMPORTANT: One of these two connections must have a resistor to prevent the LED from burning out.**

*The anode is the longer leg of the LED, while the cathode is the shorter leg of the LED.

### Turning On the LED by Touching a Button

To turn on an LED by touching a button, you'll need the LED itself, a resistor, the button, the Arduino board, and the protoboard.

![Circuit in Tinkercad connecting an LED to an Arduino board to turn it on by touching a button.](/images/contenido/aprende-arduino-desde-cero/circuito-led-2.webp)

With this setup, you could already turn it on, but let's take a closer look:

- A cable is connected from **5V to a connection on the red line** (+).
- Another cable is connected from **GND to a connection on the black line** (-).
- A button is connected as follows:
    - In one of its legs, a **resistor is connected to the red line** (+), which allows power to reach the button.
    - In the other leg, a **cable is connected to the LED's anode** you want to turn on when touching the button. This cable carries the output current of the button.
- The LED is connected as follows:
    - The anode column is connected to the output of the button, which will turn it on when you touch the button.
    - The cathode column has a cable connected to a resistor that leads to the black line (-) to complete the circuit.

### Regulating the LED with a Potentiometer

A potentiometer is like a faucet; depending on its position, it allows **more or less voltage** to pass through. This is explained in Ohm's Law (section 3).

![Circuit in Tinkercad connecting an LED to an Arduino board to adjust its brightness using a potentiometer.](/images/contenido/aprende-arduino-desde-cero/circuito-led-3.webp)

To regulate the brightness of an LED with a potentiometer, you'll need the LED itself, the potentiometer, a resistor, the Arduino board, and the protoboard.

With this setup, you could already turn it on and adjust the brightness, but let's take a closer look:

- A cable is connected from **5V to a connection on the red line** (+).
- Another cable is connected from **GND to a connection on the black line** (-).
- A potentiometer is connected as follows:
    - The **central column** is connected to a cable that will be connected to the anode column of the LED you want to turn on.
    - One of the two **side columns** is connected with a cable from the red line (+) to provide power to the potentiometer.
    - The other **side column** is connected with a cable from the black line (-) to complete the circuit.
- The LED is connected as follows:
    - The anode column is connected to the output of the potentiometer.
    - The cathode column has a cable connected to a resistor that leads to the black line (-) to complete the circuit.

## Components, What Can You Do?

The beauty of Arduino is that it offers a wide variety of components, as well as countless utilities and possible programs.

There are numerous projects you can create with Arduino, from games to home automation. [You can see 46 projects you can do in this link](https://www.xataka.com/makers/46-proyectos-makers-para-hacer-verano-arduino-raspberry-pi) (in Spanish).

If you want to learn more about these components, stay tuned for section 6 of this guide, where we explain where you can learn more.

## Where to Learn More? Reference Websites

This guide has been a brief **introduction to the world of Arduino and electricity**. If you've enjoyed it and want to learn more, there's a highly recommended website for learning Arduino and how to handle various components. It's Luis Llamas' website in the Arduino tutorials section: [https://www.luisllamas.es/tutoriales-de-arduino/](https://www.luisllamas.es/tutoriales-de-arduino/).