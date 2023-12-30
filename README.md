# Linked-List
# Merge sort two linked lists
/****************************************************************
 
    Following is the class structure of the Node class:

        class Node
        {
        public:
	        int data;
	        Node *next;
	        Node(int data)
	        {
		        this->data = data;
		        this->next = NULL;
	        }
        };

*****************************************************************/

Node *mergeTwoSortedLinkedLists(Node *head1, Node *head2)
{
    //Write your code here
	if(head1 == NULL || head1->next == NULL){
		return head1;
	}
	if(head2 == NULL){
		return head1;
	}
    if (head1 == NULL) {
         return head2;
    }
	Node newnode(0);
	Node *tail = &newnode;

	while(head1 && head2){
		if(head1->data < head2->data){
			tail->next = head1;
			head1 = head1->next;
		}
		else{
			tail->next = head2;
			head2 = head2->next;
		}
		tail = tail->next;
	}
	if(head1){
		tail->next = head1;
	}
	if(head2){
		tail->next = head2;

	}
       
	return newnode.next;
	
}
