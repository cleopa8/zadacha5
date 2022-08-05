#include <stdio.h>
#include <stdlib.h>

#define struct(n) typedef struct n n; struct n

struct(listnode){
  int data; listnode *next;
};
struct(listnodelist){
  listnode *l; listnodelist *next;
};
void readlist(listnode **n){
               for(int x; 1 == scanf("%d", &x);){
                              listnode *p = malloc(sizeof(listnode));
                              *p = (listnode){x, *n};
                              *n = p;
               }
}

void readlistnodelist(listnodelist **n){

                              listnodelist *p = malloc(sizeof(listnodelist));
                              listnode *p1 = malloc(sizeof(listnode));
                              readlist(&p1);
                              *p = (listnodelist){p1, *n};
                              *n = p;

}

void printlist(listnode *n){
for(; n != NULL; n = n->next){
               printf("%d", n->data);
               putchar('\n');
}
}

void delete1(listnode **n, int k, int n1){
               //listnode *p = malloc(sizeof(*n+k));
               listnode *p = malloc(sizeof(listnode));
              // *p = ()
            //   p = (listnode){(*n + k + n1)->data, *n + k + n1};
              // *n = p;
               //  printf("%d", p->data);
                int count = 0;

                 while (k < count){
                              count++;
                               n = (**n).next;
                 }
        while (n1 >= count)
        {
            count++;
            n = (**n).next;
       //    free(*n->next);
              *p = (listnode){(**n).next->data, (**n).next};
           *n= p;

        }



}

void push(listnode **n, listnode **n1, int k){
               //listnode *p = malloc(sizeof(*n+k));
               listnode *p = malloc(sizeof(listnode));
              // *p = ()
            //   p = (listnode){(*n + k + n1)->data, *n + k + n1};
              // *n = p;
               //  printf("%d", p->data);
                int count = 0;

                 while (k < count){
                              count++;
                               n = (**n).next;
                 }
        while (n1 != NULL)
        {
           // count++;
            n = (**n).next;

       //    free(*n->next);
              *p = (listnode){(**n1).next->data, (**n1).next};
           *n= p;

        }



}

void fromlisnodetlist(listnodelist *n){
 for(; n != NULL; n = n->next){
//              printlist(n->next->data);
               putchar('\n');
}
}
int main()
{
              // int z = 2;

    listnode *head = NULL;
        listnode *head2 = NULL;

    readlist(&head);
    printlist(head);
    //function 1: delete elements from k place to n-th place
    delete1(&head, 2, 4);
    printlist(head);
    //function 2 insert elements into list head from another linked list head2
     readlist(&head2);
    printlist(head2);
    push(&head, head, 4);
     printlist(head);
     //third function
      listnodelist *head3 = head ;
//      readlistnodelist( listnodelist  **n);
   return 0;
}
