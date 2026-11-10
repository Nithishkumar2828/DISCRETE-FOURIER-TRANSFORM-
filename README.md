# EXP 1 A : COMPUTATION OF DFT USING DIRECT AND FFT

# AIM: 
  To Obtain DFT and FFT of a given sequence in SCILAB. 

# APPARATUS REQUIRED: 
  PC installed with SCILAB. 

# PROGRAM: 
  # EXP 1 A : COMPUTATION OF DFT USING DIRECT AND FFT

# AIM: 

# To Obtain DFT and FFT of a given sequence in SCILAB. 

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
    // DISCRETE FOURIER TRANSFORM 
    
    DIRECT METHOD:
    
    clc;
    clear;
    clf;
    
    xn = [1,2,3,4,4,3,2,1];
    
    N = length(xn);
    n = 0:N-1;
    j = %i;
    
    Xk = zeros(1, N);
    
    // Direct DFT calculation
    for k = 0:N-1
        for r = 0:N-1
            Xk(k+1) = Xk(k+1) + ...
                xn(r+1)*exp(-j*2*%pi*k*r/N);
        end
    end
    
    disp("DFT output:");
    disp(Xk);
    
    K = 0:N-1;
    magnitude = abs(Xk);
    phase = atan(imag(Xk), real(Xk));
    
    subplot(3,1,1);
    plot2d3(n, xn);
    xtitle("Input Sequence", "n", "x(n)");
    
    subplot(3,1,2);
    plot2d3(K, magnitude);
    xtitle("Magnitude Spectrum", "k", "|X(k)|");
    
    subplot(3,1,3);
    plot2d3(K, phase);
    xtitle("Phase Spectrum", "k", "Phase (radians)")
    
    
    INDIRECT METHOD:
    
    clc;
    clear;
    clf;
    
    xn = [1,2,3,4,4,3,2,1];
    N = length(xn);
    n = 0:N-1;
    
    Xk = fft(xn);
    
    disp("FFT output:");
    disp(Xk);
    
    K = 0:N-1;
    magnitude = abs(Xk);
    phase = atan(imag(Xk), real(Xk));
    
    y = ifft(Xk);
    
    subplot(2,2,1);
    plot2d3(n, xn);
    xtitle("Input Sequence", "n", "x(n)");
    
    subplot(2,2,2);
    plot2d3(K, magnitude);
    xtitle("Magnitude Spectrum", "k", "|X(k)|");
    
    subplot(2,2,3);
    plot2d3(K, phase);
    xtitle("Phase Spectrum", "k", "Phase (radians)");
    
    subplot(2,2,4);
    plot2d3(n, real(y));
    xtitle("Inverse FFT Output", "n", "x(n)");

# OUTPUT: 

<img width="1052" height="1386" alt="WhatsApp Image 2026-11-10 at 11 09 15 AM" src="https://github.com/user-attachments/assets/675f95a9-3048-4efd-aced-85f59425530c" />


