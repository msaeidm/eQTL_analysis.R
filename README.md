# eQTL_analysis.R
GTEx data integration for eQTLs
# Example GTEx eQTL data extraction (using public GTEx API)
library(rjson)

gtex_url <- "https://gtexportal.org/api/v2/association/singleTissueEqtl"
gene <- "LTA"  
snp <- "rs909253"

response <- fromJSON(file = paste0(gtex_url, "?geneId=", gene, "&variantId=", snp))
print(paste("eQTL p-value for", snp, ":", response$pvalue))
