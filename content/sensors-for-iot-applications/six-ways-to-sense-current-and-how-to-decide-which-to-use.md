# Six ways to sense current and how to decide which to use

High-precision current sensing is key to improve efficiency of closed-loop control systems, i.e. motor drives.&#x20;

Shunt Resistors

Shunt resistors are used in wide range of industrial applications and offer relatively high accuracy at low temperature drift. However, their use is limited by the power dissipation caused by their own resistance value. In applications with high common-mode voltages, shunt resistors require isolated amplifiers such as the [AMC1200](http://www.ti.com/product/amc1200) or, for the highest-performing systems, an isolated delta-sigma modulator like the [AMC1304L05](http://www.ti.com/product/amc1305m05). This device offers a low input voltage range of ±50mV allowing you to use smaller resistance shunts without compromising performance.&#x20;

Rogowski Coil

Rogowski coils measure alternating current (AC) only and are wrapped around a conductor that distributes the current to be sensed. They deliver a voltage proportional to the rate of change of the AC current and therefore require an integrator before being processed using an [analog-to-digital converter](http://www.ti.com/lsds/ti/data-converters/analog-to-digital-converter-products.page) (ADC).

[https://edadocs.software.keysight.com/kkbopen/what-is-a-rogowski-coil-current-probe-587212158.html](https://edadocs.software.keysight.com/kkbopen/what-is-a-rogowski-coil-current-probe-587212158.html)

Rogowski coils are suitable for retrofitting applications because the coil can be mounted around the conductor without interrupting the current flow. They don’t use a metal core, so the mechanical tolerances of the positioning both influence and limit the achievable accuracy. For the same reason, they don’t saturate and are thus used in high-current applications. Their low inductance allows usage in systems with high slew rates.

Current Transformers

In current transformers (CTs), the primary AC current generates a field in a magnetic core. This magnetic field induces a proportional current in the secondary winding. A burden resistor is required to convert the current to a voltage signal for further processing in an ADC.

The accuracy of CTs depends on the mechanical tolerances of the setup, burden accuracy and temperature drift of the magnetic core. The saturation level of the magnetic core limits the dynamic range of a CT. On the other hand, dedicated design allows you to tailor the CT for a certain use case. CTs are widely used for sensing currents in power grids.

Magnetoresistive sensors change their resistance with the presence of magnetic field, direct current (DC) or AC. Magnetoresistive sensors are small in size and are typically used for position and angle sensing. They are cost-effective alternatives for low-current applications that don’t require high accuracy.

Depending on the material used, you can choose from two types of magnetoresistive sensors:

* Anisotropic magnetoresistance (AMR) sensors use ferromagnetic materials in which a magnetic field influences the electrical resistance. The resistance variation is very small; therefore, Wheatstone bridges are often used to sense it.
* Giant magnetoresistance (GMR) sensors rely on a significantly higher impact of the magnetic field on the resistance of a structure built of alternating ferromagnetic and nonmagnetic layers. There is no free lunch, though – compared to AMR sensors, the production process is more complex and expensive.

Hall-effect sensors deliver a voltage signal proportional to an AC or DC magnetic field. They are inherently noisy, and the voltage level is highly temperature-dependent. You can address both limitations using clever excitation approaches like those used in the [DRV411](http://www.ti.com/product/drv411) sensor signal-conditioning integrated circuit (IC).

Hall sensors can be used in open-loop applications that don’t require high accuracy levels. For better accuracy, closed-loop approaches are best; these include the Hall sensor, a magnetic core with compensation winding, and a signal-conditioning circuit that is usually in the form of a complete module. Closed-loop modules are available for wide range of accuracy, current and cost levels. Other examples of Hall-effect sensors include the [DRV5000 family](http://www.ti.com/lsds/ti/sensors/hall-effect-sensor-overview.page?keyMatch=drv5000\&tisearch=Search-EN-Everything).

Fluxgate sensors deliver the highest level of sensitivity, widest dynamic range, and lowest noise and temperature-drift performance compared to other current-sensing methods. The design of an external fluxgate sensor is complex and requires low mechanical tolerances; only a few manufacturers worldwide offer fluxgate-sensor modules. TI recently announced the [DRV421](http://www.ti.com/product/drv421), the industry’s first fully integrated fluxgate sensor with all of the required signal-conditioning functions for closed-loop DC and AC applications. With a magnetic core and a compensation coil, this solution allows easy manufacturing of high-accuracy and low-level (leakage) current modules.

Table 1 compares all of the methods described in this post.



Table 1: Comparison of current sensing methods

Stay tuned next month for more details on shunt-based current sensing.

Additional resources:

* Read other posts on [current sensing](http://e2e.ti.com/tags/current%2bsensing%2bblog)
* Learn more about the [DRV421](http://www.ti.com/product/drv421) magnetic sensing IC
* Learn more about the [DRV5053](http://www.ti.com/product/drv5053) hall effect sensor
* [Shunt-based non-isolated current sensing](http://www.ti.com/lsds/ti/amplifiers-linear/current-sense-amplifiers-overview.page?familyAliasId=1203170)
