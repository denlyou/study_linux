# study_linux
리눅스 명령어 및 서버 설정 공부

## 내용

- [swapfile설정 (환경 ubuntu14)](./swapfile.md)
- [crontab사용 방법](./crontab.md)

### update 예정사항

##### 실행하는 명령어의 위치를 찾아주는 명령어 (which, where)
  - a 옵션 : 검색가능한 모든 위치에 해당 명령어를 검색

```bash
$ which find
$ which -a find
$ whereis find
```

##### 심볼릭 링크의 위치를 확인 하는 명령어 (readlink)
  - (기본적으로 ll로도 확인 가능하다)
  - a 옵션 : 원래 파일 위치

```bash
  $ readlink -a find
```

##### 운영체제 정보 캐내기(?!)
- 운영체제 확인 및 비트 확인

```bash
$ grep . /etc/*-release
$ getconf LONG_BIT
```
> - http://zetawiki.com/wiki/%EB%A6%AC%EB%88%85%EC%8A%A4_%EC%A2%85%EB%A5%98_%ED%99%95%EC%9D%B8,_%EB%A6%AC%EB%88%85%EC%8A%A4_%EB%B2%84%EC%A0%84_%ED%99%95%EC%9D%B8
> - http://zetawiki.com/wiki/%EB%A6%AC%EB%88%85%EC%8A%A4_32%EB%B9%84%ED%8A%B8_64%EB%B9%84%ED%8A%B8_%ED%99%95%EC%9D%B8
