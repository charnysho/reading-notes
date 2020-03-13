## JS Debugging

### The JS interpreter processes one line of code at a time. When a statement needs from another function, it stacks (or piles) the new function on top of the current task.

### Error types

1. Reference Error (This is caused by a variable that is not declared or is out of scope)

2. SyntaxError (Creates an instance representing a syntax error that occurs while parsing code in eval().)

3. TypeError (Creates an instance representing an error that occurs when a variable or parameter is not of a valid type.)

4. Range Error (If you call a function using numbers outside of its accepted range)

### Handling exceptions

1. Try (Block of code to be tested for errors while it is being executed)
2. Catch (Block of code to be executed, if an error occurs in the try block. If no error occurs, this block of code is never executed)
3. Finally (Block of code to be executed regardless of the try / catch result)

```
function myFunction()
  var message, x;
  message = document.getElementById("message");
  message.innerHTML = "";
  x = document.getElementById("demo").value;
  try { 
    if(x == "") throw "Empty";
    if(isNaN(x)) throw "Not a number";
    if(x > 10) throw "Too high";
    if(x < 5) throw "Too low";
  }
  catch(err) {
    message.innerHTML = "Error: " + err + ".";
  }
  finally {
    document.getElementById("demo").value = "";
  }
}
```

4. The `throw` statement allows you to create a custom error. Technically you can throw an exception (throw an error). The exception can be a JavaScript String, a Number, a Boolean or an Object: