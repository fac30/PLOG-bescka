## Guidance
Answer the following questions considering the learning outcomes for
- [Week 02](https://learn.foundersandcoders.com/course/syllabus/developer/week02-project02-chatbot/learning-outcomes/)

Make sure to record evidence of your processes. You can use code snippets, screenshots or any other material to support your answers.

Do not fill in the feedback section. The Founders and Coders team will update this with feedback on your progress.


SGC

Continue: 
* RTD 
  
Stop 
***

Go


## Assessment
 ### 1. Show evidence of some of the learning outcomes you have achieved this week.

* Write code that executes asynchronously

* Use callbacks to access values that aren’t available synchronously
* Use the fetch method to make HTTP requests and receive responses
* Configure the options argument of the fetch method to make GET and POST requests
* Understand server-side development using Node.js.
```javascript
async function ask(prompt) {
  const fetch = (await import('node-fetch')).default;
  try {
    const response = await fetch('http://localhost:5000/generate-response', {
      method: 'POST',
      headers: { 'Content-Type': 'application/json' },
      body: JSON.stringify({ message: prompt }),  
    });

    const data = await response.json();

    if (data.error) {
      throw new Error(data.error); 
    }

    return data.response;  
  } catch (error) {
    console.error('Error communicating with Python backend:', error);
    return 'Sorry, something went wrong while processing your request.';
  }
}

module.exports = { ask };
```

* Set up a Node.js environment for web development
* Use environment variables for managing secrets and sensitive keys in Node.js
* Use npm to manage project dependencies and scripts in a Node.js environment.
[index.js - node/ discord setup](https://github.com/fac30/PRO02_Ben_Tania_Levi/blob/main/index.js)



 ### 2. Show an example of some of the learning outcomes you have struggled with and/or would like to re-visit.

Testing! Few examples of implemented testing frameworks in the project.  

## Feedback (For CF's)
> [**Course Facilitator name**]  
> [*What went well*]  
> [*Even better if*]
