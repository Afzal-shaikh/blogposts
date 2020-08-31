# Var,Let & Const

## lets talk about **Var** first

we use it to declare a variable like this

```js
    var x = 100;
```
but do you know you can decalre it again ??
```js
    var x = 100;
    var x = 300;
    consol.log(x)//will successfully print 300 in your console

```
yes, the var variables are redefinable 

which means in a long code you can define a variable twice by mistake  and then spend a lot of time trying to figure out what went wrong 

 scoping -
 var as we know is function scoped , which means its only availible in the function that it is created 
```js
    function name(){
        var name = "penguin";//only available in this function

        console.log(name);//will work
    }

    name() //will work

    console.log(name);//will scream at you in red color

```


 so what happens when it is declared outside a function ?
 it becomes globally scoped

 ```js
    if(marks > 40){
        var grade = "pass"; //variable decalred not within a function 
        console.log("your grade is ${grade}")
    }

 ```
 if you write this code , and then in your console type out `console.log(grade)` then it will still print the grade which means **the variable `grade` is being stored even after the execution** of that line which is not required,  which means the var grade has leaked from it's block and can create problems later on 



mainly these are the points where  _Var_ differs with _let_ and _const_
 you can learn more about _var_ about [here](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/var "MDN Webdocs Var")


## Now let's talk about 'Let' and 'Const' 

first of all let and const cannot be redefined like var 

no way to use the same variable name again 

```js

    let x = 100;
    let x = 300 ; //will not work and will scream at you in red 
```
but as let and const are block scoped meaning they're available in the block they're defined in 

```js

let marks = 78
let isPass = false;//globally scoped 

if(marks > 50){//start of the block

    let isPass = true; //block scoped

}//end of the block

console.log(isPass)//will print 'false'
```
here we've used the same name `isPass` to define a variable two times but both of them refer to two different vairable values , which means they're not the same variable because of their scoping , while the first `isPass' is defined globally , what we have to do is to update it instead of redefining it for the desired outcome 

```diff
- let isPass = true; 
+ isPass = true;
```

while a let defined variable can be changed like this a `const` defined cannot be changed however, you can change attributes in a const defined object , for e.g

```js
    const student= {
        name = 'penguin'
        marks = 78
    }

    //we cannot reassign the whole variable like

    student = { name = 'not penguin' } // this will not work

    //but we can change the properties 

    student.marks = 97; //this will work


```

so, i think this information is enough to understand differences between Var , Let & Const 
Hopefully you've gained something from this
As this is my first post i hope you liked it, Thank you
i intend to post more about whatever i have learned you can follow me for more such posts on twitter [@aFlying_Penguin](https://twitter.com/aFlying_Penguin)
