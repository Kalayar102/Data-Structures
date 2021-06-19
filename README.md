# Data-Structures

package src.datastucters;

public class IntegerList {

        // Properties
// Data Source - sourceArray
//  List size -size
        private int[] sourceArray;
        private int size;

        //Constants
        private static int DEFAULT_SIZE = 10;

        //constructors
//  IntegerList(size)
//  IntegerList()
        public IntegerList() {
            size = 0;
            sourceArray = new int[size];
//      size = 10
        }

        public IntegerList( int size){
            this.size = 0;
            sourceArray = new int[size];

        }

        //Functionally
        //add(item)
        public void add ( int item){
            checkSize();
            size = size + 1;
            sourceArray[size - 1] = item;


        }

        //getFirst()
        public int getFirst () {
            if (size > 0) {
                return sourceArray[0];

            } else {
                return -1;
            }

        }

        //getLast()
        public int getLast (){
            if (size > 0) {
                return sourceArray[size - 1];
            } else {
                return -1;
            }

        }


        //get index
        public int getIndex ( int index){
            if (index < sourceArray.length) {
                return sourceArray[index];

            } else {
                return -1;
            }
        }
        //get Size()
        public int getSize () {
            return size;

        }
        //set(index , value)
        public void set ( int index, int value){
            if (index < size) {
                sourceArray[index] = value;
            }
        }

        // helper methods
        public void checkSize () {
            if (this.size + 1 > sourceArray.length) {
//            make new array with larger size
                sourceArray = makeNewArray();
            }
        }

        public int[] makeNewArray () {
//            size - 5
//            size - 15
            int[] newArray = new int[size + 10];
//        sourceArray -> newArray
//        Copy Data`
            for (int i = 0; i < sourceArray.length; i++) {
                newArray[i] = sourceArray[i];
            }
            return newArray;

        }


        public void removeItem ( int index){
//    cut
//   remove
//    join

            if (index < size) {
                if (index == size - 1) {
                    sourceArray[0] = -1;
                } else {
                    int[] newArray = new int[sourceArray.length];
//                    3 <- remove item at 3
//                     before the index
                    for (int i = 0; i < index; i++)
                        newArray[i] = sourceArray[i];
                }
//                Replace items after the index
                for (int i = index + 1; i < size; i++) {
                    newArray[i - 1] = sourceArray[i];

                }
                sourceArray = newArray;
            }
        }
//        Override toString

        @Override
        public String toString () {
            String ListItems = "[";
            for (int i = 0; i < size; i++) {
                listItems += sourceArray[i];
                if (i != size - 1) {
                    listItems += " , ";

                }
            }
            listItems += "]";
            return listItems;
        }
}
    
    
    
    
    
    
    //ListDemo
    
    package src;

import src.datastuctures.IntegerLinkedList;

public class DemoList {
    public static void main(String[] args){
        IntegerList list = new IntergerList();

        list.add(10);   //0
         list.add(12);  //1
        list.add(145);  //2
        list.add(41);   //3
        list.add(343);  //4
        list.add(343);  //5
        list.add(343);  //6
        list.add(344);  //7
        System.out.println("Item at index 3 :" + list.get(3));
        System.out.println("First item : " + list.getFirst());
        System.out.println("last item :" + list.getfast());
        System.out.println("Size :" + list.geSize());


 }
}

    



