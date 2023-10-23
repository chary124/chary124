 package p1;

public class SingleLinkedList {
	//class SingleLinkedList{
	     private ListNode head ;
	   private static  class ListNode{
	         private ListNode next;
	         private int data;
	         public ListNode(int data)
	         {
	             this.data = data;
	             this.next = null;
	         }
	     }
	   public void display()
	   {
		   ListNode current = head;
		   while(current!=null)
		   {
			   System.out.print(current.data + " -> ");
			   current = current.next;
		   }
		   System.out.println(" null");
	   }
	   public int length() {
		   if(head==null)
		   {
			   return 0;
			   
		   }
		   int count = 0;
		   ListNode current = head;
		   while(current!=null)
		   {
			   count++;
			   current = current.next;
		   }
		   return count;
	   }
	   public void insertfirst(int value)
	   {
		   ListNode newnode =new ListNode(value);
		   newnode.next = head;
		   head = newnode;
	   }
	   public void insertlast(int value)
	   {
		   ListNode newnode = new ListNode(value);
		   if(head==null)
		   {
			   head = newnode;
			   return;
			   
		   }
		   ListNode current = head;
		  while(null!=current.next)
		  {
			  current = current.next;
		  }
		  current.next = newnode;
	   }
	   public void insertpos(int position, int value)
	   {
		   ListNode node = new ListNode(value);
		   if(position==1)
		   {
			   node.next = head;
			   head = node;
		   }
		   ListNode previous = head;
		   int count = 1;
		   while(count<position-1)
		   {
			   previous = previous.next;
			   count++;
		   }
		   ListNode current = previous.next;
		   node.next  = current;
		   previous.next = node;
	   }
	   public ListNode deletefirst()
	   {
		   if(head==null)
		   {
			   return null;
		   }
		   else
		   {
			   ListNode temp = head;
			   head = head.next;
			   
			   temp.next = null;
 			   return temp;
		   }
	   }
	   
	   public ListNode reverse()
	   {
		   ListNode current = head;
		   ListNode previou = null;
		   ListNode next = null;
		   while(current!=null)
		   {
			   next = current.next;
			   current.next = previou;
			   previou = current;
		        current = next;
		   }
		   return previou;
				  
	   }
	   public ListNode deletelast()
	   {
		   if(head==null||head.next==null)
		   {
			   return head;
		   }
		   ListNode current = head;
		   ListNode previous = null;
		   while(current.next!=null)
		   {
			   previous = current;
			   current = current.next;
			   
		   }
		   previous.next = null;
		   return current;
	   }
	   public void delete(int position)
	   {
		   if(position==1)
		   {
			   head = head.next;
		   }
		   else {
			   ListNode previous = head;
			 int  count = 1;
			   while(count<position-1)
			   {
				   previous = previous.next;
				   count++;
			   }
			   ListNode current = previous.next;
			   previous.next = current.next;
		   }
	   }
	 
	 
		public static void main(String[] args) {
		SingleLinkedList sll = new SingleLinkedList();
		//	sll.head = new ListNode(10);
		//	ListNode secound = new ListNode(89);
		//	ListNode third = new ListNode(78);
		//	ListNode fourth = new ListNode(23);
			
		//	sll.head.next = secound;
		//	secound.next = third ;
		//	third.next = fourth;
			
		//	sll.display();
		sll.insertlast(23);
		sll.insertlast(34);
		sll.insertlast(78);
		sll.insertlast(89);
		sll.insertlast(79);
		sll.insertfirst(6);
		sll.insertfirst(23);
		sll.insertpos(2,100);
		sll.insertpos(8,202);
 		sll.display();
		System.out.println(sll.deletefirst().data);
         sll.display();
        // ListNode reverselist = sll.reverse(head);
        // sll.display(reverselist);
        // sll.deletelast();
         System.out.println(sll.deletelast().data);
         sll.display();
         sll.delete(5);
         sll.display();
 		 int l =sll.length();
			System.out.println(" length of the single linkes list " + l );
			
 		}
	


}
