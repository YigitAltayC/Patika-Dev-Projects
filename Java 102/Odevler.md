# Kendi Liste Sınıfımızı Yazmak

```Java


public class MyList<T> {

    private int index = 0;
    private int capacity;
    private T[] arr;

    public MyList()
    {
        capacity = 10;
        arr = (T[]) new Object[capacity];
    }

    public MyList(int capacity)
    {
        this.capacity = capacity;
        arr = (T[]) new Object[capacity];
    }

    public int size(){
        return arr.length;
    }

    public int getCapacity(){
        return capacity;
    }

    public void add(T data){

        if(index >= arr.length){

            capacity *= 2;
            T[] newArr = (T[]) new Object[capacity];

            for (int i = 0; i < arr.length; i++) {
                newArr[i] = arr[i];
            }

            arr = newArr;

        }


        arr[index] = data;
        index++;
    }

    public T get(int index)
    {
        return arr[index];
    }

    public T remove(int index) {


        if(index < 0 || index >= arr.length)
            return null;

        T output = arr[index];
        arr[index] = null;
        boolean shiftToLeft = false;
        for (int i = 0; i < arr.length; i++) {

            if(arr[i] == null && !shiftToLeft){
                shiftToLeft = true;
                continue;
            }

            if(shiftToLeft){
                arr[i - 1] = arr[i];
            }

        }


        return output;

    }

    public T set(int index, T data)
    {
        if(index < 0 || index >= arr.length)
            return null;

        arr[index] = data;
        return data;
    }

    @Override
    public String toString() {
        String output = "[";
        for (int i = 0; i < arr.length; i++) {

            if(i + 1 == arr.length){
                output += arr[i];
            } else {
                output += arr[i] + ",";
            }

        }

        output += "]";
        return output;
    }

    public int indexOf(T data)
    {
        for (int i = 0; i < arr.length; i++) {
            T element = arr[i];
            if (element == data) {
                return i;
            }
        }

        return -1;
    }

    public int lastIndexOf(T data)
    {
        int lastIndex = -1;
        for (int i = 0; i < arr.length; i++) {
            T element = arr[i];
            if (element == data) {
                lastIndex = i;
            }
        }

        return lastIndex;
    }

    public boolean isEmpty(){
        for (T data: arr) {
            if(data != null)
                return false;
        }

        return true;
    }

    public T[] toArray(){

        T[] newArr = (T[]) new Object[capacity];

        for (int i = 0; i < arr.length; i++) {
            if(arr[i] == null){
                continue;
            }

            newArr[i] = arr[i];
        }

        return newArr;
    }

    public void clear(){
        arr = (T[]) new Object[capacity];
    }

    public MyList<T> sublist(int start, int finish){

        MyList<T> list = new MyList<>();

        if(start < 0){
            start = 0;
        }

        if(start > arr.length){
            start = arr.length;
        }

        if(finish > arr.length){
            finish = arr.length;
        }



        for (int i = start; i < finish; i++) {
            list.add(arr[i]);
        }

        return list;

    }

    public boolean contains(T data)
    {
        for (T element: arr) {
            if(element == data)
                return true;
        }

        return false;
    }
}


```