## Experiment No : 03

## Date of Submission : 15.05.2023

## Experiment Name :Implementation of auto and cross correlation in MATLAB.

## Theory:
<p>Cross-correlation and autocorrelation are two related signal processing operations that are used to measure the similarity between two signals or the correlation of a signal with itself.

<strong>Autocorrelation:</strong> measures the similarity of a signal with a delayed version of itself at different time lags. It is a mathematical tool used in signal processing and statistics to detect repeating patterns, predict future behavior, and estimate signal parameters. Autocorrelation is used to calculate the power spectrum of a signal, which provides information about the frequency components present in the signal.

<strong>Cross-correlation:</strong> measures the similarity between two signals as a function of the time lag between them. It is commonly used in signal processing to detect similarities between two signals or to determine the time delay between them. Cross-correlation is also used in pattern recognition, speech recognition, and image processing.

Both autocorrelation and cross-correlation can be computed using similar methods, such as the Fourier transform or convolution. The main difference between them is that autocorrelation involves a single signal, while cross-correlation involves two signals. In addition, autocorrelation is symmetric, meaning that the autocorrelation function of a signal with itself is always symmetric around zero lag, while cross-correlation is not necessarily symmetric.</p>


## Code:
<strong> For Auto and Cross Correlation: </strong>
```matlab
x = [-1 2 1];
N = length(x);

autocorr_x = zeros(1, 2*N-1);
   for k = -N+1:N-1
   	for n = 1:N
      	if n+k >= 1 && n+k <= N
 		autocorr_x(k+N) = autocorr_x(k+N) + x(n) * x(n+k);
 		end
 	end
    end

crosscorr_xx = zeros(1, 2*N-1);
   for k = -N+1:N-1
   	for n = 1:N
 		if n+k >= 1 && n+k <= N
 		crosscorr_xx(k+N) = crosscorr_xx(k+N) + x(n) * x(n+k);
 		end
 	end
    end

subplot(4,1,1)
stem(autocorr_x)
title('Autocorrelation without built in function')

subplot(4,1,2)
stem(crosscorr_xx)
title('Cross-correlation without built in function')
auto_corr1 = xcorr(x);
cross_corr1 = xcorr(x,y);

subplot(4,1,3)
stem(auto_corr1)
title('Autocorrelation with built in function')

subplot(4,1,4)
stem(cross_corr1)
title('Cross-correlation with built in function')

```
## Output:

![l3](https://github.com/Masum-1810009/DSP-Lab-Reports/assets/90197507/cf29ea33-cc1b-46dd-bb19-da0cc4f50ec2)


## Discussion and Conclusion:

<p style="text-align: justify">
In this lab we learnt to implement auto and cross correlation with and without built in function in MATLAB. But for cross correlation we didn’t learn the process for unequal length. I couldn’t implement that problem and i only could manage to do the auto and cross correlation basic codes. They ran successfully without any difficulties and shows matching result with the built in output.
</p>

