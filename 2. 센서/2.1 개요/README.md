# 1. 센서(검출기)의 일반사항
 - 검출요소(detecting elements) 에서 피측정량을 받아 들일 때, 피측정량은 아날로그 신호로 변환
 - 검출기의 출력과 피측정량(검출기 입력)에 대한 관계식은 다음과 같음
   - 출력 I_out = f(I_in) (일반적으로 선형 함수로 표현)
   - 효율 : I_out / I_in
   - 민감도 : diff(I_out) / diff(I_in) (일반적으로 상수로 근사)
</br></br>

# 2. 신호원
 - 전기적/전자적으로 물리적 신호를 생성하는 장치
 - ex) 함수발생기, 오실레이터
 - 신호원 내부적으로 부하(loading)가 존재. 부하란? 신호원에 영향을 미치는 정도.
 - 예) 전압신호원과 센서 : 센서 내부적 임피던스 (부하) 에 의해 신호원 전압의 감소
</br></br>

# 3. 요소 구분에 따른 센서의 분류
 - 세 가지 형태로 분류 가능
   1) 검출기 요소만 가진 센서 : 신호를 감지하는 검출기만 가짐
      (ex. 바이메탈 온도 센서 : 금속열팽창->금속 기계적 변형, 수은 온도계 : 온도 변화->수은 높이)
   2) 검출기 + 변환기(tranducer) : 검출기가 감지한 신호를 전기 신호로 변환
      (ex. 스트레인 게이지 : 변형 감지 -> 저항 변화 -> 전압)
   3) 검출기 + 1차 변환기 + 2차 변환기 : 1차 변환기를 거쳐 2차 변환기 통해 최종 신호 발생
      (ex. 압력 센서 : 저항 변화(스트레인게이지)->전압 변화->증폭기(휫스톤브릿지) )
</br></br>

# 4. 입력 물리량에 따른 센서의 분류

 - 온도	: 열전대, RTD, 서미스터
 - 압력(힘)	: 스트레인게이지, 정전용량형 압력 센서
 - 유량	: 터빈형, 전자유량계, 초음파 유량계
 - 수위 : 전파식, 초음파식, 플로트식
 - 변위/위치	: LVDT, 포텐셔미터, 광센서
 - 속도/가속도 : 자이로센서, 가속도계, 타코제너레이터
 - 조도/광량 :	포토다이오드, 광전소자
 - 자기장	: 홀 센서, 자기저항 센서	
 - 화학적 성분	: 가스 센서, pH 센서, 전해질 센서
</br></br>

# 4. 변환 원리에 따른 센서의 분류

 - 저항형 (Resistive)	: 물리량에 따라 저항값이 변함
   - 변형률 게이지(Strain Gauge), RTD, 포텐셔미터
 - 정전용량형 (Capacitive)	: 물리량에 따라 정전용량이 변화
   - 터치 센서, 압력 센서, 거리 센서
 - 유도형 (Inductive)	: 금속 이동이나 변화에 따라 자기 유도가 발생
   - 근접 센서, 변위 센서 (LVDT)
 - 자기형 (Magnetic)	: 자속 변화에 따라 기전력 유도 (패러데이 법칙)
   - 회전 센서, 속도 센서
 - 압전형 (Piezoelectric)	: 압력을 가하면 전하가 발생
   - 진동 센서, 마이크, 가속도 센서
 - 광학형 (Optical)	: 빛의 변화 (반사, 투과 등) 이용
   - 포토센서, 거리 센서, 코드 리더기
 - 열전형 (Thermoelectric)	: 온도차 → 기전력 발생 (제백 효과)
   - 열전대 (Thermocouple)
 - 홀 효과형 (Hall Effect)	: 자기장에 따른 전압 차 발생
   - 전류 센서, 위치 센서
 - 자기저항형 (Magnetoresistive)	: 자기장에 따라 저항 변화
   - 자기센서, 위치 탐지기
 - 초음파형 (Ultrasonic)	: 음파의 반사/도달 시간 측정
   - 거리 센서, 유량 센서
</br></br>

