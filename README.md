#READMEEXAMII
Problem 1:
LONGEST PALINDROMIC SUBSTRING
Given a string s, find the longest palindromic substring in s.
QUESTIONS:
Do we have a maximum length for a palindrome string?
Do I have to answer the problem in a specific time complexity?
Do we have to find sub palindrome at the center of the palindrome?
Could we center the substring from the palindrome?
Does the string have to be a valid palindrome to have a substring palindrome?

I:	The problem consists of finding the substring palindrome within a string. Implications such as the string’s length could be an issue for time complexity due to approaches such as brute force.
D:	For a solution I would want to have good time complexity, and a good pattern that will be effective for every string despite its length.
E: 	First to reduce time complexity we could take in consideration centering the sub palindrome down the middle of the string since it mirrors at its center. Centering the sub palindrome would read the string from both sides at the same time checking for symmetry, cutting the time to read the string.
A:	Th algorithm is design to check the size at both ends of the word, if the string isn’t the exact same length from left to right with one extra variable in the middle then it won’t scan the string even if it has a sub palindrome somewhere inside the string.
L:	The algorithm is a decent approach, because it is not using brute force and the strategy to check the valid string from both ends tackles the issue of longer palindromes. Also verifying that the palindrome is valid first avoids strange inputs such as “xxabaxy” that might have a sub palindrome but isn’t considered a palindrome.	

DUKES -7- STEPS:
STEP 1:  An example would be the valid palindrome “xabax”, and a non-valid palindrome containing a valid substring would be “xxabaxb”, both have “aba” as a substring at its center, and the mirrored center helps find the sub palindrome.
STEP 2: What I did to check for a valid sub palindrome was implementing an algorithm that would have two pointers, one at the beginning and one at the end of the string checking if the characters where equal in length approaching the center, incrementing if pointer was located at the beginning or decrementing if pointer was located at end.
STEP 3: The patterns the algorithm contains are checking the start and end characters and decrementing/incrementing towards the middle that if valid contains a mirrored palindrome.
STEP 4/STEP 5: My code initializes the String s as parameter, within the method it checks if its empty and if it is it returns and empty string “”. If the string isn’t empty it proceeds to initialize the start and end pointers it increments from start to end and decrements from end to start, if and only if the left side is greater than 0 and right is less than the length of the string and both have equivalent characters in quantities.
STEP 6: Test Cases s = “bntyuouyhgj” -> “yuouy” [sub palindrome]
STEP 7: Failed Test Cases: “hkashxxabaxxh” -> not the same length of characters on both ends 

Problem 2:
CONTAINER WITH MOST WATER
Given n integers a1, a2, ..., an, where each represents a point at coordinate (i, ai). n vertical lines are drawn such that the two endpoints of line i is at (i, ai) and (i, 0). Find two lines, which together with x-axis forms a container, such that the container contains the most water.
QUESTIONS:
Can we assume there are negative/positive integers?
Can we assume the vertical lines are represented by an array of integers?
How many vertical lines?
Since its area we are considering do we multiply the quantities of the line lengths?

I:	The problem is that we must find a combination of positive integers given in a form of array from left to right that will give us the highest area capability to hold water between them.
D:	The solution will have a pattern algorithm which checks the combination of numbers from left to right at the same time to see which one can hold the highest amounts of water.
E: 	The problem could be approached from a brute force perspective needing several passes through the n vertical lines list but using a two-pointer approach passing through the beginning and end of the list at the same time is more efficient.
A:	This approach uses a single pass through the list of the n vertical lines, but an issue may arise depending on the lengths of the inner lines, if we begin by considering the exterior most lines and reducing by them inwards. We might miss greater area findings if the inward movement is done in the wrong patter. 
L:	Although the approach might seem better compared to others, if implemented poorly it can cause a higher margin of error, but if used correctly it can produce faster results. Trying odd cases can help optimize the use of the algorithm by debugging and catering to specific cases.  

DUKES -7- STEPS:
STEP 1: We are given an  array [1, 8, 6, 2, 5, 4, 8, 3, 7] of numbers that represent vertical lines and if we multiply two of these vertical lines minus the difference of the lines we will get the max amount of water they can hold in this case (8 - 7 = 1) and so (7 x 7 = 49) where 49 is the maximum area of water.
STEP 2: The algorithm uses a two-pointer approach which compares one line from the left with one line from the right, and then increments to the left and compares to the same right and then switches and decrements from the right and so on, multiplying the values of the compared vertical lines. For example, it would compare (1 x 7) = 7 then left would decrement and it would be (8 x 7 – (difference)) = 49.
STEP 3: Patterns include incrementing and decrementing both pointers and comparing by multiplying the values of the vertical lines to get the highest combination.
STEP 4/STEP 5: My code takes an array of ints called height as a parameter and then initializes the left to 0 and the right to the length of the array -1. While the right is greater than the left it will decrement, and while the left is less than the right it will increment and after the code gets both quantities it subtracts them gets the difference and multiplies them by each other to get the final answer.  
STEP 6: Test Cases: [1, 3, 2, 6] -> (3 - 6 = 3) -> (3 x 3 = 9)
STEP 7: Failed Test Case: non-valid array of integers

Problem 3:
GENERATE PARANTHESIS
Given n pairs of parentheses, write a function to generate all combinations of parentheses.
QUESTIONS:
Do the combinations of parenthesis have to be valid “( )”? or can the also be “) (”?

I:	The n integer will define all the pairs of parentheses, the problem is to return all the possible well-formed parenthesis combinations, without odd outputs. 
D:	Generate all algorithm that will be able to identify correctly placed open and closed parenthesis and place them in an orderly matter where all possible combinations are displayed.
E: 	The goal of the solution is to properly generate parenthesis and then check the format by going through the different combinations and searching for opened and closed parenthesis.
A:	An issue may be the length of the parenthesis as the more parenthesis within the parenthesis the longer it takes to check for an opened and closed pair.
L:	It is hard to keep track of parenthesis or data in general if the algorithm doesn’t implement other helpful tools such as stack or a memory/backtracking method.

DUKES -7- STEPS:
STEP 1: For given number n = 2 the set of parentheses [()()], [(())] are valid opened closed pairs while [)()(] isn’t in the correct format.
STEP 2: The parenthesis is generated by given n and then checked for either an opened or closed parenthesis, if the pairs aren’t completed the program returns false.
STEP 3: The patterns consist of checking for initial opened parenthesis and a closed parenthesis to complete the pair.
STEP 4/STEP 5: The program takes an int n for the parameter and initializes an array list within the method called combinations that contains all possible parenthesis combinations and return them, a method checks for an open parenthesis and a closed parenthesis and if it is invalid it returns the Boolean false. A final method contains the correct format the parenthesis must follow to be considered complete or a legal format.
STEP 6: Test Case: [(((())))], [()()()()], [(())(())]
STEP 7: Failed Test Case: [()))))(], [)()()(((]

Problem 4:
MINIMUM PATH SUM
Given a grid filled with numbers, find a path from top left to bottom right which minimizes the sum of all numbers along its path.
QUESTIONS:
Can we assume the numbers are non-negative integers?
Can I move diagonally to scan the numbers or just up and down?
Does the grid have rows as well as columns?

I:	We are given a grid of rows and columns assuming to contain positive integers, and we must return the smallest sum of numbers through a path from the top left to the bottom right. The issue is to identify the combinations of numbers that will give the smallest outcome following the guidelines.
D:	The solution would consist of a pattern algorithm that would go on its own and check possible combinations and add them to find the minimum result, whether it is a small or big grid.
E: 	A possible strategy would be to 	initialize (i) for rows and (j) for columns and increment each one for every number combination in the gird to add and find the minimum sum value.
A:	The approach to solve this problem might take longer as the number of integers within the grid increases as it must check paths though the rows and columns either up/down/left/right moving one step at a time.
L:	Although it is a very simple problem for humans to solve it becomes a tricky problem to solve when dealing with positions and quantities and even more complicated when dealing with operations between rows and columns.

DUKES -7- STEPS:
STEP 1: We have an example grid with the integers {[1,3,1], [1,5,1], [4,2,1]} the minimum path sum for this grid would be 1 -> 3 -> 1 -> 1 -> 1 with an output sum of seven. 
STEP 2: To solve this problem the algorithm checks each number combination either adjacent or down (only) and adds them starting from the top left to the bottom right.
STEP 3: Patterns in the algorithm are the comparing of the numbers either up/down/left/right, which consist of either incrementing the rows or the columns.
STEP 4/STEP 5: The program starts by taking an int array [][] as a parameter and then within the method it initializes the variable index for both rows and columns. The algorithm then initializes a dummy array that will read through the regular grid and it starts by incrementing either rows or the columns at a time. At the end the algorithm goes through the grid finding the Math.min meaning the smallest sum from the integers through the path and returns the resulting summation.
STEP 6: Test Case: Path 1 -> 3 -> 1 -> 1 -> 1
STEP 7: Failed Test Case: Can’t be diagonal

Problem 5:
FIND PEAK ELEMENT
A peak element is an element that is greater than its neighbors. Given an input array nums, where nums[i] ≠ nums[i+1], find a peak element and return its index. 
QUESTIONS:
What if there are multiple peeks within the array of numbers?
If the number after the previous number are equal, do we consider the list of numbers?

I:	We have to compare the numbers within the array list and return the peak number, meaning the highest number in relation to the numbers before and after.
D:	The solution would consist of a pattern that would compare the current number to the next number within the array.
E: 	The algorithm could go one way from start to finish, for example (1, 2, 1), only comparing the first by the second and the second by the third and so on, returning the highest number in between the first and third. In this case the peek number would be the number 2 in between the position in the array index 0 and 2.
A:	The adjacent numbers can’t equal each other so arrays of that kind would not work, also an issue of time could arise depending on the length of the array. 
L:	Although this solution works well, there might be a solution that checks on both end at the same time comparing i to i+1 at the beginning incrementing and j to j-1 decrementing, cutting the run time.

DUKES -7- STEPS:
STEP 1: Given the array of integers [2, 4, 1, 6, 2] we scan the array and return the peek elements in this case we return 4 and 6 since those are the peek integers in comparison to the surrounding integers.
STEP 2: To solve the problem we scan the array of integers linearly comparing the first integer to the next and then the next integer to the next and so on.
STEP 3: A pattern consist of incrementing the array index position and comparing adjacent integers.
STEP 4/STEP 5: The program takes an array of integers [] as the main parameter and then initializes index i and increments it as long as it remains under the length of the array. Index i is compared the proceeding adjacent integer and if its greater it returns the greater integer proceeding to compare the rest of the array and returning accordingly.
STEP 6: Test Case: [4, 7, 3, 1, 3, 2] -> [7, 3]
STEP 7: Failed Test Case: [1, 1, 1, 1] -> 0

Problem 6:
LARGEST NUMBER
Given a list of integers, arrange them such that they form the largest number.
QUESTIONS:
Do the integers consist of positive and/or negative integers?
Can the integers be more than single digits, and if so, could we rearrange the order of them?

I:	The problem is to reorder an array of integers to where they form the biggest number together (non-negative integers) assuming that we can’t rearrange all the digits greater than or equal to double digit integers.
D:	The solution should consist of the biggest number made from the list of numbers including the double-digit numbers in the same order they where given. For example, if we get [2, 56, 58, 9] as an array our output would look like [958562].
E: 	A possible strategy would be to place the numbers in descending order, comparing them and then placing them in the correct format to create the largest integer. 
A:	A possible issue could be that the algorithm works for single digit integers but when dealing with digits larger than single digits the value changes and so for example, 34 is greater than 9 but in largest format it should be 934 not 349.
L:	What I learned is that it becomes harder trying to compare numbers that are double digits with single digits as they have a different value and it messes with the resulting format. 

DUKES -7- STEPS:
STEP 1: Taking in consideration an array of integers [3, 30, 34, 5, 9] the output should come out to an ordered combination of “9534330” in string format, without separating integers larger than two digits.
STEP 2: We cannot approach the integers by simply sorting them in descending number, but we must first convert them to strings and then sort the numbers, and this will result the issue of the double digits having a low leading number in comparison to a larger single digit integer.
STEP 3: The pattern consists of checking all the integers and placing them in the according descending order, taking in consideration the leading coefficient of paired integers.
STEP 4/STEP 5: The program takes the array of integers and converts the numbers into string focusing in the leading coefficient of paired numbers, in terms of generality it splits the double-digit integers and compares them in regular and reverse order. If the list is empty it returns a zero and if it isn’t it adds the integers into the largest number format.
STEP 6: Test Case: [8, 43, 5, 9] -> “98543”
STEP 7: Failed Test Case: Invalid array of integers

Problem 7:
LONGEST SUBSTRING WITHOUT REPEATING CHARACTERS
Given a string, find the length of the longest substring without repeating characters.
QUESTIONS:
Is there a maximum number limit to how long the string can be?
What happens if the substring has only one character repeated multiple times?

I:	The problem is to return a substring of characters within a string that has no repeating characters without changing its order and returning its length in form of an integer.
D:	The solution would consist of an algorithm that reads through the string and returns the length of the longest substring, by comparing the characters.
E: 	A possible strategy would be to use a second list where we read through the first string and then place the characters seen in the first string to the second list and then pass through the first string again and check if it is within the second list.
A:	The anticipated time complexity would be long since it takes a while to go through the first list, place the characters into a second list and got through the first one again to compare with the second. 
L:	This problem has the less efficient time complexity as this approach would be considered brute force, it takes a couple of steps to go through a small string, so going through a bigger string increases everything from steps to time.

DUKES -7- STEPS:
STEP 1: Given the example “abcabcbb” the output would be 3 and the explanation would be “abc” as the sequential non-repeated character string.
STEP 2: To solve this problem the algorithm must implement two separate arrays, the original and a dummy array that will hold the already seen characters to later go back and compare with the original string.
STEP 3: Patterns seen are the incrementation of indexes i and j, also the placement of seen characters to compare back and forth between the original and dummy array.
STEP 4/STEP 5: The algorithm would take the string s as its parameter and would then initialize an i and a j index position for the original array and for the second array that would contain the already seen characters within the string. Then it would have a method that would check the characters returning false if the character is within the second list or add the character to the second list if it hasn’t been seen.
STEP 6: Test Case: “wweebubeeddc” -> “ebu” -> 3
STEP 7: Failed Test Case: “wweebbccuu” -> “w” -> 1

Problem 8:
FIND FIRST AND LAST POSITION OF ELEMENT IN SORTED ARRAY
Given an array of integers nums sorted in ascending order, find the starting and ending position of a given target value.
QUESTIONS:
If given target is not found, should the program return a specific value?
Does the problem have to run in a specific time complexity?

I:	The algorithm must go trough the array list provided and return the beginning and ending position of the specific target provided, if not the program must return some sort of message confirming it was not found.
D:	The solution should return the index points of where the value begins and ends, the algorithm should be able to go through the array and compare the given target and the numbers within the array list.	
E: 	We can use a linear scan to go through the array from left to right, and if it finds an instance of the target, we then check from the end of the array to the left for a second instance and return the index values where the target was found.
A:	A possible outcome would be time, if the given array list is long the algorithm will go through every single number and in the worst case where there isn’t a found target it will go through to index 0 through the end n-1 to return an error message.
L:	Although this is a decent solution there are other approaches to this problem such as using a binary search to look for the target from the left and right at the same time approaching the center, this approach would be faster than the approach I implemented.

DUKES -7- STEPS:
STEP 1: Given the array of integers [5, 7, 7, 8, 8, 10] with a target of 8 we return the starting and end points of index positions for the targets location in this case being position [3, 4].
STEP 2: We solve the problem by searching the array of integers linearly and looking for the target, when we find the target, we return the start and end point of the index position.
STEP 3: Patterns within the algorithm consist of incrementing the index position and comparing the numbers to the set target until the integers within the array match.
STEP 4/STEP 5: The algorithm takes as parameters the array of integers and the integer target, it then initializes the index position and increments i if it is less than the length. When the integer of the array equals to the target it will return the location otherwise it returns an error message.
STEP 6: Test Case: [1, 3, 5, 5, 8, 9] -> [2, 3]
STEP 7: Failed Test Case: [1, 2, 5, 8, 9] -> ERROR

Problem 9:
FIND THE DUPLICATE NUMBER
Given an array nums containing n + 1 integers where each integer is between 1 and n (inclusive), prove that at least one duplicate number must exist. 
QUESTIONS:
Can there be more than one duplicate number?
Is there a specific time complexity the program should run under? 
Can the duplicated number be repeated more than once?

I:	The problem is that a duplicated number should be returned, so the algorithm must go through the array list and identify the duplicated number and return the actual number not the position(s).
D:	The goal is to implement an algorithm that will read through the array list quick and allocate the duplicated variable without going through the whole list.
E: 	A strategy could be to sort the array list to facilitate the reading of the string, so if one duplicated number is found the other duplicate will be adjacent to the number.
A:	Possible cases could be that the array list is long and the step to reorder the list in ascending order harms the time complexity if the duplicated integer is at the end of the array list.
L:	The solution implemented proves that with a good approach there could also be a huge issue if the right case is given, such that in the best-case scenario we find the duplicated integer at the beginning and the worst case we find it until the end.

DUKES -7- STEPS:
STEP 1: Given an array of integers [2, 4, 6, 7, 1, 1, 3], assuming that there is a duplicate number the algorithm should scan the array and return the duplicate number, in this case the number is 1.
STEP 2: The steps taken to solve this problem started by ordering the array of integers in ascending order then doing a linear scan going one by one comparing the numbers to each other adjacently to then return the duplicate number.
STEP 3: A pattern here is that if the list of integers is sorted either ascending or descending order the duplicate numbers will be side by side, and this will facilitate finding the duplicates which might have been originally scattered within the array. 
STEP 4/STEP 5: For the program the array of integers is taken as the main parameter, then initializing a sorting algorithm to sort the array in ascending order. After an integer I is initialized to serve as the index location and is incremented accordingly while it remains under the length of the array, then we take the array of integers considering the index location and compare that they’re equal and if they are the value is returned.
STEP 6: Test Case: [3, 5, 7, 3, 2] -> [2, 3, 3, 5, 7] -> 3
STEP 7: Failed Test Case: [1, 0, 4, 6, 3] -> [0, 1, 3, 4, 6] -> No duplicate

Problem 10:
REMOVE Nth NODE FROM THE END OF LIST
Given a linked list, remove the nth node from the end of list and return its head.
QUESTIONS:
Will the given value of the n node always be valid?
Is there a maximum number of nodes in the given linked list?

I:	The problem is that there is a given list of nodes and the algorithm must go through the list and identify the nth given node and remove it from the end of the array, but to remove it from the end we must first identify the length of the list of nodes.
D:	The goal of the algorithm would be to go through the list of nodes identify the end of the array and pass a second time to remove the nth node position from the end of the list.
E: 	A possible strategy is first localizing the length of the list, then to initialize a dummy head that will point at the head of the original list and the pass the dummy will make through the list will relink the previous node to the next node of the removed node.
A:	An anticipated issue is that of time, the algorithm works efficiently when the list of nodes is short, but when he list is linger it must find the length, then attach a dummy head that will go through the whole list a second time if the node removal is closer to the length.
L: 	The approach implemented had steps that could have been removed, the algorithm consisted of a two-step process when it is possible to solve in one pass, as having more passes through the list of nodes increases the time complexity.

DUKES -7- STEPS:
STEP 1: Given linked list of integers 1 -> 2 -> 3 -> 4 -> 5 with a target that n = 2 that is the node that must be removed from the end, the program should return 1 -> 2 -> 3 -> 5, with the second to last node containing the integer 4 is removed and relinked.
STEP 2: A way to approach the problem is to first find the length of the original linked list to localize the node that must be removed from the end, after the algorithm must implement a dummy linked list that connects to the original head and tracks the node the must be removed locating it, deleting it, and re linking the previous node to the next node.
STEP 3: The patterns of the algorithm include scanning the for the length as every .next node is an increment into the length size, another pattern is the path that the dummy follows to scan and delete the given target node.
STEP 4/STEP 5: The program follows a two-pass algorithm, taking as main parameters the list of nodes ant the integer target that represents the index location of the node.  The code then initializes a new dummy node and redirects it to the head of the original list of nodes, checks whether the list is empty and if it’s not, it proceeds to scan, remove, and relink the path ways from the removed target from the end of the list.
STEP 6: Test Case: 0 -> 1 -> 2 -> 3 -> 4 -> 5 -> 6 -> null [TARGET : 3] 0 -> 1 -> 2 -> 3 -> 4 -> 6 -> 7 -> null
STEP 7: Failed Test Case: A linked list of multiple lists combined

Problem 11:
BINARY TREE INORDER TRAVERSAL
Given a binary tree, return the inorder traversal of its nodes' values.
QUESTIONS:
Is the given tree sorted a specific way? 
Is there a specific time complexity the algorithm must follow?

I:	The problem consists of a tree that must be returned in the order of inorder traversal meaning that the output should produce the order of left, root, then right nodes.	
D:	An algorithm that has a recursive approach to identifying and returning the correct format of the nodes from left -> root -> right.
E: 	We will initialize the tree and have a method that checks if the tree is empty and if not continues to check the tree adding them in the correct format in a recursive fashion.
A:	Anticipated results, the tree is in nature recursive and so using a recursive method to check all the nodes and return them in a specific order will still result in a good time complexity of O(n).
L:	Since trees pair well with recursive algorithms, I would say that trying to reorder any tree in any form and returning it isn’t a difficult task when paired with a well implemented recursive method.

DUKES -7- STEPS:
STEP 1: Given a tree [1, null, 2, 3] that is originally in the order of root, left, right, the program must return the order in traversal form meaning right, root, left and so the output would be [1, 3, 2].
STEP 2: The algorithm will scan the tree recursively and with a helper tool it will adjust the traversal format, by placing the right node then the root node then the left node, in order.
STEP 3: Patters include the adding of a node, when it is not equal to null, to the correct format as it checks recursively for right and left.
STEP 4/STEP 5: The program takes the tree of nodes as the main parameter then initializing an array list that will contain the contents of the nodes in an array format. A helper tool is initialized that will return and place the correct format from other recursive methods checking the right and left side of the tree. The methods will include checking whether the left and right nodes are empty and if not, it will add then in traversal order the array list. 
STEP 6: Test Case: [3, 5, 7, 2] ORIGINAL -> [5, 3, 7, 2] TRAVERSAL
STEP 7: Failed Test Case:  [null] -> poor test case doesn’t allow us to check the correct format

Problem 12:
SHUFFLE AN ARRAY
QUESTIONS:
Is there a specific order the array should be shuffled into?
Is there a specific time complexity the algorithm should implement?

I:	The problem is to implement an algorithm that will shuffle the integers within a given array and return the new shuffled array without any duplicates of the numbers.
D:	The solution should consist of a new array of numbers having the same numbers of the original array with the difference of randomly placed numbers.
E: 	A strategy could consist of creating a new array aside from the original to store the values of the original array and pull the values out at random removing them from the dummy array as they are placed in the original array that is reset before producing the new order.
A:	Anticipated issues, if we implement a reset method that is executed towards the original array it is important to take in consideration that the original array order will be lost if it isn’t stored in a separate array.
L:	It is important to consider all aspects of the code, major issues such as resetting a set of data can be a disaster when dealing with big and important quantities of data, as it is hard and nearly impossible to reproduce without backed up information. 

DUKES -7- STEPS:
STEP 1: Given an array of integers [4, 5, 7] the program should reshuffle the contents of the array into a new order of the integers. For example, we would take the original and return another possible format of [5, 4, 7].
STEP 2: The contents of the original array will be copied into the contents of a dummy array from which the integers of the original array will be drawn at random, resetting the original array and returning a new order of the integers into the array.
STEP 3: Patterns within the algorithm include tracing the contents of the array placing the into a dummy array and returning them.
STEP 4/STEP 5: The program initializes the original array and a dummy array, as well as it keeps a copy of the original array because if a reset function is used on the original array to replace its original contents in a new order, the original order will be lost. Then an integer i will be initialized to scan through the array integers and place them into the dummy array, the contents will be shuffled, the original array will be reset, and the contents will then be placed back into the original array removing them from the dummy array one by one.
STEP 6: Test Case: [5, 7, 1, 3, 9] -> [7, 9, 3 ,1, 5]
STEP 7: Failed Test Case: [5, 5, 5, 5, 5] This case doesn’t allow the programmer to see the shuffle since all the numbers are the same.

Problem 13:
TARGET SUM
You are given a list of integers, a1, a2, ..., an, and a target, S. Now you have 2 symbols + and -. Find out how many ways to assign symbols to make sum of integers equal to target S.
QUESTIONS:
Are the integers given non-negative?
Does every integer need to have either a positive or negative sign?

I:	The problem is that the algorithm must assign either a - or + sign to every number inside the array list, the catch is that the numbers must add up to a specific valid target given.
D:	The goal is to create an algorithm that will generate all possible correct combinations of symbols attached to integers that will return the specific target, and then return the number of combinations.
E: 	A strategy could be that of trying all possible combinations of symbols, but that would result in excess amount of failed combinations. To reduce the redundancy the algorithm could implement recursion with memorization meaning that it would calculate and keep track of the solution as the symbols are placed.
A:	An issue with this approach will be the memory affecting the time complexity as the time complexity will depend on the range of size being included to allow memory for the stored summation of the operations.
L:	Although this approach is better than the brute force attempts to try all the possible combinations of symbols with integers, it is important to consider that there are better methods and options such as Dynamic Programming which optimize the solution.

DUKES -7- STEPS:
STEP 1: Given an array list of integers [1, 1, 1, 1, 1] and a given target of 3, with a combination of symbols -, and + before the integers in the array list, the program must equal to the target, and all the possible combinations must be returned in a form of an integer.
STEP 2: The algorithm will go through the integers within the array, assign them a symbol and keep track of the summation of the numbers to compare to the given target, as it goes one by one from left to right.
STEP 3: Patterns include incrementing the index location and adding the pervious numbers to the upcoming numbers in a strategy method that simulates memorization.
STEP 4/STEP 5: The program takes the array of integers and the target as main parameters, it then assigns a symbol to the numbers and adds then as it increments returning a one if the summation is equal and a 0 if it isn’t. 
STEP 6: [1, 1, 1, 1, 1] -> 5 (ALL POSSIBLE COMBINATIONS)
-1+1+1+1+1 = 3
+1-1+1+1+1 = 3
+1+1-1+1+1 = 3
+1+1+1-1+1 = 3
+1+1+1+1-1 = 3
STEP 7: Failed Test Case: [1, 1, 1] given target 5, can’t be resolved cause there isn’t enough integers to add up to the value 5 with symbols – and +.
