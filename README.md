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

In this simple example:

- The `GarbageCollectionExample` class creates a large number of `Garbage` objects and makes them garbage.
- In the main method, `System.gc()` is called to prompt the garbage collector to run.
- The garbage collector eventually calls the `finalize()` method of each object to perform some cleanup before the object is garbage collected.
- The program waits for some time to allow the garbage collector to complete its cleanup work.
