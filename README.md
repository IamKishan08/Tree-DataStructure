   #  Tree - Data Structure

A tree is a hierarchical data structure consisting of nodes, where each node has a value and references to its child nodes. The topmost node is called the **root**, and the nodes without children are called **leaf nodes**.

## Key Concepts in Tree Data Structure

 - **Root Node:** The topmost node of a tree.

 - **Parent Node:** A node that has one or more child nodes.

  - **Child Node:** A node that descends from a parent node.

 - **Leaf Node:** A node with no children.

- **Sub tree:** Any branch of the tree.

 - **Height:** The length of the longest path from the root to a leaf.

 - **Depth:** The length of the path from the root to a given node.

## Why Use Trees?

  - Efficient data search and insertion (e.g., binary search trees).

  - Represent hierarchical structures (e.g., file systems, XML/HTML parsing).

  - Enable faster retrieval than lists for certain operations.

## Types of Trees

### 1. General Trees
 - Each node can have an arbitrary number of children.

- No specific rules govern parent-child relationships.

### 2. Binary Trees
Each node can have at most two children:

   - Left child.
-
    Right child.
### 3. Binary Search Tree (BST)
A binary tree with an additional property:

   - Left subtree contains values smaller than the root.

   - Right subtree contains values greater than the root.

   - Used for searching, insertion, and deletion operations.
### 4. Balances  Trees
Trees where the height difference between left and right subtrees is minimized.

Examples:

   - AVL Tree (self-balancing BST).

   - Red-Black Tree (used in Java's TreeMap).

### 5. Trie
   A special tree used for string operations, e.g., autocomplete systems.

## Types of Tree Traversals

### 1. Pre-Order Traversal (Root → Left → Right)

   - Visit the root node.

   - Recursively traverse the left subtree.

   - Recursively traverse the right subtree.
```bash 
// Pre-order Traversal (Root -> Left -> Right)
void preOrder(Node node) {
    if (node == null) return;

    System.out.print(node.value + " "); // Visit the root
    preOrder(node.left);               // Traverse the left subtree
    preOrder(node.right);              // Traverse the right subtree
}
```

### 2. In-Order Traversal (Left → Root → Right)

- Recursively traverse the left subtree.

- Visit the root node.

- Recursively traverse the right subtree. 

```bash
// In-order Traversal (Left -> Root -> Right)
void inOrder(Node node) {
    if (node == null) return;

    inOrder(node.left);                // Traverse the left subtree
    System.out.print(node.value + " "); // Visit the root
    inOrder(node.right);               // Traverse the right subtree
}

```

### 3. Post-Order Traversal (Left → Right → Root)
- Recursively traverse the left subtree.

- Recursively traverse the right subtree.

- Visit the root node.

```bash
// Post-order Traversal (Left -> Right -> Root)
void postOrder(Node node) {
    if (node == null) return;

    postOrder(node.left);              // Traverse the left subtree
    postOrder(node.right);             // Traverse the right subtree
    System.out.print(node.value + " "); // Visit the root
}

```

### 4. Level-Order Traversal (Breadth-First Traversal)


   - Visit nodes level by level from top to bottom, left to right.

   - Requires a queue to keep track of nodes at each level.

```bash
import java.util.LinkedList;
import java.util.Queue;

void levelOrder(Node root) {
    if (root == null) return;

    Queue<Node> queue = new LinkedList<>();
    queue.add(root);

    while (!queue.isEmpty()) {
        Node current = queue.poll();  // Get the front node in the queue
        System.out.print(current.value + " "); // Visit the node

        if (current.left != null) queue.add(current.left);   // Add left child
        if (current.right != null) queue.add(current.right); // Add right child
    }
}

```



