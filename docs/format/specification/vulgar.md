# The VULGAR format

**Vulgar** is **V**erbose **U**seful **L**abelled **G**apped **A**lignment **R**eport, This format also starts with the same 9 fields 
as [SUGAR](sugar.md) output, and is followed by a series of <label, query_length, target_length> triplets. 
The label may be one of the following:  

Operator | Description
-- | --
M | Match
C | Codon
G | Gap
N | Non-equivalenced region
5 | 5' splice site
3 | 3' splice site
I | Intron
S | Split codon
F | Frameshift 

The format seems to have been originally develloped for the Exonerate tool.
The **F** seems to have been used for the definition of the GFF3 gap attribute that use the [CIGAR](cigar.md) string as reference.
