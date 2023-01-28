# Safetensor converter
## Instruction

This converter is based on [xrpgame's code](https://gist.github.com/xrpgame/8f756f99b00b02697edcd5eec5202c59).

## Converter Information
Converter is especially designed to convert .ckpt files to .safetensors on Google Colaboratory environment.
To convert, keep remind that size of RAM must be enough or size of model file is not too high, unless using Colaboratory Pro or local environment.

## Quick Guide
1. Upload .ipynb file to Google Drive.
2. Open it.
3. Run 'Prepare' cell.
4. Open 'Download' cell, and put address of model on just after '--split=8' to download it.
5. Run 'Download' cell.
6. Or you can use !cp command for copying model files from Google Drive.
7. Move all .ckpt files to '/content' folder.
8. Run 'Universal Converter' cell.
9. The script will convert all of models automatically.
10. If saved successfully, use !cp command, or download it directly. Use GitHub or Huggingface also recommeneded.

## Troubleshooting
- I failed to convert models with weird error messages.
Answer: Replace code like this.
```
#Problem
weights = torch.load(f)["state_dict"]
weights.pop("state_dict")

#Solution
weights = torch.load(f)["state_dict"]
```

- The session in Colaboratory got crashed after using all available RAM.
Answer: Don't worry. Unless you reset all runtime manually, still your work is protected.