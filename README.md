# -tree-of-traversal-
樹的走訪(tree of traversal)
#include<bits/stdc++.h>
using namespace std;
class Tree
{
public:
  int data;
  Tree *leftsubtree = NULL, *rightsubtree = NULL;
  
    Tree (int x)
  {
    data = x;
    leftsubtree = NULL;
    rightsubtree = NULL;
  }
};
void preorder (Tree * root)
{
  if (root == NULL)
    return;
  // Print the data
  cout << root->data << " ";
  // Visit Left subtree
  preorder(root->leftsubtree);
  // Visit right subtree
  preorder (root->rightsubtree);
}

void inorder(Tree * root)
{
  if (root == NULL)
    return;
  // Visit Left subtree
  inorder (root->leftsubtree);
  // Print the data
  cout << root->data << " ";
  // Visit right subtree
  inorder (root->rightsubtree);
}

void postorder (Tree * root)
{
  if (root == NULL)
    return;
  // Visit Left subtree
  postorder (root->leftsubtree);
  // Visit right subtree
  postorder (root->rightsubtree);
  // Print the data
  cout << root->data << " ";
}


int main ()
{
  Tree *root = new Tree (17);
  root->leftsubtree = new Tree (10);
  root->rightsubtree = new Tree (11);
  root->leftsubtree->leftsubtree = new Tree (7);
  root->rightsubtree->leftsubtree = new Tree (27);
  root->rightsubtree->rightsubtree = new Tree (9);
  cout << "Preorder => ";
  preorder (root);
  cout << endl;
  cout << "Inorder => ";
  inorder (root);
  cout << endl;
  cout << "Postorder => ";
  postorder (root);
  cout << endl;
  return 0;
}



