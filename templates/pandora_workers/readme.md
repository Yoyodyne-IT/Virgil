# Notes

Copy all files from the pandora repo:

```bash
for file in ~/gits/pandora/pandora/workers/*.sample; do cp -i ${file} $( basename ${file%%.sample} ); done
```
