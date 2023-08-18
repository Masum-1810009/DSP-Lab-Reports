## Experiment No : 01

## Date of Submission : 8/5/2023

## Experiment Name :Implementation of circular convolution, sum and subtract of two signals and draw two particular figures in MATLAB.

---

## Theory:
<p>Circular convolution is a mathematical operation that combines two sequences of finite length by wrapping one sequence around the other and performing a convolution operation. It is called "circular" because the end of each sequence is connected to the beginning of the other sequence, forming a circle. Circular convolution is often used in digital signal processing, particularly in the implementation of digital filters. It can be used to calculate the response of a linear time-invariant system to a periodic input signal, and it has some advantages over linear convolution in terms of computational efficiency and simplicity. To perform circular convolution, the two sequences are first padded with zeros to the same length, and then the convolution operation is performed in the same way as for linear convolution. However, instead of discarding the portions of the result that are due to the zero-padding, the result is taken modulo the length of the sequences, which wraps the result around to the beginning of the sequence. The formula for circular convolution of two sequences x and y of length N is:</p>

x[n] * y[n] = sum (k=0 to N-1) x[(n-k) mod N] * y[k]

where n is an index that ranges from 0 to N-1, and mod is the modulo operator. The result of the circular convolution is a sequence of length N, just like the input sequences.


## Code:
<strong> For circular convolution between two signals: </strong>
```matlab
1.	clc;
2.	clear;
3.	close all;
4.	x=input('Enter the first array: ');
5.	n=length(x);
6.	h=input('Enter the second array: ');
7.	
8.	z=zeros(1,n);
9.	 
10.	for i=1:n
11.	    for j=1:n
12.	        k=mod(i-j,n)+1;
13.	        z(i)=z(i)+x(j)*h(k);
14.	    end
15.	end
16.	 
17.	disp('Input Signals: ')
18.	disp(x);
19.	disp(h);
20.	disp('Circular Convolution: ');
21.	disp(z); 

```
<strong> For plotting two signals and showing their summation and subtraction: </strong>
```matlab
1.	n1 = [0, 0, 0, 2, 2, 2, 1, 1, 1, 0, 2]
2.	subplot(4, 1, 1);
3.	stem(n1);
4.	title('1st signal');
5.	xlabel('Index');
6.	ylabel('Value');
7.	 
8.	n2 = [2, 2, 0, 1, 1, 1, 0, 0, 0, 0, 3]
9.	subplot(4, 1, 2);
10.	stem(n2);
11.	title('2nd signal');
12.	xlabel('Index');
13.	ylabel('Value');
14.	 
15.	n3=n1+n2;
16.	subplot(4, 1, 3);
17.	stem(n3);
18.	title('Summation');
19.	xlabel('Index');
20.	ylabel('Value');
21.	 
22.	 
23.	n4=n1-n2;
24.	subplot(4, 1, 4);
25.	stem(n4);
26.	title('Subtraction');
27.	xlabel('Index');
28.	ylabel('Value');

```
<strong> Drawing the figure of given signals using array and plot: </strong>
```matlab
1.	x=[0 0 1 1 1 1 0 0];
2.	t=0:1:7;
3.	subplot(2,1,1);
4.	plot(t,x);
5.	 
6.	y=[0 1 1 2 2 1 1 0];
7.	t=0:1:7;
8.	subplot(2,1,2);
9.	plot(t,y);

```

## Output:

![l1](https://github.com/Masum-1810009/DSP-Lab-Reports/assets/90197507/b5d75936-d280-4fce-96df-e8a7b1cc82c4)


<p style = "text-align: center">
  <strong>Fig 1.1:</strong> Output with built in function
</p>


![l1](https://github.com/Masum-1810009/DSP-Lab-Reports/assets/90197507/b5d75936-d280-4fce-96df-e8a7b1cc82c4)

<p style = "text-align: center">
  <strong>Fig 1.1:</strong> Output without built in function
</p>


## Discussion and Conclusion:

<p style="text-align: justify">

After convolving two signals using the built-in conv function in MATLAB, we compute the convolution of the same signals without using the conv function; both implementations yield the same result, as shown by the above figures.

</p>

