Python highlighting in LaTeX
============================

A simple Python highlighting style to be used with LaTeX.

============================
Example
```python
class ObjectiveFunction:
    counter = 0

    def __init__(self):
        pass

    def f(self, x):
        ObjectiveFunction.counter += 1 #Ą ą, Ę ę, Į į, Ų ų, Ė ė, Č č, Š š, Ž ž, Ū ū
        return -1/8*(x[0]*x[1]-x[0]**2*x[1]-x[0]*x[1]**2)

    def gradF(self, x):
        ObjectiveFunction.counter += 1
        return [-1/8*(x[1]-2*x[0]*x[1]-x[1]**2), -1/8*(x[0]-2*x[0]*x[1]-x[0]**2)]
    
    def reset(self):
        ObjectiveFunction.counter = 0
```
The above code block will look like this in PDF:
![img](img.png)

============================

The package is loaded by the following line:

```tex
\usepackage{pythonhighlight}
```

It is then possible to include a Python snippet directly in the code using:

```tex
\begin{python}
def f(x):
    return x
\end{python}
```

It is also possible to include inline Python code in LaTeX with ``\pyth``:

```tex
The special method \pyth{__init__}... 
```

Last but not least, you can load an external Python file with:
```tex
\inputpythonfile{python_file.py}[23][50]
```
to display the contents of the file ``python_file`` from line 23 to line 50,
or with
```tex
\inputpythonfile{python_file.py}
```
to input the whole Python file.
