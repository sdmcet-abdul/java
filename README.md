# java


import java.util.NoSuchElementException;
import java.util.Scanner;

/*
 * To change this license header, choose License Headers in Project Properties.
 * To change this template file, choose Tools | Templates
 * and open the template in the editor.
 */

/**
 *
 * @author Asus
 */
public class arraystack1 {
     protected int arr[];
     protected int top, size, len;
     
    public arraystack1(int n)
    {
        size = n;
        len = 0;
        arr = new int[size];
        top = -1;
    }
     public boolean isEmpty()
     {
         return top==-1;
         
     }
     
     public boolean isFull()
     {
      return top==size-1;         
     }
     
     public void push(int item)
     {
         if(isFull())
         
         {
             throw new IndexOutOfBoundsException("Overflow Exception");
         }
     
         arr[++top]=item;
         len++;
     }
     
      public int pop()
    {
        if( isEmpty() )
            throw new NoSuchElementException("Underflow Exception");
        len-- ;
        return arr[top--]; 
    }

     public void display()
    {
        System.out.print("\nStack = ");
        if (len == 0)
        {
            System.out.print("Empty\n");
            return ;
        }
        for (int i = top; i >= 0; i--)
            System.out.print(arr[i]+" ");
        System.out.println();
    }  

  
   
     
     
     
 
}



class implementStack
{
    public static void main (String args[])
    {
     Scanner sc=new Scanner(System.in);
     System.out.println("stack test");
        
    
     System.out.println("enter the size of stack\n");
     int n=sc.nextInt();
     arraystack1 stk = new arraystack1(n);
     for(;;)
     {
     System.out.println("Stack Operations ");
     System.out.println("1:push ");
     System.out.println("2:pop");
     System.out.println("3:display ");
     System.out.println("4:isEmpty ");
     System.out.println("5:isfull ");
     System.out.println("enter the choice");
     int choice=sc.nextInt();
     
      switch(choice)
        {
         case 1:System.out.println("enter the element to push\n");  
               int x=sc.nextInt();
               stk.push(x);
               break;
          
         case 2:stk.pop();
                break;
         case 3:stk.display();
                break;
         default:System.exit(0);
          
        }
     }
    }
}
