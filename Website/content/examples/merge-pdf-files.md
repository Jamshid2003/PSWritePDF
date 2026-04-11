---
title: "Merge PDF files"
description: "Use PSWritePDF to merge existing PDF files from a PowerShell workflow."
layout: docs
---

This pattern is useful when a process produces separate PDF artifacts that need to be combined.

It comes from the source example at `Example/Example03.Merging/Example03.ps1`.

## When to use this pattern

- You receive multiple PDFs from upstream steps.
- The output should be one merged document.
- You want the merge step to be scriptable.

## Example

```powershell
Import-Module .\PSWritePDF.psd1 -Force

$inputFiles = @(
    "$PSScriptRoot\Input\OutputDocument0.pdf"
    "$PSScriptRoot\Input\OutputDocument1.pdf"
)
$outputFile = "$PSScriptRoot\Output\OutputDocument.pdf"

Merge-PDF -InputFile $inputFiles -OutputFile $outputFile -Verbose
```

## What this demonstrates

- using an array of input files
- writing a deterministic output path
- adding PDF merge to a larger automation

## Source

- [Example03.ps1](https://github.com/EvotecIT/PSWritePDF/blob/master/Example/Example03.Merging/Example03.ps1)

