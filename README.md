**1.Write a C++ program for implementing Singly Linked list.**

#include<iostream><br>
#include<cstdlib><br> 
using namespace std; <br>
struct node <br>
{ <br>
 int info;<br> 
 struct node *next;<br> 
}*start; <br>
class single_llist <br>
{ <br>
 public:<br> 
 node* create_node(int); <br>
 void insert_begin();<br> 
 void insert_last();<br> 
 void insert_pos();<br> 
 void delete_begin();<br> 
 void delete_last();<br> 
 void delete_pos();<br> 
 void update_begin();<br> 
 void update_last();<br> 
 void update_pos();<br> 
 void sort();<br> 
 void reverse();<br> 
 void search();<br> 
 void display();<br> 
 single_llist()<br> 
 {<br> 
 start = NULL;<br> 
 }<br> 
};<br> 
int main()<br> 
{<br> 
 int choice;<br> 
 single_llist sl,s2;<br> 
 start = NULL;<br> 
 do<br> 
 {<br> 
 cout<<"---------------------------------"<<endl;<br> 
 cout<<"Operations on singly linked list"<<endl;<br> 
 cout<<"---------------------------------"<<endl;<br> 
 cout<<"1.Insert at first"<<endl;<br> 
 cout<<"2.Insert at last"<<endl;<br> 
 cout<<"3.Insert at position"<<endl;<br> 
 cout<<"4.Delete at first"<<endl;<br> 
 cout<<"5.Delete at Last"<<endl;<br> 
 cout<<"6.Delete at position"<<endl;<br> 
 cout<<"7.Update at first"<<endl;<br> 
 cout<<"8.Update at last"<<endl;<br> 
 cout<<"9.Update at position"<<endl;<br> 
 cout<<"10.Ascending order"<<endl;<br> 
 cout<<"11.Descending order"<<endl;<br> 
 cout<<"12.Search"<<endl;<br> 
 cout<<"13.Display"<<endl;<br> 
 cout<<"14.Exit "<<endl;<br> 
 cout<<"Enter your choice :";<br> 
 cin>>choice;<br> 
 switch(choice)<br> 
 { <br>
 case 1: sl.insert_begin();<br> 
 sl.display();<br> 
 break;<br> 
 case 2: sl.insert_last();<br> 
 sl.display();<br> 
 break;<br> 
 case 3: sl.insert_pos();<br> 
 sl.display();<br> 
 break;<br> 
 case 4: s2.delete_begin();<br> 
 sl.display();<br> 
 break; <br>
 case 5: s2.delete_last();<br> 
 sl.display();<br> 
 break;<br> 
 case 6: sl.delete_pos();<br> 
 sl.display();<br> 
 break;<br> 
 case 7: sl.update_begin();<br> 
 sl.display();<br> 
 break;<br> 
 case 8: sl.update_last();<br> 
 sl.display();<br> 
 break;<br> 
 case 9: sl.update_pos();<br> 
 sl.display();<br> 
 break;<br> 
 case 10:sl.sort();<br> 
 sl.display();<br> 
 break;<br> 
 case 11:sl.reverse();<br> 
 sl.display();<br> 
 break;<br> 
 case 12:sl.search();<br> 
 sl.display();<br> 
 break;<br> 
 case 13:sl.display();<br> 
 break;<br> 
 case 14:exit(0);<br> 
 break;<br> 
 default:cout<<"Wrong choice...???"<<endl;<br> 
 break;<br> 
 }<br> 
 }<br> 
 while(choice != 14);<br> 
}<br> 
node *single_llist::create_node(int value)<br> 
{<br> 
 struct node *temp, *s;<br> 
 temp = new(struct node)<br>; 
 if (temp == NULL) <br>
 {<br> 
 cout<<"Memory not allocated"<<endl;<br> 
 return 0;<br> 
 } <br>
 else<br> 
 {<br> 
 temp->info = value;<br> 
 temp->next = NULL;<br> 
 return temp;<br> 
 }<br> 
}<br> 
void single_llist::insert_begin()<br> 
{<br> 
 int value;<br> 
 cout<<"Enter the value to be inserted : "; <br>
 cin>>value;<br> 
 struct node *temp, *s; <br>
 temp = create_node(value);<br> 
 if (start == NULL)<br> 
 {<br> 
 start = temp;<br> 
 start->next = NULL;<br> 
 cout<<temp->info<<" is inserted at first in the empty list"<<endl;<br> 
 }<br> 
 else<br> 
 {<br> 
 s = start;<br> 
 start = temp;<br> 
 start->next = s;<br> 
 cout<<temp->info<<" is inserted at first"<<endl; <br>
 }<br> 
}<br> 
void single_llist::insert_last()<br> 
{<br> 
 int value;<br> 
 cout<<"Enter the value to be inserted : "; <br>
 cin>>value;<br> 
 struct node *temp, *s;<br> 
 temp = create_node(value);<br> 
 if (start == NULL)<br> 
 {<br> 
 start = temp;<br> 
 start->next = NULL;<br> 
 cout<<temp->info<<" is inserted at last in the empty list"<<endl;<br> 
 }<br> 
 else<br> 
 {<br> 
 s = start;<br> 
 while (s->next != NULL)<br> 
 {<br> 
 s = s->next;<br> 
 } <br>
 temp->next = NULL;<br> 
 s->next = temp;<br> 
 cout<<temp->info<<" is inserted at last"<<endl;<br> 
 }<br> 
}<br> 
void single_llist::insert_pos()<br> 
{ <br>
 int value, pos, counter = 0, loc = 1;<br> 
 struct node *temp, *s, *ptr;<br> 
 s = start;<br> 
 while (s != NULL)<br> 
 {<br> 
 s = s->next;<br> 
 counter++; <br>
 }<br> 
 if (counter == 0){} <br>
 else<br> 
 {<br> 
 cout<<"Enter the postion from "<<loc<<" to "<<counter+1<<" : ";<br> 
 cin>>pos;<br> 
 s = start;<br> 
 if(pos == 1)<br> 
 {<br> 
 cout<<"Enter the value to be inserted : ";<br> 
 cin>>value;<br> 
 temp = create_node(value);<br> 
 start = temp;<br> 
 start->next = s;<br> 
 cout<<temp->info<<" is inserted at first"<<endl;<br> 
 }<br> 
 else if (pos > 1 && pos <= counter)<br> 
 {<br> 
 cout<<"Enter the value to be inserted : ";<br> 
 cin>>value;<br> 
 temp = create_node(value);<br> 
 for (int i = 1; i < pos; i++)<br> 
 {<br> 
 ptr = s;<br> 
 s = s->next;<br> 
 }<br> 
 ptr->next = temp;<br> 
 temp->next = s;<br> 
 cout<<temp->info<<" is inserted at position "<<pos<<endl;<br> 
 }<br>
 else if (pos == counter+1)<br> 
 {<br> 
 cout<<"Enter the value to be inserted : "; <br>
 cin>>value;<br> 
 temp = create_node(value);<br> 
 while (s->next != NULL)<br> 
 {<br> 
 s = s->next;<br> 
 }<br> 
 temp->next = NULL;<br> 
 s->next = temp;<br> 
 cout<<temp->info<<" is inserted at last"<<endl;<br> 
 }<br> 
 else<br> 
 { <br>
 cout<<"Positon out of range...!!!"<<endl;<br> 
 }<br> 
 }<br> 
} <br>
void single_llist::delete_begin()<br> 
{<br> 
 if (start == NULL){}<br> 
 else<br> 
 {<br> 
 struct node *s, *ptr;<br> 
 s = start;<br> 
 start = s->next;<br> 
 cout<<s->info<<" deleted from first"<<endl;<br> 
 free(s); <br>
 }<br> 
} <br>
void single_llist::delete_last()<br> 
{ <br>
 int i, counter = 0;<br> 
 struct node *s, *ptr; <br>
 if (start == NULL){}<br> 
 else <br>
 { <br>
 s = start;<br> 
 while (s != NULL) <br>
 {<br> 
 s = s->next;<br> 
 counter++;<br> 
 }<br> 
 s = start;<br> 
 if (counter == 1) <br>
 {<br> 
 start = s->next;<br> 
 cout<<s->info<<" deleted from last"<<endl;<br> 
 free(s);<br> 
 }<br> 
 else<br> 
 { <br>
 for (i = 1;i < counter;i++) <br>
 { <br>
 ptr = s;<br> 
 s = s->next;<br> 
 } <br>
 ptr->next = s->next;<br> 
 cout<<s->info<<" deleted from last"<<endl;<br> 
 free(s);<br> 
 }<br> 
 } <br>
}<br> 
void single_llist::delete_pos()<br>
{<br> 
 int pos, i, counter = 0, loc = 1;<br> 
 struct node *s, *ptr;<br> 
 s = start;<br> 
 while (s != NULL)<br>
 {<br> 
 s = s->next;<br> 
 counter++;<br> 
 }<br> 
 if (counter == 0){}<br> 
 else <br>
 {<br> 
 if (counter == 1)<br>
 {<br> 
 cout<<"Enter the postion [ SAY "<<loc<<" ] : ";<br> 
 cin>>pos;<br> 
 s = start;<br> 
 if (pos == 1)<br> 
 {<br> 
 start = s->next;<br> 
 cout<<s->info<<" deleted from first"<<endl;<br> 
 free(s);<br> 
 }<br> 
 else <br>
 cout<<"Position out of range...!!!"<<endl;<br> 
 }<br> 
 else<br> 
 {<br> 
 cout<<"Enter the postion from "<<loc<<" to "<<counter<<" : ";<br> 
 cin>>pos;<br> 
 s = start;<br> 
 if (pos == 1)<br> 
 {<br> 
 start = s->next;<br> 
 cout<<s->info<<" deleted from first"<<endl;<br> 
 free(s);<br> 
 }<br> 
 else if (pos > 1 && pos <= counter)<br> 
 {<br> 
 for (i = 1;i < pos;i++)<br> 
 {<br> 
 ptr = s;<br> 
 s = s->next;<br> 
 }<br> 
 ptr->next = s->next;<br> 
 if(pos == counter)<br> 
 {cout<<s->info<<" deleted from last"<<endl;<br> 
 free(s);}<br> 
 else <br>
 {cout<<s->info<<" deleted from postion "<<pos<<endl;<br> 
 free(s);}<br> 
 }<br> 
 else<br> 
 cout<<"Position out of range...!!!"<<endl;<br> 
 }<br> 
 }<br> 
}<br>
void single_llist::update_begin()<br> 
{ <br>
 int value, pos=1, i,counter = 0;<br> 
 struct node *s, *ptr;<br> 
 s = start;<br> 
 while (s != NULL)<br> 
 {<br> 
 s = s->next;<br> 
 counter++;<br> 
 }<br> 
 if (counter == 0){}<br> 
 else if (pos == 1)<br> 
 { <br>
 cout<<"Enter the new node : ";<br> 
 cin>>value;<br> 
 start->info = value;<br> 
 cout<<"Node updated at first position : "<<pos<<" = "<<start->info<<endl;<br> 
 }<br> 
}<br>
void single_llist::update_last()<br> 
{<br> 
 int value, pos, i,counter = 0;<br> 
 struct node *s, *ptr;<br> 
 s = start;<br> 
 while (s != NULL)<br> 
 {<br> 
 s = s->next;<br> 
 counter++;<br> 
 }<br> 
 s=start;<br> 
 if (counter == 0){}<br> 
 else<br> 
 {<br> 
 cout<<"Enter the new node : ";<br> 
 cin>>value;<br> 
 for (i = 1; i < counter ; i++)<br> 
 {<br>
 s = s->next;<br> 
 }<br> 
 s->info = value;<br> 
 cout<<"Node updated at last position : "<<counter<<" = "<<s->info<<endl;<br> 
 }<br> 
}<br> 
void single_llist::update_pos()<br> 
{<br> 
 int value, pos, i,counter = 0, loc = 1;<br> 
 struct node *s, *ptr;<br> 
 s = start;<br> 
 while (s != NULL)<br> 
 {<br> 
 s = s->next;<br> 
 counter++;<br> 
 }<br> 
 if (counter == 0){}<br> 
 else<br> 
 {<br>
 if (counter == 1)<br> 
 {<br> 
 cout<<"Enter the postion [ SAY "<<loc<<" ] : ";<br> 
 cin>>pos;<br> 
 s = start;<br> 
 if (pos == 1)<br> 
 {<br> 
 cout<<"Enter the new node : ";<br> 
 cin>>value;<br> 
 start->info = value;<br> 
 cout<<"Node updated at position : "<<pos<<" = "<<start->info<<endl;<br> 
 }<br> 
 else<br> 
 cout<<"Position out of range...!!!"<<endl;<br> 
 }<br> 
 else<br> 
 {<br> 
 cout<<"Enter the postion from "<<loc<<" to "<<counter<<" : ";<br>
 cin>>pos;<br> 
 s = start;<br> 
 if (pos == 1)<br> 
 {<br> 
 cout<<"Enter the new node : ";<br> 
 cin>>value;<br> 
 start->info = value;<br> 
 cout<<"Node updated at position : "<<pos<<" = "<<start->info<<endl;<br> 
 }<br> 
 else if (pos > 1 && pos <= counter)<br> 
 { <br>
 cout<<"Enter the new node : ";<br> 
 cin>>value;<br> 
 for (i = 1; i < pos ; i++)<br> 
 {<br> 
 s = s->next;<br> 
 }<br> 
 s->info = value;<br> 
 cout<<"Node updated at position : "<<pos<<" = "<<s->info<<endl;<br> 
 }<br> 
 else<br> 
 cout<<"Position out of range...!!!"<<endl;<br> 
 }<br> 
 }<br> 
}<br> 
void single_llist::sort()<br> 
{<br> 
 struct node *ptr, *s;<br> 
 int value;<br> 
 if (start == NULL){}<br> 
 else<br> 
 {<br> 
 ptr = start;<br> 
 while (ptr != NULL)<br> 
 {<br> 
 for (s = ptr->next;s !=NULL;s = s->next)<br> 
 {<br> 
 if (ptr->info > s->info)<br> 
 {<br> 
 value = ptr->info;<br> 
 ptr->info = s->info;<br> 
 s->info = value;<br> 
 }<br> 
 }<br> 
 ptr = ptr->next;<br> 
 }<br> 
 }<br> 
}<br>
void single_llist::reverse()<br> 
{<br> 
 struct node *ptr, *s;<br> 
 int value;<br> 
 if (start == NULL){}<br> 
 else<br> 
 {<br> 
 ptr = start;<br> 
 while (ptr != NULL)<br> 
 {<br> 
 for (s = ptr->next;s !=NULL;s = s->next)<br> 
 {<br> 
 if (ptr->info < s->info)<br> 
 {<br> 
 value = ptr->info;<br> 
 ptr->info = s->info;<br> 
 s->info = value;<br> 
 }<br> 
 }<br> 
 ptr = ptr->next;<br> 
 }<br> 
 }<br>
}<br> 
void single_llist::search()<br> 
{<br> 
 int value, loc = 0, pos = 0, counter = 0;<br> 
 struct node *s;<br> 
 s = start;<br> 
 while (s != NULL)<br> 
 {<br> 
 s = s->next;<br> 
 counter++;<br> 
 }<br> 
 if (start == NULL){}<br> 
 else<br> 
 {<br> 
 cout<<"Enter the value to be searched : ";<br> 
 cin>>value;<br> 
 struct node *s;<br> 
 s = start;<br> 
 while (s != NULL)<br> 
 {<br> 
 pos++;<br> 
 if (s->info == value)<br> 
 {<br> 
 loc++;<br> 
 if(loc == 1)<br> 
 cout<<"Element "<<value<<" is found at position "<<pos;<br> 
 else if(loc <= counter)<br> 
 cout<<" , "<<pos;<br> 
 }<br> 
 s = s->next;<br> 
 }<br> 
 cout<<endl;<br> 
 if (loc == 0)<br> 
 cout<<"Element "<<value<<" not found in the list"<<endl;<br> 
 }<br> 
}<br> 
void single_llist::display()<br> 
{<br> 
 struct node *temp;<br> 
 if (start == NULL)<br> 
 cout<<"Linked list is empty...!!!"<<endl;<br> 
 else<br> 
 {<br> 
 cout<<"Linked list contains : ";<br> 
 temp = start;<br> 
 while (temp != NULL)<br> 
 {<br> 
 cout<<temp->info<<" ";<br> 
 temp = temp->next;<br> 
 }<br> 
 cout<<endl;<br> 
 }<br> 
}<br>

 
**OUTPUT**
 
![image](https://user-images.githubusercontent.com/97940851/154899104-9aa4e4f1-b17c-4171-a1f7-af8f78132c0d.png)

 ![image](https://user-images.githubusercontent.com/97940851/154899206-d03f59ee-9be5-4288-a275-6225cf519e97.png)

 ![image](https://user-images.githubusercontent.com/97940851/154899306-2e0adfda-5d8d-4088-8ecb-9a6b702aa72e.png)
 
 ![image](https://user-images.githubusercontent.com/97940851/154899369-29738618-3ba1-4c8e-8d72-e5de39d83384.png)
 
 ![image](https://user-images.githubusercontent.com/97940851/154899432-bf483aab-0000-4138-95a3-e16cff6a3bc1.png)
 
 ![image](https://user-images.githubusercontent.com/97940851/154899856-59c1c1de-5d1b-4040-98ee-136c7ae3bc48.png)

 ![image](https://user-images.githubusercontent.com/97940851/154899887-33950d30-bdfa-4591-9ce4-8d0682b19948.png)
 
 ![image](https://user-images.githubusercontent.com/97940851/154900328-97ce57e1-26f3-4d36-bc09-746ec4d72bf6.png)


 **2.Write a C++ program to split the given Linked list into two in such a way that given element ele must be in the first node of second linked list**
 
 #include<iostream><br>
using namespace std;<br>
struct Node{<br>
int value;<br>
struct Node *next;<br>
};<br>
struct Node* head = NULL;<br>
struct Node* sHead = NULL;<br>
struct Node* temp = NULL;<br>
void insert(int new_data){<br>
struct Node* new_node = new Node();<br> 
new_node->value = new_data;<br>
new_node->next = head;<br>
head = new_node;<br>
}<br>
int n;<br>
int ele;<br>
int splitIndex;<br>
int main(){<br>
int i;<br>
cout<<"Enter number of elements you want in the list\t";<br>
cin>>n;<br>
cout<<"Enter elements :" <<endl;<br>
for(i=0;i<n;i++){<br>
cin>>ele;<br>
insert(ele);<br>
}<br>
cout<<"\nList of elements : "<<endl;<br>
Node *t;<br>
t = head;<br>
while(t != NULL){<br>
cout<<t->value<<"\t";<br>
t = t->next;<br>
}<br>
cout<<"\n\nEnter the position you want the list to split ";<br>
cin>>splitIndex;<br>
while(splitIndex < 0 || splitIndex > n-1){<br>
cout<<"Invalid position. Try again."<<endl;<br>
cin>>splitIndex;<br>
}<br>
temp = head;<br>
for(i=0;i<=splitIndex;i++){<br>
if(i==splitIndex-1){<br>
Node *tN;<br>
tN = temp->next;<br>
sHead = tN;<br>
temp->next = NULL;<br>
break;<br>
}<br>
temp = temp->next;<br>
}<br>
temp = head;<br>
if(temp == NULL){<br>
cout<<"\nFirst list is empty"<<endl;<br>
}else{<br>
cout<<"\n\nFirst list element "<<endl;<br>
while(temp != NULL){<br>
cout<<temp->value<<"\t";<br>
temp = temp->next;<br>
}<br>
}<br>
temp = sHead;<br>
if(temp == NULL){<br>
cout<<"\nSecond list is empty"<<endl;<br>
}else{<br>
cout<<"\n\nSecond list elements "<<endl;<br>
while(temp != NULL){<br>
cout<<temp->value<<"\t";<br>
temp = temp->next;<br>
}<br>
}<br>
return 0;<br>
}<br>
 
**OUTPUT**
 
![image](https://user-images.githubusercontent.com/97940851/154901341-b3bf959b-3c9b-41f3-abde-d171778d1f2f.png)
 
 **3.Write a program to implement addition of two arrays.**
 
 #include<iostream><br>
using namespace std;<br>

int main()<br>
{<br>
int size, i, arr1[10], arr2[10], add[10];<br>
cout << "\nPlease Enter the Array Size =  ";<br>
cin >> size;<br>
cout << "\nPlease Enter the First Array Items =  ";<br>
for(i = 0; i < size; i++)<br>
{<br>
cin >> arr1[i];<br>
}<br>
cout << "\nPlease Enter the Second Array Items =  ";<br>
for(i = 0; i < size; i++)<br>
{<br>
cin >> arr2[i];<br>
}<br>
for(i = 0; i < size; i++)<br>
{<br>
add[i] = arr1[i] + arr2[i];<br>
cout << arr1[i] << " + " << arr2[i] << " = " << add[i] << "\n";<br>
}<br>
cout << "\nThe Final Result of adding 2 One Dimensional Arrays = ";<br>
for(i = 0; i < size; i++)<br>
{<br>
cout << add[i] << " ";<br>
}<br>
return 0;<br>
}<br>
 
**OUTPUT**
 
 ![image](https://user-images.githubusercontent.com/97940851/154903703-22a58b67-94d3-4fc3-9aab-5a91241f2755.png)


 **4.Write a program to implement reverse order of the array element** 
 
 #include<iostream><br>
using namespace std;<br>
int main()<br>
{<br>
    int arr[10], i;<br>
    cout<<"Enter 10 Array Elements: ";<br>
    for(i=0; i<10; i++)<br>
        cin>>arr[i];<br>
    cout<<"\nThe Original Array is:\n";<br>
    for(i=0; i<10; i++)<br>
        cout<<arr[i]<<" ";<br>
    cout<<"\n\nThe Reverse of Given Array is:\n";<br>
    for(i=(10-1); i>=0; i--)<br>
        cout<<arr[i]<<" ";<br>
    cout<<endl;<br>
    return 0;<br>
}<br>
 
 **OUTPUT**
 
 ![image](https://user-images.githubusercontent.com/97940851/154902823-566a161a-5e6b-4b2f-9f77-98bf022817d7.png)
 
 **5.Write c++ program using stack array **
 
 #include <iostream><br>
using namespace std;<br>
int stack[100], n=100, top=-1;<br>
void push(int val) {<br>
   if(top>=n-1)<br>
   cout<<"\nStack Overflow"<<endl;<br>
   else {<br>
      top++;<br>
      stack[top]=val;<br>
   }<br>
}<br>
void pop() {<br>
   if(top<=-1)<br>
   cout<<"\nStack Underflow"<<endl;<br>
   else {<br>
      cout<<"\nThe popped element is "<< stack[top] <<endl;<br>
      top--;<br>
   }<br>
}<br>
void display() {<br>
   if(top>=0) {<br>
      cout<<"\nStack elements are:";<br>
      for(int i=top; i>=0; i--)<br>
      cout<<stack[i]<<" ";<br>
      cout<<endl;<br>
   } else<br>
   cout<<"Stack is empty";<br>
}<br>
int main()<br>
 {<br>
   int ch, val;<br>
   cout<<"1) Push in stack"<<endl;<br>
   cout<<"2) Pop from stack"<<endl;<br>
   cout<<"3) Display stack"<<endl;<br>
   cout<<"4) Exit"<<endl;<br>
   do<br>
    {<br>
      cout<<"\nEnter choice: "<<endl;<br>
      cin>>ch;<br>
      switch(ch)<br> 
	  {<br>
         case 1: {<br>
            cout<<"\nEnter value to be pushed:"<<endl;<br>
            cin>>val;<br>
            push(val);<br>
            break;<br>
         }<br>
         case 2: {<br>
            pop();<br>
            break;<br>
         }<br>
         case 3: {<br>
            display();<br>
            break;<br>
         }<br>
         case 4: {<br>
            cout<<"Exit"<<endl;<br>
            break;<br>
         }<br>
         default: {<br>
            cout<<"Invalid Choice"<<endl;<br>
         }<br>
      }<br>
   }while(ch!=4);<br>
   return 0;<br>
}<br>
 
 **OUTPUT**
 
 ![image](https://user-images.githubusercontent.com/97940851/154905342-e637c52a-34a4-4c49-a4cc-15653805d210.png)
	
	
**6.Construct the binary search tree for given elements**
	
# include <iostream><br> 
# include <cstdlib><br>  
using namespace std;<br>  
struct node<br>  
{<br> 
 int info;<br>  
 struct node *left;<br>  
 struct node *right;<br>  
}*root;<br>  
class BST<br>  
{<br>  
 public:<br>  
 void find(int, node **, node **);<br>  
 void insert(node *, node *);<br>  
 void del(int);<br>  
 void case_a(node *,node *);<br>  
 void case_b(node *,node *);<br>  
 void case_c(node *,node *);<br>  
 void preorder(node *);<br>  
 void inorder(node *);<br>  
 void postorder(node *);<br>  
 void display(node *, int);<br>  
 BST()<br>  
 {<br>  
 root = NULL;<br>  
 }<br>  
};<br>  
int main()<br>  
{<br>  
 int choice, num;<br>  
 BST bst;<br>  
 node *temp;<br>  
 while (1)<br>  
 {<br>  
 cout<<"-----------------"<<endl;<br>  
 cout<<"Operations on BST"<<endl;<br>  
 cout<<"-----------------"<<endl;<br>  
 cout<<"1.Insert Element "<<endl;<br>  
 cout<<"2.Delete Element "<<endl;<br>  
 cout<<"3.Inorder Traversal"<<endl;<br>  
 cout<<"4.Preorder Traversal"<<endl;<br>  
 cout<<"5.Postorder Traversal"<<endl;<br>  
 cout<<"6.Display"<<endl;<br>  
 cout<<"7.Quit"<<endl;<br>  
 cout<<"Enter your choice : ";<br>  
 cin>>choice;<br>  
 switch(choice)<br>  
 {<br>  
 case 1:<br>  
 temp = new node;<br>  
 cout<<"Enter the number to be inserted : ";<br>  
 cin>>temp->info;<br>  
 bst.insert(root, temp);<br>  
 break;<br>  
 case 2:<br>  
 if (root == NULL)<br>  
 {<br>  
 cout<<"Tree is empty, nothing to delete"<<endl;<br>  
 continue;<br> <br>  
 }<br>  
 cout<<"Enter the number to be deleted : ";<br>  
 cin>>num;<br>  
 bst.del(num);<br>  
 break;<br>  
 case 3:<br>  
 cout<<"Inorder Traversal of BST:"<<endl;<br>  
 bst.inorder(root);<br>  
 cout<<endl;<br>  
 break;<br>  
 case 4:<br>  
 cout<<"Preorder Traversal of BST:"<<endl;<br>  
 bst.preorder(root);<br>  
 cout<<endl;<br>  
 break;<br>  
 case 5:<br>  
 cout<<"Postorder Traversal of BST:"<<endl;<br>  
 bst.postorder(root);<br>  
 cout<<endl;<br>  
 break;<br>  
 case 6:<br>  
 cout<<"Display BST:"<<endl;<br>  
 bst.display(root,1);<br>  
 cout<<endl;<br>  
 break;<br>  
 case 7:<br>  
 exit(1);<br>  
 default:<br>  
 cout<<"Wrong choice"<<endl;<br>  
 }<br>  
 }<br>  
}<br>  
void BST::find(int item, node **par, node **loc)<br>  
{<br>  
 node *ptr, *ptrsave;<br>  
 if (root == NULL)<br>  
 {<br>  
 *loc = NULL;<br>  
 *par = NULL;<br>  
 return;<br>  
 } <br> 
 if (item == root->info)<br>  
 {<br>  
 *loc = root;<br>  
 *par = NULL;<br>  
 return;<br>  
 }<br>  
 if (item < root->info)<br>  
 ptr = root->left;<br>  
 else<br>  
 ptr = root->right;<br>  
 ptrsave = root;<br>  
 while (ptr != NULL)<br>  
 {<br>  
 if (item == ptr->info)<br>  
 {<br>  
 *loc = ptr;<br>  
 *par = ptrsave;<br>  
 return;<br>  
 }<br>  
 ptrsave = ptr;<br>  
 if (item < ptr->info)<br>  
 ptr = ptr->left;<br>  
 else<br>  
 ptr = ptr->right;<br>  
 }<br>  
 *loc = NULL;<br>  
 *par = ptrsave;<br>  
}<br>  

void BST::insert(node *tree, node *newnode)<br>  
{<br>  
 if (root == NULL)<br>  
 {<br>  
 root = new node;<br>  
 root->info = newnode->info;<br>   
 root->left = NULL;<br>   
 root->right = NULL;<br>   
 cout<<"Root Node is Added"<<endl;<br>   
 return;<br>  
 }<br>   
 if (tree->info == newnode->info)<br>  
 { <br>  
 cout<<"Element already in the tree"<<endl;<br>   
 return;<br>  
 }<br>   
 if (tree->info > newnode->info)<br>  
 {<br>   
 if (tree->left != NULL)<br>  
 {<br>   
 insert(tree->left, newnode);<br>   
 }<br>   
 else<br>   
 {<br>   
 tree->left = newnode;<br>   
 (tree->left)->left = NULL;<br>   
 (tree->left)->right = NULL;<br>   
 cout<<"Node Added To Left"<<endl;<br>   
 return;<br>  
 }<br>   
 }<br>   
 else<br>   
 {<br>   
 if (tree->right != NULL)<br>   
 {<br>   
 insert(tree->right, newnode);<br>   
 }<br>   
 else<br>   
 {<br>   
 tree->right = newnode;<br>   
 (tree->right)->left = NULL;<br>   
 (tree->right)->right = NULL;<br>   
 cout<<"Node Added To Right"<<endl;<br>   
 return;<br>   
 }<br>   
 }<br>   
}<br>   

void BST::del(int item)<br>   
{<br>   
 node *parent, *location;<br>   
 if (root == NULL)<br>   
 {<br>   
 cout<<"Tree empty"<<endl;<br>   
 return;<br>   
 }<br>   
 find(item, &parent, &location);<br>   
 if (location == NULL)<br>   
 {<br>   
 cout<<"Item not present in tree"<<endl;<br>   
 return;<br>   
 }<br>   
 if (location->left == NULL && location->right == NULL)<br>  
case_a(parent, location);<br>   
 if (location->left != NULL && location->right == NULL)<br>   
 case_b(parent, location);<br>   
 if (location->left == NULL && location->right != NULL)<br>   
 case_b(parent, location);<br>   
 if (location->left != NULL && location->right != NULL)<br>   
 case_c(parent, location);<br>   
 free(location);<br>  
}<br>  
 

void BST::case_a(node *par, node *loc )<br>   
{<br>   
 if (par == NULL)<br>   
 {<br>   
 root = NULL;<br>   
 }<br>   
 else<br>   
 {<br>   
 if (loc == par->left)<br>  
 par->left = NULL;<br>   
 else<br>   
 par->right = NULL;<br>  
 }<br>   
}<br>   
 

void BST::case_b(node *par, node *loc)<br>   
{<br>   
 node *child;<br>   
 if (loc->left != NULL)<br>   
 child = loc->left;<br>   
 else<br>   
 child = loc->right;<br>   
 if (par == NULL)<br>   
 {<br>   
 root = child;<br>   
 }<br>   
 else<br>   
 {<br>   
 if (loc == par->left)<br>   
 par->left = child;<br>   
 else<br>   
 par->right = child;<br>   
 }<br>   
}<br>   
 

void BST::case_c(node *par, node *loc)<br>   
{<br>   
 node *ptr, *ptrsave, *suc, *parsuc;<br>   
 ptrsave = loc;<br>   
 ptr = loc->right;<br>   
 while (ptr->left != NULL)<br>   
 {<br>   
 ptrsave = ptr;<br>   
 ptr = ptr->left;<br>   
 }<br>   
 suc = ptr;<br>   
 parsuc = ptrsave;<br>   
 if (suc->left == NULL && suc->right == NULL)<br>   
 case_a(parsuc, suc);<br>   
 else<br>   
 case_b(parsuc, suc);<br>   
 if (par == NULL)<br>   
 {<br>   
 root = suc;<br>   
 }<br>   
 else<br>  
 {<br>  
 if (loc == par->left)<br>   
 par->left = suc;<br>   
 else<br>   
 par->right = suc;<br>   
 }<br>   
 suc->left = loc->left;<br>   
 suc->right = loc->right;<br>   
}<br>   
 
 
void BST::preorder(node *ptr)<br>   
{<br>   
 if (root == NULL)<br>   
 {<br>   
 cout<<"Tree is empty"<<endl;<br>   
 return;<br>   
 }<br>   
 if (ptr != NULL)<br>   
 {<br>   
 cout<<ptr->info<<" ";<br>   
 preorder(ptr->left);<br>   
 preorder(ptr->right);<br>   
 }<br>   
}<br>  

void BST::inorder(node *ptr)<br>   
{<br>   
 if (root == NULL)<br>   
 {<br>   
 cout<<"Tree is empty"<<endl;<br>   
 return;<br>   
 }<br>  
 if (ptr != NULL)<br>   
 {<br>   
 inorder(ptr->left);<br>   
 cout<<ptr->info<<" ";<br>   
 inorder(ptr->right);<br>   
 }<br>   
}<br>   
 
void BST::postorder(node *ptr)<br>   
{<br>   
 if (root == NULL)<br>   
 {<br>   
 cout<<"Tree is empty"<<endl;<br>   
 return;<br>   
 }<br>   
 if (ptr != NULL)<br>  
 {<br>   
 postorder(ptr->left);<br>   
 postorder(ptr->right);<br>   
 cout<<ptr->info<<" ";<br>   
 }<br>   
}<br>   
 
void BST::display(node *ptr, int level)<br>   
{<br>  
 int i;<br>   
 if (ptr != NULL)<br>   
 {<br>   
 display(ptr->right, level+1);<br>   
 cout<<endl;<br>   
 if (ptr == root)<br>   
 cout<<"Root->: ";<br>   
 else<br>   
 {<br>   
 for (i = 0;i < level;i++)<br>   
 cout<<" ";<br>   
 }<br>   
 cout<<ptr->info;<br>   
 display(ptr->left, level+1);<br>   
 }<br>   
}<br>  


**OUTPUT**

![image](https://user-images.githubusercontent.com/97940851/155075924-c99358ff-d45e-4996-a4e6-eb7faab109ca.png)
	
![image](https://user-images.githubusercontent.com/97940851/155076019-cb1f9cd3-d4b7-45db-b939-64b226e3eb8d.png)
	
![image](https://user-images.githubusercontent.com/97940851/155076078-3f853406-1a76-489b-b389-df0fba0ec727.png)
	
![image](https://user-images.githubusercontent.com/97940851/155076155-c89b840e-5da9-4dbb-8fad-1b7affc91da7.png)
	

**Write a program implementing miniumum heap**	

#include <iostream><br>
#include <conio.h><br>
using namespace std;<br>
void min_heap(int *a, int m, int n){<br>
   int j, t;<br>
   t= a[m];<br>
   j = 2 * m;<br>
   while (j <= n) {<br>
      if (j < n && a[j+1] < a[j])<br>
         j = j + 1;<br>
      if (t < a[j])<br>
         break;<br>
      else if (t >= a[j]) {<br>
         a[j/2] = a[j];<br>
         j = 2 * j;<br>
      }<br>
   }<br>
   a[j/2] = t;<br>
   return;<br>
}<br>
void build_minheap(int *a, int n) {<br>
   int k;<br>
   for(k = n/2; k >= 1; k--) {<br>
      min_heap(a,k,n);<br>
   }<br>
}<br>
int main() {<br>
   int n, i;<br>
   cout<<"enter no of elements of array\n";<br>
   cin>>n;<br>
   int a[30];<br>
   for (i = 1; i <= n; i++) {<br>
      cout<<"enter element"<<" "<<(i)<<endl;<br>
      cin>>a[i];<br>
   }<br>
   build_minheap(a, n);<br>
   cout<<"Min Heap\n";<br>
   for (i = 1; i <= n; i++) {<br>
      cout<<a[i]<<endl;<br>
   }<br>
   getch();<br>
}<br>
		  
**OUTPUT**

![image](https://user-images.githubusercontent.com/97940851/156982059-7ea48fff-176c-41b8-8b34-9b76c74d9765.png)

	
**Write a program to implement maximum heap**

#include <iostream><br>
using namespace std;<br>
void max_heap(int *a, int m, int n) {<br>
   int j, t;<br>
   t = a[m];<br>
   j = 2 * m;<br>
   while (j <= n) {<br>
      if (j < n && a[j+1] > a[j])<br>
         j = j + 1;<br>
      if (t > a[j])<br>
         break;<br>
      else if (t <= a[j]) {<br>
         a[j / 2] = a[j];<br>
         j = 2 * j;<br>
      }<br>
   }<br>
   a[j/2] = t;<br>
   return;<br>
}<br>
void build_maxheap(int *a,int n) {<br>
   int k;<br>
   for(k = n/2; k >= 1; k--) {<br>
      max_heap(a,k,n);<br>
   } <br>
}<br>
int main() {<br>
   int n, i;<br>
   cout<<"enter no of elements of array\n";<br>
   cin>>n;<br>
   int a[30];<br>
   for (i = 1; i <= n; i++) {<br>
      cout<<"enter elements"<<" "<<(i)<<endl;<br>
      cin>>a[i];<br>
   }<br>
   build_maxheap(a,n);<br>
   cout<<"Max Heap\n";<br>
   for (i = 1; i <= n; i++) {<br>
      cout<<a[i]<<endl;<br>
   }<br>
}<br>	
	
	
**OUTPUT**
	
![image](https://user-images.githubusercontent.com/97940851/156982893-d0c3f3d1-1293-4cd2-b4b5-2159b27b3902.png)
	
	
**Find the subset of given set,s={s1,s2,s3,...sn} of positive integer whose sum=a given positive integer d.**

#include <iostream><br>
using namespace std;<br>

void displaySubset(int subSet[], int size)<br> 
{<br>
   for(int i = 0; i < size; i++)<br>
    {<br>
      cout << subSet[i] << "  ";<br>
   }<br>
   cout << endl;<br>
}<br>

void subsetSum(int set[], int subSet[], int n, int subSize, int total, int nodeCount ,int sum)<br> 
{<br>
   if( total == sum)<br>
    {<br>
      displaySubset(subSet, subSize);<br>     
	  
      subsetSum(set,subSet,n,subSize-1,total-set[nodeCount],nodeCount+1,sum);<br>     
      
   }<br>
   else<br>
   {<br>
      for( int i = nodeCount; i < n; i++)<br>
     {<br>    
      
         subSet[subSize] = set[i];<br>
         subsetSum(set,subSet,n,subSize+1,total+set[i],i+1,sum);<br>     
         
      }<br>
   }<br>
}<br>

void findSubset(int set[], int size, int sum)<br> 
{<br>
   int *subSet = new int[size];<br>     
   
   subsetSum(set, subSet, size, 0, 0, 0, sum);<br>
   delete[] subSet;<br>
}<br>

int main()<br> 
{<br>
   int weights[] = {10, 7, 5, 18, 12, 20, 15};<br>
   int size = 7;<br>
   findSubset(weights, size, 35);<br>
}<br>
	
**OUTPUT**
	
![image](https://user-images.githubusercontent.com/97940851/157183706-71767e74-fe41-4070-b21a-162ce9965f9a.png)
	

**WAP to store k keys into an array of size n at the location computed using a hash function, loc = key % n, where k<=n and Key takes values from [1 to m], m>n. Handle the collision using Linear probing technique.**	
	
#include<iostream><br>
#include<limits.h><br>
using namespace std;<br>
void Insert(int ary[],int hFn, int Size)<br>
{<br>
    int element,pos,n=0;<br>
    cout<<"Enter key element to insert\n";<br>
    cin>>element;<br>
    pos = element%hFn;<br> 
    while(ary[pos]!= INT_MIN)<br> 
      {<br>  
        if(ary[pos]== INT_MAX)<br>
        break;<br>
        pos = (pos+1)%hFn;<br>
        n++;<br>
        if(n==Size)<br>
        break;<br>     
       }<br>
       if(n==Size)<br>
       cout<<"Hash table was full of elements\nNo Place to insert this element\n\n";<br>
       else<br>
        ary[pos] = element;<br>    
}<br>
        void display(int ary[],int Size)<br>
		{<br>
        int i;<br>
 
       cout<<"Index\tValue\n";<br>
       for(i=0;i<Size;i++)<br>
       cout<<i<<"\t"<<ary[i]<<"\n";<br>
       }<br>   
       int main()<br>
	   {<br>
        int Size,hFn,i,choice;<br>
        cout<<"Enter size of hash table\n";<br>
        cin>>Size;<br>
        hFn=Size;<br>
        int ary[Size];<br>
        for(i=0;i<Size;i++)<br>
        ary[i]=INT_MIN;<br>
      do<br>
	  {<br>
      	cout<<"Enter your choice\n";<br>
        cout<<" 1-> Insert\n 2-> Display\n 0-> Exit\n";<br>
        cin>>choice;<br>
        switch(choice)<br>
		{<br>
        case 1:<br>
        Insert(ary,hFn,Size);<br>
        break;<br>
        case 2:<br>
        display(ary,Size);<br>
        break;<br>
        default:<br>
        cout<<"Enter correct choice\n";<br>
        break;<br>
      }<br>
}<br>
while(choice);<br>
return 0;<br>
}<br>


**OUTPUT**
	
![image](https://user-images.githubusercontent.com/97940851/162887504-83ef93f8-43e0-4ada-a1cf-e81ac1d3666b.png)

		
**Write a C++ program to implement merge sort technique using divide and conquer method**
	
#include <iostream><br>
#include<conio.h><br>
using namespace std;<br>
void Merge(int *a, int low, int high, int mid)<br>
{<br>
	int i, j, k, temp[high-low+1];<br>
	i = low;<br>
	k = 0;<br>
              j = mid + 1;<br>
             while (i <= mid && j <= high)<br>
	{<br>
		if (a[i] < a[j])<br>
		{<br>
			temp[k] = a[i];<br>
			k++;<br>
			i++;<br>
		}<br>
		else<br>
		{<br>
			temp[k] = a[j];<br>
			k++;<br>
			j++;<br>
		}<br>
	}<br>
	while (i <= mid)<br>
	{<br>
		temp[k] = a[i];<br>
		k++;<br>
		i++;<br>
	}<br>
	while (j <= high)<br>
	{<br>
		temp[k] = a[j];<br>
		k++;<br>
		j++;<br>
	}<br>
	for (i = low; i <= high; i++)<br>
	{<br>
		a[i] = temp[i-low];<br>
	}<br>
}<br>
void MergeSort(int *a, int low, int high)<br>
{<br>
	int mid;<br>
	if (low < high)<br>
	{<br>
		mid=(low+high)/2;<br>
	        MergeSort(a, low, mid);<br>
		MergeSort(a, mid+1, high);<br>
	        Merge(a, low, high, mid);<br>
	}<br>
}<br>
int main()<br>
{<br>
	int n, i;<br>
	cout<<"\nEnter the number of data element to be sorted: ";<br>
	cin>>n;<br>
 
	int arr[n];<br>
	for(i = 0; i < n; i++)<br>
	{<br>
		cout<<"Enter element "<<i+1<<": ";<br>
		cin>>arr[i];<br>
	}<br>
          MergeSort(arr, 0, n-1);<br>
	  cout<<"\nSorted Data ";<br>
	  for (i = 0; i < n; i++)<br>
          cout<<"->"<<arr[i];<br>
 
	  getch();<br>
}<br>
					    
**OUTPUT**
					    
![image](https://user-images.githubusercontent.com/97940851/162886992-f96fa23c-0778-4581-aee3-b37fa378156a.png)
	
	
**create a program to compute doubly linked list**
	
#include<iostream><br>
#include<cstdio><br>
#include<cstdlib><br>
using namespace std;<br>
struct node<br>
{<br>
    int info;<br>
    struct node *next;<br>
    struct node *prev;<br>
}*start;<br>
class double_llist<br>
{<br>
    public:<br>
        void create_list(int value);<br>
        void add_begin(int value);<br>
        void add_after(int value, int position);<br>
        void delete_element(int value);<br>
        void search_element(int value);<br>
        void display_dlist();<br>
        void count()<br>;<br>
        void reverse();<br>
        double_llist()<br>
        {<br>
            start = NULL;<br>  
        }<br>
};<br>
 int main()<br>
{<br>
    int choice, element, position;<br>
    double_llist dl;<br>
    while (1)<br>
    {<br>
        cout<<endl<<"----------------------------"<<endl;<br>
        cout<<endl<<"Operations on Doubly linked list"<<endl;<br>
        cout<<endl<<"----------------------------"<<endl;<br>        
        cout<<"1.Create Node"<<endl;<br>
        cout<<"2.Add at begining"<<endl;<br>
        cout<<"3.Add after position"<<endl;<br>
        cout<<"4.Delete"<<endl;<br>
        cout<<"5.Display"<<endl;<br>
        cout<<"6.Count"<<endl;<br>
        cout<<"7.Reverse"<<endl;<br>
        cout<<"8.Quit"<<endl;<br>
        cout<<"Enter your choice : ";<br>
        cin>>choice;<br>
        switch ( choice )<br>
        {<br>
        case 1:<br>
            cout<<"Enter the element: ";<br>
            cin>>element;<br>
            dl.create_list(element);<br>
            cout<<endl;<br>
            break;<br>
        case 2:<br>
            cout<<"Enter the element: ";<br>
            cin>>element;<br>
            dl.add_begin(element);<br>
            cout<<endl;<br>
            break;<br>
        case 3:<br>
            cout<<"Enter the element: "<br>;<br>
            cin>>element;<br>
            cout<<"Insert Element after postion: ";<br>
            cin>>position;<br>
            if(position<=0)<br>
            {<br>
            	cout<<"\n Position cannot be less then 1"<<endl;<br>
            	break;<br>
			}<br>
            dl.add_after(element, position);<br>
            cout<<endl;<br>
            break;<br>
        case 4:<br>
            if (start == NULL)<br>
            { <br>                     
                cout<<"List empty,nothing to delete"<<endl;  <br>
                break;<br>
            }<br>
            cout<<"Enter the element for deletion: "<br>;<br>
            cin>>element;<br>
            dl.delete_element(element);<br>
            cout<<endl;<br>
            break;<br>
        case 5:<br>
            dl.display_dlist();<br>
            cout<<endl;<br>
            break;<br>
        case 6:<br>
            dl.count();<br>
            break;<br>    
        case 7:<br>
            if (start == NULL)<br>
            {<br>
                cout<<"List empty,nothing to reverse"<<endl;<br>
                break;<br>
            }<br>
            dl.reverse();<br>
            cout<<endl;<br>
            break;<br>
        case 8:<br>
            exit(1);<br>
        default:<br>
            cout<<"Wrong choice"<<endl;<br>
        }<br>
    }<br>
    <br>return 0;<br>
}<br>
 void double_llist::create_list(int value)<br>
{<br>
    struct node *s, *temp;<br>
    temp = new(struct node);<br>
    temp->info = value;<br>
    temp->next = NULL;<br>
    if (start == NULL)<br>
    {<br>
        temp->prev = NULL;<br>
        start = temp;<br>
    }<br>
    else<br>
    {<br>
        s = start;<br>
        while (s->next != NULL)<br>
            s = s->next;<br>
        s->next = temp;<br>
        temp->prev = s;<br>
    }<br>
}<br>
 void double_llist::add_begin(int value)<br>
{<br>
    if (start == NULL)<br>
    {<br>
        cout<<"First Create the list."<<endl;<br>
        return;<br>
    }<br>
    struct node *temp;<br>
    temp = new(struct node);<br>
    temp->prev = NULL;<br>
    temp->info = value;<br>
    temp->next = start;<br>
    start->prev = temp;<br>
    start = temp;<br>
    cout<<"Element Inserted"<<endl;<br>
}<br>
void double_llist::add_after(int value, int pos)<br>
{<br>
    if (start == NULL)<br>
    {<br>
        cout<<"First Create the list."<<endl;<br>
        return;<br>
    }<br>
    struct node *tmp, *q;<br>
    int i;<br>
    q = start;<br>
    for (i = 0;i < pos - 1;i++<br>)<br>
    {<br>
        q = q->next;<br>
        if (q == NULL)<br>
        {<br>
            cout<<"There are less than ";<br>
            cout<<pos<<" elements."<<endl;<br>
            return;<br>
        }<br>
    }<br>
    tmp = new(struct node);<br>
    tmp->info = value;<br>
    if (q->next == NULL)<br>
    {<br>
        q->next = tmp;<br>
        tmp->next = NULL;<br>
        tmp->prev = q;  <br>    
    }<br>
    else<br>
    {<br>
        tmp->next = q->next;<br>
        tmp->next->prev = tmp;<br>
        q->next = tmp;<br>
        tmp->prev = q;<br>
    }<br>
    cout<<"Element Inserted"<<endl;<br>
}<br>
 void double_llist::delete_element(int value)<br>
{<br>
    struct node *tmp, *q;<br>
        if (start->info == value)<br>
    {<br>
        tmp = start;<br>
        start = start->next; <br> 
        start->prev = NULL;<br>
        cout<<"Element Deleted"<<endl;<br>
        free(tmp);<br>
        return;<br>
    }<br>
    q = start;<br>
    while (q->next->next != NULL)<br>
    { <br> 
               if (q->next->info == value) <br> 
        {<br>
            tmp = q->next;<br>
            q->next = tmp->next;<br>
            tmp->next->prev = q;<br>
            cout<<"Element Deleted"<<endl;<br>
            free(tmp);<br>
            return;<br>
        }<br>
        q = q->next;<br>
    }<br><br>
        if (q->next->info == value)  <br>  
    {<br>
        tmp = q->next;<br>
        free(tmp);<br>
        q->next = NULL;<br>
        cout<<"Element Deleted"<<endl;<br>
        return;<br>
    }<br>
    cout<<"Element "<<value<<" not found"<<endl;<br>
}<br>
 void double_llist::display_dlist()<br>
{<br>
    struct node *q;<br>
    if (start == NULL)<br>
    {<br>
        cout<<"List empty,nothing to display"<<endl;<br>
        return;<br>
    }<br>
    q = start;<br>
    cout<<"The Doubly Link List is :"<<endl;<br>
    while (q != NULL)<br>
    {<br>
        cout<<q->info<<" <-> ";<br><br>
        q = q->next;<br>
    }<br>
    cout<<"NULL"<<endl;<br>
}<br>
 void double_llist::count()<br>
{<br>
    struct node *q = start;<br>
    int cnt = 0;<br>
    while (q != NULL)<br>
    {<br>
        q = q->next;<br>
        cnt++;<br>
    }<br>
    cout<<"Number of elements are: "<<cnt<<endl;<br>
}<br>
 void double_llist::reverse()<br>
{<br>
    struct node *p1, *p2;<br>
    p1 = start;<br>
    p2 = p1->next;<br>
    p1->next = NULL;<br>
    p1->prev = p2;<br>
    while (p2 != NULL)<br>
    {<br>
        p2->prev = p2->next;<br>
        p2->next = p1;<br>
        p1 = p2;<br>
        p2 = p2->prev;<br>
    }<br>
    start = p1;<br>
    cout<<"List Reversed"<<endl;<br>
}<br>

**OUTPUT**
	
![image](https://user-images.githubusercontent.com/97940851/163757931-38631292-125a-4b7e-925b-1df24da5f4bd.png)
	
![image](https://user-images.githubusercontent.com/97940851/163757981-956e0580-fb85-4402-a9ac-442bb1887003.png)
	
![image](https://user-images.githubusercontent.com/97940851/163758285-cbd009c5-1caa-4c6c-8fc5-7a4ef7a2ec30.png)
	
![image](https://user-images.githubusercontent.com/97940851/163758321-c4b11354-c8a6-4c6c-9564-87dae6becee9.png)

![image](https://user-images.githubusercontent.com/97940851/163759012-7ae9bf6e-7e28-4678-84c8-04db0a2339e3.png)
	
![image](https://user-images.githubusercontent.com/97940851/163759037-1d368f41-8d03-4a53-8608-921d7d69b06d.png)
	

	
**Create a program to implement spitting of an array**
	
#include<iostream>
using namespace std;<br>
int main()<br>
{<br>
int a[20],i,n,a1[20],a2[20],k1=0,k2=0,pos;<br>
cout<<"Enter the size of an array: "<<endl;<br>
cin>>n;<br>
cout<<"Enter array elements: "<<endl;<br>
for(i=0;i<n;i++)<br>
{<br>
cin>>a[i];<br>
}<br>
cout<<"Enter the position to split the array into 2"<<endl;<br>
cin>>pos;<br>
for(i=0;i<n;i++)<br>
{<br>
if(i<pos)<br>
a1[k1++]=a[i];<br>
else<br>
a2[k2++]=a[i];<br>
}<br>
cout<<"\nArray elements of array1 \n";<br>
for(i=0;i<k1;i++)<br>
{<br>
cout<<a1[i]<<endl;<br>
}<br>
			
cout<<"\nArray elements of array2 \n";<br>
for(i=0;i<k2;i++)<br>
{<br>
 cout<<a2[i]<<endl;<br>
}<br>
cout<<"\n";<br>
return 0;<br>}<br>
			
**OUTPUT**
	
![image](https://user-images.githubusercontent.com/97940851/164607136-38a85483-21d4-400a-bf4c-5a05b031f0b9.png)
	
	
**Find the minimum cost spanning tree of a given weighted undirected graph using Prim’s Algorithm.**

#include <bits/stdc++.h><br>
using namespace std;<br>
#define V 5<br>
int minKey(int key[], bool mstSet[])<br>
{<br>
int min = INT_MAX, min_index;<br>
for (int v = 0; v < V; v++)<br>
if (mstSet[v] == false && key[v] < min)<br>
min = key[v], min_index = v;<br>
return min_index;<br>
}<br>
void printMST(int parent[], int graph[V][V])<br>
{<br>
cout<<"Edge \tWeight\n";<br>
for (int i = 1; i < V; i++)<br>
cout<<parent[i]<<" - "<<i<<" \t"<<graph[i][parent[i]]<<" \n";<br>
}<br>

void primMST(int graph[V][V])<br>
{<br>
int parent[V];<br>
int key[V];<br>
bool mstSet[V];<br>
for (int i = 0; i < V; i++)<br>
key[i] = INT_MAX, mstSet[i] = false;<br>
key[0] = 0;<br>
parent[0] = -1; // First node is always root of MST<br>
for (int count = 0; count < V - 1; count++)<br>
{<br>
int u = minKey(key, mstSet);<br>
mstSet[u] = true;<br>
for (int v = 0; v < V; v++)<br>
if (graph[u][v] && mstSet[v] == false && graph[u][v] < key[v])<br>
parent[v] = u, key[v] = graph[u][v];<br>
}<br>
printMST(parent, graph);<br>
}<br>
int main()<br>
{<br>
int graph[V][V] = { { 0, 2, 0, 6, 0 },<br>
{ 2, 0, 3, 8, 5 },<br>
{ 0, 3, 0, 0, 7 },<br>
{ 6, 8, 0, 0, 9 },<br>
{ 0, 5, 7, 9, 0 } };<br>
primMST(graph);<br>
return 0;<br>
}<br>
							      
**OUTPUT**	

![image](https://user-images.githubusercontent.com/97940851/165030684-b9a12254-874d-4827-8ba9-4b46474a499f.png)
							      
							      
**Find the minimum cost spanning tree of a given undirected graph using Kruskal’s Algorithm.**	

#include<bits/stdc++.h><br>
using namespace std;<br>
typedef pair<int, int> iPair;<br>
struct Graph<br>
{<br>
int V, E;<br>
vector< pair<int, iPair> > edges;<br>
Graph(int V, int E)<br><br>
{<br>
this->V = V;<br>
this->E = E;<br>
}<br>
void addEdge(int u, int v, int w)<br>
{<br>
edges.push_back({w, {u, v}});<br>
}<br>
int kruskalMST();<br>
};<br>

struct DisjointSets<br>
{<br>
int *parent, *rnk;<br>
int n;<br>
DisjointSets(int n)<br>
{<br>
this->n = n;<br>
parent = new int[n+1];<br>
rnk = new int[n+1];<br>
for (int i = 0; i <= n; i++)<br>
{<br>
rnk[i] = 0;<br>
parent[i] = i;<br>
}<br><br>
}<br>
int find(int u)<br>
{<br>
if (u != parent[u])<br>
parent[u] = find(parent[u]);<br>
return parent[u];<br>
}<br>
void merge(int x, int y)<br>
{<br>
x = find(x), y = find(y);<br>
if (rnk[x] > rnk[y])<br>
parent[y] = x;<br>
else // If rnk[x] <= rnk[y]<br>
parent[x] = y;<br>
if (rnk[x] == rnk[y])<br>
rnk[y]++;<br>
}<br>
};<br>
int Graph::kruskalMST()<br>
{<br>
int mst_wt = 0; <br>
sort(edges.begin(), edges.end());<br>
DisjointSets ds(V);<br>
vector< pair<int, iPair> >::iterator it;<br>
for (it=edges.begin(); it!=edges.end(); it++)<br>
{<br>
int u = it->second.first;<br>
int v = it->second.second;<br>
int set_u = ds.find(u);<br>
int set_v = ds.find(v);<br>
if (set_u != set_v)<br>
{<br>
cout << u << " - " << v << endl;<br>
mst_wt += it->first;<br>
ds.merge(set_u, set_v);<br>
}<br>
}<br>
return mst_wt;<br>
}<br>
int main()<br>
{<br>
int V = 9, E = 14;<br>
Graph g(V, E);<br>
g.addEdge(0, 1, 4);<br>
g.addEdge(0, 7, 8);<br>
g.addEdge(1, 2, 8);<br>
g.addEdge(1, 7, 11);<br>
g.addEdge(2, 3, 7);<br>
g.addEdge(2, 8, 2);<br>
g.addEdge(2, 5, 4);<br>
g.addEdge(3, 4, 9);<br><br>
g.addEdge(3, 5, 14);<br>
g.addEdge(4, 5, 10);<br>
g.addEdge(5, 6, 2);<br>
g.addEdge(6, 7, 1);<br>
g.addEdge(6, 8, 6);<br>
g.addEdge(7, 8, 7);<br>
cout << "Edges of MST are \n";<br>
int mst_wt = g.kruskalMST();<br>
cout << "\nWeight of MST is " << mst_wt;<br>
return 0;<br>
}<br>

**OUTPUT**
							      
![image](https://user-images.githubusercontent.com/97940851/165035075-721c1230-8167-4660-b3dd-2e8826d33ca4.png)
							      
**Write a C++ program for to implement BFS for undirected graph.**

#include<iostream><br>
#include<conio.h><br>
#include<stdlib.h><br>
using namespace std;<br>
 int cost[10][10],qu[10],front,rare,visit[10],visited[10];<br>
int main()<br>
{<br>
<br>
 int m,n,j,i,v,k;<br>
  cout <<"Enter no of vertices:";<br>
  cin >> n;<br>
  cout <<"Enter no of edges:";<br>
  cin >> m;<br>
  cout <<"\nEDGES \n";<br>
  for(k=1; k<=m; k++)<br>
  {<br>
      cin >>i>>j;<br>
      cost[i][j]=1;<br>
  }<br>
  cout <<"Enter initial vertex to traverse from:";<br>
  cin >>v;<br>
  cout <<"Visitied vertices:";<br>
 cout <<v<<" ";<br>
 visited[v]=1;<br>
 k=1;<br>
 while(k<n)<br>
 {<br>
  for(j=1; j<=n; j++)<br>
  if(cost[v][j]!=0 && visited[j]!=1 && visit[j]!=1)<br>
  {<br>
  visit[j]=1;<br>
  qu[rare++]=j;<br>
  }<br>
  v=qu[front++];<br>
  cout<<v <<" ";<br>
  k++;<br>
  visit[v]=0;<br>
  visited[v]=1;<br>
  }<br>
 return 0;<br>
}<br>
	
**OUTPUT**
	
![image](https://user-images.githubusercontent.com/97940851/165233030-f31d9cc8-6509-4926-b41e-87d84c5af98f.png)

	
	
**Write a C++ program for to implement DFS for undirected graph.**

#include<iostream><br>
#include<conio.h><br>
#include<stdlib.h><br>
using namespace std;<br>
int cost[10][10],i,j,k,n,stk[10],top,v,visit[10],visited[10];<br>
int main()<br>
{<br>
    int m;<br>
    cout <<"Enter no of vertices:";<br>
    cin >> n;<br>
    cout <<"Enter no of edges:";<br>
    cin >> m;<br>
    cout <<"\nEDGES \n";<br>
    for(k=1; k<=m; k++)<br>
    {<br>
        cin >>i>>j;<br>
        cost[i][j]=1;<br>
    }<br>
    cout <<"Enter initial vertex to traverse from:";<br>
    cin >>v;<br>
    cout <<"DFS ORDER OF VISITED VERTICES:";<br>
    cout << v <<" ";<br>
    visited[v]=1;<br>
    k=1;<br>
    while(k<n)<br>
    {<br>
    for(j=n; j>=1; j--)<br>
    if(cost[v][j]!=0 && visited[j]!=1 && visit[j]!=1)<br>
    {<br>
    visit[j]=1;<br>
    stk[top]=j;<br>
    top++;<br>
  }<br>
    v=stk[--top];<br>
    cout<<v << " ";<br>
    k++;<br>
    visit[v]=0;<br>
    visited[v]=1;<br> }<br>
return 0;<br>
}<br>

**OUTPUT**
	
![image](https://user-images.githubusercontent.com/97940851/165233262-86596fbd-17cb-42b1-ac01-cf69bdb89c00.png)
	
**Write a C++ program for solving the N-Queen’s Problem using backtracking**
	
#include<iostream><br>
using namespace std;<br>
int grid[10][10];<br>
//print the solution<br>
void print(int n) {<br>
    for (int i = 0;i <= n-1; i++)<br>
	 {<br>
        for (int j = 0;j <= n-1; j++)<br>
		 {<br>
            
                cout <<grid[i][j]<< " ";<br>
            <br>
        }<br>
        cout<<endl;<br>
    }<br>
    cout<<endl;<br>
    cout<<endl;<br>
}<br>
//function for check the position is safe or not<br>
//row is indicates the queen no. and col represents the possible positions<br>
bool isSafe(int col, int row, int n) <br>
{<br>
  //check for same column<br>
    for (int i = 0; i < row; i++)<br>
	 {<br>
        if (grid[i][col])<br>
		 {<br>
            return false;<br>
        }<br>
    }<br>
    //check for upper left diagonal<br>
    for (int i = row,j = col;i >= 0 && j >= 0; i--,j--) <br>
	{<br>
    	 if (grid[i][j]) <br>
		 {<br>
            return false;<br>
        }<br>
    }<br>
    //check for upper right diagonal<br>
    for (int i = row, j = col; i >= 0 && j < n; j++, i--) <br>
	{<br>
        if (grid[i][j]) <br>
		{<br>
            return false;<br>
        }<br>
    }<br>
    return true;<br>
}<br>
//function to find the position for each queen<br>
//row is indicates the queen no. and col represents the possible positions<br>
bool solve (int n, int row)<br> 
{<br>
    if (n == row) <br>
	{<br>
        print(n);<br>
        return true;<br>
    }<br>
    //variable res is use for possible backtracking<br> 
    bool res = false;<br>
    for (int i = 0;i <=n-1;i++) <br>
	{<br>
        if (isSafe(i, row, n)) <br><br>
		{<br>
            grid[row][i] = 1;<br>
            //recursive call solve(n, row+1) for next queen (row+1)<br>
            res = solve(n, row+1) || res;//if res ==false then backtracking will occur <br>
            //by assigning the grid[row][i] = 0<br>
            
            grid[row][i] = 0;<br>
        }<br>
    }<br>
    return res;<br>
}<br>
int main()<br>
{<br>
  ios_base::sync_with_stdio(false);<br>
    cin.tie(NULL);<br>
        int n;<br>
        cout<<"Enter the number of queen"<<endl;<br>
        cin >> n;<br>
        for (int i = 0;i < n;i++) <br>
		{<br>
            for (int j = 0;j < n;j++) <br>
			{<br>
                grid[i][j] = 0;<br>
            }<br>
        }<br>
        bool res = solve(n, 0);<br>
        if(res == false) <br>
		{<br>
            cout << -1 << endl; //if there is no possible solution<br>
        } else <br>
		{<br>
            cout << endl;<br>
        }<br>
  return 0;<br>
}<br>

**OUTPUT**
	
![image](https://user-images.githubusercontent.com/97940851/165235376-77ce9e2c-e571-40d4-acea-c04811fb4284.png)

**Write a C++ Program to find minimum and maximum element from an unsorted array using Divide and Conquer method.**
	
#include <iostream><br>
#include <stdio.h><br>
#include <stdlib.h><br>
#include <conio.h><br>
using namespace std;<br>
void findMinAndMax(int arr[], int low, int high, int &min, int &max)<br><br>
{<br>
if (low == high)<br>	
{<br>
if (max < arr[low])<br>
{<br>
max = arr[low];<br>
}<br>

if (min > arr[high])<br>
{<br>
min = arr[high];<br>
}<br>
return;<br>
}<br>
if (high - low == 1)<br>	
{<br>
if (arr[low] < arr[high])<br>	
{<br>
if (min > arr[low])<br>
 {<br><br>
min = arr[low];<br>
}<br>

if (max < arr[high])<br>
{<br>
max = arr[high];<br>
}<br>
}<br>
else {<br>
if (min > arr[high])<br>
{<br>
min = arr[high];<br>
}<br>

if (max < arr[low])<br>
{<br>
max = arr[low];<br><br>
}<br>
}<br>
return;<br>
}<br>
int mid = (low + high) / 2;<br>
findMinAndMax(arr, low, mid, min, max);<br>
findMinAndMax(arr, mid + 1, high, min, max);<br>
}<br>
int main()<br>
{<br>
int arr[] = { 7, 2, 9, 3, 6, 7, 8, 4 };<br>
int n = sizeof(arr) / sizeof(arr[0]);<br>
int max = arr[0], min = arr[0];<br>

findMinAndMax(arr, 0, n - 1, min, max);<br>

cout << "The minimum array element is " << min << endl;<br>
cout << "The maximum array element is " << max;<br>

return 0;<br>
}<br>

**OUTPUT**

![image](https://user-images.githubusercontent.com/97940851/165238319-ee7814ac-eb2b-4c7b-af30-4f5f0677ac94.png)
	
**Impliment red black tree**							      **
							      
#include using namespace std;
struct node
{
int key;
node *parent;
char color;
node *left;
node *right;
};
class RBtree
{
node *root;
node *q;
public :
RBtree()
{
q=NULL;
root=NULL;
}
void insert();
void insertfix(node *);
void leftrotate(node *);
void rightrotate(node );
void del();
node successor(node *);
void delfix(node *);
void disp();
void display( node *);
void search();
};
void RBtree::insert()
{
int z,i=0;
cout<<"\nEnter key of the node to be inserted: ";
cin>>z;
node *p,*q;
node *t=new node;
t->key=z;
t->left=NULL;
t->right=NULL;
t->color='r';
p=root;
q=NULL;
if(root==NULL)
{
root=t;
t->parent=NULL;
}
else
{
while(p!=NULL)
{
q=p;
if(p->keykey)
p=p->right;
else
p=p->left;
}
t->parent=q;
if(q->keykey)
q->right=t;
else
q->left=t;
}
insertfix(t);
}
void RBtree::insertfix(node *t)
{
node *u;
if(root==t)
{
t->color='b';
return;
}
while(t->parent!=NULL&&t->parent->color=='r')
{
node *g=t->parent->parent;
if(g->left==t->parent)
{
if(g->right!=NULL)
{
u=g->right;
if(u->color=='r')
{
t->parent->color='b';
u->color='b';
g->color='r';
t=g;
}
}
else
{
if(t->parent->right==t)
{
t=t->parent;
leftrotate(t);
}
t->parent->color='b';
g->color='r';
rightrotate(g);
}
}
else
{
if(g->left!=NULL)
{
u=g->left;
if(u->color=='r')
{
t->parent->color='b';
u->color='b';
g->color='r';
t=g;
}
}
else
{
if(t->parent->left==t)
{
t=t->parent;
rightrotate(t);
}
t->parent->color='b';
g->color='r';
leftrotate(g);
}
}
root->color='b';
}
}

void RBtree::del()
{
if(root==NULL)
{
cout<<"\nEmpty Tree." ;
return ;
}
int x;
cout<<"\nEnter the key of the node to be deleted: ";
cin>>x;
node *p;
p=root;
node *y=NULL;
node *q=NULL;
int found=0;
while(p!=NULL&&found==0)
{
if(p->key==x)
found=1;
if(found==0)
{
if(p->key<x)
p=p->right;
else
p=p->lef
;
}
}
if(found==0)
{
cout<<"\nElement Not Found.";
return ;
}
else
{
cout<<"\nDeleted Element: "<key;
cout<<"\nColour: ";
if(p->color=='b')
cout<<"Black\n";
else
cout<<"Red\n";

     if(p->parent!=NULL)<br>
           cout<<"\nParent: "<<p->parent->key;<br>
     else<br>
           cout<<"\nThere is no parent of the node.  ";<br>
     if(p->right!=NULL)<br>
           cout<<"\nRight Child: "<<p->right->key;<br>
     else<br>
           cout<<"\nThere is no right child of the node.  ";<br>
     if(p->left!=NULL)<br>
           cout<<"\nLeft Child: "<<p->left->key;<br>
     else<br>
           cout<<"\nThere is no left child of the node.  ";<br>
     cout<<"\nNode Deleted.";<br>
     if(p->left==NULL||p->right==NULL)<br>
          y=p;<br>
     else<br>
          y=successor(p);<br>
     if(y->left!=NULL)<br>
          q=y->left;<br>
     else<br>
     {<br>
          if(y->right!=NULL)<br>
               q=y->right;<br>
          else<br>
               q=NULL;<br>
     }<br>
     if(q!=NULL)<br>
          q->parent=y->parent;<br>
     if(y->parent==NULL)<br>
          root=q;<br>
     else<br>
     {<br>
         if(y==y->parent->left)<br>
            y->parent->left=q;<br>
         else<br>
            y->parent->right=q;<br>
     }<br>
     if(y!=p)<br>
     {<br>
         p->color=y->color;<br>
         p->key=y->key;<br>
     }<br>
     if(y->color=='b')<br>
         delfix(q);<br>
 }<br>
}

void RBtree::delfix(node *p)
{
node *s;
while(p!=root&&p->color=='b')
{
if(p->parent->left==p)
{
s=p->parent->right;
if(s->color=='r')
{
s->color='b';
p->parent->color='r';
leftrotate(p->parent);
s=p->parent->right;
}
if(s->right->color=='b'&&s->left->color=='b')
{
s->color='r';
p=p->parent;
}
else
{
if(s->right->color=='b')
{
s->left->color=='b';
s->color='r';
rightrotate(s);
s=p->parent->right;
}
s->color=p->parent->color;
p->parent->color='b';
s->right->color='b';
leftrotate(p->parent);
p=root;
}
}
else
{
s=p->parent->left;
if(s->color=='r')
{
s->color='b';
p->parent->color='r';
rightrotate(p->parent);
s=p->parent->left;
}
if(s->left->color=='b'&&s->right->color=='b')
{
s->color='r';
p=p->parent;
}
else
{
if(s->left->color=='b')
{
s->right->color='b';
s->color='r';
leftrotate(s);
s=p->parent->left;
}
s->color=p->parent->color;
p->parent->color='b';
s->left->color='b';
rightrotate(p->parent);
p=root;
}
}
p->color='b';
root->color='b';
}
}

void RBtree::leftrotate(node *p)
{
if(p->right==NULL)
return ;
else
{
node *y=p->right;
if(y->left!=NULL)
{
p->right=y->left;
y->left->parent=p;
}
else
p->right=NULL;
if(p->parent!=NULL)
y->parent=p->parent;
if(p->parent==NULL)
root=y;
else
{
if(p==p->parent->left)
p->parent->left=y;
else
p->parent->right=y;
}
y->left=p;
p->parent=y;
}
}
void RBtree::rightrotate(node *p)
{
if(p->left==NULL)
return ;
else
{
node *y=p->left;
if(y->right!=NULL)
{
p->left=y->right;
y->right->parent=p;
}
else
p->left=NULL;
if(p->parent!=NULL)
y->parent=p->parent;
if(p->parent==NULL)
root=y;
else
{
if(p==p->parent->left)
p->parent->left=y;
else
p->parent->right=y;
}
y->right=p;
p->parent=y;
}
}

node* RBtree::successor(node *p)
{
node *y=NULL;
if(p->left!=NULL)
{
y=p->left;
while(y->right!=NULL)
y=y->right;
}
else
{
y=p->right;
while(y->left!=NULL)
y=y->left;
}
return y;
}

void RBtree::disp()
{
display(root);
}
void RBtree::display(node *p)
{
if(root==NULL)
{
cout<<"\nEmpty Tree.";
return ;
}
if(p!=NULL)
{
cout<<"\n\t NODE: ";
cout<<"\n Key: "<key;
cout<<"\n Colour: ";
if(p->color=='b')
cout<<"Black";
else
cout<<"Red";
if(p->parent!=NULL)
cout<<"\n Parent: "<parent->key;
else
cout<<"\n There is no parent of the node. ";
if(p->right!=NULL)
cout<<"\n Right Child: "<right->key;
else
cout<<"\n There is no right child of the node. ";
if(p->left!=NULL)
cout<<"\n Left Child: "<left->key;
else
cout<<"\n There is no left child of the node. ";
cout<<endl;
if(p->left)
{
cout<<"\n\nLeft:\n";
display(p->left);
}

if(p->right)<br>
{<br>
 cout<<"\n\nRight:\n";<br>
             display(p->right);<br>
}<br>

 }<br>
}
void RBtree::search()
{
if(root==NULL)
{
cout<<"\nEmpty Tree\n" ;
return ;
}
int x;
cout<<"\n Enter key of the node to be searched: ";
cin>>x;
node *p=root;
int found=0;
while(p!=NULL&& found==0)
{
if(p->key==x)
found=1;
if(found==0)
{
if(p->key<x)
p=p->right;
else
p=p->left;
}
}
if(found==0)
cout<<"\nElement Not Found.";
else
{
cout<<"\n\t FOUND NODE: ";
cout<<"\n Key: "<key;
cout<<"\n Colour: ";
if(p->color=='b')
cout<<"Black";
else
cout<<"Red";
if(p->parent!=NULL)
cout<<"\n Parent: "<parent->key;
else
cout<<"\n There is no parent of the node. ";
if(p->right!=NULL)
cout<<"\n Right Child: "<right->key;
else
cout<<"\n There is no right child of the node. ";
if(p->left!=NULL)
cout<<"\n Left Child: "<left->key;
else
cout<<"\n There is no left child of the node. ";
cout<<endl;

 }<br>
}
int main()
{ int ch,y=0;
RBtree obj;
do
{
cout<<"\n\t RED BLACK TREE " ;
cout<<"\n 1. Insert in the tree ";
cout<<"\n 2. Delete a node from the tree";
cout<<"\n 3. Search for an element in the tree";
cout<<"\n 4. Display the tree ";
cout<<"\n 5. Exit " ;
cout<<"\nEnter Your Choice: ";
cin>>ch;
switch(ch)
{
case 1 : obj.insert();
cout<<"\nNode Inserted.\n";
break;
case 2 : obj.del();
break;
case 3 : obj.search();
break;
case 4 : obj.disp();
break;
case 5 : y=1;
break;
default : cout<<"\nEnter a Valid Choice.";
}
cout<<endl;

}while(y!=1);<br>
return 1;<br>
}


	
	
Tower of hanoi

  #include <iostream>
   using namespace std;
    void towers(int, char, char, char);
       int main()
  {
     int num;
     cout<<"Enter the number of disks : ";
     cin>>num;
       cout<<"The sequence of moves involved in the Tower of Hanoi are :\n";
       towers(num, 'A', 'C', 'B');
        return 0;
      }
     void towers(int num, char frompeg, char topeg, char auxpeg)
        {
     if (num == 1)
        {
    cout<<"Move disk 1 from peg "<<frompeg<<" to peg "<<topeg<<"\n";
    return;
         }
       towers(num - 1, frompeg, auxpeg, topeg);
         cout<<"Move disk "<<num<<" from peg "<<frompeg<<" to peg "<<topeg<<"\n";
          towers(num - 1, auxpeg, topeg, frompeg);
       }



