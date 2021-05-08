# Session 2 Assignment

## Overall Network Training in Excel
![Alt text](backprop_excel.png?raw=true "Backpropagation in Excels")


## Major Steps
* Forward pass - Based on randomally intialized weight w1..w8 calculate vallue for each neurons.
```
    h1 = w1*i1+w2*i2; h2 = w3*i1+w4*i2
    a_h1 = σ(h1); a_h2 = σ(h2)
    o1 = w5*a_h1+w6*a_h2; o2 = w7*a_h1+w8*a_h2
    a_o1 = σ(o1); a_o2 = σ(o2)
```

* Calculate the L2 error
```
    E1 = 1/2(t1-a_o1)^2
    E2 = 1/2(t2-a_o2)^2
```	

* Backpropagate Error to update weights w1..w8 using ```w(i+1) = w(i) - lr*δ(Error)/δw(i)```
** Gradient calculation-
    ```
    δ(E)/δ(w1) = δ(E1)/δ(w1) + δ(E2)/δ(w1) where;
    δ(E1)/δ(w1) = (a_o1-t1)*a_o1*(1-a_o1)*w5*a_h1*(1-a_h1)*i1					
    δ(E2)/δ(w1) = (a_o2-t2)*a_o2*(1-a_o2)*w7*a_h1*(1-a_h1)*i1

    δ(E)/δ(w2) = δ(E1)/δ(w2) + δ(E2)/δ(w2) where;
    δ(E1)/δ(w2) =  (a_o1-t1)*a_o1*(1-a_o1)*w5*a_h1*(1-a_h1)*i2					
    δ(E2)/δ(w2) = (a_o2-t2)*a_o2*(1-a_o2)*w7*a_h1*(1-a_h1)*i2

    δ(E)/δ(w2) = δ(E1)/δ(w3) + δ(E2)/δ(w3) where;
    δ(E1)/δ(w3) =  (a_o1-t1)*a_o1*(1-a_o1)*w6*a_h2*(1-a_h2)*i1					
    δ(E2)/δ(w3) =  (a_o2-t2)*a_o2*(1-a_o2)*w8*a_h2*(1-a_h2)*i1	

    δ(E)/δ(w2) = δ(E1)/δ(w4) + δ(E2)/δ(w4) where;
    δ(E1)/δ(w4) =  (a_o1-t1)*a_o1*(1-a_o1)*w6*a_h2*(1-a_h2)*i2					
    δ(E2)/δ(w4) =  (a_o2-t2)*a_o2*(1-a_o2)*w8*a_h2*(1-a_h2)*i2	

    𝜹(Error)/δw5  = (a_o1-t1)*a_o1*(1-a_o1)*a_h1

    𝜹(Error)/δw6  = (a_o1-t1)*a_o1*(1-a_o1)*a_h2	

    𝜹(Error)/δw7  = (a_o2-t2)*a_o2*(1-a_o2)*a_h1	

    𝜹(Error)/δw8  = (a_o2-t2)*a_o2*(1-a_o2)*a_h2								
    ```

* Training Error with different Learning Rates
![Alt text](error_with_varraying_learning_rate.png?raw=true "Error with diff Learning Rates")
