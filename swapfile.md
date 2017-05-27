> # study_linux
> 리눅스 명령어 및 서버 설정 공부

## swapfile 설정

- 확인하기 : `top` 또는 `free` 명령어로 확인하기

```shell
free -h
```

- `df` 명령 등으로 주저장장치와는 다른 장치를 설정해 주는 것도 좋습니다

- `dd` 명령으로 스왑으로 사용할 파일을 생성합니다

```shell
dd if=/dev/zero of=/var/swapfile bs=1024 count=1024KB
```


- 스왑 파일 등록 및 사용하도록 설정합니다.

```shell
mkswap -v1 /var/swapfile
chmod 600 /var/swapfile
swapon /var/swapfile
```

- 정상정으로 동작하는지 확인 합니다

```shell
free -h
```

- 재부팅시 자동으로 동작하도록 설정하기 : 편집기로 /ect/fstab 파일을 열고 다음을 추가합니다.

```shell
/var/swapfile     swap     swap    defaults    1 1
```
** 주의 : 이 파일을 잘못 설정하면 부팅시 오류가 생길수 있으니 주의할 것 **

## 스왑 파일 삭제하기

- 스왑 파일 해제하기

```shell
swapoff /var/swapfile
```

- 스왑 파일 삭제하기

```
rm -f /var/swapfile
```
