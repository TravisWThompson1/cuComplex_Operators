# cuComplex_Operators

The cuComplex_Op.h header file can be used to overload the aritmetic operators for the cuComplex structures cuFloatComplex and cuDoubleComplex. The overloaded operators include +, -, *, and /. This way, the arithemtic functions in the CUDA complex header file cuComplex.h do not have to be directly invoked causing clutter in the code.

```
cuDoubleComplex a = make_cuDoubleComplex(1, 2);
cuDoubleComplex b = make_cuDoubleComplex(3, 2);

cuDoubleComplex c = a + b;
```
In addition, using an overloaded arithmetic operator with a non-cuComplex structure is allowed. The overloaded operators are written using templates so any standard arithmetic type (int, long, float, double) is allowed and in any order.

```
cuFloatComplex a = make_cuFloatComplex(1, 2);
float b = 7;
double c = 4

cuFloatComplex c = a * b;
cuFloatComplex d = c / a;
```

The arthimetic operators will always return the cuComplex structure that was used in the operations. However, mixing cuComplex structures is not currently allowed.

```
cuDoubleComplex a = make_cuDoubleComplex(1, 2);
cuFloatComplex b = make_cuFloatComplex(3, 2);

cuDoubleComplex c = a + b; // NOT ALLOWED
```


