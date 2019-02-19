## TinyTeX for Korean

```bash
tlmgr --repository http://www.preining.info/tlgpg/ install tlgpg
# mandatory packages
tlmgr install cjk-ko cjk nanumtype1 xecjk luatexko lua-visual-debug cfr-lm nfssext-cfr unfonts-core unfonts-extra xetexko luatexko
# optional but important packages
tlmgr install setspace hyperref cleveref pgf preview xcolor enumitem listings tcolorbox environ trimspaces
tlmgr update --all
```
