This is the sample document repo for reference. A document repo usually includes the following directories and files:

- _static: dicrectory which includes static files for source files
- source_common: dicrectory which includes common source files that both English version and Chinese version use
- source_en: dicrectory which includes source files for English version
- source_zh: dicrectory which includes source files for Chinese version
- Makefile: 
- README.md: instructions for how to install and build sphinx document repos

Besides, the first page should be unified in the same format. Please refer to the sample rst file `index.rst`.

## Prerequisites

python3.8 is prefered

```shell
sudo apt install texlive-xetex texlive-latex-recommended
pip install sphinx sphinx-autobuild sphinx_rtd_theme rst2pdf
# install to support chinese charactor search
pip install jieba3k
```

## Get Fandol font for linux system

* [Fandol](https://ctan.org/pkg/fandol) - Four basic fonts for Chinese typesetting

Download the fandol package from the aboved website(wget http://mirrors.ctan.org/fonts/fandol.zip) and unzip it.

Copy the fold named fandol to /usr/share/fonts or ${HOME}/.fonts.

If fandol exists in /usr/share/fonts, we can ignore this step.

## support zh_CN search in html

1. 安装 结巴中文分词：

   ```bash
   # install to support chinese charactor search
   pip install jieba3k
   ```

2. 在 sphinx 工程的 `conf.py` 中写上 `language = 'zh'` ，然后就可以 `make html` 了。

## Compilation

```shell
## build html
make html # build document to static html files
python3 -m http.server --directory build/html
# open http://localhost:8000 in browser
 
## make  pdf 

# for English doc
make pdf LANG=en

# for Chinese doc
make pdf LANG=zh

```

## Testing

TODO

## Deployment

TODO

## Built With

* [Sphinx](http://www.sphinx-doc.org) - Document auto generate tool  
* [Latex](https://www.latex-project.org/) - High-quality typesetting system 

## License

This project is licensed under the MIT License - see the LICENSE file for details

## Acknowledgments
