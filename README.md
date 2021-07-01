# True_Or_False_C#
LEARN C#
True or False?
You’re taking an interactive quiz written in C#. Everything is going fine until you respond to this question:

title

This application wasn’t checking your input. When you used an unexpected format, it couldn’t ask the question again and marked your answer as wrong. (By botanical definition, eggplants really are berries!).

In this project, you’ll build a C# program that presents a quiz the right way: using arrays and loops, it will check the format of user input and repeat the question if the format is incorrect. After the quiz is complete, it will check the user’s responses against the correct answers and present a score.

title

Let’s get started!

Tasks
22/22 Complete
Mark the tasks as complete by checking them off
Setup Arrays
1.
We’ll need arrays to hold the questions, answers, and user responses.

First declare and initialize a questions array of type string[]. The array should contain your own true or false questions.


Stuck? Get a hint
2.
Declare and initialize an answers array of type bool[]. It should contain the correct answers for each question, in the same order.


Stuck? Get a hint
3.
Declare responses array of type bool[]. It should be an empty array with the same length as the questions array.


Stuck? Get a hint
4.
To avoid any errors later on, write yourself an if statement that checks if the length of the questions array IS NOT equal to the length of the answers array.

If they are not equal, write a warning to the console.


Hint
You’ll need the Length property, the != operator, and an if statement, which looks like:

if (x != y)
{
  Console.WriteLine("Warning! x doesn't equal y.");
}
Ask Questions
5.
Now we’ll loop through the questions array, asking each question and recording the user’s responses.

First, create a variable askingIndex to keep track of the currently asked question. Set it to 0.


Hint
This variable should be of type int.

6.
Build an empty foreach loop that iterates through each question in questions.


Hint
Here’s an example foreach loop:

foreach (double temp in temps)
{
}
7.
Before we ask a question, we’ll need to define some empty variables. Declare these in the loop:

input — the text the user enters
isBool — true if the user input can be converted to a boolean, otherwise false
inputBool — the boolean version of the user’s entry

Hint
input is of type string
isBool is of type bool
inputBool is of type bool
8.
Ask the question once. In the loop:

Print the current question to the console
Print True or false? to the console
Capture the user’s input in input

Hint
Use Console.WriteLine() to print to the console and Console.ReadLine() to read from the console.

9.
Now let’s check if the user’s input can be converted to a boolean.

Call the method Boolean.TryParse() to convert the user input to a boolean value.

This method takes two arguments: a string value to convert and a bool variable to store the converted string. It returns true if the conversion was successful, false otherwise.

Here’s the method signature:

public static bool TryParse(string value, out bool result)
Use input and inputBool as arguments and capture the returned value in isBool.


Stuck? Get a hint
10.
At this point, the program asks each question once and doesn’t do anything with the response.

Run your code to make sure that everything is working fine. It should look something like this:

$ dotnet run
Eggplant is a vegetable.
True or False?
no
Eggplants are a species in the nightshade family.
True or False?
true

Stuck? Get a hint
11.
We may have to ask the current question multiple times if the user responds in the wrong format. Create an empty while loop within the foreach loop.

It should continue looping while isBool is false.


Stuck? Get a hint
12.
If the user does not respond with “true” or “false”, then we’ll need to ask for a proper response again. Within the while loop:

Print Please respond with 'true' or 'false'. to the console
Capture the user’s input in input
Try to convert input to a boolean using Boolean.TryParse()

Stuck? Get a hint
13.
At this point, your while loop is complete. It should repeatedly ask for input until the user’s input can be successfully parsed as a boolean.

Outside of the while loop but inside the foreach loop, store the user’s boolean answer in responses and increment askingIndex by 1.


Stuck? Get a hint
14.
Well done! The asking part of the quiz is over. Test your code to make sure the responses are being recorded correctly.

Do this by printing out the values of responses at the end of your code (outside of the loops).


Stuck? Get a hint
Calculate Score
15.
Now that the user has answered all of the questions, we’ll need to compare those responses to the answers array and count the number of correct responses.

First, define a few variables:

scoringIndex — to loop through the responses. Set to 0
score — to count the number of correct responses. Set to 0

Stuck? Get a hint
16.
Create an empty foreach loop that iterates through each answer in answers.


Stuck? Get a hint
17.
First, capture the response matching the answer.

Within the loop, use scoringIndex to access an element in responses and store the value in a variable.


Stuck? Get a hint
18.
Second, write out the user response and correct answer for each answer in answers.

It should look similar to this:

1. Input: True | Answer: False

Stuck? Get a hint
19.
Now we’ll add to the user’s score if the response matches the answer.

Still within the loop, use an if statement that increments score if the response equals the answer.


Stuck? Get a hint
20.
Outside of the if statement but within the foreach loop, increment scoringIndex by 1.


Stuck? Get a hint
21.
At this point your foreach loop should print out the user responses and answers and calculate a score.

Outside of this loop, announce the user’s score. It may look similar to this:

You got 4 out of 5 correct!

Stuck? Get a hint
22.
Congrats on building this app! Run it one more time with dotnet run: it can run a true or false quiz, gracefully handle user input, and calculate user scores.

If you’re app isn’t running right, check the hint for troubleshooting tips.

If you’d like to extend your work, here’s a suggestion:

If you wanted to make multiple quizzes, you would have to type out the same code multiple times. Fix this issue by refactoring your code into a method RunQuiz(). It should take two arguments: a string[] array of questions and bool[] array of answers. It should have the same behavior as your current app.

string[] questions = new string[]
{
  /*...*/
};
 
bool[] answers = new bool[] 
{
  /* ...*/
};
 
RunQuiz(questions, answers);
