# Olah Data Semarang
# WhatsApp : +6285227746673
# IG : @olahdatasemarang_
# Levinsohn Petrin Estimation of Production Functions Use estprod With (In) R Software
install.packages("readxl")
install.packages("httr")
install.packages("estprod")
library("httr")
library("readxl")
library("estprod")
# Import Data Excel Into R From Github Olah Data Semarang (timbulwidodostp)
github_link <- "https://github.com/timbulwidodostp/estprod/raw/main/estprod/estprod.xlsx"
temp_file <- tempfile(fileext = ".xlsx")
req <- GET(github_link, 
# authenticate using GITHUB_PAT
authenticate(Sys.getenv("GITHUB_PAT"), ""),
# write result to disk
write_disk(path = temp_file))
estprod <- readxl::read_excel(temp_file)
# Estimate Levinsohn Petrin Estimation of Production Functions Use estprod With (In) R Software
levinsohn_model<-levinsohn_petrin(data=estprod,var1~var2|var3|var4,exit=~exit,id="id",time="year",bootstrap=TRUE)
summary(levinsohn_model)

# Levinsohn Petrin Estimation of Production Functions Use estprod With (In) R Software
# Olah Data Semarang
# WhatsApp : +6285227746673
# IG : @olahdatasemarang_
# Finished
