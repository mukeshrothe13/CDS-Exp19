# AIM

To learn about queues in C++.

## Problem Statement

Write a program to perform enqueue and dequeue operations in C++.

## Theory

Queues are a type of container adaptor that operate on a first in, first out (FIFO) principle. In a queue, elements are inserted at the back (end) and removed from the front. Queues typically use an encapsulated object, such as a deque or list (sequential container class), as their underlying container, providing a specific set of member functions for accessing and manipulating elements.

## Program Code
```javascript
//Mukesh Rothe 23070123089
#include <iostream>
using namespace std;
#define size 5
#define ERROR -9999
class Queue{
    int rear, front, ar[size];
    public:
    Queue(){
        rear = -1;
        front = -1;
        ar[0]=0;
    }
    void enqueue(int);
    int dequeue();
    void disp();
};
void Queue :: enqueue(int num){
    if (rear == (size+1)){
        cout<<"Queue is full"<<endl;
    }
    else{
        if(front == -1){
            ar[++front]=num;
            rear++;
        }
        else{
            ar[++rear]=num;
        }
    }

    }
int Queue ::dequeue(){
    if(front ==-1 || front ==(rear+1)){
        cout<<"Queue is empty"<<endl;
        return ERROR;
    }
    else{
        int val = ar[front++];
        return val;
    }
}
void Queue :: disp(){
    if(front ==-1 || front ==(rear+1)){
        cout<<"Quee=ue is empty"<<endl;
        return;
    }
    else{
        int i = front ;
        while (i!=(rear+1)){
            cout<<ar[i];
            i++;
        }
    }
}

int main(){
        Queue q1;
        q1.enqueue(4);
        q1.enqueue(8);
        q1.enqueue(3);
        q1.disp();
        int val = q1.dequeue();
        cout<<endl<<"Deleted element: "<<val<<endl;
        q1.disp();

}
```

## Output

![Screenshot 2024-10-21 195008](https://github.com/user-attachments/assets/3c8f2692-9529-47a8-9cfd-c29ede7773d9)
## Conclusion

We learned how to implement enqueue and dequeue operations in C++.
