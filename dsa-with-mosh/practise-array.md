public class MyClass {
    public static void main(String args[]) {
      Array numbers =new Array(3);
      numbers.print();
    }
}
public class Array {
    private int[] items;
    
    public Array(int length) {
        items = new int[length];
    }
    public void print() { //print method aa samesanena
        for(int i = 0;i < items.length; i++)
        System.out.println(items[i]);
    }
}


public class MyClass {
    public static void main(String args[]) {
      Array numbers =new Array(3);
      numbers.print();
    }
}
public class Array {
    private int[] items;
    private int count;
    
    public Array(int length) {
        items = new int[length];
    }
    public void print() { //print method aa samesanena
        for(int i = 0;i < count; i++)
        System.out.println(items[i]);
    }
}

// this is the insert method

public class MyClass {
    public static void main(String args[]) {
      Array numbers =new Array(3);
      numbers.insert(10);
      numbers.insert(20);
      numbers.insert(30);
      numbers.print();
    }
}
public class Array {
    private int[] items;
    private int count;
    
    public Array(int length) {
        items = new int[length];
    }
    public void insert(int item) {
    //   and add the new item at the end of current Array
    items[count] = item;   //pass an index count and increment it
    count++;
    }
    public void print() { //print method aa samesanena
        for(int i = 0;i < count; i++)
        System.out.println(items[i]);
    }
}

//   if the array is full , resize it
public class MyClass {
    public static void main(String args[]) {
      Array numbers =new Array(3);
      numbers.insert(10);
      numbers.insert(20);
      numbers.insert(30);  //kuwo kale ayaa kuso daarnay si dynamically ayuu uso dabacay
      numbers.insert(40);
      numbers.print();
    }
}
public class Array {
    private int[] items;
    private int count;
    
    public Array(int length) {
        items = new int[length];
    }
    public void insert(int item) {
        //   if the array is full , resize it
        if(items.length == count) {
            // create a new array(twise the size)
            int[] newitems = new int[count * 2];
            // copy all the existing items
             for(int i = 0; i < count; i++)
             newitems[i] = items[i];
            // set "items" to this new array
            items = newitems;
        }
    //   and add the new item at the end of current Array
    items[count] = item;   //pass an index count and increment it
    count++;
    }
    public void print() { //print method aa samesanena
        for(int i = 0;i < count; i++)
        System.out.println(items[i]);
    }
}

// remove items to the arrays
public class MyClass {
    public static void main(String args[]) {
      Array numbers =new Array(3);
      numbers.insert(10);
      numbers.insert(20);
      numbers.insert(30);  //kuwo kale ayaa kuso daarnay si dynamically ayuu uso dabacay
      numbers.insert(40);
      numbers.removeAt(1);
      numbers.print();
    }
}
public class Array {
    private int[] items;
    private int count;
    
    public Array(int length) {
        items = new int[length];
    }
    public void insert(int item) {
        if(items.length == count) {
            int[] newitems = new int[count * 2];
             for(int i = 0; i < count; i++)
             newitems[i] = items[i];
            items = newitems;
        }
    //   and add the new item at the end of current Array
    items[count] = item;   //pass an index count and increment it
    count++;
    }
    public void removeAt(int index) {
        // valiadate the index
        if (index < 0 ||index >= count)  // if count is 4 it means the last index is 3
    }       throw new IllegalArgumentsException();
    
    // shift the item to the left to fill the hole 
    // [10, 20, 30, 40] we have this array
    // we have to remove index: 1 -- shifting everyitem one step to the left
    // we remove index: 20 and shifting the hole back into the next index
    // 1 <- 2
    for(int i = index; i < count; i++)
    // set items into left side
    items[i] = items[i + 1];
    
    count--;
    
    public void print() { //print method aa samesanena
        for(int i = 0;i < count; i++)
        System.out.println(items[i]);
    }
}