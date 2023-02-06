public class Linkedlist {

    private class Node {
        private int value;
        private Node next;
        public Node(int value) {
        this.value = value;
    }

    private Node first;
    private Node second;

//    addfirst
//    addlast
//    deletefirst
//    deletelast
//    contains
//    indexof

    public Node addlast(int item) {
        var node = new Node(item);

        if (first == null) {
            first = node;
            second = node;
        }
        else {
            second.next = node;
            second = node;
        }
        }
    }
}

public class Main {
    public static void main(String[] args) {
//        Linkedlist list = new Linkedlist();
//        var list = new Linkedlist();  isticmal kan si aad uga dheeratid line ka hore si uu uso lablabanin linkedlist ga
        var list = new Linkedlist();
        list.addLast(10);
        list.addLast(20);
        list.addLast(30); 
        list.print();
    }
}

