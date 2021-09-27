#!/usr/bin/R

library(rvest)
library(polite)
library(dplyr)
library(magrittr)
library(purrr)
library(kableExtra)
library(hrbrthemes)

url <- "https://en.wikipedia.org/wiki/Manchester_United_F.C."

session = bow(user_agent = "Manchester United Squad list | 2021/2022 Season", url)

ManchesterSquadlist <- scrape(session) %>% html_nodes("table:nth-child(125)") %>% html_table()


ManchesterSquadlist <- as.data.frame(ManchesterSquadlist)

ManchesterSquadlist <- ManchesterSquadlist[c(2:35),]

ManchesterSquadlist <- ManchesterSquadlist[,c(1:4)]

names(ManchesterSquadlist)[1] <- "JerseyNumber"
names(ManchesterSquadlist)[2] <- "PlayerPosition"
names(ManchesterSquadlist)[3] <- "Nation"
names(ManchesterSquadlist)[4] <- "PlayerName"

ManchesterSquadlist <- ManchesterSquadlist %>% select(c(3,4,2))

ManchesterSquadlist <- ManchesterSquadlist[c(2:17,19:34),]

ManchesterSquadlist <- ManchesterSquadlist[]

ManchesterSquadlist$PlayerName[5] <- 'Harry Maguire (captain)'

kbl(ManchesterSquadlist) %>%  kable_styling(bootstrap_options = "striped", full_width = F, position = "left") %>% column_spec(2, image = spec_image(c(
  "https://upload.wikimedia.org/wikipedia/commons/8/89/Bandera_de_Espa%C3%B1a.svg",
  "https://upload.wikimedia.org/wikipedia/en/4/4c/Flag_of_Sweden.svg",
  "https://upload.wikimedia.org/wikipedia/commons/f/fe/Flag_of_C%C3%B4te_d%27Ivoire.svg",
  "https://upload.wikimedia.org/wikipedia/en/b/be/Flag_of_England.svg",
  "https://upload.wikimedia.org/wikipedia/en/b/be/Flag_of_England.svg",
  "https://upload.wikimedia.org/wikipedia/en/c/c3/Flag_of_France.svg",
  "https://upload.wikimedia.org/wikipedia/commons/5/5c/Flag_of_Portugal.svg",
  "https://upload.wikimedia.org/wikipedia/commons/8/89/Bandera_de_Espa%C3%B1a.svg",
  "https://upload.wikimedia.org/wikipedia/en/c/c3/Flag_of_France.svg",
  "https://upload.wikimedia.org/wikipedia/en/b/be/Flag_of_England.svg",
  "https://upload.wikimedia.org/wikipedia/en/b/be/Flag_of_England.svg",
  "https://upload.wikimedia.org/wikipedia/en/b/be/Flag_of_England.svg",
  "https://upload.wikimedia.org/wikipedia/en/b/be/Flag_of_England.svg",
  "https://upload.wikimedia.org/wikipedia/commons/f/fe/Flag_of_C%C3%B4te_d%27Ivoire.svg",
  "https://upload.wikimedia.org/wikipedia/en/0/05/Flag_of_Brazil.svg",
  "https://upload.wikimedia.org/wikipedia/commons/5/5c/Flag_of_Portugal.svg",
  "https://upload.wikimedia.org/wikipedia/en/c/c3/Flag_of_France.svg",
  "https://upload.wikimedia.org/wikipedia/commons/5/5c/Flag_of_Portugal.svg",
  "https://upload.wikimedia.org/wikipedia/commons/f/fe/Flag_of_Uruguay.svg",
  "https://upload.wikimedia.org/wikipedia/en/b/be/Flag_of_England.svg",
  "https://upload.wikimedia.org/wikipedia/en/b/be/Flag_of_England.svg",
  "https://upload.wikimedia.org/wikipedia/en/b/be/Flag_of_England.svg",
  "https://upload.wikimedia.org/wikipedia/en/b/be/Flag_of_England.svg",
  "https://upload.wikimedia.org/wikipedia/en/0/05/Flag_of_Brazil.svg",
  "https://upload.wikimedia.org/wikipedia/en/b/be/Flag_of_England.svg",
  "https://upload.wikimedia.org/wikipedia/commons/f/ff/Flag_of_Serbia.svg",
  "https://upload.wikimedia.org/wikipedia/commons/2/20/Flag_of_the_Netherlands.svg",
  "https://upload.wikimedia.org/wikipedia/en/4/4c/Flag_of_Sweden.svg",
  "https://upload.wikimedia.org/wikipedia/commons/1/10/Flag_of_Scotland.svg",
  "https://upload.wikimedia.org/wikipedia/en/b/be/Flag_of_England.svg",
  "https://upload.wikimedia.org/wikipedia/commons/c/ce/Flag_of_Tunisia.svg",
  "https://upload.wikimedia.org/wikipedia/en/b/be/Flag_of_England.svg"), 70,70)) %>%  column_spec(1:4, bold = T, border_right = T)%>% column_spec(2:4, width = "0.5em", background = "#FF7F7F") %>% footnote(general = "Data scrapped from Wikipedia.com")

