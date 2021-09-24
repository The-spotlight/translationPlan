![img](https://miro.medium.com/max/700/1*ETaBc5fV8cEgztR61U9d2Q.jpeg)

**The three pillars of a web application are the following:**

1. Manipulating the DOM
2. Recognizing JavaScript events
3. Communicating with the server

Today we will be looking at the second pillar: **Recognizing JavaScript Events**

JavaScript Events are composed of two parts. The first is called an **‘event listener’**. You may have used many event listeners while browsing the internet without even knowing it. An event listener is an **action** of the user — it is something that **happens**. The computer waits, or **‘listens’**, for this action to occur. Like listening for a friendly cry or an echo from a distance snowy mountain range. A very common event listener you may be well acquainted with, is **‘click’**.

When you click a button on a website, that, in essence, is a command for something to now be **executed**. Which brings us two the second part of recognizing a JavaScript event: ‘**handlers’**. The handler is the change that should take place when the event listener tells it to change.

A simple example would be deleting a photo from your computer. Firstly you would click the delete button. Doing so would be the **action** that the computer was waiting for. It was ‘**listening**’ for that command. Once it hears the command of the event listener, the computer would **execute** the deletion of your photo. The **very act of deleting** the photo is the event ‘**handler**’.

**Let’s compose the entire element to see what it looks like:**

Our JavaScript Event has two **parameters**, which each take one **argument**. The first argument is the ‘listener’, and the second argument is the ‘handler’. But, firstly, we need to attach our event listener & handler to an **HTML element**. So let’s grab those elements. For our first element, let’s choose to grab a generic delete button, from generic HTML, with an id of ‘delete-btn’ and place it in a variable called ‘deleteButton’. For our second element, let us grab what we would like to delete, which in this case would be an image. That would look like this:

![img](https://miro.medium.com/max/442/1*OkE7XH2z22Cay8IRnWwSfA.png)

Now we can proceed to add the event listener to our deleteButton variable:

![img](https://miro.medium.com/max/260/1*u17R2q2_MQ8NSuzZD1ZeXg.png)

Then we need to add the **action** or **listener** that we want to ‘listen’ for. In this case we want to listen for a ‘**click**’:

![img](https://miro.medium.com/max/335/1*rU1mtOz5BNDbkTGqqpChXw.png)

Next we want to include what we would like to be **executed** once the ‘click’ occurs. Remember, this is called our event **handler**.

![img](https://miro.medium.com/max/466/1*aPep_gULu4kQA0U_vBZVdQ.png)

**Summary:**

A JavaScript Event is a way for the user to interact with the web application to change the DOM. The JavaScript Event must firstly be attached to an HTML element. The event then takes in two arguments: an event listener, and an event handler. The listener is the ‘action’ that the computer is ‘listening’ for. For example, the computer may be waiting for a click or keypress to take place. The event handler is what takes place once the event listener (like the click) takes place. The handler executes something to change the DOM.