*/
# Doubly-linked-list-basic-operation
doubly-linked list Write a menu-driven program to do the following operation in a doubly-linked list :
1. Insertion: Adds an element to a sorted linked list
2. Deletion: to delete a specific node.
3. Search: returns true if the node is present in the linked list and false otherwise.
4. Display: to display all elements of a linked list
*/

       package javaapplication41;
                import java.util.Scanner;
      public class DoublyLinkedList {  
       class Node{  
        int data;  
        Node previous;  
     Node next;  
        Node head;
        public Node(int data) {  
            this.data = data;  
        }  
    }   
    Node head, tail = null;  
    public void addNode(int data) {  
        Node newNode = new Node(data);  
     if(head == null) {  
            head = tail = newNode;  
            head.previous = null;  
            tail.next = null; 
     }  
        else {  
            tail.next = newNode;  
            newNode.previous = tail;  
            tail = newNode;  
            tail.next = null;  
        }  
    }  
    public void display() {    
     Node current = head;  
        if(head == null) {  
            System.out.println("List is empty");  
            return;  
        }  
        System.out.println("Nodes of doubly linked list: ");  
        while(current != null) {    
            System.out.print(current.data + " ");  
            current = current.next;  
        }  
    }
    public void searchNode( int value) {  
        int i = 1;  
        boolean saif = false; 
     Node current = head;  
        if(head == null) {  
            System.out.println("List is empty");  
            return;  
        } 
      while(current != null) {   
            if(current.data == value) {  
                saif = true;  
                System.out.println("True");  
            }
                else
                 System.out.println("False");  
                break;        
                }}  
    public void sortList() {  
        Node current = null, index = null;  
        int temp;  
        if(head == null) {  
            return;  
        }  
        else {  
            for(current = head; current.next != null; current = current.next) {  
            for(index = current.next; index != null; index = index.next) {  
            if(current.data > index.data) {  
                        temp = current.data;  
                        current.data = index.data;  
                        index.data = temp;   }}}}}  
    public void deleteNode(int n) {  
         if(head == null ) {
                 return;
             }
        else {    
            Node current = head;  
              int pos =n;  
            for(int i = 1; i < pos; i++){  
                current = current.next;  
            }  
            if(current == head) {  
                head = current.next;  
            }  
             else if(current == tail) {  
                tail = tail.previous;  
            }  
            else {  
                current.previous.next = current.next;  
                current.next.previous = current.previous;  
            }  
             current = null;  
        }  
    }  
    public static void main(String[] args) {  
        Node head = null; 
    
        Scanner scan = new Scanner(System.in);
        DoublyLinkedList saif1 = new DoublyLinkedList();  
         System.out.println("Welcome dear");          
        char ch;
        do
        {   
            System.out.println("NOTE !! all elemments will be SORTED");
            System.out.println("just choose the number of the operation you want to apply");
            System.out.println("\nDoubly Linked List Operations\n");
            System.out.println("1. Insert an element");
            System.out.println("2. Delete an element");
            System.out.println("3. Search for an item if it is present");
            System.out.println("4. Display elements");
             int choice = scan.nextInt(); 
              
              switch (choice)
            {
                case 1 : 
                System.out.println("Enter integer element ");
                saif1.addNode( scan.nextInt() );  
                 break;                          
                case 2 : 
                System.out.println("Delete an element");
                saif1.deleteNode( scan.nextInt() );                     
                break;              
                 case 3 : 
                System.out.println("Enter integer to know  if it is present ");
                saif1.searchNode(scan.nextInt());
                break;    
                 case 4:   
                System.out.println("This is The Doubly linked list you made");
                saif1.display();    
                break;  
              }
               saif1.sortList();
               System.out.println("\nDo you want to continue (Type y or n) \n");
               ch = scan.next().charAt(0);   
        } while (ch == 'Y'|| ch == 'y' );
        
      }  
     }
