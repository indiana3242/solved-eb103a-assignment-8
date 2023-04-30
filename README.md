Download Link: https://assignmentchef.com/product/solved-eb103a-assignment-8
<br>
<ul>

 <li>Description</li>

 <li>Unless specified otherwise, you have to show <em>all </em>of your work. We cannot look into your mind and determine 72 your thinking process unless it is written out. You may refer to the numbers of the FDs as you refer to the 73 original FDs or as you number FDs in the new sets you get to simplify your explanation.</li>

</ul>

74                  2. You have to follow the procedures we covered in class and not any other procedures for what’s asked for. 75             You must use only the algorithmic techniques and not the ad-hoc approach that was described using the 76         university example, which may or may not work.

<ul>

 <li>2 Review of the procedure</li>

 <li>For your convenience a summary is provided. It may or may not be helpful for any specific question.</li>

 <li>Input: A relational schema (informally, a relation) R and a set of FDs <em>α</em>.</li>

 <li>Output: A set of relational schemas (informally, relations) such that the decompostion (a formal term for the</li>

 <li>set) satisfies the conditions</li>

 <li>It is lossless join</li>

 <li>It preserves dependencies 84 3. The resulting tables are in 3NF. 85 Procedure:</li>

 <li>Find a minimal cover for <em>α</em>, say <em>ω</em></li>

 <li>Produce a relation from each FD in <em>ω </em>by combining the attributes from both the LHS and the RHS</li>

 <li>One by one, remove a relation that is a subset of another relation</li>

 <li>If (at least) one of the relations contains a key of R, you are done</li>

 <li>Otherwise, add a relation whose attributes form a key for R</li>

 <li>Example 1. Assume that I am supposed to do that for</li>

 <li>Relational Schema R = ABCDEF, with the following set of FDs</li>

 <li><em>α</em>:</li>

 <li>AA → ABB</li>

 <li>AB → C</li>

 <li>B → C</li>

 <li>E → F</li>

 <li>F → E</li>

 <li>I will start with the given set as Old, and I will attempt to simplify it by producing a “candidate” set New. In 100 general, the two sets are not equivalent. I can replace Old by New if and only if I can prove equivalence.</li>

</ul>

101                    Let’s start. Below we have a table with the current Old and the proposed New.

<table width="199">

 <tbody>

  <tr>

   <td width="115">Old</td>

   <td width="84">New</td>

  </tr>

  <tr>

   <td width="115">1. AA → ABB</td>

   <td width="84">1. A → B</td>

  </tr>

  <tr>

   <td width="115">2. AB → C</td>

   <td width="84">2. AB → C</td>

  </tr>

  <tr>

   <td width="115">3. B → C</td>

   <td width="84">3. B → C</td>

  </tr>

  <tr>

   <td width="115">4. E → F</td>

   <td width="84">4. E → F</td>

  </tr>

  <tr>

   <td width="115">5. F → E</td>

   <td width="84">5. F → E</td>

  </tr>

 </tbody>

</table>

102

103 New was obtained by removing the “defective” parts of Old (which appeared only in 1.), which produces a 104 trivially equivalent New, so there is nothing to do for proving the equivalence. New now becomes Old.

<table width="173">

 <tbody>

  <tr>

   <td width="92">Old</td>

   <td width="81">New</td>

  </tr>

  <tr>

   <td width="92">1. A → B</td>

   <td width="81">1. A → B</td>

  </tr>

  <tr>

   <td width="92">2. AB → C</td>

   <td width="81">2. A → C</td>

  </tr>

  <tr>

   <td width="92">3. B → C</td>

   <td width="81">3. B → C</td>

  </tr>

  <tr>

   <td width="92">4. E → F</td>

   <td width="81">4. E → F</td>

  </tr>

  <tr>

   <td width="92">5. F → E</td>

   <td width="81">5. F → E</td>

  </tr>

 </tbody>

</table>

105

106 We attempt to simplify 2. in Old getting 2. in New. New could only be stronger, so to prove equivalence we 107          need to prove 2. in New from all in Old.

108 We compute A<sup>+ </sup>= ABC, and as it contains C, we proved equivalence. New becomes Old.

<table width="173">

 <tbody>

  <tr>

   <td width="81">Old</td>

   <td width="92">New</td>

  </tr>

  <tr>

   <td width="81">1. A → B</td>

   <td width="92">1. A → BC</td>

  </tr>

  <tr>

   <td width="81">2. A → C</td>

   <td width="92">2. B → C</td>

  </tr>

  <tr>

   <td width="81">3. B → C</td>

   <td width="92">3. E → F</td>

  </tr>

  <tr>

   <td width="81">4. E → F 5. F → E</td>

   <td width="92">4. F → E</td>

  </tr>

 </tbody>

</table>

109

110 We attempt to simplify 1. and 2. in Old getting 1. in New. This is an application of the union rule, which always 111 produces an equivalent set. So there is nothing to prove/check and New becomes Old.

<table width="173">

 <tbody>

  <tr>

   <td width="92">Old</td>

   <td width="81">New</td>

  </tr>

  <tr>

   <td width="92">1. A → BC</td>

   <td width="81">1. A → C</td>

  </tr>

  <tr>

   <td width="92">2. B → C</td>

   <td width="81">2. B → C</td>

  </tr>

  <tr>

   <td width="92">3. E → F</td>

   <td width="81">3. E → F</td>

  </tr>

  <tr>

   <td width="92">4. F → E</td>

   <td width="81">4. F → E</td>

  </tr>

 </tbody>

</table>

112

113 We will try something that does not work, just to have an example. You do <em>not </em>need to try transformations that 114                     you believe do not work (if your belief is correct).

115 We attempt to simplify 1. in Old getting 1. in New. New could only be weaker, so to prove equivalence we need 116                     to prove 1. in Old from all in New.

117 We compute A<sup>+ </sup>= AC. As BC is not in AC, we proved non-equivalence. So we continue with Old (and do not 118            replace it by New).

<table width="173">

 <tbody>

  <tr>

   <td width="92">Old</td>

   <td width="81">New</td>

  </tr>

  <tr>

   <td width="92">1. A → BC</td>

   <td width="81">1. A → B</td>

  </tr>

  <tr>

   <td width="92">2. B → C</td>

   <td width="81">2. B → C</td>

  </tr>

  <tr>

   <td width="92">3. E → F</td>

   <td width="81">3. E → F</td>

  </tr>

  <tr>

   <td width="92">4. F → E</td>

   <td width="81">4. F → E</td>

  </tr>

 </tbody>

</table>

119

120 We attempt to simplify 1. in Old getting 1. in New. New could only be weaker, so to prove equivalence we need 121                     to prove 1. in Old from all in New.

<ul>

 <li>We compute A<sup>+ </sup>= ABC. As BC is in ABC, we proved equivalence.</li>

 <li>We are done, but in general we need to make sure that no simplifications are possible. Here this is trivial because</li>

 <li>There are no defective parts</li>

 <li>The union rule cannot be applied</li>

 <li>Both sides of all the FDs consist of one attribute only, so no simplification is possible (generally, this step 127 will require more work because even in a minimal cover there may be several attributes in some sides of 128 some FDs, and we need to check whether some of them should be removed).</li>

 <li>Our minimal cover <em>ω </em>is</li>

 <li>A → B</li>

 <li>B → C</li>

 <li>E → F</li>

 <li>F → E</li>

 <li>We get the following tables/relations</li>

 <li>AB 136 2. BC</li>

 <li>EF</li>

 <li>FE</li>

 <li>We remove FE because it is a subset of EF and we get</li>

 <li>AB 141 2. BC</li>

 <li>EF</li>

 <li>We now proceed to get a global key for R. Perhaps one of the 3 tables already includes a global key for R. We 144 compute</li>

 <li>AB<sup>+ </sup>= ABC</li>

 <li>BC<sup>+ </sup>= BC</li>

 <li>EF<sup>+ </sup>= EF</li>

 <li>but we need R = ABCDEF.</li>

 <li>We examine all the attributes of R accounting for all the FDs that are satisfied. It may be simplest to use the 150 minimal cover, so we will do that. But you can use any equivalent set of FDs, including the initial set given to us.</li>

 <li>We classify the attributes based on where they appear in the FDs:</li>

 <li>On both sides: B, E, F</li>

 <li>On left side only: A</li>

 <li>On right side only: C</li>

 <li>Nowhere: D</li>

 <li>AD appear in every key. C does not appear in any key. B, E, and F may appear in a key. We start with ABDEF, 157 which must contain a key. We cannot remove AD but may try to remove B, E, and F.</li>

 <li>We attempt to remove B. We compute ADEF<sup>+ </sup>= ABCDEF. We can remove B and we continue with ADEF.</li>

 <li>We attempt to remove E. We compute ADF<sup>+ </sup>= ABCDEF. We can remove E and we continue with ADF.</li>

 <li>We attempt to remove F. We compute AD<sup>+ </sup>= ABCD. We cannot remove F and we continue with ADF.</li>

 <li>Nothing else can be done. To remind: AD have to be in every key and we cannot remove F from ADF (because 162 we tried to remove it and did not succeed).</li>

</ul>

163                   As nothing else can be done, ADF is a global key. (ADE is another global key, but we are only looking for one.) 164          Our final decomposition is

<ul>

 <li>AB</li>

 <li>BC</li>

 <li>EF</li>

 <li>ADF</li>

 <li>3 Assignments</li>

 <li>You are given a relational schema R = ABCDE satisfying the set of FDs <em>α</em>:</li>

 <li>AC → E</li>

 <li>AC → CB</li>

 <li>E → DE</li>

 <li>D → B</li>

 <li>(a) Compute <em>ω</em>, a minimal cover for <em>α</em>. You do not need to prove that what you claim to be a minimal 176 cover is in fact a minimal cover.</li>

 <li>Review Example 1.</li>

 <li><em>Do not skip any steps in your solution. </em>That means for your larger case</li>

 <li>Whenever your want to show an equivalence of two sets of FDs, you need to <em>explicitly </em>compute the 180 closure of an appropriate set of attributes using an appropriate set of FDs.</li>

 <li>You do <em>not </em>need to prove that you have actually obtained a minimal cover. (You will be asked for</li>

 <li>such a proof in another problem.)</li>

 <li>You are given a relational schema R = ABCDEF satisfying the set of FDs <em>α</em>:</li>

 <li>AB → C</li>

 <li>A → E</li>

 <li>DE → F</li>

 <li>E → EF</li>

 <li>F → B</li>

 <li>(a) Compute <em>ω</em>, a minimal cover for <em>α</em>. You do not need to prove that what you claim to be a minimal 190 cover is in fact a minimal cover.</li>

 <li>Review Example 1.</li>

 <li><em>Do not skip any steps in your solution. </em>That means for your larger case</li>

 <li>Whenever your want to show an equivalence of two sets of FDs, you need to <em>explicitly </em>compute the 194 closure of an appropriate set of attributes using an appropriate set of FDs.</li>

 <li>You do <em>not </em>need to prove that you have actually obtained a minimal cover. (You will be asked for</li>

 <li>such a proof in another problem.)</li>

 <li>You are given a relational schema R = ABCDEFGH satisfying the set of FDs:</li>

 <li>AB → CD</li>

 <li>C → EF</li>

 <li>E → C</li>

 <li>F → G</li>

 <li>(a) Prove that the given set of FDs is already a minimal cover. To do that show that no simplification is 203 Attempt all simplifications.</li>

</ul>

204 To show that a simplification is not possible, you will need to <em>explicitly </em>compute the closures of the 205 relevant sets of attributes using the FDs in a relevant set of FDs. Do not use any shortcuts or heuristics.

<ul>

 <li>(b) Produce a decomposition satisfying the conditions for Output in Section 3.2.</li>

</ul>