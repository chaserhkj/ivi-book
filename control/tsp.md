# Non-SCPI Devices

This part will contain the example to control an non-SCPI deivce. We would take
Keithley's TSP commands as example non-SCPI command system.

The example script would concentrate on operating a **Keithley's System
SourceMeter 2600 Series SMU device** to **measure the I-V characteristic diagram of
a diode**.

## Example code

```(python)
import visa
import numpy as np
from matplotlib import pyplot as plt
from time import sleep

addr = 'TCPIP0::192.168.1.2::INSTR'
start = -5.0
end = 5.0
num = 100
limiti = 0.1
delay = 0.01

rm = visa.ResourceManager("@py")
ins = rm.get_instrument(addr)
V = np.linspace(start, end, num)

ins.write('reset()')
ins.write('smua.source.func = smua.OUTPUT_DCVOLTS')
ins.write('smua.source.limiti = {}'.format(limiti))
ins.write('smua.measure.rangei = {}'.format(limiti))

ins.write('smua.source.output = smua.OUTPUT_ON')

I = []
for i in V:
    ins.write('smua.source.levelv = {}'.format(i))
    sleep(delay)
    cur = float(ins.ask('print(smua.measure.i())'))
    I.append(cur)

ins.write('smua.source.output = smua.OUTPUT_OFF')

plt.plot(V, I)
plt.show()
```

## Detailed comments
