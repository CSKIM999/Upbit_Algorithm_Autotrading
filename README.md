# Upbit_Algorithm_Autotrading
작년 초 완성한 알고리즘 자동매매 프로그램의 Python 파일입니다. IDE 상에서 실행하실 수 있습니다.

본래 key값을 입력하는 창을 만들고, 해당 파일을 Pyinstaller 를 통해 exe 파일로 재배치하여 배포하는것이 최종 목표였습니다.
실사용하기엔 부족한 면이 많이 보여서, 앞서 설명한 유동key 값의 구현까진 하지 못하고,
자신의 KEY 값을 넣고 pyinstaller 를 사용하여 응용프로그램파일로 만들 수 있습니다.

현재는 access & secret KEY 값이 지워진 상태로 Commit 되어 Balance 확인을 위해 RESET 버튼을 누르더라도 작동하지 않습니다.
모든 기능은 access & secret KEY 를 사용하므로, KEY 값을 입력해주어야 정상작동합니다.

# 사용방법
### 사용하시기에 앞서 래리 윌리엄스의 변동성돌파 전략을 숙지하시면 더욱 정확히 사용 가능합니다 
### [변동성돌파알고리즘] : [https://the-nest-of-cskim.tistory.com/5?category=1012985]
* * *
> ## Algorithm
> ##### 거래기준봉, 변동성상수(CONST NUM), 코인Ticker(COIN NAME)을 설정 후 우측 SET 버튼을 눌러주세요
> ##### 3가지 변수가 설정완료되면, 하단의 START 버튼이 활성화됩니다.
> ##### START 버튼과 함께 LOADING BAR 가 움직이고 THREAD 창에 현재 감시하는 TICKER의 감시가격이 표시됩니다.
> ### >>중요<<
> ### [[ 현재가가 매수조건을 만족할 경우 ]] 
> ### [[ 현재 주문할 수 있는 "KRW 전액" 을 "시장가" 로 매수합니다 ]]
> ##### 특수한 매수신호 TEXT 가 THREAD 에 표시되고, 거래기준봉에 따른 단위시간의 끝에 전량 매도합니다.
* * *
> ### 거래기준봉
> ##### 10분, 30분, 60분을 선택할 수 있습니다.
> ##### 10분보다 더 작은 기준봉은 수수료를 계산한 BACKTESTING 결과 승률이 더 낮게 책정되어 제외했습니다.
> ##### 선택하지 않고 SET 버튼을 누를경우 30분봉 SET 이라는 TEXT 가 출력되나, 실제로 SET 되지는 않으니 설정 후 SET 버튼을 눌러주세요
* * *
> ### CONST NUM ( 변동성상수 )
> ##### float 형태로 소수점단위까지 입력이 가능합니다. 다만, 자신의 자산을 사용하는 매매프로그램이니 신중히 입력해주세요.
> ##### 소수점 첫째자리까지는 유효하게 작동합니다.
> ##### 만약 선택하지 않고 SET 버튼을 누를경우, DEFAULT 값인 1.0 이 입력되어 SET 됩니다.
* * *
> ### COIN NAME ( COIN TICKER - 코인이름 )
> ##### 거래하고자 하는 COIN-TICKER 를 입력해주세요.
> ##### TICKER 는 영어 대소문자 모두 가능하며 3글자만 입력해주셔야 합니다. ( EX : BTC )
> ##### 만약 KRW 마켓에 없는 TICKER 를 입력 시, DEFAULT 값인 BTC 가 대신 입력됩니다.
> ##### 마찬가지로 선택하지 않고 SET 버튼을 누르는 경우에도, DEFAULT 값인 BTC 가 대신 입력됩니다.
* * *
> #### STOP LOSS
> ##### 본래 STOP LOSS 기능도 추가하고자 그리드 안에 구현해두었으나, 기능은 구현되지 않았습니다.
* * *
> ### 실행 BOX
> ##### 3가지 변수를 모두 SET 한다면 START 버튼이 활성화됩니다.
> ##### 만약 거래를 중단하고싶다면, RESET-ALL 버튼을 눌러주세요
* * *

### 총 3개의 TICKER를 "동시" 감시할 수 있습니다.
### 전략 자체를 의심하진 않으나, 자신의 자산을 거래하는 만큼 신중한 상수결정을 필요로 합니다.
### 코드 사용은 자유지만, START 버튼을 누르는 동시에 책임은 자신에게 있습니다.
