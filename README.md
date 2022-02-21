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



