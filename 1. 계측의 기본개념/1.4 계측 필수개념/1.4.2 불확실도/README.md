# 1. 불확실도

- 측정값이 참값으로부터 어느 정도 오차 범위 내에 있을 지 정량적으로 추정하는 것.
- 오차의 분포 범위(±0.1°C at 95% confidence level)

## 1.1 계산 방법
    
### 1.1.1 Root Mean Square(RMS) Method
 
- 여러 불확실도 요소들을 합할 떄 사용
- ![image](https://github.com/user-attachments/assets/d9dc4f4e-33e9-4a3a-a7cd-26c09c251ba3)
- 오차 요소들이 <B>서로 독립적</B> 이여야 함
</br></br>
### 1.1.2 (Type A 평가)표준 편차 방법(Standard Deviation Method)

- 반복 측정을 통한 불확실도 산정
- ![image](https://github.com/user-attachments/assets/ff450f8b-5233-44d5-8bff-a02b4503a72c)
- Type A 평가(통계적 분석을 바탕으로 불확실도를 구하는 방법) 에 해당
</br></br>

### 1.1.3 Type B 평가

- 기존의 정보, 문서, 규격, 경험 등을 바탕으로 불확실도를 추정하는 방법
- Datasheet, Calibration Certification, 경험, 측정기 해상도등을 고려
- 예시 : 센서 스펙이 +-1%인 경우, 불확실도 u = a/(sqrt(3)) = 0.577% (균일분포 가정)
</br></br>

### 1.1.4 확장 불확실도(Expanded Uncertainty)

- 신뢰 수준을 명시하기 위해 도입
- U = k*u
- 여기서 k는 coverage factor
- 일반적으로 k=2면 95% 신뢰수준, k=3 이면 99.7%
</br></br>

### 1.1.5 최대값 기준방법(Worst-Case)

- 모든 가능한 오차 요소를 합산해서 가장 보수적인 불확실도를 도출
- ![image](https://github.com/user-attachments/assets/35ed2851-2897-4961-b62b-e7f8f13aa829)
- 보수적 설계, RMS합성이 불가한 경우, 사전 검증이나 사양 설계 단계 등에 사용
- 실제보다 오차가 커질 가능성 높음
</br></br>

### 1.1.6 몬테카를로 시뮬레이션 

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
