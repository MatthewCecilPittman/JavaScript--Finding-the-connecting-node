# JavaScript--Finding-the-connecting-node
Google interview question
```
Good morning! Here's your coding interview problem for today.

This problem was asked by Google.

Given two singly linked lists that intersect at some point, find the intersecting node. The lists are non-cyclical.

For example, given A = 3 -> 7 -> 8 -> 10 and B = 99 -> 1 -> 8 -> 10, return the node with value 8.

In this example, assume nodes with the same value are the exact same node objects.

Do this in O(M + N) time (where M and N are the lengths of the lists) and constant space.
```
```
class ListNode { 
constructor(data, next = null) {
this.data = data;
this.next = next;
}
}
class LinkdedList {
constructor(){
this.head = null;
this._length = 0;
}
}
insertNodeAtBeginning = (data) => {
let next = this.head;
this.head = new ListNode(data, next);
this._length++;
return this.head;
}
insertNodeAtEnd = (data)=> {
let currentNode = this.head;
if(currentNode){
while(currentNode.next){
currentNode = currentNode.next;
}
currentNode.next = new ListNode(data);
}
this._length++;
return this.head;
}
insertNodeAtMiddle = (data, index) => {
if (
index !== 0 &&
index !== this._length &&
this._length > 1
) {
let currentNode = this.head;
let count = 0;
 while(count !== index -1){
count++;
currentNode = currentNode.next;
}
let prevNode = currentNode;
let nextNode = prevNode.next;
let newNode = new ListNode(data, nextNode);
prevNode.next = newNode;
this._length++;
return newNode;
} else{
return 'Error: Ooops, please check givenn index';
}
}
deleteNodeAtIndex = index => {
let deletedNode;
if (index === 0) {
deleteNode = this.head;
let nextNode = deleteNode.next;
this.head = nextNode.next;
}
else if(index!== this.length -1)
{
let currentNode = this.head;
let count = 0;
while(count !== index -1) {
count++;
currentNode = currentNode.next;
}
let prevNode = currentNode;
deletedNode = prevNode.next;
let nextNode = deletedNode.next;
prevNode.next = nextNode;
}
else {
return 'Error: Ooop, please check the given index';
}
this._length--;
return deletedNode;
}
deleteFirstNode = () => {
let deletedNode = this.head;
let nextNode = deletedNode.next;
this.head = nextNode;
this._length--;
return deletedNode;
}
deleteNodeAtIndex = index => {
let deletedNode = null;
if (index !== this._length -1) {
let currentNode = this.head;
let count = 0;
while (count !== index -1){
count++;
currentNode = currentNode.next;
}
let prevNode = currentNode;
deletedNode = prevNode.next;
let nextNode = deletedNode.next;
prevNode.next = nextNode;
} else{
return 'Error: Ooops, please check given index';
}
this._length--;
return deletedNode;
}
deleteLastNode = () => {
let currentNode = this.head;
let nextNode = currentNode.next;
while(nextNode.next){
currentNode = nextNode;
nextNode = currentNode.next;
}
let deletedNode = nextNode;
currentNode.next = null;
this._length--;
return deletedNode;
}
getLength = () => {
return this._length;
}
getListNodeAtIndex = index => {
let currentNode = this.head;
let count = 0;
while (count < index){
count++;
currentNode = currentNode.next;
}
return currentNode;
}
getLastListNode = () => {
let currentNode = this.head;
while (currentNode.next){
currentNode = currentNode.next;
}
let lastNode = currentNode;
return lastNode;
}


```
