# 1. Amplifier - 연산증폭기(Operation Amplifier, OP-AMP)
 - 입력된 전압을 증폭시켜 출력하는 직류 연결형 고이득 전압 증폭기
 - 일반적으로 부귀환(Negative Feedback)을 통해 이득을 조절하여 사용
 - 이상적인 op-amp의 특성은 다음과 같음
   - 입력 임피던스(R_in) : ∞
   - 출력 임피던스(R_out) : 0
   - 전압 이득(G) : ∞
  </br></br>
  
## 1.1 비반전연산증폭기(Non-inverting amplifier)
![image](https://github.com/user-attachments/assets/439b380b-4939-4f99-82e9-37a6866c5934)
</br>

- 이득(Gain)만큼 입력이 증폭되어 출력
- 피드백 저항의 비례하여 연산 증폭비를 조절
- 출력 Vout = ( 1+ Rf/Ri</B> ) * Vin

- 회로 해석
  - 연산 증폭기 출력이 되먹임 되므로 V_ = V+
  - V+ 에 걸리는 전압은 Vin이므로 V_ = Vin
  - Ri에 걸리는 전압은 따라서 Vin - 0 (gnd)
  - 전류 Ii = (Vin-0)/Ri
  - Rf에 걸리는 전압은 Vout-Va, Va = Vin이므로 Vout-Vin
  - 전류 If = (Vout - Vin)/Rf
  - Ii = If 이므로 (Vout-Vin)/Rf = Vin/Ri
  - <B>따라서 Vout/Vin = 1+ Rf/Ri</B>
  </BR></BR>

## 1.2 반전연산증폭기(Inverting Amplifier)
  ![image](https://github.com/user-attachments/assets/c1f24986-2610-44e5-829b-adab039643fe)
 </br>

- 비반전 연산증폭기와 다르게 입력 전압을 -단에 연결, 출력을 반전 증폭
- 출력 Vout = -Rf/Ri * Vin
- 회로 해석
  - 연산증폭기 출력이 되먹임되므로 V_ = V+
  - V_ = Va, V+ = gnd이므로 V_ = Va = 0(gnd) (이를 가상접지라 함)
  - Ri에 걸리는 전압은 Vin - Va
  - 따라서 전류 Ii = (Vin - 0)/Ri
  - Rf에 걸리는 전압은 Va - Vout = -Vout
  - 따라서 전류 If = (Va - Vout)/Rf
  - If = Ii 이므로, Vin/Ri = -Vout/Rf
  - <B>따라서 Vout/Vin = -Rf/Ri</B>
    </BR></BR>
  
## 1.3 차등증폭기(Diffrential Amplifier)
![image](https://github.com/user-attachments/assets/8b79a93d-3006-451e-a59b-8f9782de6b1b)
</br>

- 회로 해석
  - I1 = I+ + Ig
  - I2 = I_ + If
  - I+ = I_ = 0
  - 따라서 I1 = Ig (1), I2 = If (2) 
  - Ig = (Va - 0)/Rg
  - If = (Vout - Vb)/Rf
  - I1 = (V1-Va)/R1
  - I2 = (V2-Vb)/R2
  - (1)에 따라, (V1-Va)/R1 = Va/Rg
  - (2)에 따라, (V2-Vb)/R2 = (Vout-Vb)/Rf
  - Va = Vb이므로, Vb에 Va를 대입
  - Vout에 대해 최종 정리 시 다음 식 도출
  - ∴ Vout = (1 + Rf/R2)* (Rg/(R1+Rg))*V1 - Rf/R2 * V2
  - 만약 R1=R2=Rg=Rf일 때, 식은
  - ∴ Vout = V1-V2
</br></br>

# 2. Filter
- 신호처리기에서 사용하는 필터는 디지털 필터와 아날로그 필터로 나뉨
- 일반적으로 신호 특성에 따라 다르지만 아날로그 필터와 디지털 필터를 함께 사용하는 경우 많음(PRE FILTER : ANALOG, POST FILTER : DIGITAL)
- 아날로그 필터와 디지털 필터의 대상과 특성은 다름. 다름 표 참고

  |항목|아날로그 필터|디지털 필터|
  |----|-------------|------------|
  |대상|연속 시간 신호|샘플링 된 이산 신호|
  |위상 제어|어렵거나 제한적|정밀 제어 가능|
  |리플/감쇠|소자 특성에 따라 결정|수치적으로 자유롭게 설계|
  |설계변경 난이도|어려움(회로 변경)|쉬움(소프트웨어 재설계)
  |실시간 처리성능|지연 없음|연산 지연 존재(SAMPLING 지연)|
  |잡음 내성|EMI, 열잡음에 민감|상대적으로 강함|

## 2.1 Analog Filter
  
### 2.1.1 Low Pass Filter

![image](https://github.com/user-attachments/assets/86e104d8-9711-4312-8b79-1a4251bf50f6)

- 기능
  - 고주파 잡음 제거 : 차단 주파수 이상의 고주파 잡음 제거
  - 앨리어싱 방지 : 고주파수 성분 허용 시 샘플링 주파수가 아무리 높아도 이론 상 무한대의 주파수성분이 존재, 앨리어싱 노이즈 발생
- 통과대역 : 0 ~ fc(차단주파수)
- 사용 예 : 센서 신호의 평균화, ADC 샘플링 전 설치
- 회로 해석
  - 라플라스 변환을 통해 변환된 각 변환 요소는
    - R : R
    - C : 1/Cs
  - 전압 분배 법칙을 통해 Vout에 걸리는 전압을 추정
  ∴ Vout = Vin * (1/Cs) / (R+ 1/Cs) = 1/(RCS+1)

  - 차단주파수 : 주파수 영역 (S=jw) 해석 시,
  ∴ H(jw) = 1/(1+jwRC), 차단주파수 Wc = 1/RC, fc = 1/(2*pi*RC)

### 2.1.2 High Pass Filter
</br></br>

## 2.2 Digital Filter

### 2.2.1 FIR(Finite Impulse Response) Filter  

- 유한한 응답동안 임펄스 응답만 존재하는 필터
- 형식
  
  ![image](https://github.com/user-attachments/assets/a3377113-9910-438d-a3a7-36c9b483204c)
  </BR>
  (y(n) = 출력, x(n-k) = 과거 입력)
  
- 4계 입력 FIR필터의 경우</BR></BR>
  ![image](https://github.com/user-attachments/assets/b856c2a2-e9a5-497d-b0a8-10c632c1e1a1)

- 구조 : 과거 입력을 기반, 입력에 특정 계수를 곱해(최근 입력값은 큰 계수, 오래된 입력값은 작은 계수) 가중 평균을 적용 
- 특징
  - 항상 안정적(모든 계수 유한)
  - 선형 위상 구현 가능
  - 설계 및 구현이 직관적
  - 계산량 많음(높은 차수 필요)

- 설계 : window, remez 등 방법 있으나 여기선 window 법으로만 설명</br>
- Window 방법 : 이상적 필터의 임펄스응답(ex. low pass : sinc함수)을 유한한 길이로 가르기 위해 끝 부분을 부드럽게 감쇠시키도록 곱하는 방법
  
  ![image](https://github.com/user-attachments/assets/2e6bd3c0-98d5-4a50-a9f8-3d2f562c2319)

  - 이상적 임펄스 응답은 이론적으로 무한 길이로 실제 구현 불가, 따라서 특정 윈도우를 곱해 유한한 길이로 자름

![image](https://github.com/user-attachments/assets/615a1232-7190-415e-9f9e-063e25e00e9a)

   
    
