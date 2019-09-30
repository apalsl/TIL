## Git Error

![ERROR_GIT_1](../img/Git_gtk.PNG)

```
ERROR_GIT_1   
gtk의 ssh-askpass를 사용하여 ssh 인증을 하도록 환경 변수 설정이 되어있는데 터미널에서 gtk 앱이 구동되지 않아서 발생함. 무슨말인지 모르겠음, git 터미널이 아니라서 그런걸로 예상?  
관리자 권한은로 /etc/profile.d/gnome-ssh-askpass.sh 를 수정

unset SSH_ASKPASS 추가하면 끝.
```
