***
# __*Portfolio*__
***

## **Classes**:
In the summer of 2021, we are taking 3 classes. These classes are: 

### 1. CSCI 70300: Data Structure High Level Language Lecture 

- Click **[here](Data_Structures)** to see work done in Data Structures.


### 2. CSCI 70900: Programming High Level Language Lecture

- This is the programming language we're learning.
![alt text](https://cdn.worldvectorlogo.com/logos/java.svg)

- Here is a piece of code we did in class:

``` java
// Brian Mueller, Julian Irimina, Jovani Cardenas

/*
PSEUDOCODE:
Start off with 12 stones
loop while stones > 0
    current player is USER or AI
    current player
        scanner choice of 1, 2, 3 stones
        TODO LATER: input sanitization: type anything else --> error, try again
    AI
        randomly choose 1, 2, 3
    remove stones
after loop, current player wins
*/

import java.util.Scanner;
import java.lang.Math;

class Nim {
    public static void main(String[] args) {

        Scanner count = new Scanner(System.in);

        System.out.println("Welcome to the game of Nim. There is a bag with 12 stones.");
        System.out.println("To play this game, you can remove 1-3 stones. You will be playing against the computer.");
        System.out.println("Whoever removes the last stone is the winner.");

        int numStones = 12;
        String currentPlayer = "USER";
        while(numStones > 0){
            if(currentPlayer == "USER"){
                System.out.println("How many stones do you want to remove? Enter 1, 2, or 3.");
                int stonesToRemove = count.nextInt();
                while(stonesToRemove > 3 || stonesToRemove < 1){ // number besides 1, 2, 3
                    System.out.println("Oops! Try again: enter 1, 2, or 3.");
                    stonesToRemove = count.nextInt();
                }
                while(stonesToRemove > numStones){ // ex: 2 stones remaining, user enters 3
                    System.out.println("There are only " + numStones + " stones remaining.");
                    System.out.println("Try again, enter a number up to " + numStones);
                    stonesToRemove = count.nextInt();
                }
                numStones -= stonesToRemove;
                System.out.println("Stones remaining: " + numStones);
                if(numStones < 1){
                    break;
                }
                currentPlayer = "COMPUTER";
            } else {
                int stonesToRemove = compNum();
                while(stonesToRemove > numStones){ // in case random choice > stones remaining
                    stonesToRemove = compNum();
                }
                System.out.println("The computer removed " + stonesToRemove);
                numStones -= stonesToRemove;
                System.out.println("Stones remaining: " + numStones);
                if(numStones < 1){
                    break;
                }
                currentPlayer = "USER";
            }
        }
        System.out.println("The winner is " + currentPlayer + ".");
    }

    public static int compNum(){
        return (int) (Math.random()*3 + 1);
    }
}
```

### 3. SEDC 71900: Methods 1

|#| Assignment Name | Date Pushed |
|--:|:---------------:|:-------:|
|1|[01_lesson](https://github.com/hunter-teacher-cert/work_csci70900-JCardenas62/blob/master/meth1/01_lesson)| 07/13/2021|
|2|[02_livecode](https://github.com/hunter-teacher-cert/work_csci70900-JCardenas62/blob/master/meth1/02_livecode)| 07/14/2021|
|3|[03_IntroNetLogo](https://github.com/hunter-teacher-cert/work_csci70900-JCardenas62/blob/master/meth1/03_IntroNetLogo)| 07/19/2021|
|4|[06_unplugged](https://github.com/hunter-teacher-cert/work_csci70900-JCardenas62/blob/master/meth1/06_unplugged)| 07/20/2021|





