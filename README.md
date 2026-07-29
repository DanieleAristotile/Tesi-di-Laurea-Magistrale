# 📖 Template Tesi - Istruzioni

Questo repository contiene un **template Bookdown** per la stesura della **tesi**.

Il template articola il lavoro di tesi in **5 capitoli principali**, ma è possibile apportare modifiche a seconda delle proprie esigenze.

La repository contiene diversi file `.Rmd` da compilare (⚙️) in **R Studio**.  In particolare:

| File                 | Descrizione | 
|----------------------|------------------|
| `index.Rmd`          | Metadati del documento (⚙️ **ma ⚠️ non modificare**, se non strettamente necessario) |
| `00-prefazione.Rmd`  | ⚙️ Prefazione - Motivazioni, riflessioni personali e ringraziamenti  (⚙️ max 1 pag,❗**opzionale**) |
| `01-introduzione.Rmd`| ⚙️ Capitolo 1 - Contesto, identificazione problema, revisione letteratura, obiettivi, struttura tesi (20%) |
| `02-metodi.Rmd`      | ⚙️ Capitolo 2 - Presentazione formale delle metodologie statistiche (30%) |
| `03-dati.Rmd`        | ⚙️ Capitolo 3 - Descrizione dati e analisi descrittiva (15%) |
| `04-applicazioni.Rmd`| ⚙️ Capitolo 4 - Presentazione dei risultati, interpretazione e confronto con la letteratura esistente (30%) |
| `05-conclusioni.Rmd` | ⚙️ Capitolo 5 - Riepilogo dei risultati, contributo del lavoro, limitazioni e possibili sviluppi futuri (5%) |
| `06-bibliografia.Rmd`| ⚙️ **ma ⚠️ non modificare**. La bibliografia viene generata dal file `biblio.bib` |

*Nota*: la percentuale riportata intende fornire un'indicazione di massima sulla proporzione di ciascun capitolo rispetto al lavoro di tesi, senza considerare Prefazione, Appendici e Bibliografia.

Altri file inclusi nella repository:

| File | Descrizione |
|--------------------|--------------|
| `biblio.bib` | File BibTeX dove riportare i riferimenti bibliografici (❗**modificare, ma non compilare**) |
| `frontespizio.tex` | **Frontespizio**: inserire titolo, info personali e eventuale dedica (❗**modificare, ma non compilare**) |
| `logoSapienza.png` |  Logo Sapienza ufficiale da utilizzare per la versione PDF (⚠️ **non modificare**) |
| `_bookdown.yml` | Impostazioni generali del book (⚠️ **non modificare**, se non strettamente necessario) |
| `_output.yml` | Impostazioni sul formato output (⚠️ **non modificare**, se non strettamente necessario) |
| `style.css` | Impostazioni per l'output HTML (⚠️ **non modificare**, se non strettamente necessario) |
| `preamble.tex` | Impostazioni generali per generare il PDF (⚠️ **non modificare**, se non strettamente necessario) |


---


## ✍️ Scrittura della tesi

La tesi viene redatta in **R Studio** sfruttando **R Markdown**, un linguaggio che consente di **integrare testo e codice R** nello stesso file. 

In particolare, è possibile 
- scrivere normalmente il testo;
- includere blocchi di codice R (**chunk**) per fare analisi, creare grafici, etc;
- includere formule matematiche sfruttando il linguaggio **LaTeX**;
- creare tabelle;
- caricare immagini esterne;
- citazioni automatiche dai riferimenti bibliografici.

📘 Risorse utili:
- [Guida ufficiale R Markdown](https://bookdown.org/yihui/rmarkdown/)
- [Guida completa Bookdown](https://bookdown.org/yihui/bookdown/)
- [Documentazione LaTeX](https://www.latex-project.org/help/documentation/)
- [Documentazione LaTeX per le formule matematiche](https://www.latex-project.org/help/documentation/amsldoc.pdf)


ℹ️ DATA

Per i dati, ricordatevi che avete accesso alla Banca dati WorkSpace EIKON/ Datastream

L'accesso a questa Banca dati è riservato esclusivamente ai laureandi e agli studenti dei docenti afferenti al MEMOTEF secondo le indicazioni pubblicate sul sito di Facoltà https://economia.web.uniroma1.it/it/workspace-datastream

Per accedere al servizio di consultazione, previsto in sede presso la Biblioteca Milone, occorre scrivere con email istituzionale all’indirizzo

biblioteca.milone@uniroma1.it, mettendo me in cc.

Successivamente la Biblioteca invierà una comunicazione con l'indicazione di giorno e orario di prenotazione della postazione.


---



### 📚 Citazioni e bibliografia

- Inserire i riferimenti nel file **`biblio.bib`** in formato **BibTeX**.
- Per citare una fonte nel testo, usare la sintassi `@chiave`, ad esempio `@smith2020`.  
- La bibliografia viene generata automaticamente alla fine del documento.

📘 Risorse utili:
- [Guida alle citazioni in R Markdown](https://bookdown.org/yihui/bookdown/citations.html)
- [Esempi di file BibTeX](https://www.bibtex.com/g/bibtex-format/)


---


## ⚙️ Compilazione della tesi in HTML 

Per generare la versione HTML, occorre aprire ciascun file `.Rmd` e compilarlo cliccando sul pulsante **Knit** nella barra strumenti di **R Studio**.

Oltre all'anteprima in `.html`, nella cartella `output/` verranno salvati i file. 

*Nota:* la versione HTML non include il frontespizio ed è utile solo in fase di revisione.


## ⚙️ Compilazione della tesi in PDF 

La versione **PDF** della tesi si ottiene eseguendo da Console R il seguente comando:

   ```r
   bookdown::render_book("index.Rmd", "bookdown::pdf_book")
   ```

Il PDF verrà salvato nella cartella `output/` insieme al file sorgente `tesi.tex`.


### 📚 Copertina e frontespizio

La copertina (per la stampa) e il frontespizio della versione definitiva devono seguire le indicazioni Sapienza.

1) Per la **copertina** si raccomanda di usare il [template Word](https://www.uniroma1.it/it/pagina/impaginazione-della-tesi-e-logo)

2) Il **frontespizio** viene generato da questo template, ma solo per la versione PDF. Assicurarsi di aver inserito le **informazioni personali** (titolo, autore, matricola, relatore, anno accademico) nel file `frontespizio.tex`.


---


## 🧱 Requisiti software

Assicurarsi di avere installato le versioni più recenti di [R e RStudio](https://posit.co/download/rstudio-desktop/) 

Installare [MikTex](https://miktex.org) e aggiornare le librerie Tex.

Quindi installare i seguenti pacchetti, da console R:

```r
install.packages("bookdown")
install.packages("tinytex")  # per la compilazione PDF
tinytex::install_tinytex()
```

*Nota*: queste installazioni vanno fatte solo una volta, o comunque periodicamente man mano che le versioni software diventano obsolete.


---

# ⚙️ Uso di GitHub per backup e condivisione

L'idea è quella di connettere GitHub e RStudio in modo che possiate

- salvare agevolmente le modifiche sia su PC/Hard Disk, sia su una vostra repository GitHub

- condividere il vostro repository GitHub, quindi la vostra tesi, con il relatore/correlatore per permettere revisioni, feedback etc.

Per fare ciò, si rimanda a quanto riportato [qui](https://rfortherestofus.com/2021/02/how-to-use-git-github-with-r)

In particolare, basta (e)seguire quanto riportato nelle sezioni:

1) Install Git

2) Config Git

3) Sign up for GitHub

4) How to Connect RStudio Projects with GitHub Repositories (procedura **GitHub First**)





