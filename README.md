# Gen-711-Final-Project-
Final Project for Gen 711 Class 

<details>
<summary>Methods</summary>

<details>
  <summary>Read Quality</summary>
- Fastqc was run on the samples to summarize read quality and base assessment in HTML format<br />
- The html files were transferred using Powershell and the several figures were observed <br />
</details>

<details>
  <summary>Trimming</summary>
  - Trimmomatic was run on the samples to trim off low quality reads and adapters<br />
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
  - PROKKA 
</details>
      
</details>




<details>
  <summary>Results</summary>

<details>
  <summary>Fastqc</summary>

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

</details>
  
</details>
