# Awesome CV로 생성한 PDF 파일을 Github Page로 배포

정확한 사용 방법은 [원본 레포지토리](https://github.com/posquit0/Awesome-CV) 참고

## LaTex 패키지 설치

macOS 전용 Latex 패키지인 [MacTex](https://www.tug.org/mactex/mactex-download.html) 설치

## 환경 변수 설정

`xelatex` 명령어를 사용하기 위해 환경 변수 설정

```bash
# 세션마다 환경 변수를 설정하지 않으려면 ~/.zshrc 파일에 추가 필요
$ export PATH="/Library/TeX/texbin:$PATH"
```

## LaTex 파일 내용을 수정한 뒤 PDF 파일 생성

```bash
$ xelatex {your-cv}.tex
```

## index.html 파일에서 원하는 PDF 파일을 참조하도록 경로 수정

```html
<a id="download-link" href="resume.pdf" download="resume.pdf">
  <span class="download-text">Download PDF</span>
</a>
```

```javascript
const pdf = await pdfjsLib.getDocument("resume.pdf").promise;
```

## Github Page로 배포

[Github 문서](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site) 참고해서 배포
