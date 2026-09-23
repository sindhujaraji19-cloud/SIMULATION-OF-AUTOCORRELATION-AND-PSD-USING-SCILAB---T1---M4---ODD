# SIMULATION-OF-AUTOCORRELATION-AND-PSD-USING-SCILAB---T1---M4---ODD
# SIMULATION OF AUTOCORRELATION AND PSD USING SCILAB

## AIM

Write a program for Autocorrelation and PSD of signals in SCILAB and verify Wiener-Khinchin relation.

## EQUIPMENTS NEEDED

- Computer with i3 Processor
- SCI LAB

## THEORY

The Wiener-Khinchin theorem states that the power spectral density of a wide sense stationary random process is the Fourier transform of the corresponding autocorrelation function.

### Power Spectral Density (PSD)

$$
S_{XX}(\omega)=FT[R_{XX}(\tau)]
=\int_{-\infty}^{\infty}R_{XX}(\tau)e^{-j\omega\tau}d\tau
$$

### Autocorrelation Function (ACF)

$$
R_{XX}(\tau)=IFT[S_{XX}(\omega)]
=\frac{1}{2\pi}\int_{-\infty}^{\infty}S_{XX}(\omega)e^{j\omega\tau}d\omega
$$

## ALGORITHM

### 1. Load or Define the Signal:

Input your time-domain signal.

### 2. Compute Autocorrelation:

Calculate the autocorrelation function of the signal.

### 3. Compute Power Spectral Density (PSD):

Estimate the PSD of the signal, either directly using a method like Welch’s periodogram or by using the Fourier transform of the autocorrelation.

### 4. Plot Results:

Visualize the autocorrelation function and PSD.

## CODE
clc;
clear;
close;

// Time
t = 0:0.01:6;

// Analog signal
x = sin(2*%pi*0.7*t);

// Autocorrelation
Rxx = xcorr(x,x);

// PSD
PSD = abs(fft(x)).^2;

// Frequency
f = 0:length(PSD)-1;

// Plot 1 - Original signal
subplot(3,2,1);
plot(t,x);
xlabel("Time");
ylabel("Amplitude");
title("Analog Signal");

// Plot 2 - Autocorrelation
subplot(3,2,2);
plot(Rxx);
xlabel("Samples");
ylabel("Amplitude");
title("Autocorrelation");

// Plot 3 - PSD
subplot(3,2,3);
plot(f,PSD);
xlabel("Frequency");
ylabel("Power");
title("Power Spectral Density");

// Plot 4 - Autocorrelation waveform
subplot(3,2,4);
plot(Rxx);
xlabel("Lag");
ylabel("Rxx");
title("Autocorrelation");

// Plot 5 - Frequency spectrum
subplot(3,2,5);
plot(f,PSD);
xlabel("Frequency");
ylabel("Power");
title("PSD");

## PROCEDURE

- Refer Algorithms and write code for the experiment.
- Open SCILAB in System.
- Type your code in New Editor.
- Save the file.
- Execute the code.
- If any Error, correct it in code and execute again.
- Verify the generated waveform using Tabulation and Model Waveform.

## OUTPUT
<img width="736" height="576" alt="image" src="https://github.com/user-attachments/assets/e4a8f022-7d89-4acf-8fc0-82a918e179b0" />

## RESULT
Thus the autocorrelation and PSD are executed in Scilab and output is verified.
