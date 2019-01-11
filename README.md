# PBR's bug

cfg file containing `keywords` section will prevent pbr for generating
proper METADATA.

Failed METADATA file can be seen [here](./METADATA_faulty),
when you remove the `keywords` section, then proper METADATA is generated.
Correct METADATA file can be seen [here](./METADATA_correct).

To reproduce:

```shell

$ python setup.py bdist_wheel

# verify the metadata
$ unzip ./dist/pbr_md-0.0.0-py3-none-any.whl
$ cat ./pbr_md-0.0.0.dist-info/METADATA

# remove 'keywords' section and rerun the script
```