# 미션 - 입학 연수 2기 과제

## 1. 프로젝트 개요
- 본 과제는 터미널 기초 명령어 숙달, Git/GitHub를 통한 버전 관리, 그리고 Docker를 이용한 컨테이너 환경 구축을 목표한다.

## 2. 실행 환경

- OS: macOS 15.7.4
- Shell: zsh
- Docker: 28.5.2
- Git: 2.53.0

## 3. 수행 체크리스트

- [x] 터미널 기본 조작 및 폴더 구성
- [x] 권한 변경 실습
   - 파일('test.txt'): '-rw-r--r--' -> 'chmod 600' -> '-rw-------'
   - 디렉토리('testdir'): 'dr-xr-xr-x(555) -> 'chmod700' -> 'drwx------'
- [x] Docker 설치/점검
- [x] hello-world 실행
- [x] 'docker ps -a' 명령어로 컨테이너 상태 확인
- [x] Nginx 웹 서버 컨테이너 실행 및 브라우저 접속 성공
- [x] Docker Desktop 설치 완료
- [x] Docker 데몬 동작 확인 ('docker info')
   - Server Version: 28.5.2
   - Operation System: OrbStack (macOS 기반)
   - Kernel Version: 6.17.8-orbstack
   - Architecture: x86_64
   - CPUs:6, Total Memory: 15.67GiB
- [x] 커스텀 Docker 이미지 빌드 및 실행
   - Dockerfile 작성 (Nginx 베이스 이미지 활용)
   - index.html 작성 및 한글 깨짐 방지(UTF-8) 설정
   - 'docker build -t my-real-final .' 명령어로 이미지 생성
   - 'docker run -p 9000:80' 명령어로 포트 포워딩 및 브라우저 접속 확인
      ![접속화면](./mission1/안녕하세요.png)
- [x] Docker 볼륨 영속성 검증
   - '-v "$PWD":/usr/share/nginx/html' 옵션을 사용하여 호스트와 컨테이너를 연결했습니다.
   - 소스코드 (index.html) 수정 시 빌드 없이도 실시간으로 반영되는 것을 확인했습니다.
      ![접속화면](./mission1/볼륨연결.png)
   - 컨테이너를 삭제하고 다시 생성해도 데이터가 유지되는 영속성을 확인했습니다. 
      ('docker stop $(docker ps -q))
## 4. 과제 완료 소감
- Git과 Docker의 기초적인 사용법을 익혔습니다.
- 특히 권한 설정과 볼륨 마운트 개념이 흥미로웠습니다.
