+++
draft = false
type = "blog"
image = "/blog_img/2019-03-29/cover.png"
thumbImage = "/blog_img/2019-03-29/marker-5.png"
frontPageImage = "/blog_img/2019-03-29/marker-5.png"
date = "2019-04-01"
title = "Importing and Using Your Own Marker Genes"
hardLineBreak = true 
categories = ["marker genes", "import", "Score Cells"]
joinLines = false
author = "Iva Černoša"
shortExcerpt = "If you ever felt limited by the Marker Gene widget, here you can discover how to bypass it" 
longExcerpt = "If you ever felt limited by the Marker Gene widget, here you can discover how to bypass it by importing your own marker genes and using them to score your dataset" 
+++
<i><b>Note:</b> This blog heavily references and uses the data we identified in our previous blog <a href="https://singlecell.biolab.si/blog/2019-03-pancreas-baron-cellsyst2016/">Clustering Cells in Mouse Pancreas</a>, therefore it is advisable for everyone less experienced with scOrange to read it before tackling this one.</i>
<br>
<br>
Orange already has a build-in widget with marker genes, but what if your marker genes are not included in its library? Well, there is no reason to give up, with only a few extra steps you can easily import your own. 
\
{{% figure src="/blog_img/2019-03-29/marker-1-1.png" %}}
\
As usual, we first need to import our data. We are using the data from mouse pancreas (<a href="https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5228327/">Baron <i>et al.</i></a>, GEO accession: <a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE84133">GSE84133</a>). We import and normalise our data using Load Data, Gene Name Matcher and Single Cell Preprocess widgets (a detailed description of these steps is available in our previous blog <a href="https://singlecell.biolab.si/blog/2019-03-pancreas-baron-cellsyst2016/">Clustering Cells in Mouse Pancreas</a>). Alternatively, you can avoid downloading the data from the GEO database by using the Single Cell Datasets widget to load the dataset Pancreas cells in mouse.
\
{{% figure src="/blog_img/2019-03-29/marker-1-2.png" %}}
\
We can import our marker genes using the File widget. Here we are using the marker genes that we identified and saved in the last steps of our earlier blog. Marker genes can be formatted in a simple table. In case your data does not include Entrez IDs for your genes, you have to process them with the Genes widget first (with organism set to <i>Mus Musculus</i> in this case), so that scOrange assigns them Entrez IDs and can later match them to the genes in the data you are analysing. 
\
{{% figure src="/blog_img/2019-03-29/marker-2.PNG" %}}
\
To connect out marker genes and our data, we use Score Cells widget and make sure we correctly mark our input data. Marker genes should be attached as genes and our data as data. 

{{% figure src="/blog_img/2019-03-29/marker-3.PNG" %}}
\
Orange has now scored cells based on our markers. To visualise this, we use t-SNE and colour cells based on the Cell Score with it. Since yellow coloured cells in this graph represent cells that score higher for selected genes and we selected the markers for beta cells in in the previous step, these are more likely to be beta cells. 

{{% figure src="/blog_img/2019-03-29/marker-4.png" %}}
\
*References*
<br>
Baron M., Veres A., Wolock S..L, <i>et al.</i> A Single-Cell Transcriptomic Map of the Human and Mouse Pancreas Reveals Inter- and Intra-cell Population Structure. <i>Cell Syst.</i> 2016;3(4):346–360.e4. doi:10.1016/j.cels.2016.08.011
