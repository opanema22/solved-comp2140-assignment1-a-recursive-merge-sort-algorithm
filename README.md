Download Link: https://assignmentchef.com/product/solved-comp2140-assignment1-a-recursive-merge-sort-algorithm
<br>
<strong>What you should implement: </strong>Implement the following algorithms and methods (you can add any necessary private helper methods):

<ol>

 <li><strong>A recursive merge sort algorithm: </strong>Implement the algorithm exactly as discussed in class. These are the methods you need to write:

  <ul>

   <li>The public driver mergeSort method: It simply calls the private recursive method with the array and the extra parameters (the start and end indices and the extra array temp) that the recursive method needs. This method must check the validity (null? empty?) of the array to be sorted.</li>

   <li>The private recursive helper mergeSort method: It does the recursive merge sort. It receives the array, indices start and end, and the temporary array as parameters. Its task is to merge sort positions start to end-1 (inclusive) in the array — and it must not touch any other positions in the array. This is the method that should have the new base case added to it.</li>

   <li>The non-recursive helper merge method: It merges two sorted sublists (defined by three indices start, mid, and end) into one sorted list, using the extra array temp. Make sure that you use the indices to define the sublists in a way that is consistent with how sublists are defined by indices in all other parts of the code: from some index up to, but not including, some other index.</li>

  </ul></li>

</ol>

Reminder: Only the public driver method should create an array. All the other methods used by merge sort must use the arrays and positions (indices) that they are passed in their parameters without creating any other arrays.

<ol start="2">

 <li><strong>A recursive merge sort algorithm that does not use a shared temp array: </strong>Implement the algorithm exactly as discussed in class, however do not send a shared temporary array to the private helper method. There are three methods you need to write:

  <ul>

   <li>The public driver mergeSortInefficient method: It simply calls the private recursive method with the array and the extra parameters (the start and end indices) that the recursive method needs. This method must check the validity (null? empty?) of the array to be sorted.</li>

   <li>The private recursive helper mergeSortInefficient method: It does the recursive merge sort. It receives the array, indices start and end, <strong>but does not receive a temporary array as a parameter</strong>. Calls will be in the form mergeSortInefficient(array,start,end). Its task is to merge sort positions start to end-1 (inclusive) in the array — and it must not touch any other positions in the array.</li>

   <li>The non-recursive helper merge method: It merges two sorted sublists (defined by three indices start, mid, and end) into one sorted list and return a sorted array. This function will explicitly return a merged sorted array. Make sure that you use the indices to define the sublists in a way that is consistent with how sublists are defined by indices in all other parts of the code: from some index up to, but not including, some other index.</li>

   <li>Please note that not using a temporary array will require copying many values over and over again.</li>

  </ul></li>

 <li><strong>A recursive quick sort algorithm: </strong>Implement the algorithm exactly as discussed in class. If there are just two items to be sorted, swap them if necessary. You need to write the following methods:

  <ul>

   <li>The public driver quickSort method: It simply calls the private recursive method, passing it the extra parameters (the start and end indices) the recursive method needs.</li>

   <li>The private recursive helper quickSort method: It is the recursive quick sort method, which receives the array, and indices start and end as parameters. Its task is to quick sort positions start to end-1 (inclusive) in the array — and it must not touch any other positions in the array.</li>

   <li>The private non-recursive median-of-three method: It chooses a pivot from the items in positions start to end-1 (inclusive) in the array using the median-of-three method, and swaps the chosen pivot into position start in the array. Consider the case when the array does not have three values to compute the pivot.</li>

   <li>The private non-recursive partition method: It partitions the items in positions start to end-1 (inclusive) in the array using the chosen pivot (which it assumes is already in position start), and returns the final position of the pivot after the partition is complete. It should use one simple for-loop.</li>

  </ul></li>

 <li><strong>A radix sort algorithm that sorts a positive integer array by starting from the biggest digits of numbers: </strong>In the class example where the biggest value was in hundreds, radix sort used 1s first, then 10s and finally 100s to sort values. In this assignment, radix sort should start from the biggest digit to sort the array. For example, if the biggest number is 3289, it should first consider 3 to assign the number to a bucket.</li>

 <li><strong>A method that verifies that an array is in sorted order: </strong>It should be passed an array and it must check that each item is no bigger than the next item in the array. It should return true if the array is in sorted order and false if it is not.</li>

 <li><strong>A method to fill an array with values to sort: </strong>It should be passed a non null int array array. It should fill the array with the numbers 0 to length-1, in order.</li>

 <li><strong>A method to randomize an array that is filled with numbers: </strong>It should be passed an array array and a number <em>n</em>. It should perform <em>n </em>random swaps in the array.</li>

</ol>

To perform a random swap, randomly choose two positions in the array and then swap the contents of those two positions.

<ol start="8">

 <li><strong>A testing method that allows you to compare (and to verify) these sorting methods using a simple statistic:</strong></li>

</ol>

Time each of the sorting algorithms 100 times working on an array of arraySize items (use a randomization parameter numSwaps to make randomized swaps on the array). Make sure you randomize the array every time you sort it, so you are not sorting a sorted array. Also, make sure that you verify that the sorting method works each time — print a useful error message (including the name of the sorting algorithm that sorted the array) if the array is not sorted.

Store the timings of each sorting algorithm in another array (which needs to be of type long). You can find out time costs by using System.nanoTime() before and after the call, and recording the elapsed time.

Then use the arrays of timings and the method that we have provided below for you to report the arithmetic mean of the timings for each of the sorting algorithms. The following example shows how to use it:

double quickSortMean = arithmeticMean( quickSortTimings );

(Note: We expect that your testing method will contain repeated code — Java does not make it easy to avoid in this case. So do not worry about it!)

<ol start="9">

 <li><strong>The method that computes the arithmetic mean of timings:</strong></li>

</ol>

/*******************************************************************

<ul>

 <li>arithmeticMean</li>

</ul>

*

<ul>

 <li>Purpose: Compute the average of long values.</li>

 <li>To avoid long overflow, use type double in the computation.</li>

</ul>

*

******************************************************************/ public static double arithmeticMean( long data[] ) { double sum = 0; for (int i = 0; i &lt; data.length; i++) sum += (double)data[i];

return sum / (double)data.length;

} // end arithmeticMean

<ol start="10">

 <li>Of course, you need to write a main method to call the above testing method (number 8) for a given array size and number of swaps, which in turn calls the sorting algorithms, and the methods that fill the array and verify that it is sorted.</li>

</ol>

<strong>Concerns. </strong>Output of your Java file must contain a report of the experimental set-up. What is the array size, what is the number of swaps? Print out all relevant parameters. Please avoid magical numbers in your code. There should be only ONE return per method. See the programming standards (under content/course documents) file on UMLearn, and follow the suggestions. Assignments will be graded by considering these standards. Your code must not give any warnings or errors when compiled and run.