# Gen-711-Final-Project-
Final Project for Gen 711 Class 

<details>
  <summary>Background</summary>
  The data and methods for this project were taken from https://github.com/Joseph7e/MDIBL-T3-WGS-Tutorial. The goal of the research was to study seaweed-eating microbes collected from MDIBL, Acadia National Park. The data was collected by Anthony Hay, Steven Weicksel, Dana-Lynn Koomoa-Lange, Leah Elliot, Melissa Chisholm, and Princess Rodriguez. The DNA was extracted and Illumina sequencing was used for downstream analysis. 
</details>

<details>
<summary>Methods</summary>

<details>
  <summary>Read Quality</summary>
- Fastqc was run on the samples to summarize read quality and base assessment in HTML format<br />
- The HTML files were transferred using Powershell and several figures were observed <br />
</details>

<details>
  <summary>Trimming</summary>
  - Trimmomatic was run on the samples to trim off low-quality reads and adapters<br />
  - Fastqc was run on the trimmed data to assess read quality <br />
</details>

  <details>
    <summary>Genome Assembly</summary>
      - Genome was put together with SPAdes using the forward, reverse, and unpaired reads <br />
  </details>

<details>
  <summary>Genome Assesment</summary>
  - QUAST was used to assess how well the genome was put together <br />
  - BUSCO was used to determine how complete the genome is using highly conserved genes (OrthoDB) <br />
</details>

<details>
  <summary>Genome Annotation</summary>
  - PROKKA is run to annotate the genome <br />
</details>

<details>
  <summary>Organism Identification</summary>
  - 16s sequence was extracted from the PROKKA output for BLAST <br />
  - BLAST was used to identify the most closely related genome to the sample to attempt to identify the organism <br />
  - The 16s sequence was BLASTed against the contigs generated from SPAdes <br />
</details>

<details>
  <summary>Read Mapping</summary>
  - The fasta file is run through bwa mem to convert it to a SAM file using the forward and reverse reads of the genome <br />
  - samtools was used to construct a coverage table of the SAM files <br />
</details>

<details>
  <summary>Non-Target Contig Removal</summary>
  - blobtools was used to visualize the genome assembly using the contigs file, BLAST hits file, and the SAM file <br />
  - The graph was generated as a png and downloaded to be observed <br />
</details>

<details>
  <summary>Filter Genome Assembly</summary>
  - The blobtools tables were filtered by coverage and length <br />
  - A list of contigs we wanted to keep was constructed <br />
  - The assembly was filtered based on the list of contigs <br />
  - Then the final contigs are BLASTed against UNIvec to ensure no contamination is found <br />
</details>

<details>
  <summary>For Contamination</summary>
  - Take out sequences that came up when the final contigs were BLASTed against UNIvec <br />
  - Go back to QUAST and run down the methods again using BUSCO, PROKKA, BLAST, bwa mem, samtools, and blobtools <br />
  - Once the new final list of contigs has gone through the methods again make sure to BLAST against UNIvec to make sure there is no contamination <br />
</details>
<details>
  <summary>Genome Visualization</summary>
  - The PROKKA .gbk file from after filtering the genome was placed into a program called proksee <br />
  - Proksee gave a visualization of the genome <br />
  - Grant JR, Enns E, Marinier E, Mandal A, Herman EK, Chen C, Graham M, Van Domselaar G, and Stothard P​
        Proksee: in-depth characterization and visualization of bacterial genomes​
        Nucleic Acids Research, 2023, gkad326, https://doi.org/10.1093/nar/gkad326 <br />
</details>
      
</details>




<details>
  <summary>Results</summary>

<details>
  <summary>Fastqc</summary>

-Quality of raw reads before trimming shows slightly poor quality
<details>
  <summary>Caylin Fastqc untrimmed</summary>

![plot](images/Caylin%20R1-1.png)
R1

![plot](images/Caylin%20R2-1.png)
R2

</details>

<details>
  <summary>Graham Fastqc untrimmed</summary>

![plot](images/Graham%20R1-1.png)
R1

![plot](images/Graham%20R2-1.png)
R2

</details>

<details>
  <summary>Ethan Fastqc untrimmed</summary>

![plot](images/Ethan%20R1-1.png)
R1

![plot](images/Ethan%20R2-1.png)
R2

</details>
-Qulaity of trimmed reads using trimmomatic shown to have improved.
<details>
  <summary>Caylin Fastqc trimmed</summary>

![plot](images/Caylin%20R1-2.png)
R1

![plot](images/Caylin%20R2-2.png)
R2

</details>

<details>
  <summary>Graham Fastqc trimmed</summary>

![plot](images/Graham%20R1-2.png)
R1

![plot](images/Graham%20R2-2.png)
R2

</details>

<details>
  <summary>Ethan Fastqc trimmed</summary>

![plot](images/Ethan%20R1-2.png)
R1

![plot](images/Ethan%20R2-2.png)
R2

</details>

</details>

<details>
  <summary>Quast</summary>
-Quast data showing contig lengths GC content and N50 data 
  <details>
    <summary>Caylin</summary>

  ![plot](images/Caylin%20Quast-1.png)
    before

  ![plot](images/Caylin%20Quast-2.png)
    after
  </details>

  <details>
    <summary>Graham</summary>

  ![plot](images/Graham%20Quast-1.png)
    before

  ![plot](images/Graham%20Quast-2.png)
    after
  </details>

  <details>
    <summary>Ethan</summary>

  ![plot](images/Ethan%20Quast.png)
    before

  ![plot](images/Ethan%20Quast-2.png)
    after
  </details>
</details>

<details>
  <summary>Blobtools</summary>
  Identification of organism through blobtools showing both before and after filtering.
  <details>
    <summary>Caylin</summary>

  ![plot](images/Caylin%20Blobtool%201-1.png)
  
  ![plot](images/Caylin%20Blobtool%201-2.png)


After Filtering 
  
  ![plot](images/Caylin%20Blobtool%202-1.png)
  
  ![plot](images/Caylin%20Blobtool%202-2.png)
  </details>
  <details>
    <summary>Graham</summary>

  
  ![plot](images/Graham%20Blobtool%201-1.png)
  
  ![plot](images/Graham%20Blobtool%201-2.png)


After Filtering 
  
  ![plot](images/Graham%20Blobtool%202-1.png)
  
  ![plot](images/Graham%20Blobtool%202-2.png)
  </details>
  <details>
    <summary>Ethan</summary>

  
  ![plot](images/Ethan%20Blobtool%201-1.png)
  
  ![plot](images/Ethan%20Blobtool%201-2.png)


After Filtering 
  
  ![plot](images/Ethan%20Blobtool%202-1.png)
  
  ![plot](images/Ethan%20Blobtool%202-2.png)
  </details>
  
</details>

<details>
  <summary>PROKsee genome visualization</summary>

  ![plot](images/Caylin_visualization.png)
  ![plot](images/Ethan_visualization.png)
  ![plot](images/Graham_visualization.png)
</details>
</details>
