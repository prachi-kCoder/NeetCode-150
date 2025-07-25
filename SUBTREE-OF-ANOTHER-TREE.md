# SUBTREE OF ANOTHER TREE
- Try On :https://leetcode.com/problems/subtree-of-another-tree/description/

```cpp
bool matchCompleteTree(TreeNode* node , TreeNode* subNode) {
        if (!node && !subNode) return true ;
        if (!node || !subNode || node->val != subNode->val) return false ;

        return (matchCompleteTree(node->left, subNode->left) && matchCompleteTree(node->right , subNode->right)) ;
    }
    bool isSubtree(TreeNode* root, TreeNode* subRoot) {
        if (!root && subRoot) return false ;
        if (matchCompleteTree(root,  subRoot)) return true ;

        return (isSubtree(root->left , subRoot) || isSubtree(root->right, subRoot)) ;
    }
```

# 🔍 Complexity Analysis

| METRIC   | COMPLEXICITY  |    HOW ? |
|-----------|-------------|------------|
| 🧭 TIME  |  O(N*k)          |  n the worst case, we compare the subtree rooted at every node of root (≈N nodes), and each comparison takes up to O(k) time to match all k nodes of subRoot. So it's N potential roots × k nodes to compare.   | 
| 🧠 SPACE | O(h) or O(N) |  Recursive Depth : O(N) for Skewed tree & O(logN) for balanced trees |
