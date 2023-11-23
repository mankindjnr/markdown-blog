<h5 style="color:blue;">Binary Search | Linear Search</h5>

Binary Search is an efficient algorithm for finding an item from a sorted list of items. It works by repeatedly dividing in half the portion of the list that could contain the item, until you've narrowed down the possible locations to just one.

Here's a step-by-step pseudocode of how Binary Search works:

Find the middle element of the array.
If the middle element is the target, return the index.
If the target is less than the middle element, repeat the process with the left half of the array.
If the target is greater than the middle element, repeat the process with the right half of the array.
If the array does not contain the target, return -1 or some value indicating that the target is not found.