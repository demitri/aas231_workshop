# Object-Oriented Code

### Numerical Arrays

Consider an array in IDL (or C):

```
spectrum = [10, 15, 5, 35, 39, 41, 36, 30]
```

This is literally nothing more than a block of memory containing these values, a list of numbers.The array doesn’t know how to do anything; any operation must be performed by an external function.

```
IDL> print, total(spectrum)
      211.000
IDL> print, mean(spectrum)
      26.3750
```

Any meaning is up to you to keep track of – basically only through the variable’s name. While to you it might represent masses, velocities, magnitudes, observations... no array is really any different from any other.

### Python Lists

Consider a Numpy array in Python:

```python
import numpy as np
spectrum = np.array([10, 15, 5, 35, 39, 41, 36, 30])
```

This is more than a list of numbers – the variable spectrum “knows” how to perform certain tasks by accessing methods (functions) or properties with the “dot” syntax:

```python
>>> spectrum.size
8
>>> spectrum.max()
41
>>> spectrum.mean()
26.375
>>> spectrum.sum()
211
```

The variable `spectrum` knows how many elements are in the array, how to determine the minimum and maximum values, how to calculate the mean and sum, and more.

### What Is An Object?

An object is a structure that contains the data and knows how to perform common operations on them without requiring external functions.

An object is defined to represent an idea that you are trying to model, grouping together related data and functionality into a single unit.This idea called encapsulation, which is the heart of object-oriented programming.

If you are familiar with C, think of an object as a `struct` (i.e. a predefined number of named variables grouped together), but add not just data, but functions that are specific to that data.

A class in Python would look like this:

```python
class MyClass(object):
	def __init__(self):
		self.a = None
		self.b = None
		
	def sum_ab(self):
		return self.a = self.b
```

Here, the class has two variables (`a` & `b`), and a *method*, which is really just a function. Functions that are defined in and only callable from a class are called methods.

We create a new object like this:

```python
x = MyClass()
```

and can set its values like this:

```python
x.a = 86
x.b = 99
```

Similarly, we can call the method like this:

```python
print(x.sum_ab())
```

How is this useful? All of the data and the functionality associated with that data is encapsulated in the same object - this is the definition of object-oriented code.

Imagine a more practical example. Let's say you have an SDSS spectrum file, and you want to read the RA value. Normally, the code to read it might look like this:

```python
from astropy.io import fits

hdu_list = file.open(filename)
hdu1 = hdu_list[0]
header = hdu1.header

ra = header["RA"]
```

The details of where the RA value is, which HDU, which header keyword, are all bookkeeping and can take up many lines of your code. Once you navigate the file, you can then do your analysis. The bookkeeping code is also very repetitive.

A better way to organize your code is to collect (encapsulate) the data and the methods to read an SDSS file in a class, then reuse that class. The result might look like this:

```python
from spectrum import SDSSSpectrum	

spec = SDSSSpectrum(filename)
print(spec.ra())
print(spec.dec())
print(spec.redshift())
```

The methods `ra()`, `dec()`, and `redshift()` are all defined in the object and know how to use the data it contains to produce those values. Note that the spectrum file does not contain the value for redshift - it's something that much be calculated.

## Exercise

Create a file called `spectrum.py` that defines an SDSSSpectrum class, and make the code above work.