# Doubly Linked List

**Aim:** <br>
To study and implement Doubly Linked List. <br>
<br>
**Theory:** <br>
A doubly linked list is another implementation of linked structures defined as a collection of nodes in a linear order. <br>
Each node consists of: <br>
Data - the value or information contained in the node. <br>
Two pointers: <br>
Pointer to the previous node in the order (called as prev). <br>
Pointer to the next node in the order (called as next). <br>

Advantages of Doubly Linked Lists: <br>
&#8594; Bidirectional Traversal <br>
&#8594; Efficient Deletions <br>
&#8594; Efficient Insertions <br>
<br>

Disadvantages of Doubly Linked Lists: <br>
&#8594; Complexity <br>
&#8594; Increased Memory Usage <br>
<br>

**Code:** <br>
<br>

```
#include <iostream>
using namespace std;

struct node 
{
    int data;        
    node* next;      
    node* prev;      
};

node* createnode(int value) 
{
    node* newnode = new node();  
    newnode->data = value;       
    newnode->next = nullptr;    
    newnode->prev = nullptr;   
    return newnode;
}


void insertdata(node*& head, int value) 
{

    node* newnode = createnode(value);
    if (head == nullptr) 
    {
        head = newnode;
    } 

    else 
    {
        node* temp = head;
        while (temp->next != nullptr) 
        {
            temp = temp->next;
        }

        temp->next = newnode;
        newnode->prev = temp;
    }
}


void displayfwd(node* head) 
{
    node* temp = head;
    cout << "Forward: ";

    while (temp != nullptr) 
    {
        cout << temp->data << "  ";
        temp = temp->next;
    }
}

void displayrev(node* head) 
{
    node* temp = head;

    if (temp == nullptr) 
    {
        return;
    }

    while (temp->next != nullptr) 
    {
        temp = temp->next;
    }
    cout << "Reverse: ";

    while (temp != nullptr) 
    {
        cout << temp->data << " ";
        temp = temp->prev;
    }
}

int main() 
{
    node* head = nullptr; 
    insertdata(head, 10);
    insertdata(head, 20);
    insertdata(head, 30);
    insertdata(head, 40);

    cout << "Doubly Linked List: "<<endl;
    displayfwd(head);
    cout<<endl;
    displayrev(head);

    return 0;
}

```
<br>


**Outputs:**  <br>
<br>
![expdll output](https://github.com/tanishaamenon/CDS---Doubly-Linked-Lists/blob/main/exp17dll.JPG) <br>
<br>

**Conclusion:** <br>
&#8594; We learnt about searching in C++. <br>
&#8594; We learnt the use case of the types of searching in C++. <br>
*******
<br>
