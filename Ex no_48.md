# EX 48 C functions to perform all basic operations in Doubly Linked List.
## DATE:19/05/25
## AIM:
To write a C functions to perform all basic operations in Doubly Linked List.

## Algorithm
1. Analyze the question
2. Follow the algorithm
3. Try the code
4.  Check for error
5. Run & Display the output

## Program:
```
/*
C functions to perform all basic operations in Doubly Linked List.

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

// Insert at the front
void insertFront(Node **head, int value) {
    Node *newNode = (Node *)malloc(sizeof(Node));
    newNode->data = value;
    newNode->prev = NULL;
    newNode->next = *head;

    if (*head != NULL)
        (*head)->prev = newNode;
    *head = newNode;
}

// Insert at the end
void insertEnd(Node **head, int value) {
    Node *newNode = (Node *)malloc(sizeof(Node));
    newNode->data = value;
    newNode->next = NULL;

    if (*head == NULL) {
        newNode->prev = NULL;
        *head = newNode;
        return;
    }

    Node *temp = *head;
    while (temp->next != NULL)
        temp = temp->next;

    temp->next = newNode;
    newNode->prev = temp;
}

// Delete a node by value (first occurrence)
void deleteNode(Node **head, int value) {
    if (*head == NULL) return;

    Node *temp = *head;

    while (temp != NULL && temp->data != value)
        temp = temp->next;

    if (temp == NULL) return; // Not found

    if (temp->prev != NULL)
        temp->prev->next = temp->next;
    else
        *head = temp->next;

    if (temp->next != NULL)
        temp->next->prev = temp->prev;

    free(temp);
}

// Display list forward
void displayForward(Node *head) {
    Node *temp = head;
    printf("Forward: ");
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}

// Display list backward
void displayBackward(Node *head) {
    if (head == NULL) return;
    Node *temp = head;
    while (temp->next != NULL)
        temp = temp->next;

    printf("Backward: ");
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->prev;
    }
    printf("\n");
}

int main() {
    Node *head = NULL;

    insertEnd(&head, 10);
    insertEnd(&head, 20);
    insertFront(&head, 5);

    displayForward(head);
    displayBackward(head);

    deleteNode(&head, 20);

    displayForward(head);
    displayBackward(head);

    return 0;
}


## Output:

Forward: 5 10 20 
Backward: 20 10 5 
Forward: 5 10 
Backward: 10 5 

## Result:
Thus the program was executed and the output was verified successfully.
