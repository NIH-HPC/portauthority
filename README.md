# portauthority

Sometimes, you just need any free TCP port to run a service.
Rather than guessing, you can, at least on Linux, bind port 0 and the kernel will give you a suitable free port to use.
But if you tell an application to use port 0, it may not tell you which port in actuality was assigned and tell you to find your service there, at port 0.

`portauthority` embodies a simple and known [1] set of steps to bind port 0, find out what you were assigned, tell you what it was, then release it so you can use it.
It's subject to race conditions since the port in theory could be taken by something else in the time between `portauthority` released it and you use it.


1. See also:
 - https://eklitzke.org/binding-on-port-zero
 - https://www.dnorth.net/2012/03/17/the-port-0-trick/
