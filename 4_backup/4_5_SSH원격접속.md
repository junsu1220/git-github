# 깃허브에 SSH 원격 접속하기

ssh는 secure shell의 줄임말로 보안이 강화된 안전한 방법으로 정보를 교환합니다.

ssh는 컴퓨터 고유의 프라이빗키와 퍼블릭키를 통해 아이디,비밀번호 없이 깃허브를 사용할 수 있습니다.

터미널창에서 `ssh-keygen`이라고 입력하면 ssh키가 저장되는 디렉토리 경로가 표시됩니다.

여기서 엔터를 누르면 비밀번호가 생성되는데 

id_rsa 파일이 프라이빗키이고 , id_rsa.pub 파일이 퍼블릭 키입니다.

다시 확인하려면 `cd ~/.ssh` , `ls -al`을 하시면 됩니다.

이제 ssh로 깃허브에 접속해보겠습니다.

`cd ~/.ssh` , `cat id_rsa.pub`로 퍼블릭 키에 담긴 내용을 확인하고

ssh-rsa부터 문자열 끝까지 선택한 후 copy합니다. 

이후 깃허브에 로그인해 settings를 들어가서 ssh and GPG keys를 누른 후

new ssh key를 누릅니다. 타이틀에 적당한 이름을 붙이고 key항목에 아까 복사한 퍼블릭 키값을 붙여넣습니다.

add ssh key를 눌러 추가하고 비밀번호를 누르면 깃허브서버에 올리는게 끝났습니다.

# SSH 주소로 원격 저장소 연결하기

레포지토리를 만들때 HTTPS가 아닌 SSH로 주소를 복사해

`cd ~` , `git init connect-ssh` , `cd connect-ssh` 로 해당 디렉토리에 들어간 후

`git remote add origin 복사한 주소 붙여넣기` 를 하면 앞으로 이 폴더는 로그인 없이

푸시나 풀을 할 수 있습니다.
