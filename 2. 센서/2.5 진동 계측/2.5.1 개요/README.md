# 1. 개요

## 1.1 목적
- 현장의 기계설비에서 발생하는 진동은 기기를 노화시키거나 계속적인 위험도 이상의 진동으로 기기의 결함을 발생시킬 수 있는 요소임
- 진동은 기계적 결함을 사전 예방할 수 있는 중요 신호로, 효율적인 유지 보수 및 수명 연장을 위한 데이터를 제공함.
</BR></BR>

## 1.2 특성
- 기기 설비의 진동은 주로 고주파수 진동(팬, 펌프, 구동기 등) 과 저주파수 진동(회전체-발전기, 밸브) 로 크게 나눌 수 있음
- 진동의 주파수 대역에 따라 다음과 같이 측정 파라메터를 나눌 수 있음 (Reference 4.1)
  - 저주파수 진동(~100hz) : 주로 기계적 결함, 불균형으로 발생하며 변위(Displacement), 속도(velocity)를 측정 필요
  - 고주파수 진동(100hz~) : 마모, 불균형, 베어링 결함등으로 발생하며 가속도(Acceleration) 측정 필요
- 진동 측정 및 분석을 위해 필요한 주요 신호 표현방식은 다음과 같음
  - RMS(Root Mean Squrae)
  - Peak to Peak(pk-pk)
  - Peak(Pk)
  - 주파수 스펙트럼(Frequency Spectrum)
</br></br>

# 2. 계측기 선정 고려사항

## 2.1 측정범위
- 고/저주파수 측정을 위해 측정범위는 **최소 0.1 ~ 10khz** 이상이여야 하며, 고/저주파수 진동에 대한 정확도가 고려되어야 함(Reference 4.2)
- 고주파수 진동의 경우 가속도계를 사용하고, 저주파수 진동의 경우 근접센서(변위센서) 가 적합

## 2.2 선형성
- 진동의 선형범위를 보장 해야 하며, 진동 크기와 주파수에 따라 비선형적 왜곡이 발생하지 않아야 함

## 2.3 응답속도와 샘플링 주파수
- 고속회전기기 및 고주파수진동에 대해 민감하게 반응할 수 있도록 계측기의 응답속도 및 샘플링 주파수 중요
  - 응답속도 : 저주파수(~100hz)는 수 ms이내, 고주파수는(100hz ~ 10 khz)는 수 us 이내 (일반적으로)
  - 샘플링 주파수 : 최소 신호 주파수의 2배(Nyquist) (Reference 4.3)

## 2.4 환경 요인
- 온도, 전기적간섭(EMI) 등의 환경적 요인을 고려하여 내열/내진/방폭 성능을 고려하여 선정
</BR></BR>

# 3. 계측기 설치 및 연결, 성능 시험 고려사항항

## 3.1 설치 위치
- 핵심 부위인 베어링, 축, 구동부에 가까운 위치가 가장 이상적
- 일반적으로 진동은 회전하는 부분(베어링, 회전축)에 발생
- 진동 모드(단일 모드, 비선형모드)에 맞추어 설치 위치 조정
- 진동 측정의 방향성에 따라 센서가 맞춰져야 함. 설치 방향을 회전축 방향에 맞춰 설치하며, 단일축 센서는 수평/수직을 조합하고 다축 센서는 여리 진동을 동시 측정할 수 있게 위치를 조정 함</br>
  (Reference 4.4) 

## 3.2 설치 방법
- 센서의 종류에 따라 설치 방식이 달라짐
- 가속도계는 일반적으로 스터드 마운트(stud mount) 방식, 근접센서는 비접촉식으로 설치
- 설치 방식에 따라 주파수 응답 특성이 변화함 주의

## 3.3 배선
- EMI 환경에 맞추어 차폐 케이블 활용(차폐 케이블과 접지 신호 연결은 VENDOR요건에 따라 수행)
- 출력신호 형태(4-20mA, 5V) 에 따라 DCS/PLC 신호 확인
- 전원공급선과 신호전송선 분리

## 3.4 방폭(Explosion proof) 
- 설치 환경에 맞추어 방폭 요건 고려(ATEX, IEC, NEMA 7/9)
- 예시 : 가연성 가스 존재 시 (ZONE 1 : 가스 존재 높음, ZONE 2: 드물게 가스) 방폭 필요 (EX d 등급) (Reference 4.5)

## 3.5 방수, 방진(Water proof)
- 먼지/습기 등으로부터 보호 위해 방수 고려(IP)
- 먼지/입자에 민감시 IP6X (완전 방진) 고려 (Reference 4.6)

## 3.6 설치 부 온도
- 고온 환경의 경우 계측기의 내열 성능 확인 후 설치

## 3.7 전자기간섭(EMI)
- 아날로그 신호의 경우 EMI로 인한 신호 왜곡 발생 가능
- 차폐(기기 금속 차폐, 차폐케이블 활용)와 접지/필터링(전원공급선 EMI 필터) 활용 

## 3.8 성능 시험

### 3.8.1 기준 진동 측정
- 측정 현장의 정상상태 진동 및 진동레벨 기록, 데이터 수집, 정상상태의 주파수 분석

### 3.8.2 알람(Alarm) 설정
- 다단계 알람 설정 : 진동 수준이 증가할 수록 알람 중요도 증가하도록 설정(경고/심각한 경고/비상 정지) (Reference 4.7)
- 알람 임계값 설정 : Vendor 설정치 준수, 배수 기준 설정, 통계적 방법 등 존재
  
  - Vendor 설정치 : 회전기기 공급 Vendor에서 제공하는 진동치 설정</BR>
  - 배수 기준 : 진동 정상 범위의 진동치 기준, N 배수 기준으로 설정. 펌프의 베어링등 비회전부 부착 센서에서 진동 측정 시 알람 참고 기준은 아래 참고(Reference 4.7)
    
    ![image](https://github.com/user-attachments/assets/f65e1b17-1da6-4308-ba4d-4fec2fc23f16) </BR>
    * Category 1 : 높은 신뢰성 수준의 펌프
    * Category 2 : 일단, 덜 중요 용도 펌프


# 4. 참고 문서
1. ISO 10816-1, "Mechanical vibration - Evaluation of machine vibration by measurements on non-rotating parts - Part 1: General guidelines"
2. ISO 5349, "Mechanical vibration - Measurement and evaluation of human exposure to hand-transmitted vibration"
3. IEEE 1057-2017, "IEEE Standard for Digital Signal Processing Applications in the Electric Power Industry"
4. ISO 10816-3, "Mechanical vibration - Evaluation of machine vibration by measurements on non-rotating parts - Part 3: Industrial machines (in situ measurement)"
5. IEC 60079, "Explosive atmospheres - Part 0: Equipment - General requirements"
6. IEC 60529, "Degrees of protection provided by enclosures (IP Code)"
7. ISO 10816-7, "Mechanical vibration — Evaluation of machine vibration by measurements on non-rotating parts Part 7"


