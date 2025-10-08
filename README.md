<h1>ExpNo 5 : Implement Simple Hill Climbing Algorithm</h1> 
<h3>Name:     Divya A        </h3>
<h3>Register Number:       2305002007      </h3>
<H3>Aim:</H3>
<p>Implement Simple Hill Climbing Algorithm and Generate a String by Mutating a Single Character at each iteration </p>
<h2> Theory: </h2>
<p>Hill climbing is a variant of Generate and test in which feedback from test procedure is used to help the generator decide which direction to move in search space.
Feedback is provided in terms of heuristic function
</p>


<h2>Algorithm:</h2>
Step 1- Read the target string from the user.

Step 2- Generate a random initial solution of the same length as the target.

Step 3- Calculate the score (difference) between the current solution and the target.

Step 4- Repeat the following steps until the score becomes zero: a. Display the current score and solution. b. Mutate one random character in the current solution to create a new solution. c. Calculate the score of the new solution. d. If the new solution has a lower score, replace the old one.

Step 5- When the score becomes zero, stop the process.

Step 6- Print the final solution as the target string.

## PROGRAM
```
import random, string

def hill_climb():
    target = input("Enter the target string: ")
    sol = [random.choice(string.printable) for _ in target]
    score = lambda s: sum(abs(ord(a)-ord(b)) for a,b in zip(s, target))
    best, best_score = sol, score(sol)

    while best_score:
        print(best_score, "".join(best))
        new = best.copy()
        new[random.randrange(len(new))] = random.choice(string.printable)
        new_score = score(new)
        if new_score < best_score:
            best, best_score = new, new_score

    print("Final:", "".join(best))

hill_climb()
```

<hr>
<h2>Sample Input and Output</h2>
<h2>Sample String:</h2> Hello
<h2>Output:</h2>
<img width="410" height="346" alt="image" src="https://github.com/user-attachments/assets/b27b7f91-60a6-4af8-bfdd-0d2990168844" />
<img width="512" height="591" alt="image" src="https://github.com/user-attachments/assets/1ad1f5f2-f8bf-432d-a98f-12dd921cdc51" />

## RESULT:
Thus the program to Implement Simple Hill Climbing Algorithm has been executed successfully.
