# BLDC motor guide

{% hint style="info" %}
Don't know how to read a BLDC motor's spec sheet, check out [this section](#bldc-motor-lingos)
{% endhint %}

*Authors: Julian Ho, Cass Wang*

## What is a BLDC motor?

BLDC motor stands for Brushless DC motor, as their name implies, brushless DC motors do not use brushes. With brushed motors, the brushes deliver current through the commutator into the coils on the rotor.

![Motors comparison](https://www.renesas.com/sites/default/files/inline-images/fig2-different-type-of-motors-en.jpg)

With a BLDC motor, it is the permanent magnet that rotates; rotation is achieved by changing the direction of the magnetic fields generated by the surrounding stationary coils. To control the rotation, you adjust the magnitude and direction of the current into these coils.

![BLDC internals](https://www.renesas.com/sites/default/files/inline-images/fig3-a-bldc-monitor-en.gif)

By switching on/off each pairs of stators really quickly, the BLDC motor can achieve a high rotational speed.

This is a simple table comparing a brushed DC motor, AC induction motor, and a BLDC motor:

![DC vs AC vs BLDC motor](https://www.edn.com/wp-content/uploads/media-1178418-bldctab1.jpg)

BLDC motors are commonly found in drones, electric cars, even robots!

## Types of BLDC motor

There are a couple different types of BLDC motor on the market for different applications. Here are some examples,

### Small motor

![drone motor](https://asset1.djicdn.com/assets/e310/features/s1bg-eb83d6f693bc50c348bac81127a0708d.jpg)

* <150g weight
* <5cm diameter
* 11.1-22.2v operational voltage
* ~0.3 NM torque
* application: small drones

### Mid-size motor

![rc car motor](https://cdn.shopify.com/s/files/1/0227/7805/2685/products/66_800x.jpg?v=1604039398)

* 400-1000g weight
* 5-10cm diameter
* 22.2-44.4v operational voltage
* ~4 NM torque
* application: RC cars, electric skateboard, robot actuator

### Stepper motor

![stepper motor](https://cdn-reichelt.de/bilder/web/xxl_ws/A300/RCT_34HS1456.png)

* ~400g weight
* 5-8cm diameter
* 11.1-22.2v operational voltage
* ~0.9 NM torque
* application: 3D printers, servos

## BLDC motor lingos

When shopping for a BLDC motor, there are a couple motor specific terms to consider.

* Max RPM (KV - RPM per volt)
  * 2200KV @ 10v = `KV x V` = 22,000 RPM max speed
* Max Torque (NM - [newton-meter](https://en.wikipedia.org/wiki/Newton-metre))
  * 1 NM = able to lift 1 KG weight attached to the end of a 1 meter long stick
* Max Power (W - Watts)
  * 835w @ 10v = `W/V` = 83.5Amp max power draw
* Motor Efficiency (%)
  * 90% efficiency = 90% of theoretical power
* Input Volt (S - li-ion Cells)
  * 6S = `S x 3.7V` = 22.2v
* Max Current (A - Amps)
  * 50A @ 10v = `A x V` = 500W max power
* Motor poles (N-P)
  * 24N40P = 24 stator poles, 40 permanent magnet poles
* Outrunner/Inrunner
  * Outrunner = motor body spin with output shaft
  * Inrunner = only output shaft will spin, body is stationary
* Motor numbering
  * 6355 = 63mm diameter, 55mm length

## BLDC electric speed controllers (ESC)

To drive a BLDC motor, you need a dedicated speed controller (ESC) to control it. Here are different types of ESC for different applications. These ESCs (like the motors above) are considered hobbyist-use, but they are quite sufficient for building small/mid-size robots.

### Drone ESC

![drone esc](https://cdn.getfpv.com/media/catalog/product/cache/1/image/9df78eab33525d08d6e5fb8d27136e95/a/i/aikon-ak32-35a-blheli32-2-4s-esc.jpg)

* very light ~9g
* very small footprint (size of a dollar coin)
* 1-6S input voltage
* ~40A max continuous current
* cheap
* application: small drone, small fighter robot, RC helicopter
* downside: cannot handle big motors, heat up very quickly, only simple motor control algorithms available

### RC car ESC

![car esc](https://images-na.ssl-images-amazon.com/images/I/61uJXess5mL._AC_SX425_.jpg)

* 3-12S input voltage
* ~50A max continuous current
* can handle medium size motors
* have active cooling
* affordable
* application: RC car, RC boat, electric skateboard
* downside: limited control protocol (PWM only), only simple motor control algorithms available

### Robot ESC

![odrive](https://images.squarespace-cdn.com/content/v1/58aff26de4fcb53b5efd2f02/1497230897496-GTMBNP5FZX1AQ9XTAFUW/ke17ZwdGBToddI8pDm48kCk9mSdcm3omhb4y0rzE2UB7gQa3H78H3Y0txjaiv_0fDoOvxcdMmMKkDsyUqMSsMWxHk725yiiHCCLfrh8O1z4YTzHvnKhyp6Da-NYroOW3ZGjoBKy3azqku80C789l0lqfkVpRp1g_2L-WsTQRP4K8zjDEmixMFHPtmSt0dm4CtxbCRswi6y2y0diUNJAOFw/IMG_20170611_181036.jpg)

* commonly used in robotic arm, actuator control
* more expensive
* ~120A max continuous current
* can handle large motors
* offer fine positional control of motor
* offer programmatic control (serial/USB/CANbus)
* application: robot, robotic arm
* downside: quite pricey, not plug-and-play, need to tune the motor manually before use

## BLDC control algorithms

There are 2 most common motor control algorithm used in hobbyist ESCs.

* Sensorless BLDC Motor Control
  * [Quick video](https://www.youtube.com/watch?v=WYJWdMV3YMs)
  * Advantage: No need for dedicated encoder on the motor
  * Downside: Weak low speed control, less speed less torque
* Field Oriented Control (FOC)
  * [Quick video](https://www.youtube.com/watch?v=YPD1_rcXBIE)
  * Advantage: Full torque at any speed
  * Downside: Require fine motor tuning (PID), and dedicated encoder
