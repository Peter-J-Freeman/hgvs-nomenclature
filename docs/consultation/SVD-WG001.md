## Community Consultation

### NOTE

In the original proposal the descriptions included the nucleotide (A, C, G or T) that was identified as not changed (g.50377648A=, c.1823A=, n.611T=). It should be noted that, following existing HGVS standards (e.g. g.123456del, c.123dup) this addition is **not necessary**; g.50377648=, c.1823= and n.611= are correct and preferred HGVS descriptions.

### Proposal SVD-WG001 (no change)

- Status: <code class="spot1">accepted</code>: proposal SVD-WG001 was opened for **Community Consultation** on May 14 (2015), closing on Jul.16 (2015). Since no major objections were received the SVD-WG decided to **accept** the proposal on Oct.6 (2015). The proposal was part of the HGVS nomenclature **version 15.11** update.

The proposal suggests to extend the HGVS recommendations to allow description of **variant tested but no change detected** using the character `=` (equal to); g.50377648<code class="spot1">=</code>, m.15366<code class="spot1">=</code>, c.1823<code class="spot1">=</code>, n.611<code class="spot1">=</code>, r.377<code class="spot1">=</code>, p.Val76<code class="spot1">=</code>. The description should include the position(s) screened (nucleotides or amino acids) and the reference sequence used should always be mentioned.

### Examples

#### DNA

- NC_000023.11:g.32867908=: a screen was performed showing that nucleotide g.32867908 was a "G" like in the genomic reference sequence (the nucleotide was not changed).
- NM_004006.1:c.123=: a screen was performed showing that nucleotide c.123 was a "C" like in the coding DNA reference sequence (the nucleotide was not changed).: **NOTE**: the description c.123C>C is not allowed
- NM_004006.1:c.[123=;456=;789=]: a screen was performed showing that nucleotides c.123, c.456 and c.789 (all on the same allele) were identical to the coding DNA reference (the nucleotide was not changed).
- LRG_199t1:c.[633A>G];[633=]: a screen was performed showing that one allele carries variant c.633A>G and the other allele the reference sequence (a "A").: **NOTE**: LRG_199t1:c.[633A>G];[531\_648=;961\_1149=] specifies that only exons 7 (c.531 to c.648) and 10 (c.961 to c.1149) of the DMD gene were analysed.
- NM_001849.3:c.-1\_\*1=: a screen was performed showing that nucleotides c.-1 to c.\*1 of the COL6A2 gene (including the entire protein coding DNA sequence) were as in coding DNA reference sequence NM_001849.3 (exons only).
- NM_001849.3:c.=: a screen was performed showing that the entire coding DNA reference sequence (NM_001849.3, exons only, incl. UTR's) did not contain variants.
- LRG_476:g.4950_39800=: a screen was performed showing that nucleotides g.4950 to g.39800 of the COL6A2 gene were as in the genomic reference sequence (LRG_476, exons and introns).

#### RNA

- NM_004006.1:r.470= &nbsp; (c.470=): a screen was performed showing that nucleotide r.470 (on RNA level) was a "u" as in the RNA reference sequence (the nucleotide was not changed).: **NOTE**: description of the variant at DNA level is mandatory

#### protein

- LRG_199p1:p.(Phe41=) &nbsp; (LRG_199t1:c.123C>T): the predicted consequence of variant c.123C>T (DNA level) is that amino acid residue 41 is an "Arg" like in the protein reference sequence (the nucleotide was not changed, RNA was not analysed).: **NOTE**: description of the variant at DNA level is mandatory (depending on the amino acid, up to 5 different DNA changes may leave the amino acid unchanged).

### [Original proposal](http://www.hgvs.org/mutnomen/comments001.html)
