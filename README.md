<p align="center">
    <img src="https://user-images.githubusercontent.com/8983173/130322857-185831e2-f041-46eb-a17f-0a69d066c4e5.png" alt="Gotenberg Logo" width="150" height="150" />
    <h3 align="center">Gotenberg</h3>
    <p align="center">A Docker-powered stateless API for PDF files</p>
    <p align="center"><a href="https://gotenberg.dev/docs/getting-started/introduction">Documentation</a> &#183; <a href="https://gotenberg.dev/docs/getting-started/installation#live-demo-">Live Demo</a> 🔥</p>
</p>

---

Gotenberg provides a developer-friendly API to interact with powerful tools like Chromium and LibreOffice for converting 
numerous document formats (HTML, Markdown, Word, Excel, etc.) into PDF files, and more!

## Quick Start

Open a terminal and run the following command:

```
docker run --rm -p 3000:3000 gotenberg/gotenberg:7
```

Alternatively, using the historic Docker repository from our sponsor [TheCodingMachine](https://www.thecodingmachine.com):

```
docker run --rm -p 3000:3000 thecodingmachine/gotenberg:7
```

The API is now available on your host at http://localhost:3000.

Head to the [documentation](https://gotenberg.dev/docs/getting-started/introduction) to learn how to interact with it 🚀

## Windows Dockerless Setup

1. [Download](https://www.google.com/chrome/) + install Chrome
2. [Download](https://www.libreoffice.org/download/download-libreoffice/) + install LibreOffice
3. [Download](https://github.com/unoconv/unoconv/releases) unoconv release, unzip and paste unoconv file into `C:\Program Files\LibreOffice\program` or anywhere you want 
4. [Download](https://www.pdflabs.com/tools/pdftk-server/) + install PDFTK
5. [Download](https://github.com/qpdf/qpdf/releases/) + install QPDF (choose the msvc64.exe asset)
6. Update the commands in the step 7 to point to the correct paths for the installed programs
7. Run ```
    set "CHROMIUM_BIN_PATH=C:\Program Files\Google\Chrome\Application\chrome.exe"
	set "PYTHON_FOR_UNOCONV_PATH=C:\Program Files\LibreOffice\program\python.exe"
	set "UNOCONV_BIN_PATH=C:\Program Files\LibreOffice\program\unoconv"
	set "LIBREOFFICE_BIN_PATH=C:\Program Files\LibreOffice\program\soffice.exe"
	set "PDFTK_BIN_PATH=C:\Program Files (x86)\PDFtk Server\bin\pdftk"
	set "QPDF_BIN_PATH=C:\Program Files\qpdf 11.6.1\bin\qpdf"
```
8. Build the gotenberg executable for windows `make buildWindows` (can be done on any machine)
9. Run `gotenberg.exe --log-level=debug` or see the Makefile `run` command for more argument options
10. Send requests to the API, for example: `curl -X POST http://localhost:3000/forms/libreoffice/convert -F files=@"C:\Users\cloudarchiveadmin\Desktop\DocsConvert\fakeRtf.rtf" --output fakeRtf.pdf`

## Sponsors

<p align="center">
    <a href="https://thecodingmachine.com">
        <img src="https://user-images.githubusercontent.com/8983173/130324668-9d6e7b35-53a3-49c7-a574-38190d2bd6b0.png" alt="TheCodingMachine Logo" width="429" height="210" />
    </a>
</p>

## Badges

[![Docker pulls](https://img.shields.io/docker/pulls/gotenberg/gotenberg)](https://hub.docker.com/r/gotenberg/gotenberg)
[![Docker pulls](https://img.shields.io/docker/pulls/thecodingmachine/gotenberg)](https://hub.docker.com/r/thecodingmachine/gotenberg)
[![Continuous Integration](https://github.com/gotenberg/gotenberg/actions/workflows/continuous_integration.yml/badge.svg)](https://github.com/gotenberg/gotenberg/actions/workflows/continuous_integration.yml)
[![Go Reference](https://pkg.go.dev/badge/github.com/gotenberg/gotenberg.svg)](https://pkg.go.dev/github.com/gotenberg/gotenberg/v7)
[![Codecov](https://codecov.io/gh/gotenberg/gotenberg/branch/main/graph/badge.svg)](https://codecov.io/gh/gotenberg/gotenberg)
