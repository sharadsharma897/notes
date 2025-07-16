Destructing
Destructuring in Function Parameter Lists
For example, if a function accepts a parameter that will contain an object it can be destructured to "pull out" the object properties and make them available as locally scoped variables (i.e., variables only available inside the function body).

function storeOrder(order) {
  localStorage.setItem('id', order.id);
  localStorage.setItem('currency', order.currency);
}
Instead of accessing the order properties via the "dot notation" inside the storeOrder function body, you could use destructuring like this:

function storeOrder({id, currency}) { // destructuring
  localStorage.setItem('id', id);
  localStorage.setItem('currency', currency);
}
It's very important to understand, that storeOrder still only takes one parameter in this example! It does not accept two parameters. Instead, it's one single parameter - an object which then just is destructured internally.

The function would still be called like this:

storeOrder({id: 5, currency: 'USD', amount: 15.99}); // one argument / value!
