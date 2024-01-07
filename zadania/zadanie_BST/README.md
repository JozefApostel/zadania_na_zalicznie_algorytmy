    public class Node {
    int data;
    Node left, right;

        public Node(int data) {
            this.data = data;
            this.left = this.right = null;
        }

        public void insert(int data) {
            if (data < this.data) {
                // Wstawianie po lewej stronie
                if (left == null) {
                    left = new Node(data);
                } else {
                    left.insert(data);
                }
            } else if (data > this.data) {
                // Wstawianie po prawej stronie
                if (right == null) {
                    right = new Node(data);
                } else {
                    right.insert(data);
                }
            }
            // Ignorowanie duplikatów (przy założeniu, że nie są one dozwolone)
        }

        public Node contains(int data) {
            if (data == this.data) {
                return this;
            }

            if (data < this.data && left != null) {
                return left.contains(data);
            } else if (data > this.data && right != null) {
                return right.contains(data);
            }