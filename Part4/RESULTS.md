RESULTS
--------------------

> After working with the three different languages, we realized we got the same behaviour: random numbers as a result. Such a behaviour is called Race Condition, as we are trying to increase and decrease the same variable at a time. That leads to a different final result each time because one thread sees how the variable changes its value while it is still doing the same operation with it.

> In the particular case of C, we can see that it gives 0 (correct answer) as a final result quite often (but still randomly).

> In the particular case of Go, we can see that it always gives 0 (correct answer) if the number of usable cores is 1.