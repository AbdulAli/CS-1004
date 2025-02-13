# CS-1004 - Grand Quiz # 1 (60 minutes Quiz)
### Your answers should be crisp and to the point. Don't write paragraphs, unless it's for code.

## Q#1 - Heap (1 minute)
What is BSS in a heap?

## Q#2 - Pointers (5 minutes)
Analyze the following C++ program and determine its behavior:
```
#include <iostream>
using namespace std;

int main() {
    int *a, *b;
    a = new int;  // Dynamically allocate memory
    *a = 42;      // Assign a value to allocated memory
    b = a;        // b now points to the same memory as a
    *b = 24;      // Modify value through b
    delete a;     
    *b = 10;      // What happens here?
    return 0;
}
```

Questions:
1.	What will happen when *b = 10; is executed after delete a;?
2.	Why are a and b considered dangling pointers (if they are) or true alias (if they are)?
3.	How can you modify the code to prevent the issue?


## Q#3 - Pointers (4 minutes)
Consider the following C++ program:
```
#include <iostream>
using namespace std;

int main() {
    int arr[2][3] = {{1, 2, 3}, {4, 5, 6}};
    int (*ptr)[3] = arr;  

    cout << *(*(ptr + 1) + 2) << endl;  

    return 0;
}
```
Question: What will be the output of this program? 
## Q#4 - Recursion (15 minutes) 

Scenario: The Climbing Stairs Problem

You are climbing a staircase with *n* steps. You can either take 1 step or 2 steps at a time.  How many distinct ways can you climb to the top?

For example:

*   If n = 1, there is only 1 way (1 step).
*   If n = 2, there are 2 ways (1+1 or 2).
*   If n = 3, there are 3 ways (1+1+1, 1+2, 2+1).
*   If n = 4, there are 5 ways (1+1+1+1, 1+1+2, 1+2+1, 2+1+1, 2+2).

Your Task:

Write a recursive function called `climbStairs(int n)` that takes the number of steps `n` as input and returns the number of distinct ways to climb to the top.

Hint: Think about how the number of ways to reach step `n` relates to the number of ways to reach step `n-1` and step `n-2`.

Example Usage:

```
int ways = climbStairs(4);
cout << ways << endl; // Output: 5
```


## Q#5 – Classes (15 minutes)

Contingency and the Necessary Being

Reflect on your own existence. You exist, but you could have been born at a different time, in a different place, to different parents. Your existence is contingent – it depends on a chain of events that could have easily unfolded differently.

Consider your thoughts. They change constantly, influenced by your experiences, your emotions, and countless other factors. A moment ago you were thinking about this question, but soon you'll be thinking about something else. Your thoughts are contingent – they are fleeting and dependent on other things.

Look around you. The chair you're sitting on, the device you're reading this on, the room you're in – all of these things exist, but they could have been otherwise. They are contingent – their existence depends on a multitude of factors, from the materials they're made of to the people who created them.

Even the planet we live on is contingent. It exists, but it could have formed differently, or not at all. Its existence depends on the laws of physics, and even the laws of physics themselves exist contingently – i.e., they need something to be the way they are.

The concept of contingency suggests that *everything* we observe in the universe is contingent – it exists, but it could have been otherwise. However, this chain of contingency must ultimately lead back to something that is *not* contingent, something that *must* exist, something that is necessary. This is the necessary being, the ultimate ground of all existence.

Scenario: Tracing Contingency

Imagine you are tracing the contingency of a simple action: you decide to have a cup of tea.

1.  Your *decision* to have tea is contingent on your current state (perhaps you're tired, or thirsty).
2.  Your *current state* is contingent on your previous experiences, your sleep, your diet, etc.
3.  Your *experiences* are contingent on the people you've met, the places you've been, the events that have happened to you.
4.  These events are contingent on the state of the world, including the physical laws that govern it.
5.  And even the laws of physics are contingent.

Your Task:

Write a C++ program that represents this chain of contingency, tracing it back towards the necessary being. Since we cannot fully represent the complexity of this, we will simplify. We will represent each contingent thing as a class, and its dependence on something else as a member variable (representing the thing it depends on).

1.  Create a class `Decision` with a member variable of type `CurrentState`.
2.  Create a class `CurrentState` with a member variable of type `PreviousExperiences`.
3.  Create a class `PreviousExperiences` with a member variable of type `LifeEvents`.
4.  Create a class `LifeEvents` with a member variable of type `PhysicalLaws`.
5.  Create a class `PhysicalLaws` with a member variable of type `NecessaryBeing`.
6.  Create a class `NecessaryBeing` with a function `void exist()`. This class represents the necessary being, and its `exist()` function signifies its inherent existence.

Each class (except `NecessaryBeing`) should have a function (e.g., `trace()`) that prints a message explaining its contingency and then calls the `trace()` function of the member variable it depends on. The `Decision` class's `trace()` function should start the chain. The `PhysicalLaws` class's `trace()` function should call the `trace()` function of the `NecessaryBeing` class.


Example Usage:

```
NecessaryBeing necessaryBeing;
PhysicalLaws physicalLaws(necessaryBeing);
LifeEvents lifeEvents(physicalLaws);
PreviousExperiences previousExperiences(lifeEvents);
CurrentState currentState(previousExperiences);
Decision decision(currentState);

decision.trace();
```


## Q#6 - Stack with pointers (20 minutes)

Scenario: Stack Data Structure

A stack is a linear data structure that follows the Last-In, First-Out (LIFO) principle.  Imagine a stack of plates. You can only add a new plate on top of the stack, and you can only remove the topmost plate.  The last plate you put on is the first one you take off.

Key Operations:

*   Push: Adds an element to the top of the stack.
*   Pop: Removes and returns the top element from the stack.
*   IsEmpty: Checks if the stack is empty.
*   Peek (or Top): Returns the top element without removing it.

Your Task:

Implement a stack data structure using a struct and pointers in C++.  The stack should store integers.

1.  Create a struct named `Node` that represents an element in the stack.  Each `Node` should contain an integer `data` and a pointer `next` that points to the next `Node` in the stack (or nullptr if it's the bottom of the stack).

2.  Create a struct named `Stack` that represents the stack itself.  It should contain a pointer `top` that points to the topmost `Node` in the stack (or nullptr if the stack is empty).

3.  Implement the following functions for the `Stack` struct:

    *   `void push(int value)`: Adds a new element with the given `value` to the top of the stack.
    *   `int pop()`: Removes and returns the top element.  If the stack is empty, return -1 (or throw an exception).
    *   `bool isEmpty()`: Returns true if the stack is empty, false otherwise.
    *   `int peek()`: Returns the value of the top element without removing it. If the stack is empty, return -1.

Example Usage:

```
Stack s;
s.push(10);
s.push(20);
s.push(30);

cout << s.pop() << endl; // Output: 30
cout << s.peek() << endl; // Output: 20
cout << s.isEmpty() << endl; // Output: 0 (false)
```

