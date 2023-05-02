Download Link: https://assignmentchef.com/product/solved-cop3502-p1-blackjack
<br>
<h1>Overview</h1>

In this project students will simulate a simplified version of the game Blackjack. Students will implement random card drawing, calculation, state tracking, and console input systems. The project is designed to be a playful yet practical opportunity to practice data types, console I/O, control structures, and libraries.




<h1>Rules of the Road</h1>

<em>Forewarning: this specification does NOT follow the rules of casino Blackjack. Don’t drop out of your studies and move to Vegas just because you can beat your own randomized AI! </em>




A typical game will play out as follows:




The player will be dealt one card at the start of the game (where a game is one round of play). The player, based on the value of his cards, can either ask for another card (a hit) or choose to hold (stand). The dealer will then begin his turn and try to beat the player’s hand. The player is competing against the dealer, who has his own hand. Whomever is closer to 21 at the end of the game (as long as they don’t exceed 21) wins the game.




<ol>

 <li><em>Player’s turn</em>: Player tries to reach or come close to 21 without going over (as 21 is the highest hand).</li>

 <li><em>Dealer’s turn</em>: Dealer tries to beat exceed the player’s hand without going over 21.</li>

 <li>Determine the winner at the end of the game and increment the win count.</li>

 <li>Repeat!</li>

</ol>




You will need a while loop in your program. The loop will allow you to play successive games without restarting the program each time; it will also allow you to keep a win count over multiple games.




Here is the basic syntax of a while loop:




<strong>while</strong> (boolean expression)

{

// Statements }




If the boolean expression evaluates to true, the loop continues. If/when it ever evaluates to false, then the loop terminates (we skip over the loop block) and continue with the program.




Here is an example of a while loop:




<strong>int</strong> x= 0; <strong>while</strong> (x &lt; 17)

{

x += 10;

}

The variable <strong><sub>x</sub></strong> is initialized to zero and the conditional statement is checked. Since <sub>0</sub> is less than <sub>17</sub>, the expression evaluates to <sub>true</sub> and the statement in the while loop block will be executed. The number <sub>10</sub> is added to the value of <strong><sub>x</sub></strong>, so <strong><sub>x</sub></strong> is now <sub>10</sub>. We’ve reached the end of the loop, so we jump back up to the conditional statement. The expression evaluates to true since <sub>10</sub> is less than <sub>17</sub>, so we execute the statement in the loop again. Now <strong><sub>x</sub></strong> is equal to <sub>20</sub>. Once more the loop block ends and we jump back up to the conditional statement. Since <sub>20</sub> is not less than 17, the expression evaluates to <sub>false</sub> and the loop block will be skipped, and we jump to the code after the loop.




In this project, you will need to loop until the player chooses the exit option from the menu.




<h1>Structure</h1>

<em>Now that you have a general overview, here are the nitty gritty details. </em>




When the program starts it should print “<strong><sub>START GAME #1</sub></strong>” to the console, and the player should automatically be dealt their first card. With each new game played it should print the corresponding game number in this way.




To determine what card the player is dealt, a random number must be generated between 1 and 13; it is then added to the player’s hand. The range of random generation will be from 1-13. The values correspond to these cards:




<u>Value</u>               <u>Card</u>

1                      ACE!

2-10                 (correspond to their face values)

<ul>

 <li>JACK!</li>

 <li>QUEEN!</li>

 <li>KING!</li>

</ul>




Face cards (King, Queen, Jack) are worth a value of 10. If the player is dealt a King (generated as 13), the value 10 should be added to the player’s hand value rather than a 13. Aces have a value of 1. Every other card will be worth its face value.




Whenever a card is dealt, print the value of the card and the total value of your hand. (See sample output for format). If the card you were dealt was a face card or an ace then print the type of card. For example, if you were dealt a King you would print “<strong>Your card is a KING!</strong>” If the card was not a face card or an ace print the value of the card. For example, “<strong>Your card is a 2!</strong>”.




After the card is dealt, print the menu to the screen. The menu should look like this:




<ol>

 <li>Get another card</li>

 <li>Hold hand</li>

 <li>Print statistics</li>

 <li>Exit</li>

</ol>




If the player chooses option 1, the player will be dealt another card. If the player has a hand of 21, they automatically win and “<strong>BLACKJACK! You win!</strong>” is printed; then a new game is started. If the player’s hand exceeds 21, the dealer automatically wins; print, “<strong>You exceeded 21! You lose.</strong>”, then start a new game.




If the player chooses to hold their hand (option 2), then the dealer will be dealt his hand. To determine the dealer’s hand, generate a random number between 16 and 26 (both inclusive).




If the dealer’s hand is above 21, the player automatically wins. If both the dealer and player have the same value hand then no one wins. In this case print “<strong>It’s a tie! No one wins!</strong>”. Otherwise, whoever has the higher hand value wins the round. If the player wins, print “<strong>You win!</strong>”. If the dealer wins print “<strong>Dealer wins!</strong>” After the winner (or tie) has been determined, a new game is started.




If the player chooses option 3, you will print the statistics of the game. Throughout your program you will need to keep track of the number of games played, the player’s number of wins, the dealer’s’ number of wins and the number of ties. Print out all these values as well as the percentage of player wins to the total number games played. Format your percentage value to one decimal point. See sample output for format.




If option 4 is selected, exit the program.




If any other input is entered, print the following text:




Invalid input! Please enter an integer value between 1 and 4.




Then redisplay the menu. You can assume that the input will be numeric for this project (but not future projects.)




<h1>Random Numbers</h1>

For random numbers, you <strong>must use</strong> the <sub>P1Random</sub> class provided:




<strong>P1Random rng = new P1Random(); </strong>




You can get a new int value between zero (<sub>0</sub>) and some number (exclusive!) using the <sub>nextInt()</sub> method:




<strong>int myNumber = rng.nextInt(10); </strong><em>// Yields a random number in range [0,9]</em>




To get a number in a specific range, use these commands:




<strong>int myNumber = rng.nextInt(13) + 1; </strong><em>// A random number in range [1,13]</em>




<strong>int myValue = rng.nextInt(11) + 16; </strong><em>// A random number in range [16,26]</em>




<strong>NOTE: you must only pull random numbers as you need them, and you must use them in that order.</strong>




Do not get random values and throw them away!

Do not get clever with how you generate random numbers!




If you do, your output will diverge, and it could <strong>seriously impact</strong> your grade.

<strong> </strong>

<h1>Submissions</h1>

<strong>NOTE</strong>: Your output must match the example output *exactly*. If it does not, <strong><em>you will not receive full credit for your submission</em></strong>!




File:                 BlackJack.java

Method:           Submit on ZyLabs





