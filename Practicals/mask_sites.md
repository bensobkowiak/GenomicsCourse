Solution to masking sites:

```R
require(seqinr)
fasta<-seqinr::read.fasta("P1_aligned.fasta",forceDNAtolower = F)
mask_positions<-c(1:264,29674:29903)
newfasta<-lapply(1:length(fasta), function(x){replace(fasta[[x]],mask_positions,"N")})
names(newfasta)<-names(fasta)
seqinr::write.fasta(newfasta,names(newfasta),"P1_aligned_masked.fasta",open = "w")
```

[Back to activity](Align_consensus.md)
