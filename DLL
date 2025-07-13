class Node {
    int data;
    Node prev, next;

    Node(int data) {
        this.data = data;
        this.prev = null;
        this.next = null;
    }
}

public class DLL {
    Node head;

    // Insert at Beginning
    public void insertAtBeginning(int data) {
        Node newNode = new Node(data);
        if (head == null) {
            head = newNode;
            return;
        }
        newNode.next = head;
        head.prev = newNode;
        head = newNode;
    }

    // Insert at End
    public void insertAtEnd(int data) {
        Node newNode = new Node(data);
        if (head == null) {
            head = newNode;
            return;
        }
        Node temp = head;
        while (temp.next != null) {
            temp = temp.next;
        }
        temp.next = newNode;
        newNode.prev = temp;
    }

    // Insert at Specific Position
    public void insertAtPosition(int data, int pos) {
        if (pos < 1) {
            System.out.println("Position should be >= 1");
            return;
        }
        if (pos == 1) {
            insertAtBeginning(data);
            return;
        }

        Node newNode = new Node(data);
        Node temp = head;

        for (int i = 1; temp != null && i < pos - 1; i++) {
            temp = temp.next;
        }

        if (temp == null) {
            System.out.println("Position out of bounds.");
            return;
        }

        newNode.next = temp.next;
        if (temp.next != null)
            temp.next.prev = newNode;

        temp.next = newNode;
        newNode.prev = temp;
    }

    // Delete at Beginning
    public void deleteAtBeginning() {
        if (head == null) {
            System.out.println("List is empty.");
            return;
        }
        if (head.next == null) {
            head = null;
            return;
        }
        head = head.next;
        head.prev = null;
    }

    // Delete at End
    public void deleteAtEnd() {
        if (head == null) {
            System.out.println("List is empty.");
            return;
        }
        if (head.next == null) {
            head = null;
            return;
        }
        Node temp = head;
        while (temp.next != null) {
            temp = temp.next;
        }
        temp.prev.next = null;
    }

    // Delete at Specific Position
    public void deleteAtPosition(int pos) {
        if (pos < 1) {
            System.out.println("Position should be >= 1");
            return;
        }
        if (head == null) {
            System.out.println("List is empty.");
            return;
        }
        if (pos == 1) {
            deleteAtBeginning();
            return;
        }

        Node temp = head;
        for (int i = 1; temp != null && i < pos; i++) {
            temp = temp.next;
        }

        if (temp == null) {
            System.out.println("Position out of bounds.");
            return;
        }

        if (temp.next != null)
            temp.next.prev = temp.prev;
        if (temp.prev != null)
            temp.prev.next = temp.next;
    }

    // Display the list
    public void display() {
        Node temp = head;
        System.out.print("null<->");
        while (temp != null) {
            System.out.print(temp.data + "<->");
            temp = temp.next;
        }
        System.out.println("null");
    }

    // Main Method
    public static void main(String[] args) {
        DLL list = new DLL();

        list.insertAtEnd(10);
        list.insertAtEnd(20);
        list.insertAtEnd(30);
        list.insertAtEnd(40);
        list.insertAtEnd(50);
        list.display(); // null<->10<->20<->30<->40<->50<->null

        list.insertAtPosition(25, 3);
        list.display(); // null<->10<->20<->25<->30<->40<->50<->null

        list.deleteAtPosition(4);
        list.display(); // null<->10<->20<->25<->40<->50<->null
    }
}
