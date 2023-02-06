package com.rockthejvm;

import java.sql.Array;
import java.util.Arrays;
import java.util.LinkedList;

public class dsaMosh {
    public static void main(String[] args) {
        LinkedList list = new LinkedList();
        list.addLast(10);
        list.addLast(20);
        list.addLast(30);
        list.addFirst(50);
        list.removeFirst();
        list.removeLast();
        System.out.println(list.contains(10));
        System.out.println(list.indexOf(10));
        System.out.println(list.size());
        var Array = list.toArray();
        System.out.println(Arrays.toString(Array));
        System.out.println(list);
    }
}
