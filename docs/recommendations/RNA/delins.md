# Deletion-Insertion

<!-- ## Definition -->

Deletion-Insertion (delins): a sequence change where, compared to a reference sequence, one or more nucleotides are replaced by one or more other nucleotides **and which is not** a substitution, inversion or conversion.

## Syntax

```sh exec="true"
bin/pull-syntax -c -f docs/syntax.yaml rna.delins
```

## Notes

- all variants **should be** described at the DNA level, descriptions at the RNA and/or protein level may be given in addition.
- by definition, when **one** nucleotide is replaced by **one** other nucleotide the change is a [substitution](substitution.md).
- two variants separated by one or more nucleotides should preferably be described individually and **not** as a "delins"
  - exception: two variants separated by one nucleotide, together affecting one amino acid, should be described as a "delins" (e.g. `r.142_144delinsugg` `p.(Arg48Trp)`). **NOTE:** this prevents tools predicting the consequences of a variant to make conflicting and incorrect predictions of two different substitutions at one position.
  - **conversions**, a sequence change where a range of nucleotides are replaced by a sequence from elsewhere in the genome, are described as a "delins". The previous format "con" is no longer used (see [Community Consultation SVD-WG009)](../../consultation/SVD-WG009.md)).
- RNA-fusion transcripts represent a special case of deletion-insertion variant. The fusion break point is described using **"::"**. **NOTE:** to avoid confusion, HGVS recommends to follow the [HGNC guidelines](https://www.genenames.org/about/guidelines/) to describe products of gene translocations or fusions (format GENESYMBOL1::GENESYMBOL2) and readthrough transcripts (format GENESYMBOL1-GENESYMBOL2).
- for all descriptions the **most 3' position** possible of the reference sequence is arbitrarily assigned to have been changed (**3'rule**)

## Examples

- `r.775delinsga`: a deletion of nucleotide r.775 (a "u", not described), replaced by nucleotides "ga", changing <code>..aggc<code class="del">u</code>cauu..</code> to <code>..aggc<code class="ins">ga</code>cauu..</code>.
- `r.775_777delinsc` : a deletion of nucleotides r.775 to r.777 ("uca", not described), replaced by nucleotides "c", changing <code>..aggc<code class="del">uca</code>uu..</code> to <code>..aggc<code class="ins">c</code>uu..</code>.
- `r.902_909delinsuuu`: a deletion of nucleotides r.902 to r.909, replaced by nucleotides uuu
- `r.142_144delinsugg` (`p.Arg48Trp`): a deletion replacing nucleotides r.142 to r.144 (cga, not described) with ugg. **NOTE:** the variant can also be described as `r.[142c>u;144a>g]`, i.e. two substitutions. This format is preferred when either of the two variants is known as a frequently occurring variant ("polymorphism")
- RNA conversion (based on [SVD-WG009](../../consultation/SVD-WG009.md))
  - `NM_004006.2:r.2623_2803delins2804_2949`: conversion replacing nucleotides r.2623 to r.2803 (exon 21) with nucleotides r.2804 to r.2949 (exon 22) as found in the DMD coding RNA sequence file NM_004006.2
  - `r.415_1655delins[AC096506.5:g.409_1649]`: conversion replacing nucleotides r.414 to r.1655 with nucleotides 409 to 1649 as found in the genomic reference sequence AC096506.5
  - `r.1401_1446delins[NR_002570.3:r.1513_1558]`: conversion in exon 9 of the CYP2D6 gene replacing exon 9 nucleotides r.1401 to r.1446 with those of the 3' flanking CYP2D7P1 gene, nucleotides r.1513 to r.1558
- RNA fusion transcripts (based on [SVD-WG007](../../consultation/SVD-WG007.md))
  - translocation fusion: `NM_152263.2:r.-115_775::NM_002609.3:r.1580_*1924` describes a TPM3::PDGFRB fusion transcript where nucleotides r.-115 to r.775 (reference transcript NM_152263.2, TPM3 gene) are coupled to nucleotides r.1580 to r.\*1924 (reference transcript NM_002609.3, PDGFRB gene)
  - **deletion fusion**
    - `NM_002354.2:r.-358_555::NM_000251.2:r.212_*279`: describes an EPCAM::MSH2 fusion transcript where nucleotides r.-358 to r.555 (reference transcript NM_002354.2, EPCAM gene) are coupled to nucleotides r.212 to r.\*279 (reference transcript NM_000251.2, MSH2 gene)
    - `NM_002354.2:r.?_555::guaugauuuuuuaataa::NM_000251.2:r.212_?`: describes an EPCAM::MSH2 fusion transcript where only the fusion break point has been characterised, showing the insertion of a 17 nucletoide sequence (guaugauuuuuuaataa) between two fusion transcripts

## Discussion

!!! note "What is an **"indel"**?"

    The term "indel" is not used in HGVS nomenclature (see [Glossary](../../background/glossary.md). The term is confusing, having different meanings in different disciplines.

!!! note "Can I describe a "gc" to "ug" variant as a dinucleotide substitution (<code class="invalid">r.4gc>ug</code>)?"

    No this is not allowed. By definition a substitution changes **one** nucleotide into **one** other nucleotide (see [Substitution](http://www.HGVS.org/varnomen/recommendations/RNA/variant/substitution/)). The change <code>augu<code class="del">gc</code>ca</code> to <code>augu<code class="ins">ug</code>ca</code> should be described as `r.5_6delinsug`, i.e. a deletion/insertion (indel).

!!! note "The BRCA1 coding RNA reference sequence from position r.2074 to r.2080 is `caugaca`. A variant frequently found in the population is <code>cau<code class="sub">a</code>aca</code> (`r.2077g>a`). In a patient I found the sequence <code>cau<code class="sub">a</code><code class="ins">ua</code>aca</code>. Can I describe this variant as <code class="invalid">r.[2077g>a;2077_2078insua]</code>?"

    The shortest description of this variant is `r.2077delinsaua`. However, since the variant is likely a combination of two other variants it is acceptable to describe it as <code class="invalid">r.[2077g>a;2077_2078insua]</code>.
