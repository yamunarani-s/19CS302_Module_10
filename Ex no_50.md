# EX 50 C function to delete a node from a Doubly Linked List at the beginning of the list.
## DATE: 19/05/25
## AIM:
To write a C function to delete a node from a Doubly Linked List at the beginning of the list.

## Algorithm
1. Analyze the question
2. Follow the algorithm
3. Try the code
4. Check for error
5. Run & Display the output

## Program:
```
/*
C function to delete a node from a Doubly Linked List at the beginning of the list.

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

void deleteAtBeginning(Node **head) {
    if (*head == NULL) {
        printf("List is empty\n");
        return;
    }

    Node *temp = *head;
    *head = temp->next;

    if (*head != NULL)
        (*head)->prev = NULL;

    free(temp);
}

## Output:
Original list: 10 20 
After deleting at beginning: 20 
After deleting at beginning again: 
List is empty



## Result:
Thus the program was executed and the output was verified successfully.
