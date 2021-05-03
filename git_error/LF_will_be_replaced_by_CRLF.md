# Git Error - LF will bee replaced by CRLF in *.*

git init후, 첫 add 명령어를 수행 시 다음과 같은 에러가 생길때가 있다.  

```
warning: LF will be replaced by CRLF in ad.md.  
The file will have its original line endings in your working directory
```

이는 문서의 끝을 처리하는데 있어서, OS마다 차이가 있기때문에 발생하는데, Unix에서는 Line의 끝이 __LF(Line Feed)__ 로, Window에서는 __CR(Carriage Return)__ 와 __LF(Line Feed)__, 즉 __CRLF__ 로 이루어 지기 때문이다.  

따라서 Unix 환경에서는 CRLF will be replaced.. 에러가 발생할 것이고  
Window 환경에서는 LF will be replaced.. 에러가 발생할 것이다.  

## 해결

git이 자동으로 LF를 CRLF로 바꿔주는것이 상관없다면, 아래 명령어를 통해 경고메세지를 제거해줄 수 있다.  

`git config core.autocrlf true`