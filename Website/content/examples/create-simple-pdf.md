---
title: "Create a simple PDF"
description: "Use PSWritePDF to create a small document from PowerShell."
layout: docs
---

This pattern is useful when a script needs to emit a compact PDF artifact.

It comes from the source example at `Example/Example01.HelloWorld/Example01_Simple.ps1`.

## When to use this pattern

- You need a generated PDF artifact.
- The content can be authored directly in PowerShell.
- You want to combine text and simple lists.

## Example

```powershell
Import-Module .\PSWritePDF.psd1 -Force

New-PDF {
    New-PDFText -Text 'Hello ', 'World' -Font HELVETICA, TIMES_ITALIC -FontColor GRAY, BLUE
    New-PDFText -Text 'Generated from PowerShell.' -Font HELVETICA -FontColor RED
    New-PDFList -Indent 3 {
        New-PDFListItem -Text 'First item'
        New-PDFListItem -Text 'Second item'
    }
} -FilePath "$PSScriptRoot\Example01_Simple.pdf" -Show
```

## What this demonstrates

- creating a document in a script block
- combining text and list elements
- writing the generated file to disk

## Source

- [Example01_Simple.ps1](https://github.com/EvotecIT/PSWritePDF/blob/master/Example/Example01.HelloWorld/Example01_Simple.ps1)

