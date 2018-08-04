# binary-search-tree
#level order traversal in bst
#include <iostream>
#include<queue>

using namespace std;

struct node
{
int data;
 struct node *left;
  struct node*right ;


};
queue<node*>myQ;
 struct node *root,*s,*p;
 struct node*get_new_node(int x)
 {
 node* n=new node();
n->data=x;
 n->left=NULL;
 n->right=NULL;

 return n;
 }
struct node *create(struct node*root ,int x)
 {
 if (root==NULL)
 {root=get_new_node(x);
  return root ;}
  else if (x<root->data)
  {root->left=create(root->left,x);}
  else {root->right =create(root->right,x);}}
  void level_order(struct node*root)
   {if (root==NULL)
    return ;
    myQ.push(root);
    while(!myQ.empty())
    {
    node*current =myQ.front();
    cout<< current->data;

    if (current->left !=NULL)
    myQ.push(current->left);


    if (current->right !=NULL)
    myQ.push(current->right);

myQ.pop();
    }

   }

int main()
{root=NULL;
root=create(root,5);
root=create(root,7);
root=create(root,3);
root=create(root,9);
root=create(root,13);
root=create(root,12);
level_order(root);
    return 0;
}
