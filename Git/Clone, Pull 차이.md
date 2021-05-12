# Clone과 Pull의 차이

git clone, git pull 둘 다 remote Repo -> local Repo로 코드를 가져오는것은 동일하다.  

하지만 git clone은 __local에 아무것도 없는상태__ 에서 원격저장소의 데이터를 가져오는 것을 의미하고, git pull은 __local에 데이터가 존재하고__ 원격저장소의 수정상태를 반영하기 위해 하는것이다. 

## 가장 큰 차이점 : remote설정을 자동으로 하나 안하나

아래의 두 명령어는 같은 명령을 의미한다.

```
1. git clone {URL}
2. git init + git remote add origin {URL} + git pull origin master
```

즉 git clone은 remote 설정을 자동으로 해주는 __초기 다운로드__ 에 사용되고  
git pull은 remote 설정이 이미 되어있을 때 __업데이트 사항등을 다운로드__ 할때 사용된다.