PART 1: 15 Practice Exercise Questions

**1. Call Stack & Event Loop**

A web page has a button that logs "Start", then uses setTimeout to log "Async Task", and finally logs "End".

Explain the execution order using Call Stack, Callback Queue, and Event Loop.

- Execution order: Start--> End --> Async Task
- console.log("Start") goes to call stack then executes.
- setTimeout() callback goes to callback queue
- console.log("End") then it executes
- Event loop moves callback from queue to call stack.

**2. Callback Queue**

You are loading ads after page load using setTimeout.

Why does the ad load after the main content even if the timeout is 0ms?

- Because setTimeout() is asynchronous.
- The callback waits in callback queue until the call stack is empty, so main content executes first.

**3. JSON.parse()**

You receive this API response as a string:

'{"id":101,"name":"Laptop","price":50000}'
Convert it into a JavaScript object and access the name.

- const obj = JSON.parse('{"id":101,"name":"Laptop","price":50000}');
- console.log(obj.name);

**4. JSON.stringify()**

You want to store user details in localStorage.

Convert the following object into JSON string:
{ username: "admin", role: "manager" }

- const jsonstr = JSON.stringify({ username: "admin", role: "manager" });
- console.log(jsonstr);

**5. Array forEach – Real-Time Example**

You have a list of users and want to print a welcome message for each user.

Use forEach() to log messages.

const users = ["Raj","Ravi","Krishana"];

users.forEach(user=>{
console.log(`Welcome ${user}`);
});

**6. Array map – Price Calculation**

An e-commerce site gives 10% discount on all prices.
Use map() to create a new discounted price list.

const prices = [1000,2000,3000];

const discounted = prices.map(p=> p*0.9);

**7. Array filter – Search Feature**

You want to show only available products from a product list.

Use filter() to return items with inStock === true.

const products = [{name:"Phone",inStock:true},{name:"TV",inStock:false}];

const available = products.filter(p=> p.inStock===true);

**8. Array reduce – Cart Total**

Calculate the total price of items in a shopping cart using reduce().

const cart = [500,1000,1500];

const total = cart.reduce((sum,price) => sum+price,0);

**9. Function Declaration vs Arrow Function**

Create a function to calculate GST using:

Function Declaration

Arrow Function

Mention one key difference.

- // Function Declaration

function calculateGST(price) {

return price * 0.18;

}

- // Arrow Function

const calculateGSTArrow = price => price * 0.18;

- Key Difference is Arrow finctions do not have their own this.

**10. Closures – Secure Counter**

Create a counter function that cannot be directly modified from outside.

- function counter() {

let count = 0;

return function () {

count++;

return count;

};

}

const increment = counter();

**11. Callback Function – Login Validation**

You validate a user and then redirect them.

Implement validation using callback functions.

- function login(user, callback) {

if (user === "admin") {

callback("Login successful");

}

}

login("admin", msg => console.log(msg));

**12. Callback Hell – Payment Processing**

A payment flow involves:

Validate user
Process payment
Generate invoice

Explain why nested callbacks become difficult to manage.

- Nested callbacks make code:
- Hard to read, Difficult to debug, Difficult to maintain.

**13. Promises \& async/await**

Convert this promise-based API call into async/await:
fetch(url).then(res => res.json()).then(data => console.log(data));

- async function getData() {
  const res = await fetch(url);
  const data = await res.json();
  console.log(data);
  }

**14. DOM Manipulation – Dynamic UI**

You click a button and dynamically add a new list item to <ul>.

Which DOM methods will you use?

Methods are used:

- document.createElement()
- appendChild()
- querySelector()

**15. Event Listeners – Form Validation**

A form should display an error message when submitted without input.

Explain how addEventListener() helps.

- addEventListener() listens to form submit events and executes validation logic without reloading the page.

- Example:
  form.addEventListener("submit", e => {
  if (input.value === "") {
  e.preventDefault();
  alert("Input required");
  }
  });
