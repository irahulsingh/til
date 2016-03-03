I came across a problem where I need to know the name of the class defined inside moudules when any methods defined inside class is called.

e.g.

```
module A
	class B << self
		def myFun
		end
	end
end
``` 
Now when I call A::B.myFun, I want to know name of the class dynamically (I mean no hardcoding).

 
```
deconstantize
```

Using deconstantize we can know parents module name

e.g.

```
"A::B".deconstantize
```
returns A, but this is opposite of my original problem. I wanted the result as B. I found demodularize which solves my problem.

e.g.
```
"A::B".demodularize
```
will return B and this is what I wanted to know. 

So demodularize is opposite of deconstantize

###### Note: I hardcoded "A::B" as string above but we can get it using self.to_s inside the called method.