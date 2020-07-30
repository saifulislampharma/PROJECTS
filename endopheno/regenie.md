1. make the bed files
2. run step1
 
 1. we need to perform the maf to exclude the low variance snps
    
      /data/saiful/transomic/base_model/gwas/plink  --bfile ./beds_files/merge_bed12  --maf 0.05 --geno 0.1 --hwe 1e-15  --mind 0.1  --write-snplist  --out qc_pass
3. run step2
