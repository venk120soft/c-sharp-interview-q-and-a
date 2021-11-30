```javascript
// Create Node Class

using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace LinkedListTutorial
{
    public class Node
    {
        //private fields
        private object _data;
        private Node _next;
        //constructor
        public Node(object data, Node next)
        {
            this._data = data;
            this._next = next;
        }
        //public Properties
        public object Data
        {
            get { return this._data; }
            set { this._data = value; }
        }
        public Node Next {
            get { return this._next;}
            set { this._next=value;}
        }

    }
}


// Then LinkedList Class

using System;
using System.Collections;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace LinkedListTutorial
{
    public class LinkedList1
    {
        //private Fields
        //reference to the first node in the list
        private Node _head;
        // mid element
        private Node _midElement;
        //How many items are currently in the list
        private int _count;
        //constructor
        //Creates a new linked list
        public LinkedList1()
        {
            this._head = null;
            this._count = 0;
        }
        //Properties
        //gets a count of objects in the list if the list is empty 
        public bool Empty { get { return this._count == 0; } }
        //gets a count of objects in the list
        public int Count { get { return this._count; } }
        //gets a mid element
        public Node MidElement { get { return this._midElement; } }
        #region Display elements in List
        public void printAllNodes()
        {
            Node current = _head;
            while (current != null)
            {
                Console.WriteLine(current.Data);
                current = current.Next;
            }
        }
        #endregion

        #region Add Functionality
        /// <summary>
        /// Add an object to the list at the specified index
        /// </summary>
        /// <param name="index">index to add object</param>
        /// <param name="obj">object to add</param>
        /// <returns>object added to the list</returns>
        public object AddAt(int index, object obj)
        {
            lock (this)
            {
                // Checking If the given index is greater than the size of the list then throw an exception
                if (index > _count || index < 0)
                    throw new ArgumentOutOfRangeException("Index:" + index);
                Node current = this._head;
                if (this.Empty || index == 0)
                    this._head = new Node(obj, this._head);
                else
                {
                    //this loop must not be while(current.Next!=null)
                    for (int i = 0; i < index - 1; i++)
                        current = current.Next;
                    current.Next = new Node(obj, current.Next);
                }
                _count++;   
            }
              
            return obj;
        }
        // Adding Without index
        public object Add(object obj)
        {
            return this.AddAt(_count, obj);
        }
        public object AddFirst(object data)
        {
            return new Node(data, _head);
        }

        public object AddLast(Object data)
        {
            if (_head == null)
                return new Node(data, null);
            else
            {
                Node current = _head;
                while (current.Next != null)
                    current = current.Next;
                return new Node(data, current.Next);
            }
        }
       
        #endregion
        #region Update old data with new data
        public bool Update(object oldItem, object newItem)
        {
            lock (this)
            {
                Node currentNode = this._head;
                while (currentNode != null)
                {
                    if (currentNode.Data.ToString().Equals(oldItem.ToString()))
                    {
                        currentNode.Data = newItem;
                        return true;
                    }
                    currentNode = currentNode.Next;
                }
                return false;
            }
        }
        #endregion
        #region Remove Functionality
        public object RemoveAt(int index)
        {
            if (index < 0)
                throw new ArgumentOutOfRangeException("Index: " + index);

            if (this.Empty)
                return null;
            if (index >= this._count)
                index = _count - 1;
            Node current = this._head;
            object result = null;

            if (index == 0)
            {
                result = current.Data;
                this._head = current.Next;
            }
            else
            {
                for(int i=0;i<index-1;i++)
                    current = current.Next;
                result = current.Next.Data;
                current.Next = current.Next.Next;
            }
            _count--;
            return result;
        }

        #endregion
        
        #region Finding Mid element
        public Node MidElement1(LinkedList1 lList){
            Node current = this._head;
            if(current==null ||lList.Count==1){
                return current;
            }
            for(int i=0;i<this._count/2;i++){
                current=current.Next;
            }
            _midElement=current;
            return _midElement;
        }
        public Node MidElement1(LinkedList1 lList){
            Node current = this._head;
            int count=0;
            if(current==null){
                return current;
            }
            _midElement =this._head;
            while(current !=null)
            {
                // this can be && also.
                // this will return true for all odd numbers
                if(count & 1){
                    _midElement = _midElement.Next;
                }
                count=count++;
                current= current.Next;
            }
            return _midElement;
        }
        #endregion
        
        #region Removing duplicate elements from 
        /// <summary>
        /// Algo : Using Hashing Effecient way O(n) for both sorted and unsorted list
        /// </summary>
        /// <param name="list"></param>
        /// <returns></returns>
        public void RemoveDuplicatesFromList(LinkedList1 list)
        {
            if (list.Count < 2)
            {
                return;
            }
            ArrayList tempList = new ArrayList();
            Node current = this._head;
            Node prev = null;
            while (current != null)
            {
                if (tempList.Contains(current.Data))
                {
                    // We have to delete the element from the linked list
                    prev.Next = current.Next;
                    _count--;
                }
                else
                {
                    // We have to add the element
                    tempList.Add(current.Data);
                    prev = current;
                }
                current = current.Next;
            }
        }
        #endregion
        #region Reversing the linked list
        public LinkedList1 Reverse(LinkedList1 lList)
        {
            if(lList.Empty || IList.Count==1)
                return lList;
            Node currentNode= lList._head;
            Node nextNode,prevNode = null;
            while(currentNode!=null)
            {
                nextNode = currentNode.Next; // temp variable
                currentNode.Next = prevNode; // Assigning the previous node to next node
                prevNode = currentNode; // Assigning the current node to previous which is head now
                currentNode = nextNode; // Assigning temp variable to the current node
            }

            lList._head = prevNode;
            return IList;
        }
        
        //In this way, the head of the linked list will point to the last node of the linked list. Also, each node’s “Next” and “Previous” properties need to be swapped too.
        public void ReverseLinkedList(LinkedList linkedList)
        {
            LinkedListNode start = linkedList.Head;
            LinkedListNode temp = null;
            while (start != null)
            {
                temp = start.Next;
                start.Next = start.Previous;
                start.Previous = temp;
                if (start.Previous == null)
                {
                    linkedList.Head = start;
                }
                start = start.Previous;
            }
        }
        #endregion
        
        public void Clear()
        {
            // to clear the list
            this._head = null;
            this._count = 0;
        }

        public int IndexOf(object obj)
        {
            Node current = this._head;
            for (int i = 0; i < this._count; i++)
            {
                if (current.Data.Equals(obj))
                    return i;
                current = current.Next;
            }
            return -1;
        }
        public bool Contains(object obj)
        {
            return this.IndexOf(obj) > -1;//!=-1 (or) >=0
        }
        public object Get(int index)
        {
            if (index < 0)
                throw new ArgumentOutOfRangeException("Index: " + index);
            if (this.Empty)
                return null;
            if (index >= this._count)
                index = _count - 1;
            Node current = this._head;
            for (int i = 0; i < index; i++)
                current = current.Next;

            return current.Data;

        }
        public object this[int index]
        {
            get { return this.Get(index); }
        }
        
    }

}

// In Program.cs

using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace LinkedListTutorial
{
    class Program
    {
        static void Main(string[] args)
        {
            LinkedList1 L1 = new LinkedList1();
            L1.Add("MY Name");
            L1.Add("is");
            L1.Add("Venkatesh");
            L1.Add("I am a");
            L1.Add("Software Engineer");

            L1.AddAt(0,"Active");            
            L1.AddAt(1, "In");

            L1.printAllNodes();
            
            Console.WriteLine(L1.Update("is", "are"));
            Console.WriteLine("After Updation");
            L1.printAllNodes();

            Console.WriteLine(L1.Contains("iS"));
            Console.WriteLine(L1.Contains("is"));
            Console.WriteLine(L1.IndexOf("is"));
            Console.WriteLine(L1.Get(5));

            L1.RemoveAt(6);
            Console.WriteLine("After romoving  item in the list");
            L1.printAllNodes();
            
            L1.Reverse(L1);
            Console.WriteLine(L1.Count);
            Console.WriteLine("reverse List");
            L1.printAllNodes();
            
            L1.Clear();
            
            Console.WriteLine(L1.Count);     
            Console.ReadLine();
        }
    }
}
```
