이 리포지토리는 Nvidia Jetson Orin Nano Super 8GB를 이용해서 Yolov11을 구동하는 예시입니다.

# 전체적인 프로세스 정리
1. 장치 구입 후 JetPack6.2 설치하기(jtop 등...)
2. OpenCV 4.10.0 빌드하기
3. Ultralytics 패키지 설치하기
   https://docs.ultralytics.com/guides/nvidia-jetson/ (공식 문서대로 따라하시면 됩니다) , 넘파이 관련 오류가 발생하면 버전을 낮춰 설치 (pip install numpy==1.23.5)
5. Pytorch 및 torchVision 등 설치(torch 2.5.0,torchvision 0.20)
6. 1번 파일 실행하여 CUDA 활성화 여부 확인
7. 2번 파일 실행하여 pt 파일을 engine 파일로 변경하기... DLA 활성화 되어 있으므로 다른 파일도 활용가능
8. 3번 파일 실행하여 추론 시간 확인 및 끝!

# 사용한 장치 관련
1. JetPack 6.2 버전
2. nvmeSSD SK Hynix P.31 SSD 1TB (SD카드의 경우 속도가 현저하게 느려 사용 비추천)

# 필자가 발생했던 오류 정리
1. SSD에 JetPack을 설치하기 위해서는 반드시 Nvidia의 SDK Manager가 필요합니다. 필자의 경우 우분투 22.04 버전의 운영체제를 활용하여 설치 후 SDK Manger를 구동하였습니다. https://developer.nvidia.com/sdk-manager 공식 문서의 지침을 참고하세요!
2. 윈도우 wsl로 진행한 결과 빌드 과정에 계속적으로 문제가 발생하였습니다. (가상 포트 연결이 계속 단락되는 문제 발생)

# VNC 활성화
공식 문서 참고(https://developer.nvidia.com/embedded/learn/tutorials/vnc-setup) 하여 설정 기본 비밀번호는 'thepassword'로 되어 있음, vino가 없다는 오류가 나오면 pip로 설치해주기!

# jtop
<img width="499" alt="image" src="https://github.com/user-attachments/assets/fa6c1a5c-625d-4d6e-be11-915c0fa11bba" />

# 실행화면
<img width="955" alt="image" src="https://github.com/user-attachments/assets/a1eb4221-bc64-4895-b60b-96038a575c84" />

# 코멘트
지속적으로 연구하며 발생하는 버그는 업데이트하겠습니다!
현재 Orin Nano Super 장치 구입이 원활하지 않습니다..^^ 
