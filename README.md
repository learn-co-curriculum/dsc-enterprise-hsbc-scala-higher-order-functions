
# Higher Order Functions

## Higher Order Functions

A higher order function is a function or method that:
* Takes other functions as parameters
* Has a result as a function

## A method that takes a function


```scala
def process(x:Int, y:Int, f:(Int, Int) => Int) = f(x,y)
```




    process: (x: Int, y: Int, f: (Int, Int) => Int)Int
    



The above example has three arguments: An `Int`, another `Int`, and a higher order function that takes two `Int` and returns an `Int`

To run the above we can run:


```scala
process(4, 6, (x, y) => x * y)
```




    res5: Int = 24
    



or


```scala
process(4, 6, _ * _)
```




    res6: Int = 24
    



## A function that takes a function

Of course a function can also take a function


```scala
val process = (x:Int, y:Int, f:(Int, Int) => Int) => f(x, y)
```




    process: (Int, Int, (Int, Int) => Int) => Int = <function3>
    



The above example is a function that has three arguments: An Int, another Int, and a higher order function that takes two Int and returns an Int

To run the above we can run:


```scala
process(4, 6, (x, y) => x * y)
```




    res7: Int = 24
    



or


```scala
process(4, 6, _ * _)
```




    res8: Int = 24
    



## A function that returns a function

* A function, or method can return a function
* This is also a higher order function



```scala
val process = (x:Int, y:Int) => (z:Int) => x + y + z
val f2 = process(10, 10)
f2(3)
```




    process: (Int, Int) => Int => Int = <function2>
    f2: Int => Int = <function1>
    res9: Int = 23
    



A method returning a function, note the `def`


```scala
def process(x:Int, y:Int) = (z:Int) => x + y + z
val f2 = process(10, 10)
f2(3) //23
```




    process: (x: Int, y: Int)Int => Int
    f2: Int => Int = <function1>
    res10: Int = 23
    



Running both a `def` and a `function` as if they are they’re the same semantics is no accident. Though mechanically different after a while the difference between the two becomes blurry.

## Higher Order Functions Conclusion

* Can come in either of these forms
  * Functions taking other functions
  * Functions returning other function
  * Methods taking functions
  * Methods returning functions
* The distinguishing features of methods and functions becomes blurry
