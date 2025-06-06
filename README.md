🚀 Queue Implementation Using Singly Linked List in C
This C program demonstrates how to implement a Queue (FIFO) data structure using a Singly Linked List (SLL). It supports dynamic memory allocation and includes basic operations such as:

Insertion (Enqueue)

Deletion (Dequeue)

Display Queue Elements

📁 Features
Dynamic Queue: Uses malloc() to allocate memory, allowing for flexible queue size.

Linked List-Based: No need for predefined array size, avoids overflow unless system memory is full.

Error Handling: Handles both queue overflow and underflow gracefully.

Interactive Console Menu: Allows users to perform multiple operations interactively.

📌 Functions
void insertq(struct Queue **front, struct Queue **rear, int x);
Inserts an element at the rear of the queue.

int removeq(struct Queue **front, struct Queue **rear);
Removes an element from the front of the queue and returns it.

void display(struct Queue *p);
Displays all elements in the queue.

🛠 Sample Run
Enter the option from following 1.Insert 2.Remove 3.Display Queue
Enter your option 1
Enter a number to be inserted 10
Do you want to continue (y/n) y
Enter your option 1
Enter a number to be inserted 20
Do you want to continue (y/n) y
Enter your option 3
The Queue Elements are
10
20
Do you want to continue (y/n) n
Thank You
📌 Usage
Compile and run with:

