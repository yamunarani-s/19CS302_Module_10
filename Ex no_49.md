# EX 49 C function to search an element in the doubly linked list.
## DATE:19/05/25
## AIM:
To write a C function to search an element in the doubly linked list.

## Algorithm
1. Analyze the question
2. Follow the algorithm
3. Try the code
4.  Check for error
5. Run & Display the output
   
## Program:
```
/*
C function to search an element in the doubly linked list.

Developed by: 
RegisterNumber:  
*/
```
#include <stdio.h>
#include <stdlib.h>

typedef struct Node {
    int data;
    struct Node *prev;
    struct Node *next;
} Node;

Node* search(Node *head, int key) {
    Node *temp = head;
    while (temp != NULL) {
        if (temp->data == key)
            return temp;
        temp = temp->next;
    }
    return NULL;
}



## Output:

Element 20 found.

## Result:
Thus the program was executed and the output was verified successfully.
