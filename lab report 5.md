## Experiment No : 05

## Date of Submission : June 11, 2023

## Experiment Name :Experimental study of implementing Causal, Anti-Causal & Non-Causal signal.

---

## Theory:
<p style="text-align: justify">
  <strong>Causal Signal:</strong> A continous time signal x(t) which is said to be causal if x(t) = 0 for t<0.
</p>
![Causal Signal](https://github.com/Masum-1810009/DSP-Lab-Reports/blob/Masum-1810009-patch-1/lab%205%20(1).png)
<strong>Fig 5.1:</strong> Causal signal  
  
![Theory](lab 5 (2).png)  

<p style="text-align: justify">
  <strong>Anti-Causal Signal:</strong> A continous time signal x(t) which is said to be anti-causal if x(t) = 0 for t>0.
  
  <p>
  <strong>Fig 5.2:</strong> Anti-causal signal
  </p>
</p>
<p style="text-align: justify">
  <strong>Non-Causal Signal:</strong> A continous time signal x(t) which is said to be non-causal if x(t) is non zero for t>0.
  ![Theory](lab 5 (3).png)
  <p>
  <strong>Fig 5.3:</strong> Non-causal signal
  </p>
</p>

## Code:

```matlab
% Causal 
clc
x = [2 3 4 5 3];
syms y

Cs = 0;
for i=1:length(x)
    Cs = Cs + x(i) * y^(1-i);
end
display(Cs);

% Anti-causal
At_cs = 0;
for i=length(x):-1:1
    At_cs = At_cs + x(i) * y^(length(x)-i);
end
display(At_cs);

% Non-causal
max_ind = 4; % from mid value
ind = find(max_ind==x);
N_Cs = 0;
for i=1:length(x)
    N_Cs = N_Cs + x(i) * y^(ind-i);
end
display(N_Cs);
```

## Output:
![Output](lab 5 (4).png)
<p style = "text-align: center">
  <strong>Fig 5.4:</strong> Output of the causal, anti-causal & non-causal signal
</p>



## Discussion and Conclusion:

<p style="text-align: justify">

The code was executed and the output was verified. The output was correct comapared with the theories. But the task where we need to plot them in figures, i was unsuccessful and i couldn't find a better solution which was meaningful to me.

</p>

