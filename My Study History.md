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
        + MSI 메인보드 -> SETTING - Advanced - Wake Up Event Setup - 두번째나 세번째 줄에  Resume By PCI-E Device이랑 온보드 옵션을 
        + DEnabled 로 바꾸고  저장하고 재부팅 (https://m.blog.naver.com/hansimee79/220783602034)
    2. 장치관리자 설정
        + 네트워크 어댑터 - 속성 - 전원 관리 -  전원을절약하기 위해 컴퓨터가 이 장치를 끌 수 있음.[체크 해제]
        + 고급 - 매직 패킷, 패턴 패킷, 웨이크 온 랜, wake up 종료 사용으로 변경
    3. 공유기 설정 [IPTIME]
        + 192.168.0.1 로 공유기 설정 접속(접속 안되면 cmd-ipconfig-기본 게이트웨이 ip로 접속)
        + 관리도구 - 고급설정 - 보안기능 - 공유기 접속 관리
          + 공유기 외부 접속 허용 : 원격 관리 포트 사용 체크 - 포트에 임의의 숫자 입력(무작위 3333)
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

2018.12.22~2018.12.28
----
* 강화학습 모델링 테스트[다양한 주가 종목을 이용]

-연말 휴가-
----

2019.01.03
----
* 강화학습 모델링 재시작
    * 파라메터 조정 후 백테스트의 수익률 확인
    * 백테스트 PV시작가격 1000만원으로 시작

2019.01.04~ 01.05
---
* 강화학습 프로젝트
    * 시계열 변수 생성하는 코드 패키지로 메이킹.
    * Clan & github 패키지 연동

2019.01.09~ 01.11
---
* 강화학습 프로젝트
    * 여러 모델 세트별 수익률 체크.
        * 1. 기존 데이터 사용[파라메터 고정]
        * 2. 지표를 종가로 나누어 비율로 사용한 데이터 사용[파라메터 고정]
        
2019.01.14
----
* 강화학습 프로젝트
    * 가격 보조 지표 변수 재설정
    * 주식 종목별 알고리즘 생성

2019.01.15
---
* 강화학습 회의 - 건대

2019.01.16 ~ 18
---
* 컨퍼런스 발표 준비 & PPT 제작

2019.01.19 
---
* 보아즈 9회 컨퍼런스
    * 강화학습을 이용한 주식 트레이딩 알고리즘 발표
    * 발표 영상 : 유튜브 
        * https://www.youtube.com/watch?v=5x6nbN-6tFU&list=PLThNmt_l7b6D3pVHtXXm69wEyFjRavSZB&index=4
    * 컨퍼런스 주제 및 결과 정리(강화학습 이용한 모의투자 실전 트레이딩)
        * 최종 수익 : 10일 트레이딩 결과 수익률 4.99%
        * ``` 총 매입 : 29,899,065
            매입 종목 개수 : 메리츠화재, 기아차 등 10개 종목
            평가금액 : 31,393,540
            수익률 및 평가손익 : 4.99%, 1,494,475
            가장 많이 오른 종목 : 골든브릿지증권(26.99%)
            가장 많이 하락한 종목 : 아모레퍼시픽(-4.23%) 
            ```
    * ![default](https://user-images.githubusercontent.com/44763265/51785896-1dcd7980-21a0-11e9-838b-90a47b3822c8.PNG)

2019.02.02 ~ 02.28
---
* 알고리즘 공부 [ 파이썬 ]
    * 필수 알고리즘 with 파이썬 교재 이용
    * 다양한 실습문제 풀어보기


2019.03.01 ~ 03
---
* SVM Code Sumit
* kaggle data analysis

2019.03.04~
---
* 취업 자기소개서 작성 시작

~ 04.10
---
* 그 동안 2019 상반기 채용에 대비해 여러 기업에 대한 자소서를 작성했음.
* 새로 시작한 두 개의 프로젝트 & 공모전
    * 2019 IQC Global Insight (퀀트 투자 세계 대회)
    * 부동산 114 공모전

04.11
---
* 넥슨 서류 합격 및 과제 진행
    * Data EDA

04.12
* 넥슨 과제 EDA 마무리
    * FRQuency 확인, 이상치 처리 ,결측값 처리, Feature enginerring.

04.13
* 넥슨 과제 협업필터링, 거리 계산

04.14
* 다변량 자료분석 학교 수업 복습

04.15
* 확률론 과제, 글영 과제
* 넥슨 과제 분석 
    * 변수간 거리 구하기, 차원 재조정

2020.01.30 study History 재시작
======

2020.01
---

2020.01.30
* Edwith - 파이토치로 시작하는 딥러닝 기초 수강
    * lecture : 도커환경설정
* Edwith - 논문으로 짚어보는 딥러닝의 맥
    * lecture 1 : 딥러닝 & 딥러닝 개발 도구
    * lecture 2 : 앞으로 우리가 다뤄볼 내용들

2020.02.03
* Edwith - 논문으로 짚어보는 딥러닝의 맥
    * lecture 3 : Convolutional Neural Network(CNN)의 기초

2020.02.12
* Edwith - 논문으로 짚어보는 딥러닝의 맥
    * lecture 7 : 4가지 CNN 살펴보기: AlexNET, VGG, GoogLeNet, ResNet

~2020.02.20
* Edwith - 논문으로 짚어보는 딥러닝의 맥
    * lecture 8 : Overfitting을 막는 regularization

* 2020.02.22 ~ 23
  * 실전 투자자의 매매 기록 수집 방법 고안
  * 0.계좌 개설
  * 1.미래에셋대우 & 키움 계좌 및 아이디 생성[02.22 오후 9시 개설 - 신분증 진위 확인 소요 시간때문에 바로 진행 x]
    * 2020.02.23 16:50 신분증 진위 확인
  * 2.영웅문s(모바일앱)에서 공인인증서 발급
  * 3.실전투자대회 참가신청

* 2020.02.24 ~ 03.02
    * 매매내역 파이썬 크롤링 코딩
    * 더욱 자동화하기 위해 세부 코딩
* ~ 2020.03.22
  * 매매내역 크롤링 코딩 완료 및 자동화하여 매일 작동화
  * 신규 과제 파악
  * CNN 공부

