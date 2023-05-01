Download Link: https://assignmentchef.com/product/solved-ccu-oop-homework-4-integer-set
<br>
<strong>HW #4 </strong><strong>(Integer Set)</strong>

<ul>

 <li>Design and implement, using C++, or Java if you prefer, a simple ADT called <strong>IntSet </strong>for sets of integers. Each object of class <strong>IntSet </strong>can hold zero or more integers in the range 0 through 100.</li>

 <li>A set should be represented internally as an array of ones and zeros. Array element <em>a[i] </em>is 1 if integer <em>i </em>is in the set. Array element <em>a[j] </em>is 0 if integer <em>j </em>is not in the set.</li>

 <li>The default constructor should initialize a set to an empty set, i.e., a set whose array representation contains all zeros.</li>

 <li>The ADT should support the following set of operations:</li>

</ul>

<h1>HW #4</h1>

<ul>

 <li>default constructor <strong>IntSet() </strong>– creates an empty set.</li>

 <li>constructor with one integer parameter – creates a set containing just the given integer. Example: <em>IntSet(0) </em>creates the set {0}.</li>

 <li>function <strong>isEmpty() </strong>– returns true if the set is empty, else false; does not change the set.</li>

 <li>function <strong>size() </strong>– returns the number of elements in the set, an integer between 0 and 100; does not change the set.</li>

</ul>

<h1>HW #4</h1>

<ul>

 <li>functiin <strong>setPrint() </strong>– prints set to <em>cout </em>with entries surrounded by curly braces and separated by commas (or a blank, if you prefer); returns nothing; does not change the set.</li>

</ul>

Example: if the set <em>A </em>has element 1, 4, and 7, <em>A.setPrint() </em>prints {1, 4, 7}.

<ul>

 <li>function <strong>setUnion() </strong>– creates a third set which is the settheoretic union of two existing sets.</li>

 <li>function <strong>setIntersetion() </strong>– creates a third set which is the set-theoretic intersection of two existing sets.</li>

</ul>

<h1>HW #4</h1>

<ul>

 <li>function <strong>relativeComplement() </strong>– creates a third set which is the set of elements that are in set A and not in set B.</li>

 <li>function <strong>symmetricDifference() </strong>– creates a third set whose elements belong to set A or to set B but not both.</li>

 <li>function <strong>isEqualTo() </strong>– returns true of the two sets are equal, false otherwise; does not change either set.</li>

</ul>

<h1>HW #4</h1>

<ul>

 <li>The class must be organized as two files, a header file, <em>h</em>, containing the class definition and an implementation file, <em>intset.cpp</em>, containing the code for the functions of the class.</li>

 <li>Order of values in a set is unimportant but the set should not contain duplicates.</li>

 <li>The following is a suggestion of how your <em>h </em>could possibly look like.</li>

</ul>

<strong>#ifndef INTSET_H #define INTSET_H</strong>

<strong>class IntSet { public:</strong>

<strong>IntSet() { emptySet(); } // default constructor</strong>

<strong>IntSet( int ); // alternate (overloaded) constructor</strong>

<strong>IntSet setUnion( const IntSet&amp; ); IntSet setIntersection( const IntSet&amp; ); bool isEmpty( void ); int size( void );</strong>

<strong>IntSet relativeComplement( const IntSet&amp; ); IntSet symmetricDifference( const IntSet&amp; ); void setPrint( void ) const; bool isEqualTo( const IntSet&amp; ) const; // Auxiliary functions</strong>

<strong>……………….. private:</strong>

<strong>int set[ 101 ]; // range of 0 – 100 // Private member functions, if necessary</strong>

<strong>};</strong>

<strong>#endif</strong>

<h1>HW #4 (6)</h1>

<ul>

 <li><strong>Testing your solution</strong>: Run the following test driver program to test you class. Make sure that all results are correct before submitting your solution.</li>

 <li>Feel free to write your own test program to ensure your solution is OK.</li>

</ul>

// Test program for the IntSet class

#include &lt;iostream.h&gt; #include “intset.h“

int main()

{

IntSet Empty; // the empty set

// for singleton sets {0} .. {3}

IntSet S0(0), S1(1), S2(2), S3(3);

IntSet A, B, C, D, E, F, G; // to hold computed sets

// Show and test empty set cout &lt;&lt; “
Show and test the empty set…
”; cout &lt;&lt; “Empty = “; Empty.setPrint();

cout &lt;&lt; ” has “&lt;&lt; Empty.size() &lt;&lt; ” elements.” &lt;&lt; endl;

if ( Empty.isEmpty() )

cout &lt;&lt; “The set is empty
” &lt;&lt; endl;

else

cout &lt;&lt; “The set is *not* empty
” &lt;&lt; endl;

// Show and test {1} cout &lt;&lt; “S1 = “; S1.setPrint();

cout &lt;&lt; ” has “&lt;&lt; S1.size() &lt;&lt; ” elements.” &lt;&lt; endl;

if ( S1.isEmpty() )

cout &lt;&lt; “Set S1 is empty
” &lt;&lt; endl;

else

cout &lt;&lt; “Set S1 is *not* empty
” &lt;&lt; endl;

// Compute some unions

A = S0.setUnion(Empty); S0.setPrint(); cout &lt;&lt; ” union “; Empty.setPrint(); cout &lt;&lt; ” = “; A.setPrint(); cout &lt;&lt; endl &lt;&lt; endl;

<ul>

 <li>= S0.setUnion(S1);</li>

 <li>= S3.setUnion(S2);A.setPrint(); cout &lt;&lt; ” union “; B.setPrint(); cout &lt;&lt; ” = “; C = A.setUnion(B); C.setPrint(); cout &lt;&lt; endl &lt;&lt; endl;</li>

 <li>= A.setUnion(S3);</li>

 <li>= B.setUnion(S0);A.setPrint(); cout &lt;&lt; ” union “; B.setPrint(); cout &lt;&lt; ” = “; D = A.setUnion(B); D.setPrint(); cout &lt;&lt; endl &lt;&lt; endl; // Compute intersection, relative complement, and symmetric difference</li>

</ul>

E = A.setIntersection(S3); cout &lt;&lt; “Intersection of “; A.setPrint(); cout &lt;&lt; ” and “; S3.setPrint(); cout &lt;&lt; ” is: “; E.setPrint(); cout &lt;&lt; endl &lt;&lt; endl;

G = D.relativeComplement(S0); cout &lt;&lt; “Relative complement of “; D.setPrint(); cout &lt;&lt; “and “; S0.setPrint(); cout &lt;&lt; ” is: “; G.setPrint(); cout &lt;&lt; endl &lt;&lt; endl;

F = B.symmetricDifference(A); cout &lt;&lt; “Symmetric difference of “; B.setPrint(); cout &lt;&lt; ” and “; A.setPrint(); cout &lt;&lt; ” is: “; F.setPrint(); cout &lt;&lt; endl &lt;&lt; endl;

// Test if two sets are equal cout &lt;&lt; “Set A: “; A.setPrint(); cout &lt;&lt; endl; cout &lt;&lt; “Set B: “; B.setPrint(); cout &lt;&lt; endl; if ( A.isEqualTo(B) )

cout &lt;&lt; “Set A is equal to set B
”;

else

cout &lt;&lt; “Set A is not equal to set B
”;

cout &lt;&lt; endl; return 0; }




<table width="864">

 <tbody>

  <tr>

   <td width="864"><strong>Show and test the empty set…</strong><strong>Empty = {— } has 0 elements. The set is empty</strong><strong>S1 = { 1 } has 1 elements. Set S1 is *not* empty</strong><strong>{ 0 } union {— } = { 0 }</strong><strong>{ 0 1 } union { 2 3 } = { 0 1 2 3 }</strong><strong>{ 0 1 3 } union { 0 2 3 } = { 0 1 2 3 }</strong><strong>Intersection of { 0 1 3 } and { 3 } is: { 3 }</strong><strong>Relative complement of { 0 1 2 3 } and { 0 } is: { 1 2 3 }</strong><strong>Symmetric difference of { 0 2 3 } and { 0 1 3 } is: { 1 2 }</strong><strong>Set A: { 0 1 3 }</strong><strong>Set B: { 0 2 3 }</strong><strong>Set A is not equal to set B </strong></td>

  </tr>

 </tbody>

</table>

import lib.IntSet;

public class test { public static void main(String [] args) {

IntSet Empty = new IntSet();

IntSet S0 = new IntSet(0);

IntSet S1 = new IntSet(1);

IntSet S2 = new IntSet(2);

IntSet S3 = new IntSet(3);

IntSet A, B, C, D, E, F, G;

System.out.println(“
Show and test the empty set…”);

System.out.print(“Empty = “);

Empty.setPrint();

System.out.println(” has ” + Empty.size() + ” elements.”); if (Empty.isEmpty())

System.out.println(“The set is empty
”); else

System.out.println(“The set is *not* empty
”);

System.out.print(“S1 = “);

S1.setPrint();

System.out.println(” has ” + S1.size() + ” elements.”); if (S1.isEmpty())

System.out.println(“Set S1 is empty
”); else

System.out.println(“Set S1 is *not* empty
”);

A = S0.setUnion(Empty);

S0.setPrint();

System.out.print(” union “);

Empty.setPrint();

System.out.print(” = “);

A.setPrint();

System.out.print(“

”);

<ul>

 <li>= S0.setUnion(S1);</li>

 <li>= S3.setUnion(S2);</li>

</ul>

A.setPrint();

System.out.print(” union “);

B.setPrint();

System.out.print(” = “);

<ul>

 <li>= A.setUnion(B);</li>

</ul>

C.setPrint();

System.out.print(“

”);

<ul>

 <li>= A.setUnion(S3);</li>

 <li>= B.setUnion(S0);</li>

</ul>

A.setPrint();

System.out.print(” union “);

B.setPrint();

System.out.print(” = “);

<ul>

 <li>= A.setUnion(B);</li>

</ul>

D.setPrint();

System.out.print(“

”);

<ul>

 <li>= A.setIntersection(S3);</li>

</ul>

System.out.print(“Intersection of “);

A.setPrint();

System.out.print(” and “);

S3.setPrint();

System.out.print(” is “);

E.setPrint();

System.out.print(“

”);

G = D.relativeComplement(S0);

System.out.print(“Relative complement of “);

D.setPrint();

System.out.print(” and “);

S0.setPrint();

System.out.print(” is “);

G.setPrint();

System.out.print(“

”);

F = B.symmetricDifference(A);

System.out.print(“Symmetric difference of”);

B.setPrint();

System.out.print(” and “);

A.setPrint();

System.out.print(” is “);

F.setPrint();

System.out.print(“

”); System.out.print(“Set A:”);

A.setPrint();

System.out.println();

System.out.print(“Set B:”);

B.setPrint(); System.out.println(); if (A.isEqualTo(B))

System.out.println(“Set A is equal to set B
”); else

System.out.println(“Set A is not equal to set B
”);

System.out.println();

}

}