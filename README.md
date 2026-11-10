# EXP 1 A : COMPUTATION OF DFT USING DIRECT AND FFT

# AIM: 
  To Obtain DFT and FFT of a given sequence in SCILAB. 

# APPARATUS REQUIRED: 
  PC installed with SCILAB. 

# PROGRAM: 
    clc;
    clear;
    xn=[1 2 3 4 4 3 2 1];
    n1=0:1:length(xn)-1;
    subplot(3,1,1);
    plot2d3(n1,xn);
    xlabel('Time n');
    ylabel('Amplitude xn');
    title('Input Sequence');
    j=sqrt(-1);
    N=length(xn);
    Xk=zeros(1,N);
    for k=0:N-1
    for n=0:N-1
    Xk(k+1)=Xk(k+1)+xn(n+1)*exp((-j*2*%pi*k*n)/N);
    end
    end
    disp(Xk)
    K1=0:1:length(Xk)-1;
    magnitude=abs(Xk)
    subplot(3,1,2);
    plot2d3(K1,magnitude);
    xlabel('frequency(Hz)');
    ylabel('magnitude(gain)');
    title('magnitude spectrum');
    angle = atan(imag(Xk),real(Xk))
    subplot(3,1,3);
    plot2d3(K1,angle);
    xlabel('frequency(Hz)');
    ylabel('Phase');
    title('Phase spectrum')


# OUTPUT: 

<img width="1052" height="1386" alt="WhatsApp Image 2026-11-10 at 11 09 15 AM" src="https://github.com/user-attachments/assets/675f95a9-3048-4efd-aced-85f59425530c" />


