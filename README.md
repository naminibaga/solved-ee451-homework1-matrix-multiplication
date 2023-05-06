Download Link: https://assignmentchef.com/product/solved-ee451-homework1-matrix-multiplication
<br>
<h1>  <strong>Naive Matrix Multiplication </strong></h1>

Implement the naive matrix multiplication to multiply two matrices of dimension 4<em>K</em>× 4<em>K</em>. Report the execution time (in <em>ns</em>) and performance (in <em>FLOPS</em>).

<ol start="2">

 <li><strong>Block Matrix Multiplication</strong></li>

</ol>

A matrix can be viewed to be constructed by bigger blocks. Assume an <em>n </em>× <em>n </em>matrix is partitioned into <em>m </em>× <em>m </em>blocks and each block is a <em>b </em>× <em>b </em>matrix ,where  is called the block size. As shown in Figure 2, a 4 × 4 (<em>n </em>= 4) matrix can be viewed as a 2 × 2 (<em>m </em>= 2) block matrix; each block matrix is a 2 × 2 (<em>b </em>= 2) matrix.

Block matrix multiplication computes the output block by block. Figure 3 depicts the principle of Block Matrix Multiplication. Here, the algorithm has <em>m</em><sup>3 </sup>iterations as op-

for i = 1 to n        for j = 1 to n               for k = 1 to n

C(i,j) = C(i,j) + A(i,k)  B(k,j)

<table width="325">

 <tbody>

  <tr>

   <td rowspan="3" width="84">C(i,j)</td>

   <td rowspan="3" width="42">=</td>

   <td width="84">A(i,:)</td>

   <td rowspan="3" width="29"></td>

   <td rowspan="3" width="22"> </td>

   <td rowspan="3" width="63">B(:,j)</td>

  </tr>

  <tr>

   <td width="84"> </td>

  </tr>

  <tr>

   <td width="84"> </td>

  </tr>

 </tbody>

</table>

pose to <em>n</em><sup>3 </sup>iterations for Naive Matrix Multiplication; the computation of each iteration is based on blocks rather than a single element for Naive Matrix Multiplication.

for i = 1 to m       for j = 1 to m

for k = 1 to m  //do a matrix multi. on <strong>blocks </strong>

<strong>C’</strong>(i,j) = <strong>C’</strong>(i,j) + <strong>A’</strong>(i,k) * <strong>B’</strong>(k,j)




<table width="358">

 <tbody>

  <tr>

   <td width="132"></td>

   <td width="226">


    <table width="218">

     <tbody>

      <tr>

       <td colspan="4" rowspan="2" width="93">A’(i,:)</td>

       <td rowspan="6" width="32"></td>

       <td rowspan="6" width="18"> </td>

       <td width="22"> </td>

       <td rowspan="6" width="53">B’(:,j)</td>

       <td width="0"></td>

      </tr>

      <tr>

       <td rowspan="2" width="22"> </td>

      </tr>

      <tr>

       <td rowspan="2" width="24"> </td>

       <td rowspan="2" width="23"> </td>

       <td rowspan="2" width="25"> </td>

       <td rowspan="2" width="21"> </td>

      </tr>

      <tr>

       <td rowspan="2" width="22"> </td>

      </tr>

      <tr>

       <td colspan="4" rowspan="2" width="93"> </td>

      </tr>

      <tr>

       <td width="22"> </td>

      </tr>

     </tbody>

    </table></td>

  </tr>

 </tbody>

</table>

Figure 3: Block Matrix Multiplication

Use block matrix multiplication to solve the previous problem with block size <em>b </em>= 4<em>,</em>8<em>,</em>16 respectively. Report the execution time (in <em>ns</em>) and performance (in <em>FLOPS</em>) respectively. Compare the result against the result obtained by using naive matrix multiplication in a plot. Report your observation.

<ol start="3">

 <li>Submission</li>

</ol>

<ul>

 <li>An example program, “example.c”, which multiplies a matrix with a vector is provided. You can refer to it for some useful functions.</li>

 <li>A frame, “problem1.c” is also given; you can either insert your codes into it or write the whole program by yourself.</li>

 <li>Initialize the matrices in this way: <em>A</em>[<em>i</em>][<em>j</em>] = <em>i,B</em>[<em>i</em>][<em>j</em>] = <em>i </em>+ <em>j,C</em>[<em>i</em>][<em>j</em>] = 0, for any 0 ≤ <em>i,j &lt; n</em>. After the computation, print out the value of <em>C</em>[100][100]. Refer to “problem1.c”.</li>

 <li>For block matrix multiplication, parse the block size <em>b </em>as a command line parameter. Hence to run the <em>b </em>= 8 case, we can type: ‘./p1b 8’. To realize so, see</li>

</ul>

[1].

<ul>

 <li>Submit two .c/.cpp files and the report. ‘p1a.c’ for naive matrix multiplication; ‘p1b.c’ for block matrix multiplication. The output executables should be named ’p1a’ and ’p1b’ respectively. In the report, clearly present the measured performance with various block size <em>b</em>, including the test platform, number of runs and other variables you think are necessary.</li>

</ul>

<h1>2             K-Means algorithm</h1>

<em>K</em>-means [2] is a clustering algorithm which is widely used in signal processing, machine learning and data mining. In this problem, you will implement the <em>K</em>-Means algorithm to cluster a matrix into <em>K </em>clusters. <em>K</em>-Means algorithm has the following steps:

<ol>

 <li>Initialize a mean value for each cluster.</li>

 <li>For each data element, compute its ‘distance’ to the mean value of each cluster. Assign it to the ‘closest’ cluster.</li>

 <li>After each data element is assigned to a cluster, recompute the mean value of each cluster.</li>

 <li>Check convergence; if the algorithm converges, replace the value of each data with the mean value of the cluster which the data belongs to, then terminate the algorithm; otherwise, go to Step 2.</li>

</ol>

In this problem, the input data is a 800 × 800 matrix which is stored in the ‘input.raw’; the value of each matrix element ranges from 0 to 255. Thus, the matrix can be displayed as an image shown in Figure 4. We will have 4 clusters (<em>K</em>=4). The initial mean values for the clusters are 0, 85, 170 and 255, respectively. To simplify the implementation, you do not need check the convergence; run 30 iterations (Step 2 and 3) serially then terminate the algorithm and output the matrix into the file named ‘output.raw’. You can refer to the given program ‘problem2.c’ to read input file and write output file. It copies the input matrix to the out file directly without any modification.

Submit your ‘C/C++’ program and the report. The executable should be named ’p2’. In the report, you need include the execution time for the 30 iterations (excluding the read/write time) and the corresponding image of the output matrix. You can display the output image, ‘output.raw’, using the imageJ [4] software or the given Matlab script file, ‘show raw.m’.