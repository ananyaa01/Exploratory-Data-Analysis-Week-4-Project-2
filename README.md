# Exploratory-Data-Analysis-Week-4-Project-2
Coursera: Exploratory Data Analysis - Project 2 [ Week 4 ]


library(ggplot2)

baltimoreNEI <- NEI[NEI$fips=="24510",]

png("Plot3.png",width=550,height=450)

ggp <- ggplot(baltimoreNEI,aes(factor(year),Emissions,fill=type)) +
    geom_bar(stat="identity") +
    theme_bw() + guides(fill=FALSE)+
    facet_grid(.~type,scales = "free",space="free") + 
    labs(x="year", y=expression("Total PM"[2.5]*" Emission (Tons)")) + 
    labs(title=expression("PM"[2.5]*" Emissions, Baltimore City 1999-2008 by Source Type"))

print(ggp)

dev.off() 
