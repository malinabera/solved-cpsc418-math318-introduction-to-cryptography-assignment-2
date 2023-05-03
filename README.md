Download Link: https://assignmentchef.com/product/solved-cpsc418-math318-introduction-to-cryptography-assignment-2
<br>
<h1><strong style="font-size: 16px;">Problem 1 </strong><span style="font-size: 16px;">— Arithmetic in the AES MixColumns operation (22 marks)</span></h1>

<h1>Written Problems for CPSC 418 and MATH 318</h1>

Recall that the MixColumns operation in AES performs arithmetic on 4-byte vectors using the polynomial <em>M</em>(<em>y</em>) = <em>y</em><sup>4 </sup>+ 1. In this arithmetic, we have <em>M</em>(<em>y</em>) = 0, so <em>y</em><sup>4 </sup>= 1.

<ul>

 <li>In this part of the problem, we consider multiplication of 4-byte vectors (viewed as polynomials of degree ≤ 3 whose coefficients are bytes) by powers of <em>y</em>.

  <ol>

   <li>(2 marks) Formally prove that in this arithmetic, multiplication of any 4-byte vector by <em>y </em>is a circular left shift of the vector by one byte.</li>

   <li>(2 marks) Prove that in this arithmetic, <em>y<sup>i </sup></em>= <em>y<sup>j </sup></em>for any integer <em>i </em>≥ 0, where <em>j </em>≡ <em>i </em>(mod 4) with 0 ≤ <em>j </em>≤ 3.</li>

  </ol></li>

</ul>

<ul>

 <li>(4 marks) Use part (a) (ii) to formally prove that multiplication of any 4-byte vector by <em>y<sup>i </sup></em>(<em>i </em>≥ 0) is a circular left shift of the vector by <em>j </em>bytes, where <em>j </em>≡ <em>i </em>(mod 4) with 0 ≤ <em>j </em>≤ 3.</li>

</ul>

<ul>

 <li>Next, we consider arithmetic involving the coefficients of the polynomial</li>

</ul>

<em>c</em>(<em>y</em>) = (03)<em>y</em><sup>3 </sup>+ (01)<em>y</em><sup>2 </sup>+ (01)<em>y </em>+ (02) <em>,</em>

that appears in MixColumns, where the coefficients of <em>c</em>(<em>y</em>) are bytes written in hexadecimal (i.e. base 16) notation. Arithmetic involving this polynomial requires the computation of products involving the bytes (01), (02) and (03) in the Rijndahl field GF(2<sup>8</sup>). Recall that in this field, arithmetic is done modulo <em>m</em>(<em>x</em>) = <em>x</em><sup>8 </sup>+ <em>x</em><sup>4 </sup>+ <em>x</em><sup>3 </sup>+ <em>x </em>+ 1.

<ol>

 <li>(2 marks) Write the bytes (01), (02), (03) as their respective polynomial representatives <em>c</em><sub>1</sub>(<em>x</em>), <em>c</em><sub>2</sub>(<em>x</em>) and <em>c</em><sub>3</sub>(<em>x</em>) in the Rijndahl field GF(2<sup>8</sup>).</li>

 <li>(4 marks) Let <em>b </em>= (<em>b</em><sub>7 </sub><em>b</em><sub>6 </sub>··<em>b</em><sub>1 </sub><em>b</em><sub>0</sub>) be any byte, and let <em>d </em>= (02)<em>b </em>be the product of the bytes (02) and <em>b </em>in the Rijndahl field GF(2<sup>8</sup>). Then <em>d </em>is again a byte of the form <em>d </em>= (<em>d</em><sub>7 </sub><em>d</em><sub>6 </sub>···<em>d</em><sub>1 </sub><em>d</em><sub>0</sub>). Provide symbolic expressions for the bits <em>d<sub>i</sub></em>, 0 ≤ <em>i </em>≤ 7, in terms of the bits <em>b<sub>i </sub></em>of <em>b</em>.</li>

</ol>

<ul>

 <li>(3 marks) Provide analogous expressions as in part (b) (ii) for the byte product <em>e </em>= (03)<em>b</em>, where <em>b </em>= (<em>b</em><sub>7 </sub><em>b</em><sub>6 </sub>··<em>b</em><sub>1 </sub><em>b</em><sub>0</sub>) is any byte.</li>

</ul>

<ul>

 <li>The MixColumns operation performs multiplication of 4-byte vectors by the polynomial <em>c</em>(<em>y</em>) of part (b). In this part of the problem, you will evaluate such products symbolically.

  <ol>

   <li>(3 marks) Let <em>s</em>(<em>y</em>) = <em>s</em><sub>3</sub><em>y</em><sup>3</sup>+<em>s</em><sub>2</sub><em>y</em><sup>2</sup>+<em>s</em><sub>1</sub><em>y</em>+<em>s</em><sub>0 </sub>be a polynomial whose coefficients are bytes. Symbolically compute the product <em>t</em>(<em>y</em>) = <em>s</em>(<em>y</em>)<em>c</em>(<em>y</em>) mod <em>y</em><sup>4 </sup>+ 1. The result should be a polynomial of the form <em>t</em>(<em>y</em>) = <em>t</em><sub>3</sub><em>y</em><sup>3</sup>+<em>t</em><sub>2</sub><em>y</em><sup>2</sup>+<em>t</em><sub>1</sub><em>y</em>+<em>t</em><sub>0 </sub>where <em>t</em><sub>3</sub><em>,t</em><sub>2</sub><em>,t</em><sub>1</sub><em>,t</em><sub>0 </sub>are bytes. Provide symbolic expressions for the bytes <em>t<sub>i</sub></em>, 0 ≤ <em>i </em>≤ 3, in terms of the bytes <em>s<sub>i</sub></em>. The equations should consist of sums of byte products of the form 01<em>s<sub>i</sub></em>, 02<em>s<sub>i</sub></em>, 03<em>s<sub>i</sub></em>, 0 ≤ <em>i </em>≤ 3. You need <em>not </em>compute these individual byte products as you did in part (b).</li>

   <li>(2 marks) Write your solution of part (c) (i) in matrix form; i.e. give a 4×4 matrix <em>C </em>whose entries are bytes such that</li>

  </ol></li>

</ul>

Note that this yields the matrix representation of MixColumns presented (without proof) in class.

<strong>Problem 2 </strong>— Error propagation in block cipher modes (12 marks)

Error propagation is often an important consideration when choosing a mode of operation in practice. In this problem, you will analyze the error propagation properties of an arbitrary block cipher in various such modes; note that these properties are independent of the cipher used.

<ul>

 <li>Suppose Alice wants to send a sequence of message blocks <em>M</em><sub>0</sub><em>,M</em><sub>1</sub><em>,M</em><sub>2</sub><em>,… </em>to Bob, encrypted to ciphertext blocks <em>C</em><sub>0</sub><em>,C</em><sub>1</sub><em>,C</em><sub>2</sub><em>,… </em>using some fixed key <em>K</em>. Assume that an error occurs during transmission of a particular block of ciphertext <em>C<sub>i</sub></em>. Justifying all your answers, explain which plaintext blocks are affected after Bob decrypts this (faulty) ciphertext block <em>C<sub>i </sub></em>when the cipher is used in</li>

</ul>

<ol>

 <li>(2 marks) ECB mode? ii. (2 marks) CBC mode? iii. (2 marks) OFB mode? iv. (2 marks) CFB mode with one register?</li>

 <li>(2 marks) CTR mode?</li>

</ol>

<ul>

 <li>(2 marks) Suppose now that an error occurs in a particular plaintext block <em>M<sub>i </sub></em>before Alice encrypts it and sends the corresponding ciphertext <em>C<sub>i </sub></em>to Bob. Upon decryption of <em>C<sub>i</sub></em>, which plaintext blocks <em>M<sub>j </sub></em>are affected when using the cipher in CBC mode?</li>

</ul>

<strong>Problem 3 </strong>— Binary exponentiation (13 marks)

Recall the exponentiation algorithm given in class for evaluating <em>a<sup>n </sup></em>(mod <em>m</em>) (<em>a </em>∈ Z, <em>m,n </em>∈ N):

<ol>

 <li>Compute the binary representation of <em>n</em>:</li>

</ol>

<em>n </em>= <em>b</em><sub>0</sub>2<em><sup>k </sup></em>+ <em>b</em><sub>1</sub>2<em><sup>k</sup></em><sup>−1 </sup>+ ··· + <em>b<sub>k</sub></em>−<sub>1</sub>2 + <em>b<sub>k </sub>,</em>

with <em>b</em><sub>0 </sub>= 1<em>, b<sub>i </sub></em>∈ {0<em>,</em>1} for 1 ≤ <em>i </em>≤ <em>k</em>, and <em>k </em>= blog<sub>2 </sub><em>n</em>c<em>.</em>

<ol start="2">

 <li>Initialize <em>r</em><sub>0 </sub>≡ <em>a </em>(mod <em>m</em>).</li>

 <li>For 0 ≤ <em>i </em>≤ <em>k </em>− 1 compute )             if <em>b<sup>i</sup></em><sup>+<a href="#_ftn1" name="_ftnref1">[1]</a> </sup>= 0 <em>,</em></li>

</ol>

)       if <em>b<sub>i</sub></em><sub>+1 </sub>= 1 <em>.</em>

<ol start="4">

 <li>Output <em>r<sub>k</sub></em>.</li>

</ol>

<ul>

 <li>(3 marks) To warm up with a toy example, compute 17<sup>11 </sup>(mod 77) using the procedure above; answers that don’t use the binary exponentiation algorithm will receive no credit, even if they are correct. Show all your work, and write down all your intermediate quantities <em>b<sub>i </sub></em>and <em>r<sub>i</sub></em>. Your answer should be an integer between 0 and 76.</li>

 <li>In this problem, you will formally prove that the binary exponentiation algorithm is correct.

  <ol>

   <li>(4 marks) Define <em>s</em><sub>0 </sub>= 1 and <em>s<sub>i</sub></em><sub>+1 </sub>= 2<em>s<sub>i </sub></em>+<em>b<sub>i</sub></em><sub>+1 </sub>for 0 ≤ <em>i </em>≤ <em>k </em>−1. Use induction on <em>i </em>to</li>

  </ol></li>

</ul>

prove that

<em>i s<sub>i </sub></em>= <sup>X</sup><em>b<sub>j</sub></em>2<em><sup>i</sup></em><sup>−<em>j              </em></sup>for 0 ≤ <em>i </em>≤ <em>k .</em>

<em>j</em>=0

<ol>

 <li>(4 marks) Let <em>r<sub>i</sub></em>, 0 ≤ <em>i </em>≤ <em>k</em>, be defined as in steps 2 and 3 of the exponentiation algorithm. Use induction on <em>i </em>to prove that <em>r<sub>i </sub></em>≡ <em>a<sup>s</sup></em><em><sup>i </sup></em>(mod <em>m</em>) for 0 ≤ <em>i </em>≤ <em>k</em>.</li>

</ol>

<ul>

 <li>(2 marks) Prove that <em>a<sup>n </sup></em>≡ <em>r<sub>k </sub></em>(mod <em>m</em>), so the algorithm above does indeed compute <em>a<sup>n </sup></em>(mod <em>m</em>) as claimed.</li>

</ul>

<strong>Problem 4 </strong>— A modified man-in-the-middle attack on Diffie-Hellman (10 marks)

Suppose Alice and Bob wish to generate a shared cryptographic key using the Diffie-Hellman protocol. As usual, they agree on a large prime <em>p </em>and a primitive root <em>g </em>of <em>p</em>. Suppose also that <em>p </em>= <em>mq </em>+ 1 where <em>q </em>is prime and <em>m </em>is very small (so <em>p </em>− 1 = <em>mq </em>has a large prime factor, as is generally required). Since <em>g </em>and <em>p </em>are public, it is easy for anyone to deduce <em>m </em>and <em>q</em>; for example by successively trial-dividing <em>p</em>−1 by <em>m </em>= 2<em>,</em>4<em>,</em>6<em>,… </em>and running a primality test such as the Fermat test on the quotient <em>q </em>= (<em>p </em>− 1)<em>/m </em>until primality of <em>q </em>is established.

Suppose an active attacker Mallory<sup>1 </sup>intercepts <em>g<sup>a </sup></em>(mod <em>p</em>) from Alice and <em>g<sup>b </sup></em>(mod <em>p</em>) from Bob. She sends (<em>g<sup>a</sup></em>)<em><sup>q </sup></em>(mod <em>p</em>) to Bob and (<em>g<sup>b</sup></em>)<em><sup>q </sup></em>(mod <em>p</em>) to Alice.

<ul>

 <li>(2 marks) Show that Alice and Bob compute the same shared key <em>K </em>under this attack.</li>

 <li>(4 marks) Show that there are <em>m </em>possible values for <em>K, </em>and that Mallory can compute them all and hence easily guess the correct key <em>K </em>among them.</li>

 <li>(4 marks) What is the advantage of this variation of the man-in-the-middle attack over the version we discussed in class? Recall that for the attack from class, Mallory simply suppresses the messages <em>g<sup>a </sup></em>(mod <em>p</em>) and <em>g<sup>b </sup></em>(mod <em>p</em>) between Alice and Bob and replaces them with her own number <em>g<sup>e </sup></em>(mod <em>p</em>), which results in the shared key <em>g<sup>ae </sup></em>(mod <em>p</em>) between Mallory and Alice and the shared key <em>g<sup>be </sup></em>(mod <em>p</em>) between Mallory and Bob.</li>

</ul>

<strong>Problem 5 </strong>— A simplified password-based key agreement protocol (8 marks)

The following is a simplified (and hence problematic) version of the key generation phase of the password-based key agreement protocol that you are being asked to implement in Problem 9 (the programming problem). Here, a client first performs a one-time registration of their authentication credentials with a server. These credentials can then be used to generate authenticated session keys between server and client via communication over an insecure channel.

All participants agree on a large public prime<a href="#_ftn2" name="_ftnref2"><sup>[2]</sup></a> <em>N </em>= 2<em>q</em>+1, with <em>q </em>prime, and a public primitive root <em>g </em>of <em>N</em>. Each client has their own password <em>p</em>. To register with the server, a client computes <em>v </em>≡ <em>g<sup>p </sup></em>(mod <em>N</em>) and provides the server with the pair (<em>I,v</em>) where <em>I </em>is the client’s user id.<a href="#_ftn3" name="_ftnref3"><sup>[3]</sup></a>

<strong>Protocol:</strong>

<ol>

 <li>Client generates a random value <em>a </em>with 0 ≤ <em>a </em>≤ <em>N </em>− 1, computes <em>A </em>≡ <em>g<sup>a </sup></em>(mod <em>N</em>), and sends (<em>I,A</em>) to server, where <em>I </em>is the Client’s user id.</li>

</ol>

Server generates a random value <em>b </em>with 0 ≤ <em>b </em>≤ <em>N </em>− 1, computes <em>B </em>≡ <em>g<sup>b </sup></em>(mod <em>N</em>), and sends <em>B </em>to client.

<ol start="2">

 <li>Client computes <em>K</em><sub>client </sub>≡ <em>B<sup>a</sup></em><sup>+<em>p </em></sup>(mod <em>N</em>).</li>

</ol>

Server retrieves client’s authentication data (<em>I,v</em>) and computes <em>K</em><sub>server </sub>≡ (<em>Av</em>)<em><sup>b </sup></em>(mod <em>N</em>).

Note that this protocol is similar to Diffie-Hellman, except that the client’s password <em>p </em>and authentication credential <em>v </em>are incorporated in the key computation.

<ul>

 <li>[2 marks] Prove that Client and Server have a shared key after executing this protocol, i.e. prove that <em>K</em>server = <em>K</em>client.</li>

 <li>[3 marks] Suppose an adversary Mallory obtains client Ian’s authentication data (<em>I,v</em>) (by intercepting Ian’s transmission to the server upon his registration or by hacking into the server’s database). Show how Mallory can masquerade as Ian, i.e. execute the protocol with the server (using a value <em>A </em>of her choice) and generate a valid key <em>K</em><sub>client </sub>that the server believes is shared with Ian.</li>

 <li>[3 marks] Consider the following two problems:

  <ul>

   <li><em>Key Recovery Problem: </em>Given any values <em>A </em>≡ <em>g<sup>a </sup></em>(mod <em>N</em>) and <em>B </em>≡ <em>g<sup>b </sup></em>(mod <em>N</em>) and any <em>v </em>∈ Z<sup>∗</sup><em><sub>N</sub></em>, find a key <em>K </em>produced by the protocol above.</li>

   <li><em>Diffie-Hellman Problem: </em>Given any values <em>A </em>≡ <em>g<sup>a </sup></em>(mod <em>N</em>) and <em>B </em>≡ <em>g<sup>b </sup></em>(mod <em>N</em>), find a Diffie-Hellman key <em>K </em>≡ <em>g<sup>ab </sup></em>(mod <em>N</em>).</li>

  </ul></li>

</ul>

Note that the exponents <em>a </em>and <em>b </em>are assumed to be unknown for both these problems. Show how an attacker Mallory who can solve any instance of the key recovery problem can solve any instance of the Diffie-Hellman problem. (So informally, breaking the key agreement protocol above is at least as hard as breaking Diffie-Hellman.)

<h1>Written Problems for MATH 318 only</h1>

<strong>Problem 6 </strong>— Primitive roots for safe primes (6 marks)

Let <em>q </em>≥ 3 be a prime such that <em>p </em>= 2<em>q </em>+ 1 is also prime. Let <em>g </em>be any primitive root of <em>p</em>. Prove that with the exception of <em>g<sup>q </sup></em>(mod <em>p</em>), all the odd powers of <em>g </em>(i.e. <em>g,g</em><sup>3 </sup>(mod <em>p</em>)<em>,g</em><sup>5 </sup>(mod <em>p</em>)<em>,…,g<sup>p</sup></em><sup>−2 </sup>(mod <em>p</em>)), are primitive roots of <em>p</em>.

(<em>Hint: </em>the following fact about divisibility, which you may use without proof, might come in handy: for any three nonzero integers <em>a,b,c</em>, if <em>a </em>is a divisor of the product <em>bc </em>and gcd(<em>a,b</em>) = 1, then <em>a </em>is a divisor of <em>c</em>.)

<strong>Problem 7 </strong>— Discrete logarithms with respect to different primitive roots (8 marks)

Prove that the difficulty of the discrete logarithm problem is independent of the primitive root. Specifically, for any prime <em>p</em>, assuming that it is computationally feasible to extract discrete logarithms with respect to one primitive root of <em>p</em>, show how one can feasibly extract discrete logarithms with respect to any other primitive root of <em>p</em>.

<strong>Problem 8 </strong>— An algorithm for extracting discrete logarithms (21 marks)

Let <em>p </em>be a large prime and <em>g </em>a fixed primitive root of <em>p</em>. Letbe the modular inverse of <em>g</em>, so <em>gh </em>≡ 1 (mod <em>p</em>). Let. Define the following lists of elements in:

<em>y<sub>i </sub></em>≡ <em>ah<sup>i </sup></em>(mod <em>p</em>), 0 ≤ <em>i </em>≤ <em>m </em>− 1; <em>z<sub>j </sub></em>≡ (<em>g<sup>m</sup></em>)<em><sup>j </sup></em>(mod <em>p</em>), 0 ≤ <em>j </em>≤ <em>k </em>− 1.

Here, <em>m </em>is a positive integer (an as yet unspecified parameter) and <em>k </em>is the smallest integer with <em>k </em>≥ (<em>p </em>− 1)<em>/m</em>.

<ul>

 <li>(4 marks) Prove that there exist indices <em>i,j </em>with 0 ≤ <em>i </em>≤ <em>m </em>− 1 and 0 ≤ <em>j </em>≤ <em>k </em>− 1 such that <em>y<sub>i </sub></em>= <em>z<sub>j</sub></em>.</li>

</ul>

(<em>Hint: </em>Division with remainder of <em>x </em>by <em>m </em>where <em>x </em>is the (unknown) discrete logarithm of <em>a </em>with respect to <em>g</em>.)

<ul>

 <li>(4 marks) Consider the following procedure for computing the discrete logarithm of <em>a </em>with respect to <em>g</em>.

  <ol>

   <li>Compute the list Y = (<em>y</em><sub>0</sub><em>,y</em><sub>1</sub><em>,…,y<sub>m</sub></em><sub>−1</sub>)</li>

   <li>If <em>y<sub>i </sub></em>≡ 1 (mod <em>p</em>) for some <em>i </em>∈ {0<em>,</em>1<em>,…,m </em>− 1}, then output <em>i </em>and quit.</li>

   <li>Compute the list Z = (<em>z</em><sub>0</sub><em>,z</em><sub>1</sub><em>,z</em><sub>2</sub><em>,…,</em>) until an element <em>z<sub>j </sub></em>is found that appears in Y.</li>

   <li>Upon finding such a match, say <em>z<sub>j </sub></em>= <em>y<sub>i</sub></em>, output <em>x </em>≡ <em>jm </em>+ <em>i </em>(mod <em>p </em>− 1).</li>

  </ol></li>

</ul>

Prove that this procedure terminates and outputs the discrete logarithm of <em>a</em>.

<ul>

 <li>(4 marks) Assuming the worst case scenario (i.e. the entire list Z = (<em>z</em><sub>0</sub><em>,z</em><sub>1</sub><em>,…,z<sub>k</sub></em><sub>−1</sub>) needs to be generated), how many modular multiplication are required to extract the discrete logarithm of <em>a </em>using the procedure above? Your count should be as accurate as possible (i.e. don’t count modular multiplications that aren’t needed). You may assume that the quantities <em>m,k,h </em>and <em>g<sup>m </sup></em>(mod <em>p</em>) have been precomputed as they are independent of <em>a</em>. You may also ignore the cost of searching the list Y for an element <em>z </em>∈ Z.</li>

 <li>(4 marks) How should <em>m </em>be chosen to minimize the number of modular multiplication required by the procedure above? Explain your choice.</li>

 <li>Let <em>p </em>= 107.

  <ol>

   <li>(2 marks) Use the primitive root test from class to verify that 2 is a primitive root of <em>p</em>. Show your work.</li>

   <li>(3 marks) Use the procedure from part (b) and your choice of <em>m </em>from part (d) to compute the discrete logarithm of 6 with respect to 2 in. Show your work. You may want to verify that your final answer is correct.</li>

  </ol></li>

</ul>

<h1>Programming Problem for CPSC 418 only</h1>

<strong>Problem 9 </strong>— A secure password based authentication and key exchange protocol (35 marks)

<strong>Overview. </strong>This problem considers the full, secure version of the password-based key agreement protocol introduced in Problem 5. This protocol, executed by Client and a Server, allows the Client to demonstrate to the Server knowledge of a password, but neither the password nor any other information that could be used to derive the password need to be transmitted. Additionally, the Server does not store password-equivalent data, so someone who intercepts authentication data or steals them from the Server’s database is unable to masquerade as the Client without brute-forcing the Client’s password.

<strong>Initialization. </strong>The following quantities are public system parameters:

<ul>

 <li>A safe prime <em>N </em>= 2<em>q </em>+ 1, where <em>q </em>is a prime;</li>

 <li>A primitive root <em>g </em>of <em>N</em>;</li>

 <li>A fixed cryptographically secure hash function;</li>

 <li>The quantity <em>k </em>= <em>H</em>(<em>N</em>||<em>g</em>) (where, as always, “||” denotes concatenation).</li>

</ul>

<strong>Registration. </strong>To register with the Server, a Client with user id <em>I </em>and password <em>p </em>performs the following steps:

<ol>

 <li>Generates a <em>salt s </em>(a small random number);</li>

 <li>Computes <em>x </em>= <em>H</em>(<em>s</em>||<em>p</em>) and <em>v </em>≡ <em>g<sup>x </sup></em>(mod <em>N</em>);</li>

 <li>Transmits the authenticated triple (<em>I,s,v</em>) securely to the Server for storage (note that this authentication and secure transmission are not covered by the protocol);</li>

 <li>Disposes of <em>x</em>.</li>

</ol>

<strong>Protocol. </strong>To generate and verify a shared authenticated session key, the Server and Client perform the following steps:

<ol>

 <li>Client generates a random value <em>a </em>with 0 ≤ <em>a </em>≤ <em>N </em>− 1, computes <em>A </em>≡ <em>g<sup>a </sup></em>(mod <em>N</em>), and sends (<em>I,A</em>), where <em>I </em>is the Client’s user id.</li>

</ol>

Server generates a random value <em>b </em>with 0 ≤ <em>b </em>≤ <em>N </em>− 1, computes <em>B </em>≡ <em>kv </em>+ <em>g<sup>b </sup></em>(mod <em>N</em>), and sends (<em>s,B</em>), where <em>s </em>is the Client’s salt.

<ol start="2">

 <li>Both compute <em>u </em>≡ <em>H</em>(<em>A</em>||<em>B</em>) (mod <em>N</em>).</li>

 <li>Client computes <em>K</em><sub>client </sub>≡ (<em>B </em>− <em>kv</em>)<em><sup>a</sup></em><sup>+<em>ux </em></sup>(mod <em>N</em>).</li>

</ol>

Server computes <em>K</em><sub>server </sub>≡ (<em>Av<sup>u</sup></em>)<em><sup>b </sup></em>(mod <em>N</em>).

<ol start="4">

 <li>Client computes and sends <em>M</em><sub>1 </sub>= <em>H</em>(<em>A</em>||<em>B</em>||<em>K</em><sub>client</sub>).</li>

 <li>Server computes <em>H</em>(<em>A</em>||<em>B</em>||<em>K</em><sub>server</sub>) and compares the result to <em>M</em><sub>1</sub>. If they match, output a string indicating success; otherwise, abort.</li>

 <li>Server computes and sends <em>M</em><sub>2 </sub>= <em>H</em>(<em>A</em>||<em>M</em><sub>1</sub>||<em>K</em><sub>server</sub>).</li>

 <li>Client computes <em>H</em>(<em>A</em>||<em>M</em><sub>1</sub>||<em>K</em><sub>client</sub>) and compares the result to <em>M</em><sub>2</sub>. If they match, output a string indicating success; otherwise, abort.</li>

</ol>

Steps 1-3 generate the authenticated key shared between the Client and the Server. Steps 4-7 verify that both parties have computed the same shared key. If executed honestly, <em>K</em><sub>client </sub>and <em>K</em><sub>server </sub>are equal and the Server and Client were able to authenticate each other and establish a shared session key.

<strong>Problem. </strong>Your task is to implement the password-based key agreement protocol above in Python 3. Your program should consist of two modules, a Client and a Server, which communicate via a socket connection. All messages over the socket should be echoed to standard output by both the sending and receiving party. Each echoed message should <em>clearly </em>indicate its sender and intended receiver.

Use the implementation of SHA-256 from the Python cryptography library for your hash function. All other protocol steps should be implemented by yourself, although you may make use of other libraries in your code. A mathematical library like sympy may be useful for handling prime numbers.

<strong>Specifications. </strong>Design and implement your solution as two Python 3 programs entitled Client and Server, invoked by the respective commands

python3 Client.py               and              python3 Server.py

The Server program performs initialization as follows:

<ol>

 <li>Generates a random 512-bit safe prime by first generating a 511-bit random prime <em>q </em>and then checking whether <em>N </em>= 2<em>q </em>+ 1 is prime. If it isn’t, generate a new prime <em>q </em>and try again until a valid <em>N </em>is found.</li>

 <li>Finds a primitive root <em>g </em>of <em>N</em>.</li>

 <li>Establishes a socket connection to the Client and sends (<em>N,g</em>) to the Client via this socket connection.</li>

</ol>

The Client program performs registration as follows:

<ol>

 <li>Prompts user for a username <em>I </em>and a password <em>p</em>.</li>

 <li>Generates a random 16-byte salt <em>s </em>and computes the value <em>v </em>as described in step 2 of the registration phase.</li>

 <li>Sends the triple (<em>I,s,v</em>) to the Server via socket connection.<a href="#_ftn4" name="_ftnref4"><sup>[4]</sup></a></li>

</ol>

In addition, you must adhere to the following specifications for parameter generation and hashing:

<ul>

 <li>Generate all random numbers using a <em>secure </em>random number generator.</li>

 <li>Ensure that 0 ≤ <em>a,b </em>≤ <em>N </em>− 2.</li>

 <li>Use the implementation of SHA-256 from hazmat.primitives import hashes as your hash function.</li>

</ul>

<strong>Submission. </strong>Submit a description of your implementation in a separate README file in text format. <em>Do </em><em>not include the written portion of the programming problem in the PDF file containing your solutions to the written problems. </em>Your description must include the following:

<ul>

 <li>A short argument and citation for the security of the random number generator you used.</li>

 <li>The procedures you used for generating your prime <em>N </em>and your primitive root <em>g </em>of <em>N</em>.</li>

 <li>A list of the files you have submitted that pertain to the problem, and a short description of each file.</li>

 <li>A list of what is implemented in the event that you are submitting a partial solution, or a statement that the problem is solved in full.</li>

 <li>A list of what is not implemented in the event that you are submitting a partial solution.</li>

 <li>A list of known bugs, or a statement that there are no known bugs.</li>

</ul>

<h1>Bonus Problem for CPSC 418 and MATH 318</h1>

<strong>Problem 10 </strong>— Playfair cipher cryptanalysis, 10 marks

Decrypt the following ciphertext that was encrypted using a <em>Playfair </em>cipher. You will need to research on our own how this cipher works since we did not discuss it in class. Show all your work; including a description of any software you used and what you used it for in case you did any programming for your solution. If you wish to submit source code, please include it as text at the end of the PDF file containing your answers to the written problems. Answers without satisfactory explanation and documentation of how they were obtained will receive <em>no </em>credit. Neither will answers obtained by simply running Playfair decryption from an online crypto applet or website on the ciphertext.

A text file containing the ciphertext can be downloaded from the “assignments” page.

<em>Hint: </em>the letter “J” is omitted from the alphabet to obtain the required 5 × 5 key square.

DBFNE XTZMF TOVBQ BQTOB XAOFP RTZEQ RHQKQ VDXOK ABPRQ

IELTV KEEXX SFSBP WDBOB YBFRO EABOR HQKQV TXGUE LABTH

TRXNO NEAAY XHBOH NEXBS HRQBZ MSEXP HFGZU GKCBD POEAA

YXHBO XPHFK RQIAB PRQIE LBXFZ BISEF XPBRA PRQIW CBRXD

YGTBQ TEAAY XHBOH NEXBS HRQBP RQIEL BXBTH BQBNF SISEB

XNUXP BURBX BQROX BATBR HBPWD RPROG UGXQR SEZYO XBAEL

AXCWB YBASX RKROP RHBOP BDPIC NOXEM RPKRX TELAX CWEQF

ZSXEL RHROP RHBUX DASEX NZNGU ELBXF SDGDB TBZLV ERHBO

RQ

<a href="#_ftnref1" name="_ftn1">[1]</a> This is a standard name for active attackers and is meant to be reminiscent of the word “malicious”.

<a href="#_ftnref2" name="_ftn2">[2]</a> We denote this prime by <em>N</em>, rather than <em>p</em>, because the letter <em>p </em>is reserved for the client’s password.

<a href="#_ftnref3" name="_ftn3">[3]</a> In practice, this needs to be done in a secure and tamper-proof manner. Also, in the computation of <em>v</em>, the client would use a hash of their password <em>p </em>rather than just <em>p</em>. For details, see the protocol description in Problem 9.

<a href="#_ftnref4" name="_ftn4">[4]</a> You may assume that the registration is done in a secure and authenticated manner for this exercise.