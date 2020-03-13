#include<iostream>
using namespace std;

struct Node {
	int data;
    Node* next;
};

/* Given a reference (pointer to pointer) to the head
   of a list and an int, appends a new node at the end  */
void pushElement(struct Node** head, char new_data)
{
	/* 1. allocate node */
	struct Node* new_node = (struct Node*) malloc(sizeof(struct Node));

	struct Node* last = *head;  /* used in step 5*/

	/* 2. put in the data  */
	new_node->data = new_data;

	/* 3. This new node is going to be the last node, so make next of
		  it as NULL*/
	new_node->next = NULL;

	/* 4. If the Linked List is empty, then make the new node as head */
	if (*head == NULL)
	{
		*head = new_node;
		return;
	}

	/* 5. Else traverse till the last node */
	while (last->next != NULL)
		last = last->next;

	/* 6. Change the next of last node */
	last->next = new_node;
	return;
}

void printList(struct Node* node)
{
	while (node != NULL)
	{
		cout << node->data;
		node = node->next;	
	}
}
	
int main()	
{
	char choice, userType;
	int row, i=0;
    Node* lists[1000] = { 0 };
	cin >> row;
	while (i < row) {
		userType = getchar();
		if (userType == char(10)) {
			i++;
		}
		else
		pushElement(&lists[i], userType);
	}
	cin >> choice;
	
	while (choice!='q')
	{
		
		switch (choice)
		{
		case 'max':
		
			break;
		case 'min':
			break;
		case '?':
			//printList(lists);
			break;
		}
	}
	return 0;
}
