![image.png](https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/8668f2e6a465439a8e2376eb83cf21d8~tplv-k3u1fbpfcp-watermark.image?)

# Sync :Synchronous

There is a new coffee vending machine at park. Initially only 10–20 people are using it.

![image.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/22aa97760c084ba4967f0941b10cef32~tplv-k3u1fbpfcp-watermark.image?)

The machine can serve only one person at one time. The other needs to wait in the queue.

This is known as aynchronous execution. Similar to compiler executes the code one statement at a time and the next statement needs to wait until last execution gets completed.

## Problem:

> Things were running fine during intial days .But the you start seeing a lot of people start using the machine .Now there is a long queue every day…

# Async: Asynchronous

Seeing the opportunity, another guy opened a coffee shop at the back side of vending machine. Now half people start going to his shop instead of wating in line.

![image.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/2465c6eb0e9b4a7d91e2f611be667564~tplv-k3u1fbpfcp-watermark.image?)

This analogy is similar to asynchronous process (parallel process) You start sharing other available resource when main resource blocks the process, because you don’t want to wait.

# The scenario:

You might have seen that old govt websites reload the whole page when you start uploading something and that page keeps on loading until the upload finishes .You can’t do anything else it the uploads complete .

This type of synchronous process blocks the main thread over which app is running and provides very bad experience.

We call it blocking process. Wich unnecessarily block further processes that’s why we need to run file uploading process asynchronous so that user can keep browsing and upload keeps on happening is background

There are serval examples like :

*automation, data processing ,emails, API responses , computations , etc all of these should run on second thread asynchronously .*

## Wait but what is a thread ??

In simple words a thread is just a set of control statements (commands) to be executed.

# Await :

Await allows you to selectively , wait for async function to complete you can only await inside async function Below is the Javascript impletation .[Not all language supports Await keyword]

![image.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/363b68dec2e54cf79131aa698f939973~tplv-k3u1fbpfcp-watermark.image?)
AWAIT

# Any Cons ??

Yeah ,CPU usage increases and in some cases if not checked, it even cause memory leakage.