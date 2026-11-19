# Tandem

Tandem is a local-model workbench for Apple Silicon Macs. It runs GGUF models with llama.cpp and MLX models with mlx-lm, side by side.

This repository only hosts downloads. The source code is private.

## Requirements

- A Mac with Apple Silicon (M1 or later). Intel Macs are not supported.
- macOS 14 Sonoma or later.

## Install

1. Download `Tandem-<version>-arm64.zip` from the [latest release](../../releases/latest).
2. Double-click the zip to extract `Tandem.app`, then move it to Applications.
3. Open it for the first time. This build isn't signed with an Apple Developer ID, so macOS will block it. Use one of these:
   - In Finder, right-click Tandem.app, choose **Open**, then choose **Open** again. On macOS 15 and later, if no Open button appears, go to **System Settings → Privacy & Security** and click **Open Anyway** under the Tandem message.
   - Or run this in Terminal: `xattr -dr com.apple.quarantine /Applications/Tandem.app`

## First run

1. Open the **Engines** tab and install llama.cpp (for GGUF models) and MLX (for MLX models).
2. Press **Command–Shift–F** to open Discover. Search Hugging Face, then download a model.
3. The model appears in **Library** when the download finishes.

To download gated models, add a Hugging Face token in Discover's settings. Tandem stores it in the macOS Keychain.

Tandem keeps its data in `~/Library/Application Support/Tandem`.

## Check the download

Each release includes `SHA256SUMS.txt`. To confirm the zip wasn't altered, run:

```
shasum -a 256 Tandem-*-arm64.zip
```

The output should match the value in that file.

## Preview status

This is an early preview. It has only been tested on the developer's own Mac, so the first-run engine setup may hit problems on other machines. Please report problems in [Issues](../../issues).
