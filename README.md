# P7MExtract

**CAdES / PKCS#7 P7M document extractor**

## ⬇️ Download

* [**Download P7MExtract v1.0.1**](https://github.com/antoiovi/P7Mextract_distro/releases/download/v1.01/p7mextractv1.0.1.exe)
* [**Download SHA256.txt**](https://github.com/antoiovi/P7Mextract_distro/releases/download/v1.01/SHA256.txt)


The release contains:

* `p7mextractv1.0.1.exe` — the P7MExtract application
* `SHA256.txt` — SHA-256 checksum for the executable

---

# 🇬🇧 Quick Guide

## 1. Download

Open the official release:

[**P7MExtract v1.0.1**](https://github.com/antoiovi/P7Mextract_distro/releases/tag/v1.0.1)

Download:

```text
p7mextractv1.0.1.exe
```

The `SHA256.txt` file can be used to verify the integrity of the downloaded executable.

## 2. Put the executable in the folder containing your documents

For example:

```text
MyDocuments/
├── p7mextractv1.0.1.exe
├── invoice.pdf.p7m
├── contract.pdf.p7m
└── documents.zip
```

## 3. Run P7MExtract

Double-click:

```text
p7mextractv1.0.1.exe
```

P7MExtract automatically searches the current directory for:

```text
*.p7m
*.zip
```

## 4. Extracted documents

The extracted documents are saved automatically in:

```text
converted/
```

For example:

```text
MyDocuments/
├── p7mextractv1.0.1.exe
├── invoice.pdf.p7m
├── documents.zip
└── converted/
    ├── invoice.pdf
    └── documents/
        ├── contract.pdf
        └── report.xml
```

Existing files are not overwritten.

## 5. Digital signature verification

For every P7M file, P7MExtract performs a cryptographic verification of the CAdES / PKCS#7 digital signature.

The program displays information such as:

* Signer
* Certificate
* Certification Authority
* Signing Date
* Signature Algorithm
* Cryptographic Signature Validity

The original P7M file is never modified.

---

## 6. ZIP files

P7MExtract can also process P7M files contained inside ZIP archives.

For example:

```text
documents.zip
├── invoice001.pdf.p7m
├── invoice002.pdf.p7m
└── report.xml.p7m
```

will produce:

```text
converted/
└── documents/
    ├── invoice001.pdf
    ├── invoice002.pdf
    └── report.xml
```

---

## 7. Windows SmartScreen

When running P7MExtract for the first time, Windows may display a **Microsoft Defender SmartScreen** warning because the application is currently not signed with a Windows Authenticode certificate.

If you downloaded the executable from the official GitHub release and verified its SHA-256 checksum, Windows may be showing the warning because the application is not yet recognized by SmartScreen.

Click:

**More info → Run anyway**

For more information, see the **Windows SmartScreen** section below.

---

## 8. SHA-256 verification

The release includes:

```text
SHA256.txt
```

To verify the downloaded executable on Windows, open a Command Prompt in the directory containing the EXE and run:

```bat
certutil -hashfile p7mextractv1.0.1.exe SHA256
```

Compare the resulting value with the value contained in `SHA256.txt`.

The values must match exactly.

---

## Security

P7MExtract does not execute extracted documents, does not modify the original P7M files, does not modify the Windows Registry, and does not require an Internet connection.

The program writes extracted files and generated logs only inside the `converted` directory.

For complete information about security and digital signature verification, see the sections above.

---

## Third-Party Software

P7MExtract uses OpenSSL and libarchive.

See [THIRD-PARTY-NOTICES.txt](THIRD-PARTY-NOTICES.txt) for details.

---

# 🇮🇹 Mini guida

## 1. Scaricare il programma

Aprire la release ufficiale:

* [**Download P7MExtract v1.0.1**](https://github.com/antoiovi/P7Mextract_distro/releases/tag/v1.0.1)

Scaricare:

```text
p7mextractv1.0.1.exe
```

Il file `SHA256.txt` può essere utilizzato per verificare l'integrità dell'eseguibile.

## 2. Mettere l'eseguibile nella directory dei documenti

Ad esempio:

```text
Documenti/
├── p7mextractv1.0.1.exe
├── fattura.pdf.p7m
├── contratto.pdf.p7m
└── documenti.zip
```

## 3. Avviare P7MExtract

Fare doppio clic su:

```text
p7mextractv1.0.1.exe
```

P7MExtract ricerca automaticamente nella directory corrente:

```text
*.p7m
*.zip
```

## 4. Documenti estratti

I documenti vengono salvati automaticamente nella directory:

```text
converted/
```

Ad esempio:

```text
Documenti/
├── p7mextractv1.0.1.exe
├── fattura.pdf.p7m
├── documenti.zip
└── converted/
    ├── fattura.pdf
    └── documenti/
        ├── contratto.pdf
        └── rapporto.xml
```

I file esistenti non vengono sovrascritti.

## 5. Verifica della firma digitale

Per ogni file P7M, P7MExtract esegue la verifica crittografica della firma digitale CAdES / PKCS#7.

Vengono visualizzate, quando disponibili:

* informazioni sul firmatario;
* certificato;
* autorità certificatrice;
* data della firma;
* algoritmo della firma;
* validità crittografica della firma.

Il file P7M originale non viene modificato.

---

## 6. File ZIP

P7MExtract può elaborare anche i file P7M contenuti all'interno di archivi ZIP.

Ad esempio:

```text
documenti.zip
├── fattura001.pdf.p7m
├── fattura002.pdf.p7m
└── rapporto.xml.p7m
```

produce:

```text
converted/
└── documenti/
    ├── fattura001.pdf
    ├── fattura002.pdf
    └── rapporto.xml
```

---

## 7. Windows SmartScreen

Al primo avvio, Windows potrebbe visualizzare un avviso di **Microsoft Defender SmartScreen**, poiché l'applicazione attualmente non dispone di una firma digitale Windows Authenticode.

Se l'eseguibile è stato scaricato dalla release ufficiale GitHub e il suo checksum SHA-256 è stato verificato, l'avviso può essere dovuto semplicemente al fatto che Windows non riconosce ancora l'applicazione.

Cliccare:

**Ulteriori informazioni → Esegui comunque**

Per maggiori informazioni, consultare la sezione **Windows SmartScreen**.

---

## 8. Verifica SHA-256

La release contiene il file:

* [**Download SHA256.txt**](https://github.com/antoiovi/P7Mextract_distro/releases/download/v1.0.1/SHA256.txt)

```text
SHA256.txt
```

Per verificare l'eseguibile in Windows, aprire il Prompt dei comandi nella directory che contiene l'EXE ed eseguire:

```bat
certutil -hashfile p7mextractv1.0.1.exe SHA256
```

Confrontare il valore ottenuto con quello contenuto in `SHA256.txt`.

I due valori devono coincidere esattamente.

---

## Sicurezza

P7MExtract non esegue i documenti estratti, non modifica i file P7M originali, non modifica il Registro di sistema di Windows e non richiede una connessione a Internet.

Il programma scrive i file estratti e i log generati esclusivamente all'interno della cartella `converted`.

Per informazioni complete sulla sicurezza e sulla verifica delle firme digitali, consulta le sezioni precedenti.

---

## Third-Party Software

P7MExtract uses OpenSSL and libarchive.

See [THIRD-PARTY-NOTICES.txt](THIRD-PARTY-NOTICES.txt) for details.
