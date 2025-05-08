EXP NO:16 C PROGRAM TO SEARCH A GIVEN ELEMENT IN THE GIVEN LINKED LIST.
Aim:
To write a C program to search a given element in the given linked list.

Algorithm:
1.	Define the structure for a node in a linked list.
2.	Define the search function to find a specific character in the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the search function and perform other linked list operations as needed.
 
Program:

```
#include <stdio.h>
#include <stdlib.h>


struct Node {
    int data;
    struct Node* next;
};


int search(struct Node* head, int key) {
    struct Node* current = head;
    int position = 0;
    
    
    while (current != NULL) {
        if (current->data == key) {
            return position;  
        }
        current = current->next;
        position++;
    }
    
    return -1;  // Return -1 if element is not found
}


void insert(struct Node** head, int new_data) {
    struct Node* new_node = (struct Node*)malloc(sizeof(struct Node));
    new_node->data = new_data;
    new_node->next = *head;
    *head = new_node;
}

void display(struct Node* head) {
    struct Node* current = head;
    while (current != NULL) {
        printf("%d -> ", current->data);
        current = current->next;
    }
    printf("NULL\n");
}

int main() {
    struct Node* head = NULL;
    
    insert(&head, 10);
    insert(&head, 20);
    insert(&head, 30);
    insert(&head, 40);
    
    printf("Linked List: ");
    display(head);
    
   
    int key = 30;
    int result = search(head, key);
    
    if (result != -1) {
        printf("Element %d found at position %d.\n", key, result);
    } else {
        printf("Element %d not found in the list.\n", key);
    }
    
    return 0;
}

```

Output:
![image](https://github.com/user-attachments/assets/4a68459d-0849-42cb-81ad-9218d5d5be73)




Result:
Thus, the program to search a given element in the given linked list is verified successfully.


 
EXP NO:17  PROGRAM TO INSERT A NODE IN A LINKED LIST.
Aim:
To write a C program to insert a node in a linked list.
Algorithm:
1.	Define the structure for a node in a linked list
2.	Define the insert function to insert a new node with character data at the end of the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the insert function and perform other linked list operations as needed.
 
Program:

```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

void insert(struct Node** head, int new_data) {
   
    struct Node* new_node = (struct Node*)malloc(sizeof(struct Node));
    struct Node* last = *head;  
    new_node->data = new_data;
    new_node->next = NULL;

    if (*head == NULL) {
        *head = new_node;
        return;
    }

   
    while (last->next != NULL) {
        last = last->next;
    }

    
    last->next = new_node;
}


void display(struct Node* head) {
    struct Node* current = head;
    while (current != NULL) {
        printf("%d -> ", current->data);
        current = current->next;
    }
    printf("NULL\n");
}

int main() {
    struct Node* head = NULL;

    insert(&head, 10);
    insert(&head, 20);
    insert(&head, 30);
    insert(&head, 40);

  
    printf("Linked List: ");
    display(head);

    return 0;
}

```

Output:

![image](https://github.com/user-attachments/assets/a6347470-5d5f-4f9d-9ff3-923a4d0e2d98)


 
Result:
Thus, the program to insert a node in a linked list is verified successfully.


 
EXP NO:18 C PROGRAM TO TRAVERSE A DOUBLY LINKED LIST
Aim:
To write a C program to traverse a doubly linked list.

Algorithm:
1.	Initialize a temporary pointer (temp) to the head of the list.
2.	Use a while loop to traverse the list until the end (temp == NULL) is reached.
3.	Inside the loop, print the data of the current node.
4.	Move to the next node by updating the temp pointer to point to the next node (temp = temp->next).
 
Program:
```
#include <stdio.h>
#include <stdlib.h>

// Structure to represent a node in a doubly linked list
struct Node {
    int data;
    struct Node* next;
    struct Node* prev;
};

// Function to traverse the doubly linked list in forward direction
void traverseForward(struct Node* head) {
    struct Node* temp = head;
    
    // Traverse the list from head to end
    while (temp != NULL) {
        printf("%d <-> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

// Function to insert a new node at the end of the doubly linked list
void insert(struct Node** head, int new_data) {
    struct Node* new_node = (struct Node*)malloc(sizeof(struct Node));
    struct Node* last = *head;

    new_node->data = new_data;
    new_node->next = NULL;

    // If the list is empty, make the new node the head
    if (*head == NULL) {
        new_node->prev = NULL;
        *head = new_node;
        return;
    }

    // Otherwise, traverse to the last node
    while (last->next != NULL) {
        last = last->next;
    }

    // Insert the new node at the end
    last->next = new_node;
    new_node->prev = last;
}

// Function to display the list in reverse (traverse backward)
void traverseBackward(struct Node* head) {
    struct Node* temp = head;

    // Traverse to the last node first
    while (temp != NULL && temp->next != NULL) {
        temp = temp->next;
    }

    // Traverse the list backward
    while (temp != NULL) {
        printf("%d <-> ", temp->data);
        temp = temp->prev;
    }
    printf("NULL\n");
}

int main() {
    struct Node* head = NULL;

    // Inserting some elements into the doubly linked list
    insert(&head, 10);
    insert(&head, 20);
    insert(&head, 30);
    insert(&head, 40);

    // Display the list in forward direction
    printf("Forward Traversal: ");
    traverseForward(head);

    // Display the list in reverse direction
    printf("Backward Traversal: ");
    traverseBackward(head);

    return 0;
}

```
Output:

![image](https://github.com/user-attachments/assets/bd2e0a2b-7574-44a2-8741-dbdcd3e65e11)



Result:
Thus, the program to traverse a doubly linked list is verified successfully. 



EXP NO:19 C PROGRAM TO INSERT AN ELEMENT IN DOUBLY LINKED LIST
Aim:
To write a C program to insert an element in doubly linked list

Algorithm:
1.	Create a new node (newNode) and allocate memory for it.
2.	Set the data of the new node to the provided value.
3.	If the list is empty, set the new node as the head.
4.	If the list is not empty, traverse the list to find the last node.
5.	Set the new node's prev pointer to the last node and update the last node's next pointer to the new node.
 
Program:

```
#include <stdio.h>
#include <stdlib.h>


struct Node {
    int data;
    struct Node* next;
    struct Node* prev;
};


void insert(struct Node** head, int new_data) {
   
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    
    
    newNode->data = new_data;
    newNode->next = NULL;  // The new node will be the last node, so next is NULL

        newNode->prev = NULL;  // As it is the only node, prev is NULL
        *head = newNode;  // Make the new node the head
        return;
    }

    
    struct Node* last = *head;
    while (last->next != NULL) {
        last = last->next;  // Traverse to the last node
    }

   
    newNode->prev = last;
  
    last->next = newNode;
}


void display(struct Node* head) {
    struct Node* temp = head;
    
    
    while (temp != NULL) {
        printf("%d <-> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

int main() {
    struct Node* head = NULL;  // Initially, the list is empty

    
    insert(&head, 10);
    insert(&head, 20);
    insert(&head, 30);
    insert(&head, 40);

    
    printf("Doubly Linked List: ");
    display(head);

    return 0;
}

```

Output:

![image](https://github.com/user-attachments/assets/cbe40dd3-6768-4680-a10f-e8ee7559cad8)



Result:
Thus, the program to insert an element in doubly linked list is verified successfully.




EXP NO:20 C FUNCTION TO DELETE A GIVEN ELEMENT IN THE GIVEN LINKED LIST

Aim:
To write a C function that deletes a given element from a linked list.

Algorithm:
1.	Check if the Linked List is Empty:
o	If the head of the linked list is NULL, print a message indicating the list is empty and exit the function.
2.	Traverse the Linked List:
o	Start from the head node and iterate through the list to find the node that contains the given element (data).
3.	Handle Deletion of the First Node:
o	If the element to be deleted is found in the head node:
	Update the head of the linked list to point to the next node (i.e., head = head->next).
	Free the memory allocated to the node to be deleted.
	Exit the function.
4.	Traverse and Delete from the Middle or End:
o	If the element is not in the head node, continue traversing the list by checking each node’s next pointer.
o	When the node with the element is found, update the previous node’s next pointer to point to the next node of the node to be deleted (prev->next = current->next).
o	Free the memory allocated to the node to be deleted.
5.	Handle the Case when the Element is Not Found:
o	If the element is not found in any node, print a message indicating the element is not present in the list.
6.	End the Function.


Program:

```
#include <stdio.h>
#include <stdlib.h>


struct Node {
    int data;
    struct Node* next;
};


void deleteElement(struct Node** head, int key) {
    // Check if the list is empty
    if (*head == NULL) {
        printf("The list is empty.\n");
        return;
    }

   
    if ((*head)->data == key) {
        struct Node* temp = *head;
        *head = (*head)->next;  // Update head to the next node
        free(temp);  // Free the memory of the node
        printf("Element %d deleted from the list.\n", key);
        return;
    }

  
    struct Node* current = *head;
    struct Node* prev = NULL;

    while (current != NULL && current->data != key) {
        prev = current;
        current = current->next;  // Move to the next node
    }

  
    if (current == NULL) {
        printf("Element %d not found in the list.\n", key);
        return;
    }

    prev->next = current->next;  // Update the previous node's next pointer
    free(current);  // Free the memory of the node
    printf("Element %d deleted from the list.\n", key);
}


void insert(struct Node** head, int new_data) {
    struct Node* new_node = (struct Node*)malloc(sizeof(struct Node));
    struct Node* last = *head;

    new_node->data = new_data;
    new_node->next = NULL;

    
    if (*head == NULL) {
        *head = new_node;
        return;
    }

   
    while (last->next != NULL) {
        last = last->next;
    }

    // Insert the new node at the end
    last->next = new_node;
}


void display(struct Node* head) {
    struct Node* temp = head;
    while (temp != NULL) {
        printf("%d -> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

int main() {
    struct Node* head = NULL;


    insert(&head, 10);
    insert(&head, 20);
    insert(&head, 30);
    insert(&head, 40);

    printf("Original Linked List: ");
    display(head);

   
    int key = 20;
    deleteElement(&head, key);
    
    
    printf("Linked List after deletion: ");
    display(head);

    return 0;
}

```

Output:

![image](https://github.com/user-attachments/assets/d746796c-fe07-401d-9f53-b92fd7fde4bb)






Result:
Thus, the function that deletes a given element from a linked list is verified successfully.





