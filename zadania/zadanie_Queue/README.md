# Queue

    import java.util.LinkedList;

    public class Queue <T> {
    private LinkedList<T> queue = new LinkedList<>();

        // Method to add an element to the end of the queue
        public void add(T element) {
            queue.addLast(element);
        }

        // Method to remove and return the element from the front of the queue
        public T remove() {
            if (isEmpty()) {
                return null; // or throw an exception to indicate an empty queue
            }
            return queue.removeFirst();
        }

        // Method to check if the queue is empty
        public boolean isEmpty() {
            return queue.isEmpty();
        }

        public static void main(String[] args) {
            // Example usage:
            Queue<Integer> q = new Queue<>();
            q.add(1);
            System.out.println(q.remove()); // Output: 1
        }