Here's a simple Garbage Collection (GC) code example without comments:

```java
public class GarbageCollectionExample {
    public static void main(String[] args) {
        for (int i = 0; i < 1000; i++) {
            new Garbage();
        }

        System.gc();

        try {
            Thread.sleep(1000);
        } catch (InterruptedException e) {
            e.printStackTrace();
        }
    }
}

class Garbage {
    private int[] bigArray = new int[10000];

    @Override
    protected void finalize() throws Throwable {
        System.out.println("Object garbage collected: " + this);
    }
}
```

