# Interview Questions & Answers

## Data Structures

### Q1: What are the main differences between arrays and linked lists?

**A:**  
- **Arrays** provide O(1) access to elements by index but have fixed size (in some languages) and costly insertions/deletions (O(n)) except at the end.  
- **Linked lists** consist of nodes with pointers to next (and possibly previous) nodes, allowing O(1) insertions/deletions if you have the reference, but O(n) access by index since traversal is required.

---

### Q2: When would you use a hash table over a tree?

**A:**  
- Use a **hash table** when you need average O(1) lookup, insertion, and deletion, and order doesn't matter.  
- Use a **tree** (like a balanced BST) when you need ordered data, range queries, or guaranteed O(log n) worst-case performance.

---

### Q3: Explain how a stack and queue differ.

**A:**  
- A **stack** is LIFO (Last In, First Out); elements are added and removed from the top. Used for backtracking, function calls, etc.  
- A **queue** is FIFO (First In, First Out); elements are added at the rear and removed from the front. Used in scheduling, buffering, BFS traversal, etc.

---

## Algorithms

### Q4: Describe the difference between BFS and DFS traversals on a graph.

**A:**  
- **BFS (Breadth-First Search):** Explores neighbors level by level using a queue; useful for shortest path in unweighted graphs.  
- **DFS (Depth-First Search):** Explores as deep as possible along one branch before backtracking using recursion or a stack.

---

### Q5: What are inorder, preorder, and postorder traversals in a binary tree?

**A:**  
- **Inorder:** Left subtree → Node → Right subtree (useful for BSTs to get sorted order).  
- **Preorder:** Node → Left subtree → Right subtree (used to copy tree or serialize).  
- **Postorder:** Left subtree → Right subtree → Node (used for deleting or evaluating expression trees).

---

### Q6: Explain quicksort and its average time complexity.

**A:**  
- Quicksort is a divide-and-conquer sorting algorithm that picks a pivot, partitions the array around it, and recursively sorts partitions.  
- Average time complexity is O(n log n), but worst-case is O(n²) if pivot choices are poor.

---

## Object-Oriented Programming Concepts

### Q7: What is encapsulation and why is it important?

**A:**  
- Encapsulation hides internal object details and exposes only necessary interfaces, preventing unintended interference and misuse. It improves modularity and maintainability.

---

### Q8: Explain polymorphism with an example.

**A:**  
- Polymorphism allows objects of different classes to be treated as instances of a common superclass/interface, with method calls resolved at runtime.  
- Example: Different subclasses override a `draw()` method; calling `draw()` on a superclass reference invokes the subclass implementation.

---

### Q9: How does inheritance promote code reuse?

**A:**  
- Inheritance allows a class to derive from another, inheriting fields and methods, avoiding duplication and enabling extension/customization.

---

### Q10: What is abstraction in OOP?

**A:**  
- Abstraction means exposing only relevant details and hiding complexity, often through abstract classes or interfaces to define contracts without implementation.

---

## Big-O Complexity

### Q11: What is the time complexity of accessing an element in an array? What about a linked list?

**A:**  
- Array: O(1) time for direct index access.  
- Linked list: O(n) time because you must traverse nodes to reach the element.

---

### Q12: Compare the time complexities of searching in a balanced binary search tree vs a hash table.

**A:**  
- Balanced BST: O(log n) for search, insertion, and deletion.  
- Hash Table: O(1) average case for search, insertion, and deletion; worst case O(n) if many collisions.

---

### Q13: Explain the difference between time and space complexity.

**A:**  
- Time complexity measures the number of operations relative to input size.  
- Space complexity measures the amount of memory used relative to input size.

---

### Q14: What is the Big-O complexity of traversing all nodes in a tree?

**A:**  
- O(n), where n is the number of nodes, because each node is visited once.

---

## Additional Questions & Answers

### Q15: How does a doubly linked list differ from a singly linked list? What are its advantages?

**A:**  
- A **doubly linked list** has nodes with pointers to both the next and previous nodes, allowing traversal in both directions.  
- Advantages include easier deletion of nodes when given a pointer to the node (no need to traverse to find previous), and backward traversal.  
- Slightly more memory overhead due to storing two pointers per node.

---

### Q16: What data structure would you use to implement a LRU (Least Recently Used) cache? Why?

**A:**  
- Use a combination of a **hash table** for O(1) access and a **doubly linked list** to track usage order efficiently.  
- The hash table stores keys and pointers to nodes in the linked list, and the list maintains the order of usage for eviction.

---

### Q17: Explain the difference between depth-first and breadth-first search in terms of their space complexity.

**A:**  
- DFS space complexity is O(h), where h is the maximum depth of the search tree (stack space).  
- BFS space complexity is O(w), where w is the maximum width of the tree (queue space), which can be much larger than h in wide graphs.

---

### Q18: What is tail recursion? Why is it important?

**A:**  
- Tail recursion is a form of recursion where the recursive call is the last operation in the function.  
- Important because some languages optimize tail calls to prevent stack overflow by reusing the current stack frame.

---

### Q19: What is method overriding, and how does it differ from method overloading?

**A:**  
- **Overriding:** A subclass provides its own implementation of a method defined in its superclass, enabling polymorphic behavior.  
- **Overloading:** Multiple methods with the same name but different parameter types or counts in the same scope.

---

### Q20: Describe what a hash collision is and how it can be resolved.

**A:**  
- A **hash collision** occurs when two different keys produce the same hash value.  
- Common resolution methods:  
  - **Chaining:** Store collided elements in a linked list or bucket.  
  - **Open addressing:** Find another open slot in the hash table using probing.

---

### Q21: What are abstract classes and interfaces? How do they differ?

**A:**  
- **Abstract classes:** Can provide both method declarations and implementations; classes can inherit one abstract class.  
- **Interfaces (protocols in Swift):** Define only method/property signatures; classes or structs conform to multiple protocols.  
- Abstract classes can hold state; interfaces usually cannot.

---

### Q22: What is the difference between composition and inheritance? When would you prefer one over the other?

**A:**  
- **Inheritance** models "is-a" relationships; it enables code reuse by deriving classes.  
- **Composition** models "has-a" relationships; objects are composed of other objects to reuse functionality.  
- Prefer composition to reduce tight coupling and increase flexibility; inheritance is suitable for clear hierarchical relationships.

---

### Q23: What is the difference between a queue and a deque?

**A:**  
- A **queue** allows insertion at the rear and removal from the front (FIFO).  
- A **deque** (double-ended queue) allows insertion and removal at both front and rear ends.

---

### Q24: Explain binary search and its prerequisites.

**A:**  
- Binary search efficiently finds an element in a **sorted array** by repeatedly dividing the search interval in half.  
- Time complexity: O(log n).  
- Prerequisites: The array must be sorted; random access (array or similar structure) is needed.

---

### Q25: How does encapsulation differ from abstraction?

**A:**  
- **Encapsulation** is about hiding the internal state and requiring all interaction to be performed through an object's methods.  
- **Abstraction** focuses on exposing only relevant features and hiding complex details from the user.  
- Encapsulation is a means to achieve abstraction.

---

### Q26: What is the difference between a shallow copy and a deep copy?

**A:**  
- **Shallow copy:** Copies object references, so both copies share the same nested objects.  
- **Deep copy:** Copies the object and all objects it references recursively, creating fully independent copies.

---

### Q27: How do you detect a cycle in a linked list?

**A:**  
- Use Floyd's Tortoise and Hare algorithm:  
  - Use two pointers moving at different speeds; if they meet, a cycle exists.  
- Time complexity: O(n), space: O(1).

---

### Q28: What are the time complexities for insertion, deletion, and search in a balanced binary search tree?

**A:**  
- All three operations typically run in O(log n) time due to the balanced structure maintaining logarithmic height.

---

### Q29: What is a sentinel node in a linked list?

**A:**  
- A sentinel node is a dummy node used at the beginning or end of a linked list to simplify edge cases during insertion and deletion.

---

### Q30: Explain the difference between static and dynamic dispatch.

**A:**  
- **Static dispatch:** Method calls are resolved at compile-time (e.g., final methods, structs).  
- **Dynamic dispatch:** Method calls are resolved at runtime, enabling polymorphism (e.g., class methods, protocols with class constraints).

--- 