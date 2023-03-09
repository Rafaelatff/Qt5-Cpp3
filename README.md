# Qt5-Cpp3
Repositorie created to help during the course 'Qt 5 C++ GUI Development For Beginners : The Fundamentals'.

Let's create a new project (Non-Qt Project) and keep learning C++.

## Lambda basics

Lambdas are a C++ construct (C+11 and onward) that allows one to write un-named functions "in place", which makes the std lib algorithms much more usable.

Lambda function = **[capture list] (parameter list) -> return_value {function body}**

### Calling Lambda function 1

The first way, gives the Lambda function a name and call it.

```c++
    // Inside main
    // [capture list] (parameter list) {function lambda}
    auto func = []() {
        cout << "Hello World!" << endl;
    };
    
    // to call lambda function
    func();
```

As result:

![image](https://user-images.githubusercontent.com/58916022/224012023-925d7012-fa1f-4558-b3fa-84a0c11991a8.png)

If I comment the line 'func();' then I won't get the "Hello World!" message.

## Calling Lambda function 2

Second way, call lambda function directly after definition.

```c++
[]() {
            cout << "Hello World!" << endl;
}(); */
```

## Calling Lambda function 3

Now, we are going to define a lambda function that takes parameters and call after definition.

```c++
[](uint32_t a, uint32_t b){
        cout << "a + b = " << a + b << endl;
}(7,3);
```

As result, we have:

![image](https://user-images.githubusercontent.com/58916022/224017164-bd3f6e27-83ff-4220-8f36-cc2b4d11781e.png)

## Calling Lambda function 4

We can call a lambda function that takes parameters, is called just after definition and also returns a value.

```c++
    uint32_t sum = [](uint32_t a, uint32_t b){
        cout << "a + b = " << a + b << endl;
        return a + b;
    }(7,3);

    cout << "The sum is: " << sum << endl;
```

As result we have:

![image](https://user-images.githubusercontent.com/58916022/224023536-b23d3686-aca9-47f1-a7cd-86dc927142d5.png)

## Calling Lambda function 5

Now, it may look a little bit ackward, but we will replace, at the last code line, the sum variable for the lambda function (minus the cout inside). It will also work. Check the code:

```c++
        cout << "The sum is: " << [](uint32_t a, uint32_t b)->uint32_t{
            return a + b;
        }(7,3) << endl;
```

And check the results:

![image](https://user-images.githubusercontent.com/58916022/224024576-dc0cbbbe-7aca-4710-a45e-df9d2fc93c47.png)

## Calling Lambda function 6

Now let's start to use the capture list. The lambda function need to receive the variables in the capture list to work with them. 

```c++
    uint32_t a = 7;
    uint32_t b = 3;
    
    [a,b](){
        cout << "a is: " << a << endl;
        cout << "b is: " << b << endl;
    }();
```

As result:

![image](https://user-images.githubusercontent.com/58916022/224026245-205fbb8b-0f31-4c49-a8a8-5fc752d04399.png)


