1. Why does concat only need to work between two lists of the same representation? What would
   you have to do differently, or what would go wrong, if you tried to make it work between a
   LinkedList and an ArrayList?

   concat only works between two lists because it needs access to the specific data structure. Having them mismatch would force the program to build new nodes and copy items one by one.


2. Walk through reverse() on your linked list: name the three pointers you need alive at once,
   and explain why losing track of any one of them mid-loop corrupts the list

   The three pointers you need alive at once are prev, current, and nextNode. If you lose track of nextNode, the rest of the list gets disconnected.


3. addAnywhere and deleteAnywhere both need a bounds check. What’s the valid range for
   position in each, and what does your implementation do if a caller passes a position outside
   it?

   The valid range is 0 to size for adding and 0 to size - 1 for removing. If a caller passes a position outside,  an error happens before changing the list.


4. In LinkedList::concat, why did you need to walk to the end of the list first, when addFront
   and deleteFront never needed to? What would change about concat’s performance if
   LinkedList still tracked a tail pointer, and what would you have to keep updated elsewhere
   if you added one back?

   Because without a tail pointer, combining lists would be slow. Adding a tail pointer makes the merge instant, but means you have to write extra code to update the pointer.


5. Pick either addAnywhere or deleteAnywhere in ArrayList and explain, in your own words, what
   has to shift and in which direction, and why shifting in the wrong direction would overwrite
   data you still need.

   addAnywhere shifts items to the right starting from the back of the array down to the target. Shifting in the wrong direction would replace the item that was there before.


6. Point to the exact line in your main.cpp where a Reverse card actually changes the direction of
   play, and explain what would visibly break in the game if that call were missing.

   The reverse card changes the game direction at "table1->reverse();" at line 39. If this call is missing, the list will keep printing the players in the same order.