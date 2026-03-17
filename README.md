
# Design-of-FIR-Filters-using-hanning-window

 DESIGN OF FIR DIGITAL FILTER 

# AIM: 
          
  To generate design of low pass FIR digital filter using SCILAB 

# APPARATUS REQUIRED: 

  PC Installed with SCILAB 

# PROGRAM 
```python
clc;
clear;
close;

// Filter specifications
N = 51;                      // Filter order (number of coefficients)
fc = 0.3;                    // Normalized cutoff frequency (fc = wc/pi)
n = 0:N-1;
alpha = (N-1)/2;

// Ideal Low Pass Filter Impulse Response
hd = sin(2*%pi*fc*(n - alpha)) ./ (n - alpha);
hd(alpha+1) = 2*%pi*fc;      // Handle division by zero at center

// Hanning (Hann) Window
w = 0.5 - 0.5*cos(2*%pi*n/(N-1));

// Apply window to ideal response
h = hd .* w;

// Plot Impulse Response
subplot(2,1,1);
plot(n, h, 'r');
xlabel('n');
ylabel('h(n)');
title('Impulse Response of FIR Low Pass Filter using Hanning Window');
grid on;

// Frequency Response
[H, f] = frmag(h, 512);      // Compute frequency response
subplot(2,1,2);
plot(f, abs(H));
xlabel('Normalized Frequency');
ylabel('|H(f)|');
title('Magnitude Response of FIR Low Pass Filter');
grid on;

```

# OUTPUT
<img width="768" height="432" alt="image" src="https://github.com/user-attachments/assets/ac777a09-e980-4cd2-b2b0-a2b0881ba518" />

# RESULT
Thus, the Low Pass FIR Digital Filter was successfully designed using the Hanning Window method in SCILAB.
The impulse and frequency responses were plotted and verified to meet the low-pass characteristics.
