Download Link: https://assignmentchef.com/product/solved-cs2040s-tutorial-9
<br>
<strong>Problem 1.         </strong>(Kahn’s Algorithm)

You have seen in lecture how to implement Kahn’s Algorithm in <em>O</em>(<em>E </em>log<em>V </em>) using a priority queue. Now, implement Kahn’s Algorithm in <em>O</em>(<em>V </em>+ <em>E</em>).

<strong>Problem 2.           </strong>(Longest Path in a Directed Acyclic Graph)

To find the longest path in a directed acyclic graph, one could negate the weight of the edges and directly apply a shortest path algorithm. The shortest path in this negated graph would then be the longest path in the original graph.

Instead of negating the weights of the edges, one could also modify the relax function. Write down this modified relax function.

<strong>Problem 3.         </strong>(Shortest Path in a Tree)

What if you want to find shortest path in an undirected rooted tree? What is the simplest way to find a good order to relax the edges?

<h1>1         Problems</h1>

<strong>Problem 4.         </strong>(Exploring all Paths)

Relevant Kattis Problem: https://open.kattis.com/problems/beepers

Sometimes, it seems like a good solution to a graph problem is to explore all possible paths in the graph. Starting from some vertex <em>s</em>, we explore all possible paths to some destination <em>t</em>, and examine the resulting cost. For example, imagine you have a highway road map, with tolls specified along various roads. You want to find the route with the smallest cumulative toll.

Perhaps we can explore all possible routes using a cleverly modified DFS or BFS? Why is this a bad idea? Draw a graph in which exploring all possible paths from <em>s </em>to <em>t </em>will not work well.

<strong>Problem 5. </strong>Overcooked Relevant Kattis Problems:

https://open.kattis.com/problems/pickupsticks https://open.kattis.com/problems/reactivity https://open.kattis.com/problems/easyascab

<strong>Figure 1: </strong><em>Overcooked. </em>(Matthew Ng Zhen Rui)

After many years of playing Overcooked, you finally have fulfilled your dream of opening your own restaurant. On the opening day you are given a list of reviewers that will be coming. You want to ensure that they are served in a timely manner so that they leave good reviews for your restaurant.

You want to determine in what order you want to serve your dishes. There are a lot of dishes to serve out but you can’t serve them in any order. Given a set of <em>n </em>dishes you know certain foods must be served after another (for example, you will serve appetizers like mushroom soup before the main course like filet mignon). Given a list of <em>n </em>dishes as well as <em>k </em>constraints on relative orderings of the dishes, output a valid sequence in which the dishes can be served. You may assume that such an ordering always exists.

In addition, you want to ensure that if there are multiple possible ways to order the dishes, you output the one which is <em>lexicographically </em>the smallest (So that it looks presentable on a menu).

As an example, let’s say there were 4 dishes: Garlic Bread, Mushroom Soup, Filet Mignon Burger and Banana Split. Now, if we are given the constraints as follows:

Garlic Bread must be served before Filet Mignon Burger

Mushroom Soup must be served before Filet Mignon Burger

Banana Split must be served after everything else

These give the following valid orders:

Garlic Bread, Mushroom Soup, Filet Mignon Burger, Banana Split

Mushroom Soup, Garlic Bread, Filet Mignon Burger, Banana Split

However, we will want to output the former, since it is lexicographically smaller than the latter (since Garlic Bread is alphabetically before Mushroom Soup).

<em>Optional : In order to protect against potential modifications of the order of dishes being served, you also want to check whether any valid ordering of the dishes is unique. Note that if this is the case then the valid order will instantly be the smallest lexicographically as well. How would you do this?</em>

<strong>Problem 6.        </strong>(Tourism)

Relevant Kattis Problem: https://open.kattis.com/problems/maximizingwinnings

You are off to travel the world in your trusty old beat-up Chevrolet. You have a map, a full tank of gas, and you are off. Just as soon as you figure out where you want to go. Looking at the map, you notice that some roads look very appealing: they will make you happy with their winding curves and beautiful scenery. Other roads look boring and depressing: they will make you unhappy with their long straight unwavering vistas.

Being methodical, you assign each road a value (some positive, some negative) as to how much happiness driving that road will bring. You may assume that the happiness is spread out uniformly over the entire road, for every road on your map. You may also assume that every road spans a distance of 1 kilometer. Pondering a moment, you realize that you can only travel a fixed number <em>k </em>kilometers. Starting from here on the map, find the destination that is at most <em>k </em>kilometers away that will bring you the most net happiness. (Write out your algorithm carefully. There is a subtle issue here!)

<strong>Problem 7.        </strong>(Spaceship Troubles)

The wonderful, fantastic product made by the Whoozit Company is a newfangled spaceship with a fancy warp drive. Now, warp drives are not quite as useful as you might think: they only let you travel between a set of fixed locations, along fixed (directed) paths. One of the possible jobs at Whoozit Company is <em>Guinea Pig</em>, and you have just been promoted. They hand you a map of the universe (complete with locations and directed paths), put you in the new spaceship, and off you go.

At first, everything works fine. You start off at the little dot marked “Earth”, chose one of the neighboring dots (“Alpha Centauri”, at only 4.24 light years away), and hit the big green <em>GO </em>button. Whoosh. You made it in one piece! Wow, each hop takes exactly 1 minute, regardless of how far you go!

But then a little red light starts blinking, and the screen reads out the following error message: Error: your warp drive is now broken. Abort, Retry, Fail? After some fussing with the computer, you discover that the warp drive still works, but it has the following limitation: it can only jump five hops at a time. You cannot just jump to a neighbor of Alpha Centauri; you have to jump directly to some location that is exactly five hops away.

Describe an algorithm that will get you from Alpha Centauri back to Earth in minimum number of hops, explain why it works, and give its efficiency.

<strong>Problem 8.          </strong>(Internet Routing) <strong>(Optional)</strong>

https://open.kattis.com/problems/shortestpath3

<strong>Figure 2: </strong>A Network Diagram

Imagine a hypothetical world where there are a set of computers connected by wires called <em>the internet</em>. Each of these computers has a unique address that is used for routing. (We might call this an IP address.) Each computer needs to maintain a routing table, i.e., a table that maps destination addresses to the next hop of the route. For example, if computer <em>X </em>has links to computers <em>A</em>, <em>B</em>, and <em>C</em>, and if it receives a message for destination <em>D</em>, the routing table might specify that that message should be forwarded to <em>B</em>. The goal is to forward the message to the destination using the minimum number of hops possible.

<strong>Problem 8.a. </strong>Collectively, the routing tables specify shortest path trees. How might you use <strong>Bellman-Ford </strong>to construct the routing tables?

<strong>Problem 8.b. </strong>Now imagine we want to construct the routing tables in parallel. That is, imagine that all the computers can send information to their neighbors at the same time. How might you implement a relax step so that all the computers can run it at once? Will that work? (Why or why not?) How long will the entire Bellman-Ford execution take?

<strong>Problem 8.c. </strong>Imagine that the computers run Bellman-Ford relax rounds forever. E.g., every one minute they send their vector of estimates to their neighbors and update their routing tables as necessary. Assume that a new edge is added to the network, e.g., <em>A </em>and <em>B </em>were not neighbors and now they are. Will the ongoing algorithm fix the estimates? If so, how long will it take? If not, what needs to be done to make it work?

<strong>Problem 8.d. </strong>Imagine that the computers run Bellman-Ford relax rounds forever. E.g., every one minute they send their vector of estimates to their neighbors and update their routing tables as necessary. Assume that one edge fails in the network, e.g., <em>A </em>and <em>B </em>were neighbors and now they are not anymore. Will the ongoing algorithm fix the estimates? If so, how long will it take? If not, what needs to be done to make it work?