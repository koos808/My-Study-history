필기 시작 이전 11월 관심사
---
* Xing API를 이용해 여러 데이터들을 DB에 쌓기.
* HTS 사용법 숙지
* 여러 주식 관련 용어 숙지
* 주식 보조지표 이해
* 알고리즘 트레이딩 시스템에 관해 공부

2018.11.26
---
* 강화학습 시작
    * 주식 트레이딩 시스템에 강화학습을 도입하면 더욱 좋은 성능을 낼 것 같아서 강화학습 공부를 시작하게 됨.
    * 딥러닝/강화학습 주식투자와 알고리즘 트레이딩 책 두권을 빌려 읽기 시작함. 
    * 또한 여러 Github들을 방문해 코드를 읽어봄.

2018.11.29
-----
* GCP(Google Cloud Platform) 세팅
    * 강화학습을 돌리려는데 더욱 좋은 성능의 컴퓨터나 서버가 필요해서 GCP 세팅을 시작하게 됨.
    * 결제 카드 등록 오류가 발생함. 미해결상태로 둠.

2018.11.30
---
* 데스크톱 원격 부팅 제어 및 원격 제어
    * 컴퓨터 부팅 시 TeamViewer 자동으로 켜지지만, 컴퓨터를 수동으로 켜야한다는 불편함이 있었음.
    * 외부에서 노트북말고 데스크톱을 사용하고 싶어서 찾아보게 됨.    
    * Wake-on-LAN 설정을 통해 컴퓨터를 핸드폰으로 부팅할 수 있다는 사실을 알게 됨.

2018.12.01
---
* SPSS 시계열 분석 발표 PPT 제작
    * ARIMA & MA & 분해법(가법, 승법) & 지수 평활법 등 다양한 시계열 분석 활용.
    * 1. 시계열 분석에 앞서 데이터의 정상성(Stationary) 확인.
        + 비정상적 평균 확인하는 방법 : 그래프 그려서 추세확인, ACF & PACF, Dickey-Fuller 단위근 검정.
        + Dickey-Fuller 단위근 검정(unit root test)은 ARIMA 모형의 적분 차수를 판단하기 위한 검정 방법임.
        + 위의 방법을 실시한 결과, 데이터가 비정상성을 따른다면, 차분을 통해 정상 시계열 데이터로 변환 후 시계열 분석을 실시한다.
        + ACF/PACF를 통해 ARIMA 모형의 파라미터(p,q)를 찾는다. ACF의 신뢰구간 벗어난 막대 개수가 p이고 PACF의 신뢰구간을 벗어난 막대 개수가 q임. 대체로 좀더 여유롭게 +1개씩 지정함. 
        + ARIMA 모형을 만듦. - 모형 진단 : 잔차 ACF/PACF, Ljung-Box의 유의확률로 검정.
        + ARIMA 모형을 통해 미래 예측. 

2018.12.02
---
* 강화학습 모델링

2018.12.03~12.04
---
* 시계열 분석(예측방법론) 발표 준비

2018.12.06
---
* GCP Setting
    * 결제 카드 등록 오류가 발생 미해결상태 해결했음.
    * 내 카드는 VISA, Master 기능을 추가 안한 신용카드였음.
    * VISA 카드로 등록하니 오류 해결됨. 
    * 18년 12월 6일 12개월짜리 계정 생성함.

2018.12.07
---
* GCP Setting
    * GPU 할당량 늘려달라는 요청을 보냈는데 안된다고 답변이 옴...
    * 카드가 내 소유가 아니라서 그런 것 같다. 일단 또 보류.
* 강화학습 모델링
    * Environment,Agent 클래스 정의


2018.12.08
---
* 강화학습 모델링
    * Agent 클래스, Policy_network 모듈 정의

2018.12.09
---
* 강화학습 모델링
    * Visualizer, Policy_learner 클래스 정의

2018.12.10
---
* 강화학습 모델링
    * main, main_notraining, data_manager 정의 

2018.12.11
* 데스크톱 `WOL(Wake On Lan)` 설정
    1. 바이어스 설정
        + 애즈락 메인보드를 사용하고 있으므로 애즈락 UEFI 설정해줌.
        + Adcanced -> ACPI Configuration -> PCIE Devices Power On -> Enabled 로 변경.
    2. 장치관리자 설정
        + 네트워크 어댑터 - 속성 - 전원 관리 -  전원을절약하기 위해 컴퓨터가 이 장치를 끌 수 있음.[체크 해제]
        + 고급 - 매직 패킷, 패턴 패킷, 웨이크 온 랜, wake up 종료 사용으로 변경
    3. 공유기 설정 [IPTIME]
        + 192.168.0.1 로 공유기 설정 접속
        + 관리도구 - 고급설정 - 보안기능 - 공유기 접속 관리
          + 공유기 외부 접속 허용 : 원격 관리 포트 사용 체크 - 포트에 임의의 숫자 입력(무작위 1025)
          + DDNS 설정 : 특수기능 - DDNS 설정 - iptime DDNS 선택 - 호스트 이름에는 임의의 호스트 이름을 만들고, 사용자 ID에는 이메일 아이디를, 사용자 암호에는 접속용 암호를 설정한다. 마지막으로 추가 클릭
            + 클라이언트 차단 오류 : 펌웨어 업그레이드하면 오류 해결됨.
          + WOL 기능 설정 : DDNS 설정 바로 밑에 "WOL 기능" 항목에서 현재 접속된 PC 의 주소로 설정 체크하기
    4. 전원 설정
        + 전원 및 설정 - 추가 전원 설정 - 전원 단추 동작 설정 - 현재 사용할 수 없는 설정 변경 클릭 - 빠른 시작 켜기(권장) 체크 해제
    
    5. 원격으로 PC 이용하는 방법
        + 1. "IPTime Wol" 어플리케이션 이용
        + 2. 호스트이름 크롬창에 쳐서 들어가서 켜기
        + 3. TeamViear 프로그램을 사용하여 PC 원격 사용
    
    *`설정 완료` : 원격을 데스크톱 온오프 가능해짐 !!*

2018.12.12
---
* Desktop GPU(Tensorflow-GPU) 사용하기 위해 세팅
    * 새로운 가상환경 생성
        * python 3.7버전으로 만드니 tensorflow가 안깔렸음. python 3.6 버전으로 낮춰서 가상환경 설치함.
        * Anaconda Prompt에서 conda create를 사용하여 했는데 계속 python 3.7 버전으로 깔려서 python 3.6버전을 구글에서 다운받아 설치함.
        * 최종으로 python 3.6 버전을 사용함.
    * cuda 설치
        * 구글에 cuda toolkit 검색 - Download Now - Legacy Releases - cuda toolkit 10.0 설치
    * cuDNN 라이브러리 설치
        * 구글에 cudnn 검색 - NAVIDA Developer 회원가입 - cuDNN Download - Download cuDNN v7.4.1[Nov 8, 2018] for CUDA 10.0 version 설치 [windows]  
        * 다운 받은 zip 파일 압축 풀면 cuda 파일이 존재한다. 그 안의 'bin', 'include', 'lib' 세 폴더를 CUDA 폴더에 덮어쓰면 됨.
    * `pip` -> tensorflow-gpu, keras, matplotlib, pandas, numpy
    * 멀티커널은 안사용하는게 나음. -> no install -> `conda install nb_conda` XXX
    * 각종 오류 발생
        * `Your CPU supports instructions that this TensorFlow binary was not compiled to use: AVX2` 에러 발생.
        *  `Microsoft Visual C++ 2015 Redistributable Update 3 x64` 설치
        * `Microsoft Build Tools 2015 Update 3` 설치
        * `Microsoft Visual C++ 2015 Redistributable` 또는 `Visual Studio 2015 Community` 설치
        * 잡다한 오류가 고쳐지지 않아서 cuda 9.0 version으로 설치함.
        * http://kjun.kr/770 : 버전설명 잘되어 있음
    * 최종
        * python 3.66 , cuda_9.0.176.1 , cudnn 9.0-v7.3.1.20
        * `pip install --ignore-installed --upgrade tensorflow-gpu==1.5` 1.5버전으로 안깔면 지정된 모듈을 찾을 수 없습니다라는 오류가 발생.
        * 버전 다운그레이드해서 tensor_GPU 가상환경에 최종적으로 만듬.  
    * 텐서플로의 GPU 사용 최종 확인
        ```
        import tensorflow as tf
        hello = tf.constant('Hello, Tensorflow!')
        sess = tf.Session()
        print(sess.run(hello))
        ```
    * 마지막으로 PATH 저장해줌.

2018.12.13
----
* 자동으로 시계열 변수 만드는 R 함수 최종 작성
* 위의 함수로 이용한 데이터 강화학습 모델에 적용
    * pd.read_csv UTF-8 오류 해결 -> 옵션으로 `encoding='CP949'` 입력

2018.12.14~2018.12.21
----
* 학교 시험 공부 & 컨퍼런스[주제 : 강화학습을 이용한 주식 트레이딩 알고리즘] ppt 제작

2018.12.22
----
* 강화학습 모델링 테스트[다양한 주가 종목을 이용]
