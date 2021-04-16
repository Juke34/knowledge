# The SUGAR format

Sugar is **S**imple **U**n**G**apped **A**lignment **R**eport, which displays ungapped alignments one-per-line. 
The sugar line starts with the string "sugar:" for easy extraction from the output, and is followed by the following 9 fields in the order below:

>1. query identifier  
>2. query start position  
>3. query stop position  
>4. query strand  
>5. target identifier  
>6. target start position  
>7. target stop position  
>8. target strand  
>9. score  

Here an example of SUGAR format:  
>sugar: hs989235.cds 5 468 + hsnfg9.embl 25689 27450 + 1916

This format is used by Exonerate and seems to have been originaly developed for this tool.
The format is related to the [CIGAR](cigar.md) format which add an extra (10th) field to describe Gaped alignment.
