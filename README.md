# DSBSC_USING_PYTHON

---
Aim:

To implement and analyze Double Sideband Suppressed Carrier (DSB-SC) using Python's NumPy and Matplotlib libraries. 

---
Apparatus Required

1.	Software: Python with NumPy and Matplotlib libraries
2.	Hardware: Personal Computer

  ---
  
Theory

Double Sideband Suppressed Carrier (DSB-SC) is a type of amplitude modulation in which both sidebands (upper and lower) are transmitted, but the carrier component is suppressed (not transmitted). This improves power efficiency compared to conventional AM because no power is wasted on the carrier.

---

Algorithm

1.Initialize Parameters: Set the values for carrier frequency, message frequency, carrier amplitude, message amplitude, sampling frequency, and signal duration.
2.Generate Time Axis: Create a time vector based on the total signal duration and sampling frequency.
3.Generate Message Signal: Define the message signal as a cosine wave representing the input information.
4.Generate Carrier Signal: Define the carrier signal using the carrier frequency and amplitude.
5.Generate DSB-SC Signal: Create the double sideband suppressed-carrier signal by multiplying the message signal with the carrier signal.
6.Plot the Signals: Use Matplotlib to plot the message signal, carrier signal, and DSB-SC signal on separate subplots.


---

Program
~~~
import numpy as np
import matplotlib.pyplot as plt

Am = 5.4
Ac = 10.8
fm = 444
fc = 4440
fs = 44400

t = np.arange(0, 2/fm, 1/fs)

m = Am * np.cos(2 * 3.14 * fm * t)


c = Ac * np.cos(2 * 3.14 * fc * t)

s1 = (Ac + m) * np.cos(2 * 3.14 * fc * t)
s2 = (Ac - m) * np.cos(2 * 3.14 * fc * t)
s = s1 - s2


plt.subplot(3, 1, 1)
plt.plot(t, m)

plt.subplot(3, 1, 2)
plt.plot(t, c)

plt.subplot(3, 1, 3)
plt.plot(t, s)

plt.tight_layout()
plt.show()

~~~

---

Output Waveform

<img width="630" height="469" alt="image" src="https://github.com/user-attachments/assets/ca53ba5d-b081-4e4e-85a6-6313d0c5177b" />


---

Tabular Column

![WhatsApp Image 2025-11-04 at 21 43 57_9336da99](https://github.com/user-attachments/assets/40ef9f79-fca8-4657-b324-ebf66d992710)


---

Result

The message signal, carrier signal, and DSB-SC signal are displayed in separate plots. The DSB-SC signal shows the message information contained in the upper and lower sidebands while the carrier component is suppressed, and the spectrum clearly shows only the two sidebands. Demodulation of the DSB-SC signal requires a coherent (synchronous) detector to recover the original message.

