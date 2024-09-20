> 22110085_Nguyen Truong
<p style="text-align: center; font-size: xx-large"><b>Lab 1</b></p>

___

### Bof 1:

> Purpose of this practice: Exploit the vulneability of gets to change the
> return address of vuln() function into secretFunc() address

Here is the stack frame of the main function:

![stackFrame](StackFrame.png)

We can see that to override the Vuln() return address function, we need to pass 204 bytes then the
address of secretFunc() which is:<span style="font-size: medium; color: cyan;background: #5a6268">0x0804846b</span>

![](SecretFuncAD.png)

> Running file and passing value to array[200]:
>
![](RunFile.png)
>==> Finished
___

### Bof 2

> Purpose of this practice : Exploit the vulneability in fgets() to
> override the value of check variable,
> so that it can print "Yeah! You Win" message

Let see the stack frame of this main function: 
![](StackFrame2.png)

To be able to override the value at Check variable, we have 
to pass a least 40 bytes + value for Check.

First if it pass 44 bytes to the terminal run but the address 
for check var is different to <span style="font-size: medium; color: cyan;background: #5a6268">0xdeadbeef</span>
than i do not get the purpose yet

![](NotOverride2.png)

Only when i pass the DeadBeef var than i can finish to print 
the goal message: 
![](Overrided2.png)
>==> Finished
___
## Bof3 :

> Purpose: Override the Func() variable's address to the Shell() function

Let's take a brief look at Stack Frame of this main: 
![](StackFrame3.png)

Currently, Func is a pointer which is pointing to Sup() address
So to override and change this pointer to Shell() address we have to
find the address of shell function: 
![](ShellAddress.png)

After knowing the Shell function() address (0x0804845b)
Than we run the file and pass 128 bytes plus Shell address

![](RunFile3.png)
>==> Finished



