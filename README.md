# UnixProgramming

유닉스 프로그래밍 과제 (2020.11.29)  

## 1. 요구사항 정의  
 1) chdir()  
 : cd 명령이 제대로 먹히지 않는 버그를 수정한다(제공된 코드를 실행해 cd 명령어를 입력하면 ‘main():  no such file or directory’가 출력됨). pwd 명령을 통해 현제 디렉토리를 확인한 뒤 mkdir dirA로 새 디렉토리 dirA를 생성, cd dirA로 디렉토리를 이동하고 다시 pwd 명령으로 현재 디렉토리가 바뀌었음을 확인한다.  
 2) exit()  
 : exit()이나 return을 이용해 exit 명령을 구현한다. exit 입력 시 myshell 프로세스가 종료되는 것을 확인한다.  
 3) Background  
 : 명령 뒤에 &가 붙으면 Background에서 실행되도록 구현한다. 고아 프로세스의 생성 원리를 이용한다. sleep 10 입력 시(Foreground) 쉘프롬프트가 바로 출력되지 않고 10초 뒤에 출력되는 것과 sleep 10 & 입력 시(Background) 쉘프롬프트가 바로 출력됨을 확인한다. 이후 ps 명령을 통해 좀비 프로세스가 생겼음을 확인하고, 생기는 이유와 다음 테스트 사항에 대해 문제점과 해결 방안에 대하여 고찰한다.  
 4) SIGCHLD  
 : 자식 프로세스 wait() 시 프로세스가 온전하게 수행되도록 구현한다. "sleep 50"이 "sleep 20 &"과 "sleep 30 &"에 방해 받지 않고 수행됨과 ps를 통해 좀비 프로세스가 없음을 확인한다.  
 5) SIGINT, SIGQUIT  
 : ^C(SIGINT), ^\(SIGQUIT) 사용 시 쉘프롬프트가 종료되지 않아야 한다. Foreground 프로세스 실행 시에는 제어키(^C, ^\)을 받았을 때 프로세스가 끝나야 한다. (sleep후 제어키를 입력하면 프로세스 sleep이 종료됨을 확인한다.)  
 6) Redirection  
 : Redirection 기능을 구현한다. cat > test.txt, cat < test.txt , cat < test.txt > test1.txt 명령을 통해 redirection이 제대로 동작하는지 확인한다.  
 7) Pipe  
 : 파이프 명령 “|”을 통해 별개의 프로세스에서 동작 및 데이터 전달이 제대로 이루어지도록 구현한다. 리다이렉션과 백그라운드 모두 정상적으로 동작하도록 한다.  
