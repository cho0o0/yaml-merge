# `yaml-merge`

A super simple tool for merging YAML files into one file.
(Forked from [alexlafroscia/yaml-merge](https://github.com/alexlafroscia/yaml-merge) mainly for self usage. The license stays as MIT)

## Installation

### For the command line

```bash
npm install -g @cho0o0/yaml-merge
```

### For use through Node

```bash
npm install --save @cho0o0/yaml-merge
```

## Usage

`yaml-merge` takes a series of `yaml` files and merges them from left to right.  This means that the first file will be overwritten by properties of the second, which is overwritten by properties of the third, etc.

### Command Line

When using this tool from the command line, the output file will simply be written to the first arg.

```bash
yaml-merge output.yml test/fixtures/basic/a.yml test/fixtures/basic/b.yml
```

The provided file names will be resolved relative to the current directory. So, you an provide a relative path to the files, or an absolute path -- either method works just fine.

### As a Node package

`yaml-merge` also provides a `node` package that can be consumed to get the output file programmatically.

```javascript
const resolve = require('path').resolve;
const merge = require('@alexlafroscia/yaml-merge');

const output = merge(resolve('relative/path/to/file.yml'), '/Users/you/some/other/file.yml');
console.log(output); // Prints out the resulting YAML as a string
```
