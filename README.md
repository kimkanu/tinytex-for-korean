# TinyTeX for Korean

## TinyTeX이란?

**TinyTeX**은 [谢益辉](https://yihui.name/)에 의해 개발된 TeX Live 기반의 LaTeX 배포판으로, 기존의 TeX Live (최소 용량이 Unix 기반에서 150 MB, Windows에서 220MB)에 비해 용량이 줄었다는 장점이 있습니다. 또한, [R 패키지](https://yihui.name/tinytex/r/)로서 쓰임을 목적으로 하였기 때문에 R과 같이 쓰기에도 편리합니다.


## 설치하기

### Unix-based (Linux, macOS)

```bash
wget -qO- "https://yihui.name/gh/tinytex/tools/install-unx.sh" | sh   # Linux
curl -sL "https://yihui.name/gh/tinytex/tools/install-unx.sh" | sh    # macOS
```


### Windows (PowerShell 3.0+)

Windows의 경우, PowerShell 3.0 이상이 설치되어 있어야 합니다. (Windows 10에는 자동적으로 설치되어 있습니다.)

[**링크**](https://yihui.name/gh/tinytex/tools/install-windows.bat)를 오른쪽 클릭한 후 다른 이름으로 저장을 하고 실행해 주세요.



## 필요한 패키지 설치하기

```bash
# install gpg
tlmgr --repository http://www.preining.info/tlgpg/ install tlgpg

# some packages
tlmgr install adjustbox amscls amsfonts amsmath babel beamer biblatex bibtex booktabs caption changepage cjk-ko cm collectbox dantelogo dehyph dtk dvipdfmx dvips ec enumitem environ etex etoolbox euenc expex fancyhdr fancyvrb float fontspec forloop framed fvextra geometry glyphlist graphics graphics-cfg graphics-def gsftopk helvetic hyperref hyphen-base ifluatex ifmtarg ifplatform iftex ifxetex inconsolata jknapltx knuth-lib kotex-plain kotex-utf kpathsea l3kernel l3packages latex latex-bin latex-fonts latexconfig latexmk lineno listings lm logreq lua-visual-debug luainputenc lualibs luaotfload luatex luatexko makeindex mathspec mathtools metafont mfware ms nanumtype1 natbib oberdiek pdftex pgf pgfplots plain relsize rsfs scheme-infraonly setspace tcolorbox tetex tex tex-ini-files texlive.infra tikz-cd times tipa titlesec titling tools translator trimspaces ulem unicode-data upquote url wrapfig xcolor xetex xetexconfig xifthen xkeyval xstring xunicode zapfding

tlmgr update --all
```

이후 필요한 패키지가 설치되지 않아

```text
! LaTeX Error: File `(sty-name).sty' not found.
```

에러가 발생하면, 다음 명령어를 통해 패키지를 설치해 주세요. (아래의 (sty-name)을 위에 나온 .sty 파일의 이름으로 바꿔주세요.)

```bash
# 패키지 검색
tlmgr search --global --file "/(sty-name).sty"

# 아래와 같은 결과가 나오면, (package-name)에 해당하는 부분을 복사해 주세요.
# (package-name):
#         texmf-dist/.../(sty-name).sty
# ...

# 패키지 설치
tlmgr install (package-name)
```


## 패키지 업데이트

```
tlmgr update --self --all
tlmgr path add
fmtutil-sys --all
```
