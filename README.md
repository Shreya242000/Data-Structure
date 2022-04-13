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
	
#include<iostream>
#include<cstdio>
#include<cstdlib>
using namespace std;
struct node
{
    int info;
    struct node *next;
    struct node *prev;
}*start;
class double_llist
{
    public:
        void create_list(int value);
        void add_begin(int value);
        void add_after(int value, int position);
        void delete_element(int value);
        void search_element(int value);
        void display_dlist();
        void count();
        void reverse();
        double_llist()
        {
            start = NULL;  
        }
};
 int main()
{
    int choice, element, position;
    double_llist dl;
    while (1)
    {
        cout<<endl<<"----------------------------"<<endl;
        cout<<endl<<"Operations on Doubly linked list"<<endl;
        cout<<endl<<"----------------------------"<<endl;        
        cout<<"1.Create Node"<<endl;
        cout<<"2.Add at begining"<<endl;
        cout<<"3.Add after position"<<endl;
        cout<<"4.Delete"<<endl;
        cout<<"5.Display"<<endl;
        cout<<"6.Count"<<endl;
        cout<<"7.Reverse"<<endl;
        cout<<"8.Quit"<<endl;
        cout<<"Enter your choice : ";
        cin>>choice;
        switch ( choice )
        {
        case 1:
            cout<<"Enter the element: ";
            cin>>element;
            dl.create_list(element);
            cout<<endl;
            break;
        case 2:
            cout<<"Enter the element: ";
            cin>>element;
            dl.add_begin(element);
            cout<<endl;
            break;
        case 3:
            cout<<"Enter the element: ";
            cin>>element;
            cout<<"Insert Element after postion: ";
            cin>>position;
            dl.add_after(element, position);
            cout<<endl;
            break;
        case 4:
            if (start == NULL)
            {                      
                cout<<"List empty,nothing to delete"<<endl;  
                break;
            }
            cout<<"Enter the element for deletion: ";
            cin>>element;
            dl.delete_element(element);
            cout<<endl;
            break;
        case 5:
            dl.display_dlist();
            cout<<endl;
            break;
        case 6:
            dl.count();
            break;    
        case 7:
            if (start == NULL)
            {
                cout<<"List empty,nothing to reverse"<<endl;
                break;
            }
            dl.reverse();
            cout<<endl;
            break;
        case 8:
            exit(1);
        default:
            cout<<"Wrong choice"<<endl;
        }
    }
    return 0;
}
 void double_llist::create_list(int value)
{
    struct node *s, *temp;
    temp = new(struct node);
    temp->info = value;
    temp->next = NULL;
    if (start == NULL)
    {
        temp->prev = NULL;
        start = temp;
    }
    else
    {
        s = start;
        while (s->next != NULL)
            s = s->next;
        s->next = temp;
        temp->prev = s;
    }
}
 void double_llist::add_begin(int value)
{
    if (start == NULL)
    {
        cout<<"First Create the list."<<endl;
        return;
    }
    struct node *temp;
    temp = new(struct node);
    temp->prev = NULL;
    temp->info = value;
    temp->next = start;
    start->prev = temp;
    start = temp;
    cout<<"Element Inserted"<<endl;
}
void double_llist::add_after(int value, int pos)
{
    if (start == NULL)
    {
        cout<<"First Create the list."<<endl;
        return;
    }
    struct node *tmp, *q;
    int i;
    q = start;
    for (i = 0;i < pos - 1;i++)
    {
        q = q->next;
        if (q == NULL)
        {
            cout<<"There are less than ";
            cout<<pos<<" elements."<<endl;
            return;
        }
    }
    tmp = new(struct node);
    tmp->info = value;
    if (q->next == NULL)
    {
        q->next = tmp;
        tmp->next = NULL;
        tmp->prev = q;      
    }
    else
    {
        tmp->next = q->next;
        tmp->next->prev = tmp;
        q->next = tmp;
        tmp->prev = q;
    }
    cout<<"Element Inserted"<<endl;
}
 void double_llist::delete_element(int value)
{
    struct node *tmp, *q;
        if (start->info == value)
    {
        tmp = start;
        start = start->next;  
        start->prev = NULL;
        cout<<"Element Deleted"<<endl;
        free(tmp);
        return;
    }
    q = start;
    while (q->next->next != NULL)
    {  
               if (q->next->info == value)  
        {
            tmp = q->next;
            q->next = tmp->next;
            tmp->next->prev = q;
            cout<<"Element Deleted"<<endl;
            free(tmp);
            return;
        }
        q = q->next;
    }
        if (q->next->info == value)    
    {
        tmp = q->next;
        free(tmp);
        q->next = NULL;
        cout<<"Element Deleted"<<endl;
        return;
    }
    cout<<"Element "<<value<<" not found"<<endl;
}
 void double_llist::display_dlist()
{
    struct node *q;
    if (start == NULL)
    {
        cout<<"List empty,nothing to display"<<endl;
        return;
    }
    q = start;
    cout<<"The Doubly Link List is :"<<endl;
    while (q != NULL)
    {
        cout<<q->info<<" <-> ";
        q = q->next;
    }
    cout<<"NULL"<<endl;
}
 void double_llist::count()
{
    struct node *q = start;
    int cnt = 0;
    while (q != NULL)
    {
        q = q->next;
        cnt++;
    }
    cout<<"Number of elements are: "<<cnt<<endl;
}
 void double_llist::reverse()
{
    struct node *p1, *p2;
    p1 = start;
    p2 = p1->next;
    p1->next = NULL;
    p1->prev = p2;
    while (p2 != NULL)
    {
        p2->prev = p2->next;
        p2->next = p1;
        p1 = p2;
        p2 = p2->prev;
    }
    start = p1;
    cout<<"List Reversed"<<endl;
}

**OUTPUT**
![image](https://user-images.githubusercontent.com/97940851/163158588-ac272929-9123-48b6-a3f3-985dab283e3f.png)

![image](https://user-images.githubusercontent.com/97940851/163158632-88c8b4b5-8b2f-43e4-8d2b-40e6083acfaf.png)
	
![image](https://user-images.githubusercontent.com/97940851/163158721-ee856b26-f0e3-4939-8820-680001504ad9.png)

![image](https://user-images.githubusercontent.com/97940851/163158818-aa639f17-3f7d-485b-93a6-ded079f69142.png)
	
![image](https://user-images.githubusercontent.com/97940851/163158868-be928ce5-f8a7-4ce4-832f-99efec148d88.png)
	




