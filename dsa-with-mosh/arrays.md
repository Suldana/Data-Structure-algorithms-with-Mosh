// package of arrays
public class Array{
    private int[] items;
    
    public Array(int length) {
        items = new int[length];
    }
    public void print() {
        for(int i = 0; i < items.length; i++)
        System.out.println(items[i]);
    }
}



public class MyClass {
    public static void main(String args[]) {
      Array number[] = new Array[3];
      number.print();
    }
}

// output : 0 0 0 
// arrays oo empty ah ayaa rabna inaa soo dabacano si aan saas u sameeno waa inaan count kuso darna look
// we need another field to keep tract to the number of items in this arrays, we can not rely on the items.length
// because this is the memory we are allocating , initially we may allocate the memory 40 55 items, nut we can insert two items in this arraye
// every time we insert new item, we need to track of that number

// package of arrays
public class Array{
    private int[] items;
    private int count;
    
    public Array(int length) {
        items = new int[length];
    }
    public void print() {
        for(int i = 0; i < count; i++)
        System.out.println(items[i]);
    }
}
public class MyClass {
    public static void main(String args[]) {
      Array number[] = new Array[3];
      number.print();
    }
}

// package of arrays
public class Array{
    private int[] items;
    private int count;
    
    public Array(int length) {
        items = new int[length];
    }
    public void 
    public void print() {
        for(int i = 0; i < count; i++)
        System.out.println(items[i]);
    }
}