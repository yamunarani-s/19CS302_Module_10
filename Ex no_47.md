# EX 47 C function to insert a node in a linked list.
## DATE: 19/05/25
## AIM:
To write a C function to insert a node in a linked list.

## Algorithm
1. Analyze the question
2. Follow the algorithm
3. Try the code
4.  Check for error
5. Run & Display the output


## Program:
```
/*
C function to insert a node in a linked list.

Developed by: 
RegisterNumber:  
*/
```
#include <stdio.h>
#include <stdlib.h>

typedef struct Node {
    int data;
    struct Node *next;
} Node;

// Insert node at the end of the linked list
void insertNode(Node **head, int value) {
    Node *newNode = (Node *)malloc(sizeof(Node));
    newNode->data = value;
    newNode->next = NULL;

    if (*head == NULL) {
        *head = newNode;
    } else {
        Node *temp = *head;
        while (temp->next != NULL) {
            temp = temp->next;
        }
        temp->next = newNode;
    }
}

// Function to display the linked list (for testing)
void displayList(Node *head) {
    Node *temp = head;
    while (temp != NULL) {
        printf("%d -> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

int main() {
    Node *head = NULL;

    insertNode(&head, 10);
    insertNode(&head, 20);
    insertNode(&head, 30);

    displayList(head);

    return 0;
}


## Output:
10 -> 20 -> 30 -> NULL


## Result:
Thus the program was executed and the output was verified successfully.
