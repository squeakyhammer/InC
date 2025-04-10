# 1. 불확실도

- 측정값이 참값으로부터 어느 정도 오차 범위 내에 있을 지 정량적으로 추정하는 것.
- 오차의 분포 범위(±0.1°C at 95% confidence level)

## 1.1 계산 목적

### 1.1.1 시스템 요구 신뢰도 내 있는지 확인

- 시스템에서 요구하는 허용 정확도가 존재하는 경우, 불확실도 계산을 통해 기준 초과 가능성 확인
- 예시 : 시스템 요구 기준 정확도 0.5%, 계산된 전체 불확실도가 1% 인 경우 정확도를 초과하므로 불만족
</br></br>
### 1.1.2 임계값의 마진 확보

- 특정 물리량의 변화에 따라 임계값을 초과하거나, 임계값 이하로 내려가는 경우 사용자에게 경보 발생
- 이런 경우 안전 마진을 확보하여 불확실도의 범위 만큼 임계값을 반영하여 안전 마진 확보
- 예시 : 불확실도 1% , 임계값 200 Deg C 인 온도시스템, 임계값 초과 시 경보 발생
  - 안전을 위한 경보 : +-1% of 200 = 2 deg C, 200-2 = 198 deg C 에서 경보 발생
</br></br>

## 1.2 표기 방법

### 1.2.1 절대 불확실도
- 단위 값을 직접 표현
- 예시 : U = ±0.3°C, U = ± 0.05 A

### 1.2.2 상대 불확실도
- 측정값 대비 비율(%)
- 예시 : 측정값이 100kgf 인 압력계에서 +-1% reading 오차인 시스템의 불확실도는 1kgf/100kgf = 1%

## 1.2 계산 방법
    
### 1.2.1 Root Sum Square(RSS) Method
 
- 여러 불확실도 요소들을 합할 떄 사용
- ![image](https://github.com/user-attachments/assets/d9dc4f4e-33e9-4a3a-a7cd-26c09c251ba3)
- 오차 요소들이 <B>서로 독립적</B> 이여야 함
- 오차 요소들은 모두 같은 단위여야 함(ex. % span, % reading)
</br></br>
### 1.2.2 (Type A 평가)표준 편차 방법(Standard Deviation Method)

- 반복 측정을 통한 불확실도 산정
- ![image](https://github.com/user-attachments/assets/ff450f8b-5233-44d5-8bff-a02b4503a72c)
- Type A 평가(통계적 분석을 바탕으로 불확실도를 구하는 방법) 에 해당
</br></br>

### 1.2.3 Type B 평가

- 기존의 정보, 문서, 규격, 경험 등을 바탕으로 불확실도를 추정하는 방법
- Datasheet, Calibration Certification, 경험, 측정기 해상도등을 고려
- 예시 : 센서 스펙이 ±1%인 경우, 불확실도 u = a/(sqrt(3)) = ±0.577% (균일분포 가정, 1σ 수준)
- 최대 오차로부터 불확실도 평가 시 오차의 분포 가정 방식에 따라 계산 방식 변화
- 상세 분포는 다음 표 참고

|	분포 종류	|	가정	|	불확실도 (표준편차) 계산식|	주로 사용되는 상황	|
|-----------|-------|--------------------------|-----------------------|
|	균일분포 (Uniform)	|	모든 값이 동일한 확률로 발생	|	![image](https://github.com/user-attachments/assets/a36580eb-d3a2-4ad7-9ccb-6163e20c4e89)|명시된 최대 오차(±a)만 주어졌을 때	|
|	정규분포 (Normal)	|	중앙값 중심으로 종 모양 분포	|	![image](https://github.com/user-attachments/assets/8048c56c-e0d7-4564-be8f-c1da1de65960)	|측정 결과가 평균 중심으로 밀집 (기기 교정 등)	|
|	삼각분포 (Triangular)	|	중간값일 확률이 가장 높고 양 끝으로 갈수록 적음	|![image](https://github.com/user-attachments/assets/bb72d6ce-f701-47d2-86ed-e9f8b023ca47)|	일부 설계 허용치 평가, 실험적 오차에 가까운 경우	|
|	아르코신 분포 (Arcsine)	|	극단값일 확률이 높고 중간값은 적음	|	![image](https://github.com/user-attachments/assets/bf0eafba-2171-4c7e-a1b9-5d15380cd12c)|극히 드문 경우, 진폭 잡음 등 특이한 물리계	|

</br></br>

![image](https://github.com/user-attachments/assets/17d9d509-3785-4db3-8ebe-91f7192fea05)
</br></br>

### 1.2.4 확장 불확실도(Expanded Uncertainty)

- 신뢰 수준을 명시하기 위해 도입
- U = k*u
- 여기서 k는 coverage factor (σ 수준과 동일)
- 일반적으로 k=2면 95% 신뢰수준, k=3 이면 99.7%
- 예시 : 100 ± 0.45 deg C at k = 3 or 3σ → 99.7%수준으로 99.55 ~ 100.45 deg C 이내
- 예시 2 : 최대 허용오차 ±0.1 kgf인 압력계를 2σ (95% 수준) 불확실도 추정 -> 0.1/sqrt(3) * 2 = ±0.116 kgf
</br></br>

### 1.2.5 최대값 기준방법(Worst-Case)

- 모든 가능한 오차 요소를 합산해서 가장 보수적인 불확실도를 도출
- ![image](https://github.com/user-attachments/assets/35ed2851-2897-4961-b62b-e7f8f13aa829)
- 보수적 설계, RMS합성이 불가한 경우, 사전 검증이나 사양 설계 단계 등에 사용
- 실제보다 오차가 커질 가능성 높음
</br></br>

### 1.2.6 몬테카를로 시뮬레이션 

- 불확실도의 확률분포를 알고 있는 경우, 시뮬레이션 기반 추정
- 고급 분석, 불확실성 전파(UQ, Uncetainty Quantification)시 활용
</br></br>

### Type A vs B 비교
|구분|TYPE A|TYPE B|
|----|------|------|
|평가 방법|통계적|비통계적|
|사용 도구|평균, 표준편차|최대오차, 분포 가정|
|분포 예시|정규 분포|균일 분포, 정규 분포, 삼각 분포 등|
|불확실도 계산|S/sqrt(n)|a/srqt(3)(균일분포)|
