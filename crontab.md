# [study_linux](https://github.com/denlyou/study_linux)
> 리눅스 명령어 및 서버 설정 공부

## cron

- 작업 스케쥴러

## crontab (Vixie Cron)

- cron을 통한 반복잡업 관리
  - `crontab -l` : 설정된 내용을 표시  
  - `crontab -e` : 작업을 설정
  - `crontab -r` : 크론 작업들을 삭제

### 설정 방법

```shell
* * * * * [실행할 명령어]
```

- 공백으로 구분됨
  - 첫번째 * : 분(Min)을 설정 0~59
  - 두번째 * : 시간(Hour)를 설정 0~23
  - 세번째 * : 일(Day)을 설정 1~31
  - 네번째 * : 월(Month)을 설정 1~12
  - 다섯째 * : 요일을 설정 0\~6(일\~토)

- 설정의 예

```
*/10 2,3,4 5-6 * * echo "hello" >> ~/cron.log 2>&1
```
> 매월 5~6일 2,3,4시에 10분마다 수행 hello 출력 수행후 cron.log 파일에 로그 남김

### cron 사용자별 권한 설정

- `/etc/cron.allow` : 허가할 사용자 목록
- `/etc/cron.deny` : 거부할 사용자 목록

> 주의 : 두파일 모두 존재시 .allow파일 규칙 사용
