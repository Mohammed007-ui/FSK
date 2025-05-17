# FSK
# Aim
Write a Python program for the modulation and demodulation of FSK.
# Tools required
# Program
```
import numpy as np
import matplotlib.pyplot as plt

# Parameters
bit_rate = 1  # bits per second
f1 = 5        # frequency for bit 1
f2 = 2        # frequency for bit 0
bit_duration = 1 / bit_rate
Fs = 1000     # sampling frequency
t_bit = np.linspace(0, bit_duration, int(Fs * bit_duration), endpoint=False)

# Input binary data
data = [1, 0, 1, 1, 0, 0, 1]
modulated_signal = []

# FSK Modulation
for bit in data:
    if bit == 1:
        modulated_signal.extend(np.sin(2 * np.pi * f1 * t_bit))
    else:
        modulated_signal.extend(np.sin(2 * np.pi * f2 * t_bit))

t = np.linspace(0, bit_duration * len(data), len(modulated_signal), endpoint=False)

# Plot Modulated Signal
plt.figure(figsize=(10, 4))
plt.title("FSK Modulated Signal")
plt.plot(t, modulated_signal)
plt.xlabel("Time (s)")
plt.ylabel("Amplitude")
plt.grid(True)
plt.tight_layout()
plt.show()

```
# Output Waveform
```
![FSK](https://github.com/user-attachments/assets/70eeb5f1-2e36-4316-ab9d-5ae96f18c663)

```
# Results
```
The Python program successfully demonstrates the FSK modulation process. The modulated signal shows different frequency components corresponding to the binary input signal.

```
# Hardware experiment output waveform.
![FSK_GRAPH](https://github.com/user-attachments/assets/d730749a-26df-49df-9654-997889bde521)
