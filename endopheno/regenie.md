1. make the bed files
2. run step1
 
 1. we need to perform the maf to exclude the low variance snps
    
        /data/saiful/transomic/base_model/gwas/plink  --bfile ./beds_files/merge_bed12  --maf 0.05 --geno 0.1 --hwe 1e-15  --mind 0.1  --write-snplist  --out qc_pass

 2. then run step 1.
       
       
        ../regenie/regenie --bed ./beds_files/merge_bed12 --step 1 --extract qc_pass.snplist --keep keep_ids --phenoFile text --bsize 1000 --lowmem --lowmem-prefix ./temp/test/  --out ./temp/my_test/test_step_1
        
3. run step2


       ../regenie/regenie \
       --step 2 \
       --bed /data6/playyard/skim2/ukbb_imputed/chr1_v3.impute2 \
       --keep keep_ids \
       --phenoFile text \
       --pred /data/saiful/endopheno/data/temp/my_test_pred.list \
       --bsize 400 \
       --split \
       --out ukb_step2_chr1
