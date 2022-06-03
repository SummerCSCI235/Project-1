---  
layout: myDefault
title: PROJECT 1
---  

# Project 1: Class creation and Inheritance 

![vehicle_meme](./Content/vehicle.png)


To start off this project, you need to create a `Vehicle` class. Through inheritance you will create its children as well: `Truck`, `Car`, and `Motorcycle`. In this project you will use separate compilation with g++ to link multiple classes into one executable, and, in order to successfully complete this project, you **must** understand the prerequisite material and also the information presented in the Programming Guidelines file which can be found in blackboard under Course Material.

---

### Some additional resources

- -***Inheritance:***
 
    [Geeks for Geeks](https://www.geeksforgeeks.org/inheritance-in-c/)  
    [Caleb Curry](https://youtu.be/_rzEUwv2-eQ)

---
### Implementation:



**Work incrementally!** Work through the tasks sequentially (implement and test). Only move on to a task when you are positive that the previous one has been completed correctly. Remember that the names of function prototypes and member variables must exactly match those declared in the respective header file when implementing a class. 


---
![welding_glue_meme](./Content/superglue.png)
## Task 1: Honey, where is my super glue? 
Define and implement the abstract `Vehicle.hpp` and `Vehicle.cpp` class. 

The Vehicle class will have these member variables which should be private: 

```
   std::string name_
   std::string manufacturer_
   int wheels_
   int gas_
   int passengers_
   int cargo_
```

The Vehicle class will have these member functions, all public:

```
   // This default constructor should set all member variables to either "" or 0 depending on their type
   Vehicle();

   // Sets all member variables to what was passed in the parameters
   Vehicle(std::string name, std::string manufacturer, int wheels, int gas, int passengers, int cargo);

   std::string getName() const;                         //Should return the name_ variable
   void setName(std::string name);                      //Should set the name_ variable

   std::string getManufacturer() const;                 //Should return the manufacturer_ variable
   void setManufacturer(std::string manufacturer);      //Should set the manufacturer_ variable

   int getWheels() const;                               //Should return the wheels_ variable
   void setWheels(int wheels);                          //Should set the wheels_ variable

   int getGas() const;                                  //Should return the gas_ variable
   void setGas(int gas);                                //Should set the gas_ variable

   int getPassengers() const;                           //Should return the passengers_ variable
   void setPassengers(int passengers);                  //Should set the passengers_ variable

   int getCargo() const;                                //Should return the cargo_ variable
   void setCargo(int cargo);                            //Should set the cargo_ variable
```

---
![chose_your_vehicle_meme](./Content/choose.png)Project-1
## Task 2: CHOOSE YOUR VEHICLE!
After you are finished implementing the `Vehicle` class, now you have to define and implement the `Car`, `Motorcycle` and `Truck` classes as inherited children of the `Vehicle` class.  

The `Car` class represents an Vehicle object with the following specifications:
- It has 4 wheels
- Can hold 5 passengers
- Can hold 12 gallons of gas
- Can carry 850 pounds

The `Car` class must contain the following methods, knowing the information above and that each constructor _must_ call the `Vehicle` parameterized constructor:
```
   // name and manufacturer of this vehicle should be "" since no value was passed
   Car();

   Car(std::string name, std::string manufacturer);

   // adds a string to list_of_bumper_stickers_ 
   void addBumperStickers(std::string sticker);

   // prints out each sticker from list_of_bumper_stickers_ 
   void getBumperStickers();
```
   And for the private members it should only contain a vector of strings, that will be named as **vector<std::string> list_of_bumper_stickers_**

The `Motorcycle` class represents an Vehicle object with the following specifications:
- It has 2 wheels
- Can hold 2 passengers
- Can hold 1 gallons of gas
- Can carry 0 pounds

The `Motorcycle` class must contain the following methods, knowing the information above and that each constructor _must_ call the `Vehicle` parameterized constructor:
```
   // name and manufacturer of this vehicle should be "" since no value was passed
   Motorcycle();

   Motorcycle(std::string name, std::string manufacturer);

   /**
      if sideMotorcycle_ is false, change wheels amount from 2 to 4 
            and passenger amount from 2 to 3 and set sideMotorcycle_ to true
      if sideMotorcycle_ is true, change wheels amount from 4 to 2 
            and passenger amount from 3 to 2 and set sideMotorcycle_ to false
   */
   void toggleSideMotorcycle();

   // returns the current state of sideMotorcycle_
   bool getSideMotorcycle();

```
And as for the private members for motorcycle, you _must_ have a variable  **bool sideMotorcycle_** that represents if the motorcycle has a side car.

The `Truck` class represents an Vehicle object with the following specifications:
- It has 16 wheels
- Can hold 3 passengers
- Can hold 125 gallons of gas
- Can carry 80000 pounds
  
The `Truck` class must contain the following methods, knowing the information above and that each constructor _must_ call the `Vehicle` parameterized constructor:
```
   // name and manufacturer of this vehicle should be "" since no value was passed
   Truck();

   Truck(std::string name, std::string manufacturer);
   
   /**
      if hasTrailer_ is false, change wheels amount from 16 to 26 
            and cargo amount from 80000 to 16000 and set hasTrailer_ to true
      if hasTrailer_ is true, change wheels amount from 26 to 16 
            and cargo amount from 16000 to 80000 and set hasTrailer_ to false
   */
   void toggleTrailer();
   
   // returns the current state of hasTrailer_
   bool getTrailer(); 
```
Here is the private variable for the truck class **bool hasTrailer_**


---
### Submission:
**You will submit the following files**:  
`Car.hpp`
`Car.hpp`  
`Motorcycle.cpp`  
`Motorcycle.hpp`  
`Truck.cpp`  
`Truck.hpp` 
`Vehicle.cpp`
`Vehicle.hpp` 

Your project must be submitted on Gradescope. Although Gradescope allows multiple submissions, it is not a platform for testing and/or debugging and it should not be used for that. You MUST test and debug your program locally. Before submitting to Gradescope you MUST ensure that your program compiles (with g++) and runs correctly on the Linux machines in the labs at Hunter (see detailed instructions on how to upload, compile and run your files in the “Programming Rules” document). That is your baseline, if it runs correctly there it will run correctly on Gradescope, and if it does not, you will have the necessary feedback (compiler error messages, debugger or program output) to guide you in debugging, which you don’t have through Gradescope. “But it ran on my machine!” is not a valid argument for a submission that does not compile. Once you have done all the above you submit it to Gradescope.

---

### Testing
How to compile:  
```
g++ Vehicle.cpp Car.cpp Motorcycle.cpp Truck.cpp <test main file> -std=c++17
```

You must always implement and test you programs **INCREMENTALLY!!!**
What does this mean? Implement and test one method at a time.
**For each class**
- Implement one function/method and test it thoroughly (multiple test cases + edge cases if applicable).
- Implement the next function/method and test in the same fashion.
**How do you do this?** Write your own `main()` function to test your classes. In this course you will never submit your test program, but you must always write one to test your classes. Choose the order in which you implement your methods so that you can test incrementally: i.e. implement mutator functions before accessor functions. Sometimes functions depend on one another. If you need to use a function you have not yet implemented, you can use stubs: a dummy implementation that always returns a single value for testing Don’t forget to go back and implement the stub!!! If you put the word STUB in a comment, some editors will make it more visible.

### Grading Rubrics
**Correctness 80%** (distributed across unit testing of your submission)  
**Documentation 10%**  
**Style and Design 10%** (proper naming, modularity, and organization)  

---

### Important
You must start working on the projects as soon as they are assigned to detect any problems with submitting your code and to address them with us **well before** the deadline so that we have time to get back to you **before** the deadline. This means that you must submit and resubmit your project code **early** and **often** in order to resolve any issues that might come up **before** the project deadline.  
**There will be no negotiation about project grades after the submission deadline.**
  
  
  
  
  
