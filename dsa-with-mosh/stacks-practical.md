Implementing Stack using Arrays:


/* Java program to implement basic stack
operations */
class Stack {
	static final int MAX = 1000;
	int top;
	int a[] = new int[MAX]; // Maximum size of Stack

	boolean isEmpty()
	{
		return (top < 0);
	}
	Stack()
	{
		top = -1;
	}

	boolean push(int x)
	{
		if (top >= (MAX - 1)) {
			System.out.println("Stack Overflow");
			return false;
		}
		else {
			a[++top] = x;
			System.out.println(x + " pushed into stack");
			return true;
		}
	}

	int pop()
	{
		if (top < 0) {
			System.out.println("Stack Underflow");
			return 0;
		}
		else {
			int x = a[top--];
			return x;
		}
	}

	int peek()
	{
		if (top < 0) {
			System.out.println("Stack Underflow");
			return 0;
		}
		else {
			int x = a[top];
			return x;
		}
	}
	
	void print(){
	for(int i = top;i>-1;i--){
	System.out.print(" "+ a[i]);
	}
}
}

// Driver code
class Main {
	public static void main(String args[])
	{
		Stack s = new Stack();
		s.push(10);
		s.push(20);
		s.push(30);
		System.out.println(s.pop() + " Popped from stack");
		System.out.println("Top element is :" + s.peek());
		System.out.print("Elements present in stack :");
		s.print();
	}
}
Output
10 pushed into stack
20 pushed into stack
30 pushed into stack
30 Popped from stack
Top element is : 20
Elements present in stack : 20 10 



Implementing Stack using Linked List:

// Java Code for Linked List Implementation

public class StackAsLinkedList {

	StackNode root;

	static class StackNode {
		int data;
		StackNode next;

		StackNode(int data) { this.data = data; }
	}

	public boolean isEmpty()
	{
		if (root == null) {
			return true;
		}
		else
			return false;
	}

	public void push(int data)
	{
		StackNode newNode = new StackNode(data);

		if (root == null) {
			root = newNode;
		}
		else {
			StackNode temp = root;
			root = newNode;
			newNode.next = temp;
		}
		System.out.println(data + " pushed to stack");
	}

	public int pop()
	{
		int popped = Integer.MIN_VALUE;
		if (root == null) {
			System.out.println("Stack is Empty");
		}
		else {
			popped = root.data;
			root = root.next;
		}
		return popped;
	}

	public int peek()
	{
		if (root == null) {
			System.out.println("Stack is empty");
			return Integer.MIN_VALUE;
		}
		else {
			return root.data;
		}
	}

	// Driver code
	public static void main(String[] args)
	{

		StackAsLinkedList sll = new StackAsLinkedList();

		sll.push(10);
		sll.push(20);
		sll.push(30);

		System.out.println(sll.pop()
						+ " popped from stack");

		System.out.println("Top element is " + sll.peek());
	}
}
Output
10 pushed to stack
20 pushed to stack
30 pushed to stack
30 popped from stack
Top element is 20
Elements present in stack : 20 10 


Display Operation:

// Java program to Implement a stack
// using singly linked list
// import package
import static java.lang.System.exit;

// Driver code
class GFG {
	public static void main(String[] args)
	{
		// create Object of Implementing class
		StackUsingLinkedlist obj
			= new StackUsingLinkedlist();
		// insert Stack value
		obj.push(11);
		obj.push(22);
		obj.push(33);
		obj.push(44);

		// print Stack elements
		obj.display();

		// print Top element of Stack
		System.out.printf("\nTop element is %d\n",
						obj.peek());

		// Delete top element of Stack
		obj.pop();
		obj.pop();

		// print Stack elements
		obj.display();

		// print Top element of Stack
		System.out.printf("\nTop element is %d\n",
						obj.peek());
	}
}

// Create Stack Using Linked list
class StackUsingLinkedlist {

	// A linked list node
	private class Node {

		int data; // integer data
		Node link; // reference variable Node type
	}
	// create global top reference variable global
	Node top;
	// Constructor
	StackUsingLinkedlist() { this.top = null; }

	// Utility function to add an element x in the stack
	public void push(int x) // insert at the beginning
	{
		// create new node temp and allocate memory
		Node temp = new Node();

		// check if stack (heap) is full. Then inserting an
		// element would lead to stack overflow
		if (temp == null) {
			System.out.print("\nHeap Overflow");
			return;
		}

		// initialize data into temp data field
		temp.data = x;

		// put top reference into temp link
		temp.link = top;

		// update top reference
		top = temp;
	}

	// Utility function to check if the stack is empty or
	// not
	public boolean isEmpty() { return top == null; }

	// Utility function to return top element in a stack
	public int peek()
	{
		// check for empty stack
		if (!isEmpty()) {
			return top.data;
		}
		else {
			System.out.println("Stack is empty");
			return -1;
		}
	}

	// Utility function to pop top element from the stack
	public void pop() // remove at the beginning
	{
		// check for stack underflow
		if (top == null) {
			System.out.print("\nStack Underflow");
			return;
		}

		// update the top pointer to point to the next node
		top = (top).link;
	}

	public void display()
	{
		// check for stack underflow
		if (top == null) {
			System.out.printf("\nStack Underflow");
			exit(1);
		}
		else {
			Node temp = top;
			while (temp != null) {

				// print node data
				System.out.print(temp.data);

				// assign temp link to temp
				temp = temp.link;
				if(temp != null)
					System.out.print(" -> ");
			}
		}
	}
}
output
44 -> 33 -> 22 -> 11
Top element is 44
22 -> 11

Time Complexity: O(1), for all push(), pop(), and peek(), as we are not performing any kind of traversal over the list. We perform all the operations through the current pointer only.
Auxiliary Space: O(N), where N is the size of the stack
Top element is 22


How to Create a Stack?
Stack<E> stack = new Stack<E>();

Here E is the type of Object.

// Java code for stack implementation

import java.io.*;
import java.util.*;

class Test
{
	// Pushing element on the top of the stack
	static void stack_push(Stack<Integer> stack)
	{
		for(int i = 0; i < 5; i++)
		{
			stack.push(i);
		}
	}
	
	// Popping element from the top of the stack
	static void stack_pop(Stack<Integer> stack)
	{
		System.out.println("Pop Operation:");

		for(int i = 0; i < 5; i++)
		{
			Integer y = (Integer) stack.pop();
			System.out.println(y);
		}
	}

	// Displaying element on the top of the stack
	static void stack_peek(Stack<Integer> stack)
	{
		Integer element = (Integer) stack.peek();
		System.out.println("Element on stack top: " + element);
	}
	
	// Searching element in the stack
	static void stack_search(Stack<Integer> stack, int element)
	{
		Integer pos = (Integer) stack.search(element);

		if(pos == -1)
			System.out.println("Element not found");
		else
			System.out.println("Element is found at position: " + pos);
	}


	public static void main (String[] args)
	{
		Stack<Integer> stack = new Stack<Integer>();

		stack_push(stack);
		stack_pop(stack);
		stack_push(stack);
		stack_peek(stack);
		stack_search(stack, 2);
		stack_search(stack, 6);
	}
}
Output:

Pop Operation:
4
3
2
1
0
Element on stack top: 4
Element is found at position: 3
Element not found

Performing various operations on Stack class
1. Adding Elements: In order to add an element to the stack, we can use the push() method. This push() operation place the element at the top of the stack.

// Java program to add the
// elements in the stack
import java.io.*;
import java.util.*;

class StackDemo {

	// Main Method
	public static void main(String[] args)
	{

		// Default initialization of Stack
		Stack stack1 = new Stack();

		// Initialization of Stack
		// using Generics
		Stack<String> stack2 = new Stack<String>();

		// pushing the elements
		stack1.push("4");
		stack1.push("All");
		stack1.push("Juweria");

		stack2.push("Somalian");
		stack2.push("Ameriacan");
		stack2.push("canadian");

		// Printing the Stack Elements
		System.out.println(stack1);
		System.out.println(stack2);
	}
}
Output:

[4, All, Juweria]
[Somalian, Ameriacan, canadian]