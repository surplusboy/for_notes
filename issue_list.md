# 겪은 일들을 기록해놓는 곳 #

장황한 설명보단 체크 위주의 메모공간으로서 서술 된 것들은 사전적 의미와 조금 상이할 수 있음.

### 윈도우에서 리눅스 환경 구축 ###

WSL : 윈도우내에 리눅스 파일 시스템을 가져와 쓸 수 있게 해주는 backend 시스템  
WSL2 에는 Hyper-V 기반의 가상화 기술을 적용하여 실제 리눅스 커널을 탑재하였다.  

위의 간단한 설명을 읽으면 매우 편리한 기술임은 맞으나, 실제 환경에서 겪으며 느꼈던것은 윈도우 환경에서 개발하였더라도  
실제 서비스를 위해 운용되어야 할땐 리눅스 환경을 이용하는 것이 더 좋을 수 있다는 것이다.  
WSL 을 이용하여 윈도우에서 리눅스 파일시스템을 이용할 순 있지만, 이는 아직까진 완벽하진 않은것 같다.  (가상과 실제의 차이)  
특히 도커를 통해 컨테이너를 띄우게 될 경우 실제 환경에선 턱없이 부족한 공간이 Logical Volume 으로 잡히게 된다.  
(WSL이 사용하는 공간의 확장이 가능하긴 하다. ref : https://docs.microsoft.com/ko-kr/windows/wsl/vhd-size)  
또한 컨테이너가 사용할 수 있는 공간의 확장이 필요할때도 실제 리눅스 환경에서는 더욱 간단한 방법들로 해결이 가능하다.  
(ref : https://medium.com/@catap/how-to-increase-docker-container-disk-size-over-devicemapper-1034a0b3df6e)


### 파이참 IDE 에서 출력 콘솔 바꾸기 ###  

#### 개요 ####
파이참을 통해 확인(디버깅 등)이 필요하여 Ctrl + Shift + F10 를 이용하여 py 를 실행시킬 경우  
터미널 환경에서만 출력되는 다양한 라이브러리들이 출력되지 못하는 경우가 있다.
ex) getpass 등은 정상적인 출력이 되지 않아 코드가 실행되지 않게 된다.  

#### 해결방법 ####
해결법은 파이참에서 해당 py 의 출력 콘솔을 터미널 환경으로 변경하면 된다.
kor : 실행 → 구성 편집 → 출력 콘솔에서 터미널 에뮬레이션 → Check 
eng : Run → Edit Configurations → Python and select Emulate terminal in output console → Check
