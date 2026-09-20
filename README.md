# P7MExtract

**CAdES / PKCS#7 P7M document extractor**

P7MExtract is a Windows command-line utility designed to extract the original documents contained in digitally signed `.p7m` files.

It can also process `.p7m` files contained inside ZIP archives.

---

## 🇬🇧 English

### Description

**P7MExtract** extracts documents encapsulated in CAdES / PKCS#7 (`.p7m`) containers.

The program automatically detects the type of the extracted document and saves it with the appropriate extension.

Supported document types include:

* PDF
* XML
* HTML
* TXT
* ZIP
* OLE documents
* Binary files

P7M files contained inside ZIP archives are also processed automatically.

The original input files are **never modified**.

---

### Digital Signature Verification

For each P7M file, P7MExtract performs a **cryptographic verification of the CAdES / PKCS#7 digital signature**.

The program reports information such as:

* signer
* signing certificate
* certification authority, when available
* signing date, when available
* signature algorithm
* cryptographic signature validity

The reported signature status refers to the **cryptographic verification of the CMS/PKCS#7 signature**.

It does not by itself constitute a complete validation of the certificate chain, revocation status, OCSP/CRL status, or qualified-signature legal status.

---

### ZIP Archives

When a ZIP archive contains P7M files, the extracted documents are placed in a directory named after the ZIP archive.

For example:

```text
invoice_package.zip
```

produces:

```text
converted/
└── invoice_package/
    ├── invoice001.pdf
    ├── invoice002.pdf
    └── invoice003.xml
```

Standalone P7M files are extracted directly into:

```text
converted/
```

---

### Security

P7MExtract is designed exclusively for extracting documents from CAdES / PKCS#7 containers.

The program:

* verifies CAdES / PKCS#7 digital signatures cryptographically;
* does not execute extracted documents;
* does not launch extracted files;
* does not install additional software;
* does not modify the Windows Registry;
* does not start external applications;
* does not require an Internet connection;
* does not modify the original P7M files;
* writes extracted files to the `converted` directory;
* does not overwrite existing extracted files.

ZIP archive paths are handled defensively to prevent unsafe paths from escaping the extraction directory.

---

### How to use

Place the executable in a directory containing the files to process.

Example:

```text
P7MExtract/
├── p7mextract.exe
├── invoice.pdf.p7m
├── contract.xml.p7m
└── documents.zip
```

Run the executable.

The program automatically searches the current directory for:

```text
*.p7m
*.zip
```

Extracted documents are saved in:

```text
converted/
```

The program displays the extraction and signature verification results in the console.

A log file is also generated automatically, for example:

```text
estrazione_2026_09_20_20_15_32_417.txt
```

---

### SHA-256 Verification

A `SHA256.txt` file is distributed separately with the executable.

It contains the SHA-256 checksum of the exact executable distributed with the release.

Example:

```text
8F4A2C...D91E  p7mextract_alpha_v1.0.0_467090b.exe
```

You can verify the checksum on Windows using:

```bat
certutil -hashfile p7mextract_alpha_v1.0.0_467090b.exe SHA256
```

Compare the resulting hash with the value contained in:

```text
SHA256.txt
```

The hash must match exactly.

### Important

The SHA-256 file is an **integrity verification mechanism**.

It does not provide authentication if both the executable and the checksum file have been obtained from an untrusted or compromised source.

For this reason, obtain the executable and `SHA256.txt` from the official project/release repository.

---

### Command-line options

Display the program version:

```bat
p7mextract.exe --version
```

The version information includes:

* version
* Git branch
* Git commit

---

### Output

At the end of the execution, the program reports information such as:

```text
RESULT

ZIP archives processed :
P7M files processed    :
P7M successful         :
P7M errors             :
Output directory       :
```

---

### License

See the `LICENSE` file included in the project repository.

---

### Author

**Antonello Iovino**

2026

---

# 🇮🇹 Italiano

## Descrizione

**P7MExtract** è un'applicazione per Windows progettata per estrarre i documenti originali contenuti nei file `.p7m` firmati digitalmente.

Il programma è in grado di elaborare anche i file `.p7m` contenuti all'interno di archivi ZIP.

Il tipo di documento estratto viene riconosciuto automaticamente e il file viene salvato con la relativa estensione.

Sono supportati, tra gli altri:

* PDF
* XML
* HTML
* TXT
* ZIP
* documenti OLE
* file binari

I file originali non vengono mai modificati.

---

## Verifica della firma digitale

Per ogni file P7M, P7MExtract esegue la **verifica crittografica della firma digitale CAdES / PKCS#7**.

Quando disponibili, vengono visualizzate informazioni quali:

* firmatario
* certificato di firma
* autorità certificatrice
* data della firma
* algoritmo utilizzato
* validità crittografica della firma

Lo stato indicato riguarda la **verifica crittografica della firma CMS/PKCS#7**.

La verifica effettuata dal programma non costituisce automaticamente una validazione completa della catena dei certificati, dello stato di revoca, dei servizi OCSP/CRL o della validità giuridica di una firma qualificata.

---

## Archivi ZIP

Se un archivio ZIP contiene file P7M, i documenti estratti vengono inseriti in una directory con il nome dell'archivio ZIP.

Ad esempio:

```text
pacchetto_fatture.zip
```

produce:

```text
converted/
└── pacchetto_fatture/
    ├── fattura001.pdf
    ├── fattura002.pdf
    └── fattura003.xml
```

I file P7M presenti direttamente nella directory vengono invece estratti direttamente in:

```text
converted/
```

---

## Sicurezza

P7MExtract è progettato esclusivamente per l'estrazione di documenti contenuti in container CAdES / PKCS#7.

Il programma:

* verifica crittograficamente le firme digitali CAdES / PKCS#7;
* non esegue i documenti estratti;
* non avvia i file estratti;
* non installa software aggiuntivo;
* non modifica il Registro di Windows;
* non avvia applicazioni esterne;
* non richiede una connessione Internet;
* non modifica i file P7M originali;
* salva i documenti estratti nella directory `converted`;
* non sovrascrive i file già esistenti.

I percorsi contenuti negli archivi ZIP vengono controllati per evitare che un archivio possa estrarre file al di fuori della directory prevista.

---

## Utilizzo

Inserire l'eseguibile nella directory contenente i file da elaborare.

Ad esempio:

```text
P7MExtract/
├── p7mextract.exe
├── fattura.pdf.p7m
├── contratto.xml.p7m
└── documenti.zip
```

Avviare l'eseguibile.

Il programma ricerca automaticamente nella directory corrente:

```text
*.p7m
*.zip
```

I documenti estratti vengono salvati nella directory:

```text
converted/
```

I risultati dell'estrazione e della verifica delle firme vengono visualizzati nella console.

Il programma genera inoltre automaticamente un file di log, ad esempio:

```text
estrazione_2026_09_20_20_15_32_417.txt
```

---

## Verifica SHA-256

Insieme all'eseguibile viene distribuito separatamente il file:

```text
SHA256.txt
```

Il file contiene il checksum SHA-256 dell'esatto eseguibile distribuito.

Esempio:

```text
8F4A2C...D91E  p7mextract_alpha_v1.0.0_467090b.exe
```

Su Windows è possibile verificare il checksum con:

```bat
certutil -hashfile p7mextract_alpha_v1.0.0_467090b.exe SHA256
```

Il valore ottenuto deve essere confrontato con quello contenuto in:

```text
SHA256.txt
```

I due valori devono coincidere esattamente.

### Importante

Il file SHA-256 permette di verificare **l'integrità** dell'eseguibile.

Non garantisce invece l'autenticità se sia l'eseguibile sia il file `SHA256.txt` sono stati ottenuti da una fonte non affidabile o compromessa.

È quindi consigliato scaricare entrambi dalla repository ufficiale del progetto o dalla relativa release ufficiale.

---

## Opzioni da linea di comando

Per visualizzare la versione del programma:

```bat
p7mextract.exe --version
```

Le informazioni visualizzate comprendono:

* versione
* branch Git
* commit Git

---

## Risultato dell'elaborazione

Al termine dell'elaborazione il programma visualizza, tra le altre, le seguenti informazioni:

```text
RESULT

ZIP archives processed :
P7M files processed    :
P7M successful         :
P7M errors             :
Output directory       :
```

---

## Licenza

Consultare il file `LICENSE` presente nella repository del progetto.

---

## Autore

**Antonello Iovino**

2026
