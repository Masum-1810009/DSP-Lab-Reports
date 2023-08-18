## Experiment No : 01

## Date of Submission : 3/5/2023

## Experiment Name :Implementation of convolution using built in function and without built in function in MATLAB.

---

## Theory:
<p style="text-align: justify">
In signal processing, convolution is a mathematical operation that combines two functions to produce a third function that expresses how one of the original functions modifies the other. The operation is typically denoted by an asterisk symbol (*).

More specifically, convolution involves taking the integral of the product of two functions as one function is shifted over the other function. The resulting function is a way to describe how the original functions interact with each other.
The general representation of convolution involves two functions, let's call them f and g, which can be continuous or discrete. The convolution of f and g, denoted as (f * g), is given by: </p>

(f * g)(t) = ∫ f(τ) g(t-τ) dτ (for continuous functions)
or
(f * g)[n] = Σ f[k] g[n-k] (for discrete functions)

<p <p style="text-align: justify">
where t represents a continuous variable, n represents a discrete index, and τ and k are integration and summation variables, respectively.
Intuitively, the convolution of f and g describes how the shape of one function (g) is modified as it is shifted across the other function (f), weighted by the values of f. This produces a new function that describes the combined effect of both functions.
</p>

## Code:
<strong> With built in function </strong>
```matlab
.  x = [ 1 2 3 4];
2.	 h = [ 4 4 3 2];
3.	 
4.	 subplot( 3, 1, 1);
5.	 t = 0 :length(x)-1; 
6.	 stem( t, x);
7.	 xlabel('n');
8.	 ylabel('x[n]');
9.	 title('First Signal');
10.	
11.	 
12.	 subplot( 3, 1, 2);
13.	 t = 0:length(h)-1;
14.	 stem( t, h);
15.	 xlabel('n');
16.	 ylabel('h[n]');
17.	 title('Second Signal');
18.	 
19.	 y = conv( x, h);
20.	 
21.	 subplot( 3, 1, 3);
22.	 t = 0 : length(y)-1;
23.	 stem( t, y);
24.	 xlabel('n');
25.	 ylabel('y[n]');
26.	 title('Convoluted Signal');

```
<strong> Without built in function </strong>
```matlab
1.	x = [ 1 2 3 4];
2.	h = [ 4 4 3 2];

3.	m=length(x);
4.	l=length(h);
5.	X=[x,zeros(1,l)];
6.	H=[h,zeros(1,m)];
7.	
8.	z=[];
9.	for i=1:m
10.	    g=h.*x(i);
11.	    z=[z;g];
12.	end
13.	
14.	[r c] = size(z);
15.	k = r+c;
16.	t =2;
17.	Y =[];
18.	cd =0;
19.	
20.	while(t<=k)
21.	    for i=1:r
22.	        for j=1:c
23.	            if((i+j)==t)
24.	                cd = cd+ z(i,j);
25.	            end
26.	        end
27.	    end
28.	    t = t+1;
29.	    Y = [Y cd];
30.	    cd =0;
31.	end
32.	
33.	
34.	subplot(3,1,1); stem(x); xlabel('n');
35.	ylabel('x[n]'); title('First Signal');
36.	
37.	subplot(3,1,2); stem(h); xlabel('n');
38.	ylabel('h[n]'); title('Second Signal');
39.	
40.	subplot(3,1,3); stem(Y); xlabel('n');
41.	ylabel('Y[n]'); title('Convoluted Signal');

```

## Output:

![l1](https://github.com/Masum-1810009/DSP-Lab-Reports/assets/90197507/b5d75936-d280-4fce-96df-e8a7b1cc82c4)


<p style = "text-align: center">
  <strong>Fig 1.1:</strong> Output with built in function
</p>


![l1](https://github.com/Masum-1810009/DSP-Lab-Reports/assets/90197507/b5d75936-d280-4fce-96df-e8a7b1cc82c4)

<p style = "text-align: center">
  <strong>Fig 1.2:</strong> Output without built in function
</p>


## Discussion and Conclusion:

<p style="text-align: justify">

After convolving two signals using the built-in conv function in MATLAB, we compute the convolution of the same signals without using the conv function; both implementations yield the same result, as shown by the above figures.

</p>

