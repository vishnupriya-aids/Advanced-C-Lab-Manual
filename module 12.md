

EXP NO 26: C PROGRAM TO DISPLAY STACK ELEMENTS USING LINKED LIST.
Aim:
To write a C program to display stack elements using linked list.


Algorithm:
1.	Define a structure Node with two members: data to store the integer value and next to point to the next node in the linked list.
2.	Declare a global variable head representing the starting node of the linked list.
3.	Define a function display to print the elements of the linked list.
4.	Declare a pointer p and initialize it with the head of the linked list.
5.	Use a while loop to traverse the linked list:
6.	Print the data of the current node.
7.	Move to the next node using the next pointer.
 
Program:

#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node *next;
};

struct Node *head = NULL;

void display()
{
    struct Node *p = head;

    if (p == NULL)
    {
        printf("Stack is empty.\n");
        return;
    }

    printf("Stack elements are:\n");

    while (p != NULL)
    {
        printf("%d\n", p->data);
        p = p->next;
    }
}

int main()
{
    struct Node *p1, *p2, *p3;

    p1 = (struct Node *)malloc(sizeof(struct Node));
    p2 = (struct Node *)malloc(sizeof(struct Node));
    p3 = (struct Node *)malloc(sizeof(struct Node));

    p1->data = 10;
    p1->next = p2;

    p2->data = 20;
    p2->next = p3;

    p3->data = 30;
    p3->next = NULL;

    head = p3;

    display();

    return 0;
}


Output:

<img width="851" height="258" alt="image" src="https://github.com/user-attachments/assets/044e985d-734e-44b9-abd0-dbdc10c3d914" />



Result:
Thus, the program to display stack elements using linked list is verified successfully. 



EXP.NO 27: C PROGRAM TO POP AN ELEMENT FROM THE GIVEN STACK USING 
LINKED LIST.
Aim:
To write a C program to pop an element from the given stack using liked list.

Algorithm:
1.	Check for Empty Stack
2.	If head is equal to NULL, Print "Stack is empty."
3.	Else Proceed to the next step.
4.	Set head to point to the next node in the stack.
 
Program:

#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node *next;
};

struct Node *head = NULL;

void push(int value)
{
    struct Node *newNode;

    newNode = (struct Node *)malloc(sizeof(struct Node));

    newNode->data = value;
    newNode->next = head;
    head = newNode;
}

void pop()
{
    struct Node *temp;

    if (head == NULL)
    {
        printf("Stack is empty.\n");
        return;
    }

    temp = head;

    printf("Popped element: %d\n", head->data);

    head = head->next;

    free(temp);
}

void display()
{
    struct Node *temp = head;

    printf("Stack elements after pop:\n");

    while (temp != NULL)
    {
        printf("%d\n", temp->data);
        temp = temp->next;
    }
}

int main()
{
    push(10);
    push(20);
    push(30);

    printf("Stack before pop:\n");
    display();

    printf("\n");

    pop();

    printf("\n");
    display();

    return 0;
}


Output:

<img width="847" height="482" alt="image" src="https://github.com/user-attachments/assets/fe173779-7571-412f-9ac9-ba0c4e8378ff" />



Result:
Thus, the program to pop an element from the given stack using liked list is verified successfully.

 
EXP NO:28 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING LINKED LIST.
Aim:
To write a C program to display queue elements using linked list.
Algorithm:
1.	Check if Queue is Empty
2.	Display Queue Elements
3.	Print the data of the current node pointed to by front
4.	Update front to point to the next node.
5.	End the display function.
 
Program:


#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node *next;
};

struct Node *front = NULL;
struct Node *rear = NULL;

void enqueue(int value)
{
    struct Node *newNode;

    newNode = (struct Node *)malloc(sizeof(struct Node));

    newNode->data = value;
    newNode->next = NULL;

    if (front == NULL)
    {
        front = newNode;
        rear = newNode;
    }
    else
    {
        rear->next = newNode;
        rear = newNode;
    }
}

void display()
{
    struct Node *temp = front;

    if (front == NULL)
    {
        printf("Queue is empty.\n");
        return;
    }

    printf("Queue elements are:\n");

    while (temp != NULL)
    {
        printf("%d ", temp->data);
        temp = temp->next;
    }
}

int main()
{
    enqueue(10);
    enqueue(20);
    enqueue(30);
    enqueue(40);

    display();

    return 0;
}

Output:

<img width="855" height="301" alt="image" src="https://github.com/user-attachments/assets/09569129-7647-4779-9318-c7607b15bbbf" />


Result:
Thus, the program to display queue elements using linked list is verified successfully.


 
EXP NO:29 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING LINKED LIST

Aim:
To write a C program to insert elements in queue using linked list

Algorithm:
1.	Allocate Memory for New Node
2.	Set Data and Next Pointer
3.	Check if Queue is Empty
4.	Set both front and rear to point to the new node p.
5.	Set the next pointer of the current rear to point to the new node p.
6.	End of Enqueue Operation
 
Program:
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node *next;
};

struct Node *front = NULL;
struct Node *rear = NULL;

void enqueue(int value)
{
    struct Node *p;

    p = (struct Node *)malloc(sizeof(struct Node));

    p->data = value;
    p->next = NULL;

    if (front == NULL)
    {
        front = p;
        rear = p;
    }
    else
    {
        rear->next = p;
        rear = p;
    }
}

void display()
{
    struct Node *temp = front;

    while (temp != NULL)
    {
        printf("%d ", temp->data);
        temp = temp->next;
    }
}

int main()
{
    int n, i, value;

    printf("Enter the number of elements: ");
    scanf("%d", &n);

    for (i = 0; i < n; i++)
    {
        printf("Enter element %d: ", i + 1);
        scanf("%d", &value);

        enqueue(value);
    }

    printf("\nQueue after insertion:\n");
    display();

    return 0;
}

Output:

<img width="855" height="387" alt="image" src="https://github.com/user-attachments/assets/015fd0af-39c3-4d44-b8c1-b2b22e0b8655" />




Result:
Thus, the program to insert elements in queue using linked list is verified successfully.



EXP NO:30 C FUNCTION TO FIND THE PEEK OF QUEUE USING LINKED LIST.


Aim:

The aim of this function is to retrieve the "peek" (the front element) of a queue implemented using a linked list

Algorithm:

1.	Check if the queue is empty:
o	If the queue is empty (i.e., the front pointer is NULL), return an error or a message indicating that the queue is empty.
2.	Access the front element:
o	If the queue is not empty, return the data stored in the front node of the linked list (i.e., the element at the head of the queue).

Program:
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node *next;
};

struct Node *front = NULL;
struct Node *rear = NULL;

void enqueue(int value)
{
    struct Node *newNode;

    newNode = (struct Node *)malloc(sizeof(struct Node));

    newNode->data = value;
    newNode->next = NULL;

    if (front == NULL)
    {
        front = newNode;
        rear = newNode;
    }
    else
    {
        rear->next = newNode;
        rear = newNode;
    }
}

int peek()
{
    if (front == NULL)
    {
        return -1;
    }

    return front->data;
}

int main()
{
    int value;

    enqueue(10);
    enqueue(20);
    enqueue(30);
    enqueue(40);

    value = peek();

    if (value == -1)
    {
        printf("Queue is empty.");
    }
    else
    {
        printf("Peek element of the queue = %d", value);
    }

    return 0;
}

Output:

<img width="832" height="296" alt="image" src="https://github.com/user-attachments/assets/37e844a3-04ca-4d50-b83c-7a87ba813101" />



Result:

Thus, the program to retrieve the "peek" (the front element) of a queue implemented using a linked list is verified successfully.


