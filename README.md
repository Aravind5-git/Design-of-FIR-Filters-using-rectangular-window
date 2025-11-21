# Design-of-FIR-Filters-using-rectangular-window
#          DESIGN OF LOW PASS FIR DIGITAL FILTER 

# AIM: 
          
  To generate design of low pass FIR digital filter using SCILAB 

# APPARATUS REQUIRED: 

  PC Installed with SCILAB 

# PROGRAM 
```
// DESIGN OF LOW PASS FIR FILTER USING RECTANGULAR WINDOW
clc;
clear;
close;

// Filter specifications
N = 21;          // Filter length
fc = 0.12;       // Normalized cutoff frequency (0 < fc < 0.5)
M = N - 1;
n = 0:M;

// Ideal impulse response (sinc function)
hd = 2 * fc * sinc(2 * fc * (n - M/2));

// Rectangular window
w = ones(1, N);

// FIR filter coefficients
h = hd .* w;

// Frequency response
[H, f] = frmag(h, 1024);   // magnitude response

// ---- Plot impulse response (use plot2d3 instead of stem) ----
figure(1);
plot2d3(n, h);
title('Impulse Response of FIR Low Pass Filter (Rectangular Window)');
xlabel('n');
ylabel('h[n]');
xgrid();

// ---- Plot magnitude response ----
figure(2);
plot(f, abs(H));
title('Magnitude Response');
xlabel('Normalized Frequency');
ylabel('|H(f)|');
xgrid();

// ---- Display filter coefficients ----
disp("Filter Coefficients (h[n]):");
disp(h');

disp("Filter length (N): " + string(N));
disp("Cutoff frequency (fc): " + string(fc));
disp("Window used: Rectangular");
```

# OUTPUT
<img width="428" height="698" alt="508881061-118e7ce2-c320-41a1-8dad-a2a0d028dc91" src="https://github.com/user-attachments/assets/5db749ae-9ad4-431f-8181-6d938b4d8c33" />
<img width="762" height="598" alt="508881128-ab3d4755-2e0c-4399-90fe-09fb0de38ae2" src="https://github.com/user-attachments/assets/b9e294a2-4f39-4948-9f21-dfb027e9826e" />
<img width="758" height="632" alt="508881187-c1321a64-bed2-4b1b-a16e-85857d852212" src="https://github.com/user-attachments/assets/b14f3954-8082-4b27-8d6e-6461d49c5414" />


# RESULT
Design of low pass FIR digital filter using SCILAB was generated.
