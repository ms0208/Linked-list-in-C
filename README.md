# Linked-list-in-C
// Single list . 
#include<stdio.h>
#include<stdlib.h> 
struct Node{
    int data;
    struct Node * next;
}; 
void LLTraversal(struct Node *ptr){
    while(ptr!=NULL){
        printf(" Elements is : %d\n ",ptr->data);
        ptr= ptr->next;
    }
}
struct Node * deleteNode(struct Node * head){
    struct Node *ptr = head;
    head = head->next;
    free(ptr);
    return head;
}

int main() {
    struct Node * head;
    struct Node * second;
    struct Node * third;
    struct Node * fourth;
    head = (struct Node*)malloc(sizeof(struct Node));
    second = (struct Node*)malloc(sizeof(struct Node));
    third = (struct Node*)malloc(sizeof(struct Node));
    fourth = (struct Node*)malloc(sizeof(struct Node)); 
    head ->data = 10;
    head ->next = second; 

    second ->data = 20;
    second->next = third;

    third ->data = 30;
    third ->next = fourth;

    fourth ->data = 40;
    fourth ->next = NULL; 

    LLTraversal(head); 

    printf("change node value\n"); 
    head ->data = 50;
    head ->next=second;

    second->data = 60;
    second->next = third; 
    
    third->data = 70;
    third->next = fourth;
    
    fourth ->data = 80;
    fourth ->next = NULL; 
    LLTraversal(head);
    printf("Value interchange between node\n");
      second->next=fourth;
      fourth->next=third;
      third->next=NULL;
    
     LLTraversal(head); 
     printf("Value change of one node\n");
        second->next=third;
        third->data=100;
      third->next=fourth;
      fourth->next=NULL; 
      LLTraversal(head);
     printf("Delete Nodes\n");
        head = deleteNode(head);
    printf("After delete first node\n");
    LLTraversal(head);  

    head = deleteNode(head);
    printf("Delete 2 nodes\n");
    LLTraversal(head);
    head = deleteNode(head);
    printf("Delete 3 nodes\n");
    LLTraversal(head); 
    


    return 0;
  
}
