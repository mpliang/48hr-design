#48 Hour Questionnaire

###Question 1:

I think that the use of `width: calc(25% - 4em - 2px);` seems like bad practice. I would just stick with 2 values in the calculation and not use a mixture of %, em, and px. Also there is only a single media query. To be more responsive, I would account for more screen sizes. I think I would also use pixels for things like padding and margins and em or rem for font sizes. I did like that there was the use of a media query and flexbox display.

***

###Question 2:

1. '===' means it will evaluate if the expression is strictly equal to while '==' will use type coercion to try and evaluate. In my opinion, you should always use '===' to avoid type coercion and any unexpected errors.

2. My favorite ES2015 feature is probably template strings

    >Instead of:
    >```
    >"htttp://www.ibm.com/design/" + user + "/profile/default.html"
    >```
    >You can now do:
    >```
    >`http://wwww.ibm.com/design/${user}/profile/default.html`
    >```
    >Also multiline strings are nice.

3. 'i' will be 10 each time it's logged. This is caused by closure. The reason for this is because the function inside the set timeout will be executed after the for loop has completed and reference the last stored value of i, which in this case is 10.

The easiest way to fix this is with es6 and just changing var to let in the for loop:
```javascript
for (let i = 0; i < 10; i++) {
    setTimeout(function () {
        console.log(i);
    }, i * 100)
}
```
If using es5, here are some other solutions:
```javascript
//wrapping the set timeout in an iffe and passing in i
for (var i = 0; i < 10; i++) {
  ( function(x) {
    setTimeout( function() {
      console.log(x);
    }, x*100);
  })(i);
}

//returns function
for (var i = 0; i < 10; i++) {
  setTimeout((function(x) {
    return function(){
      console.log(x);
    }
  })(i), i*100);
}

// third argument for set timeout
for (var i = 0; i < 10; i++) {
  setTimeout(function(n) {
    console.log(n)
  }, i*100, i);
}

//binding console and i
for (var i = 0; i < 10; i++) {
  setTimeout(console.log.bind(console, i), i*100);
}

```

4. Fibonacci sequence

```javascript
let fib = (n) => {
    if (n<3) return 1;
    else return fibonacci(n-1) + fibonacci(n-2);
}
```
***

###Question 3:
1. My favorite project is probably the one I'm working on now. It's an app that tracks your budget for you each month, reminds you of bills, and also allows you to split things like rent, gas, and other miscellaneous bills with either your roommates or friends. It uses the venmo and facebook apis as well as d3. I really like this app because of how much I've learned and I feel like it is a practical app that people might actually use someday.

2. This is a personal side project so I've contributed everything so far, both front end and backend as well as the design.

3. Just learning new apis like venmo and facebook have really been challenging; setting the headers when making requests and getting back the information you want hasn't always been easy. Even though it has been challenging, it has been a great experience!
