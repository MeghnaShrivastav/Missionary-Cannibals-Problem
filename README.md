# Missionary-Cannibals-Problem
In this problem, three missionaries and three cannibals must cross a river using a boat which can carry at most two people, under the constraint that, for both banks, that the missionaries present on the bank cannot be outnumbered by cannibals. The boat cannot cross the river by itself with no people on board.
This kind of problem is often solved by a graph search method. We represent the problem as a set of states which are snapshots of the world and operators which transform one state into another.
States can be mapped to nodes of a graph and operators are the edges of the graph.
Solution:
First let us consider that both the missionaries (M) and cannibals(C) are on the same side of the river.
Left Right
Initially the positions are : 0M , 0C and 3M , 3C (B)

Now let’s send 2 Cannibals to left of bank : 0M , 2C (B) and 3M , 1C
Send one cannibal from left to right : 0M , 1C and 3M , 2C (B)
Now send the 2 remaining Cannibals to left : 0M , 3C (B) and 3M , 0C
Send 1 cannibal to the right : 0M , 2C and 3M , 1C (B)
Now send 2 missionaries to the left : 2M , 2C (B) and 1M . 1C
Send 1 missionary and 1 cannibal to right : 1M , 1C and 2M , 2C (B)
Send 2 missionaries to left : 3M , 1C (B) and 0M , 2C
Send 1 cannibal to right : 3M , 0C and 0M , 3C (B)
Send 2 cannibals to left : 3M , 2C (B) and 0M , 1C
Send 1 cannibal to right : 3M , 1C and 0M , 2C (B)’
Send 2 cannibals to left : 3M , 3C (B) and 0M , 0C
 Here (B) shows the position of the boat after the action is performed.
Formalization of the M&C Problem :
State space: triple (x,y,z) with 0≤ x,y,z≤ 3, where x,y, and z represent the number of missionaries, cannibals and boats currently on the original bank.

Initial State: (3,3,1)

Successor function: From each state, either bring one missionary, one cannibal, two missionaries, two cannibals, or one of each type to the other bank.
Note: Not all states are attainable (e.g., (0,0,1)), and some are illegal.
Goal State: (0,0,0)

Therefore all the missionaries and cannibals have crossed the river safely.
