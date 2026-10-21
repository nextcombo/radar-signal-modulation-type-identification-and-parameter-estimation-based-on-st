# Radar Signal Modulation Type Identification and Parameter Estimation Based on STFT [with MATLAB]

MATLABCode and Simulation Resultsclc;\nclear all;\nclose all;\ntic;\nfo=10e6;\nfs=100e6;\nts=1/fs;\ntao=7e-6;\n%% BPSK signal generation\ng=[1 0 1 0 1 0 1];  %7-bit barker code\nt=0:1/fs:tao-1/fs;\ns=exp(j*2*pi*fo*t);\nn=tao/length(g)*fs;\nv=[];\nM=length(g);\nN=length(t);\nfor i=1:length(g)\n    if g(i)==1;\n        w=ones(1,n);\n    elseif g(i)==0\n        w=-ones(1,n);\n    end\n    v=[v w];\nend\nS_bpsk1=s.*v;\n%% Noise\nN_noise=(randn(1,length(t))-j*randn(1,length(t))).*exp(j*2*pi*fo*t);  %Narrowband Gaussian White Noise\n​\n%% Calculate Signal-to-Noise Ratio\n                                                    \n% ratio=-3;  % signal-to-noise ratio (db) number\nratio=10;\nEx1=mean(abs(S_bpsk1).^2);\nEx2=mean(abs(N_noise).^2);\nN_A=sqrt(Ex1/(Ex2*10^(ratio/10)));\nN_noise=N_A*(randn(1,length(t))-j*randn(1,length(t))).*exp(j*2*pi*fo*t);  %Narrowband Gaussian White Noise\n%% Signal with noise\n% S_bpsk=S_bpsk1+N_noise;\nS_bpsk=S_bpsk1;\n​\n%Draw the BPSK time-domain and frequency-domain diagrams\nfigure;\nsubplot(211)\nplot(t,S_bpsk)\nxlabel('Timeline t /s');\nylabel('SignalS');\ntitle('BPSKSignal (Time domain)')\nsubplot(212)\nplot(0:fs/N:fs-fs/N,abs(fft(S_bpsk)))\nxlabel('Frequency axis f /Hz');\nylabel('Energy P');\ntitle('BPSKSignal (Frequency domain)')\n  

## Images

![Radar Signal Modulation Type Identification and Parameter Estimation Based on STFT [with MATLAB]](01.jpg)
![Radar Signal Modulation Type Identification and Parameter Estimation Based on STFT [with MATLAB]](02.jpg)
![Radar Signal Modulation Type Identification and Parameter Estimation Based on STFT [with MATLAB]](03.jpg)
![Radar Signal Modulation Type Identification and Parameter Estimation Based on STFT [with MATLAB]](04.jpg)
![Radar Signal Modulation Type Identification and Parameter Estimation Based on STFT [with MATLAB]](05.jpg)
![Radar Signal Modulation Type Identification and Parameter Estimation Based on STFT [with MATLAB]](06.jpg)
![Radar Signal Modulation Type Identification and Parameter Estimation Based on STFT [with MATLAB]](07.jpg)
![Radar Signal Modulation Type Identification and Parameter Estimation Based on STFT [with MATLAB]](08.jpg)
![Radar Signal Modulation Type Identification and Parameter Estimation Based on STFT [with MATLAB]](09.jpg)
![Radar Signal Modulation Type Identification and Parameter Estimation Based on STFT [with MATLAB]](10.jpg)
![Radar Signal Modulation Type Identification and Parameter Estimation Based on STFT [with MATLAB]](11.jpg)
![Radar Signal Modulation Type Identification and Parameter Estimation Based on STFT [with MATLAB]](12.jpg)
![Radar Signal Modulation Type Identification and Parameter Estimation Based on STFT [with MATLAB]](13.jpg)
![Radar Signal Modulation Type Identification and Parameter Estimation Based on STFT [with MATLAB]](14.jpg)

<!-- PAYMENT_BLOCK -->

## Get this dataset

- Payment link (Stripe): [Buy now](https://buy.stripe.com/3cs8yP7sY87d0vu9AB)
- Payment QR code: ![Payment QR code](pay.png)

<!-- /PAYMENT_BLOCK -->
