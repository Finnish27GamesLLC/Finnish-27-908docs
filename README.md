# Finnish-27-908docs
This repository contains text files saved by the BIGS908 software application.

The BIGS908 software application is a game simulator. The component enables the user to do the following. Load into program memory a user-defined set of game rules saved to a data file by a software application selected from a group consisting of the BIGS907 software application and the BIGS921 software application. Load into program memory a matching-strategy table selected from a group consisting of a set of combination-dependent-playing-strategy tables saved to a data file by the BIGS907 software application and a total-dependent-basic-strategy table saved to a data file by the BIGS921 software application. Use the matching-strategy table to make decisions on how to play the player's hand. Use the predetermined strategy for the play of the dealer's hand specified by the user-defined set of game rules to make decisions on how to play the dealer's hand. Simulate millions of rounds of play of the double exposure game in accordance with the user-defined set of game rules.

The BIGS908 software application enables users to model the behavior of human card counters by programming the computer-controlled player to use a card-counting strategy and by programming the computer-controlled player to use a betting strategy to vary the size of the game wager in response to changes in the card count. A typical card-counting strategy assigns a count value to each rank of card. The count value assigned to each rank of card is roughly equal to the change in the expected value of the game wager caused by the removal of one card of that particular rank from the stack.

Whenever a card is exposed, a counter adds the count value of that particular rank of card to a running total, known as the 'running count'. The running count gives the card counter a measure of the expected
value of the game wager. 

The higher the running count is the higher the expected value of the game wager. If a particular rank of card is assigned a negative count value, then the removal of one card of that particular rank from the shoe causes a change in the expected value of the game wager that is favorable to the dealer.  If a particular rank of card is assigned a count value of zero, then the removal of one card of that particular rank from the shoe causes no change in the expected value of the game wager. If a particular rank of card is assigned a positive count value, then the removal of one card of that particular rank from the shoe causes a change in the expected value of the game wager that is favorable to the player. 

If the house has a significant edge over the player, then most of the time the running count will indicate that the expected value of the game wager favors the house. Whenever the running count is high enough to indicate that the expected value of the game wager favors the player, then the card counter raises the game wager.

The card counter usually does so in accordance with a betting strategy. A bet spread is equal to the quotient of the size of the large game wagers the card counter makes when the running count is high enough to indicate that the expected value of the game wager favors the player divided by the size of the small game wagers the card counter makes when the running count is low enough to indicate that the expected value of the game wager is unfavorable to the player. If the bet spread is large enough and if the built-in house edge of a game is low enough, then under the right circumstances skilled players can use a card-counting strategy and a betting strategy to overcome the built-in house edge of a game and in the long term win more from the house than is lost to the house.

The size of the effect of the removal of any given rank of card is inversely proportional to the number of cards remaining in the stack. That is. The greater the number of cards remaining in the stack the smaller the effect of the removal of a single card to the discard pile. The smaller the number of cards remaining in the stack the larger the effect of removal of a single card to the discard pile. This fact makes the running count an inaccurate measure of the expected value of the game wager. A more accurate measure of the expected value of the game wager is desirable. Two kinds of card-counting strategies follow from two ways of achieving a more accurate measure of the expected value of the game wager.

MODELING THE BEHAVIOR OF HUMAN CARD COUNTERS: BALANCED-CARD-COUNTING STRATEGIES

Balanced-card-counting strategies call for players to assign count values to each rank of card such that when added together these count values equal zero.  For example, the following is a balanced-card-counting strategy that works well for the computer-controlled player in a simulation of the second-optional embodiment wherein: Each deck of cards consists of thirteen ranks of each of Four French suits.  The count values assigned individually to the cards by rank are as follows. Each card bearing indicia representative of the rank of ace, counts as negative one. Each card bearing indicia representative of a rank selected from a group of ranks consisting of two, three, four, five, six, and seven, counts as positive one. Each card bearing indicia representative of the rank of eight, counts as zero. Each card bearing indicia representative of a rank selected from a group of ranks consisting of nine, ten, jack, queen, and king, counts as negative one. 

The following table shows that the sum of all count values assigned to all ranks of cards present in each fifty-two card deck is equal to zero. There is a balance of positive count values and negative count values and as such, this card-counting strategy is a balanced-card-counting strategy.

Rank			Count Value		Number Of Cards  		TOTAL 

Ace			  -1			         4				        -4
Two			  +1			         4				        +4
Three			+1			         4				        +4
Four 			+1			         4				        +4
Five			+1			         4				        +4
Six			  +1			         4				        +4
Seven 		+1 			         4				        +4
Eight 		 0			         4				         0		
Nine			-1			         4				        -4
Ten			  -1			         4				        -4
Jack			-1			         4				        -4
Queen			-1			         4				        -4
King			-1			         4				        -4			
___________________________________________________________________
Totals 		 0			        52				         0

At the beginning of the shoe, if the card counter is using a balanced-card-counting strategy, then the card counter generally starts counting with an initial-running count of zero. Whenever a card is exposed, a counter adds the count value of that rank of card to a running total, known as the 'running count'. 

At the beginning of each subsequent round of play, the card counter divides the running count by their own estimate of the number of decks remaining in the stack. Card counters refer to this action as performing a true-count conversion.

By performing the true-count conversion, the card counter converts the running count into a true count. In so doing, the card counter mathematically adjusts for the fact that the size of the effect of the removal of any given card is inversely proportional to the number of cards remaining in the stack. The true count provides to the card counter a more accurate measure of the expected value of the game wager than does the running count. For that reason, many card counters use the true count to make betting and playing decisions rather than using the running count.

If the bet spread is large enough, and if the house edge is low enough, then card counters are able to turn the overall odds of the game in favor of the player by systematically varying the size of the game wager in response to the true count as follows. If the true count is high enough to indicate that the expected value of the game wager favors the player, then the card counter places a large game wager and otherwise the card counter places a minimal game wager. However, if a card counter uses an unbalanced-card-counting strategy, then the card counter can avoid the added step of making the true-count conversion.

MODELING THE BEHAVIOR OF HUMAN CARD COUNTERS: UNBALANCED-CARD-COUNTING STRATEGIES

Unbalanced-card-counting strategies call for players to assign count values to each rank of card such that when added together these count values do not equal zero. For example, the following is an unbalanced-card-counting strategy that works well for the computer-controlled player in a simulation of the second-optional embodiment wherein: Each deck of cards consists of thirteen ranks of each of Four French suits.  The count values assigned individually to the cards by rank are as follows. Each card bearing indicia representative of the rank of ace, counts as negative one. Each card bearing indicia representative of a rank selected from a group of ranks consisting of two, three, four, five, and six, counts as positive one. Each card bearing indicia representative of the rank of seven, counts as positive zero-point-five. Each card bearing indicia representative of a rank selected from a group of ranks consisting of eight and nine, counts as zero. Each card bearing indicia representative of a rank selected from a group of ranks consisting of ten, jack, queen, and king, counts as negative one. 

The following table shows that the sum of all count values assigned to all of the ranks of cards in each fifty-two card deck is not equal to zero. The sum is equal to positive two. There is not a balance of positive point counts and negative point counts and as such, this card-counting strategy is an unbalanced-card-counting strategy.

Rank			Count Value		Number Of Cards 		TOTAL 

Ace			  -1			          4				        -4
Two			  +1			          4				        +4
Three			+1			          4				        +4
Four 			+1			          4				        +4
Five			+1			          4				        +4
Six			  +1			          4				        +4
Seven 		+0.5			        4				        +2
Eight 		 0			          4				         0		
Nine			 0			          4				         0
Ten			  -1			          4				        -4
Jack			-1			          4				        -4
Queen			-1			          4				        -4
King			-1			          4				        -4			
___________________________________________________________________
Totals 		+0.5    	        52				      +2

There are two surplus count points per each fifty-two-card deck in play. On average, this causes the running count to drift upward during the course of dealing a significant portion of the stack from a shoe. When the running count reaches a certain "key count", then the running count indicates to the card counter that on average the expected value of the game wager is favorable to the player.  The card counter knows it is time to increase the size of the game wager. The key count is a significantly higher number than the initial-running count. In practice, if a card counter is using an unbalanced-card-counting strategy, then the card counter can use any number as an initial-running count.

The important thing is that the difference of the key count minus the initial-running count be correct given the predetermined set of game rules. On average, as the running count drifts upward during the course of dealing a significant portion of the stack from a shoe, it becomes easier for the card counter to attain a running count that is equal to or greater than the key count.  This adjusts for the fact that the size of the effect of the removal of any given rank of card is inversely proportional to the number of cards remaining in the stack. In this way, unbalanced card-counting strategies make the running count a more accurate measure of the expected value of the game wager than it would otherwise be.

USING AN E-Z-COUNT STRATEGY TO IDENTIFY THE BEST-CARD-COUNTING STRATEGIES THAT A HUMAN PLAYER COULD USE

An E-Z-count strategy is a balanced-card counting strategy. The E-Z-count strategy assigns a decimal-count value to each rank of card in the stack. Each decimal-count value is equal to a measurement made of the change in the expected value of the game wager caused by the removal of one card of the corresponding rank from each complete deck in the stack. There are two ways of making the above-described measurement. 

One way to make the above-described measurements is to do so simultaneously for each rank of card by using summations of various ongoing simulation results. The BIGS908 software application uses this approach. 

Most if not all human players would be unable to use the decimal-count values of an E-Z-count strategy to count cards during the course of a live game. However, some human players would be able to use integer-count values to count cards during the course of a live game. A person skilled in the art could choose the integer-count values that best approximate the decimal-count values of the E-Z-count strategy. Using these integer-count values, a person skilled in the art could derive unbalanced-card-counting strategies and balanced-card-counting strategies that work well with the betting strategy employed by the computer-controlled player.

Accordingly, the BIGS908 software application provides those skilled in the art with an easy way of identifying the card counting, and betting strategies that human players might attempt to use to gain a theoretical advantage over the house while playing a double-exposure game belonging to the Finnish 27 family of table-card games.

