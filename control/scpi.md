
# SCPI Devices

This part will contain the example to control an SCPI deivce.

The example script would concentrate on operating a **Keithley's System
SourceMeter 2400 Series SMU device** to **measure the I-V characteristic diagram of
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

ins.write('*RST')
ins.write(':SOUR:FUNC VOLT')
ins.write(':SENS:CURR:PROT {}'.format(limiti))
ins.write(':SENS:FUNC CURR')
ins.write(':SENS:CURR:RANG {}'.format(limiti))

ins.write(':OUTP ON')

I = []
for i in V:
    ins.write(':SOUR:VOLT:LEV {}'.format(i))
    sleep(delay)
    cur = float(ins.ask(':READ?'))
    I.append(cur)

ins.write(':OUTP OFF')

plt.plot(V, I)
plt.show()
```

## Detailed comments
