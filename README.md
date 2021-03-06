# 2016Algorithm_01
**Simple sorting problem**


##Init version


Analysis result:

||result|
|------| :--------: |
|I_refs|111363392|
|check |1.000000/1.000000|
|cpu_time|30.162ms|
|flt|1364|
|gcc|0|
|heap_lost|0|
|illegal_func|0|
|illegal_header|0|
|m_error|0|
|m_peak|59457536|
|maxrss|2170880|
@lang=cpp


##Insertion sort version

Analysis result:
||result|
|---|:---:|
|I_refs|5091383206|
|check|1.000000/1.000000|
|cpu_time|64.9071ms|
|flt|1113|
|gcc|0|
|heap_lost|0|
|illegal_func|0|
|illegal_header|0|
|m_error|0|
|m_peak|58482688|
|maxrss|1454080|
@lang=cpp


##Final version

Analysis result:

||result|
|---| :---: |
|I_refs|94385289|
|check|1.000000/1.000000|
|cpu_time|24.234ms|
|flt|1108|
|gcc|0|
|heap_lost|0|
|illegal_func|0|
|illegal_header|0|
|m_error|0|
|m_peak|58478592|
|maxrss|1437696|
@lang=cpp

(All with the same input, from small data to mass data)


#Conclusion

For the sorting algorithm, I used `std::sort` to test it. And I also test it with insertion sort which spent years to run it(O( n^2 )) and it's number of instructions consumed are too big, so I won't talk about it.

The first version's maximun resident size (maxrss) had much more bigger than Final version.

I did it just by discarding the stringstream and using a char to do the input.  Although it seems clumsy, it does reduce the maxrss and also the CPU time.

So, if there are a great amount of data to be inputed, it is better to avoid using stingstream.   Because stringstream use too mush memory to do the buffer things.

But there are still pros of using it, such as reading a line of seperated ints or strings until '\n'. And it can simply be done by getline() and split it by `ss<<str;` => `ss>>(int or str);`.

And the cons of using char and reading it digit by digit is that it is really indigenous, and it can cause many bugs.

This is just my rough conclusion.

