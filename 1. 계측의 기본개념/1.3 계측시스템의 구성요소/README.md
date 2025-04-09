계측 시스템은 계측 시스템은 다양한 물리량을 정밀하게 측정하고, 이를 적절한 형태로 변환하여 분석하거나 제어에 활용하기 위한 시스템이다. 
기본적으로 다음의 세 가지 핵심 구성요소로 이뤄진다:

# 1. 센서 (Sensor) 
- 물리량(온도, 압력, 유량, 위치 등)을 직접 감지하여 전기적 신호로 변환
- 예시 : 
  - 열전대(온도)
  - 스트레인게이지(힘)
  - 초음파 센서(거리)
- 측정 대상에 직접 닿는 경우도 있고, 간접 방식도 있음 출력 신호는 미약한 경우가 많아 증폭 또는 보정 필요 함
</br></br>

# 2. 신호 변환기 (Signal Conditioner)
- 센서에서 발생한 미약하거나 불안정한 신호를 증폭, 필터링, 정규화하여 다음 단계로 전달 가능한 형태로 변환
- 주요 기능:
  - 증폭(Amplification): mV → V로
  - 필터링(Filtering): 잡음 제거 (특히 EMI 환경에서)
  - 정류/변환(Conversion): 아날로그 → 디지털, 혹은 전류 ↔ 전압
- 예시:
  - 차동 증폭기
  - 필터 모듈
  - A/D 변환기
 </br></br>
 
# 3.  기록 및 분석기 (Recorder / Data Logger / HMI / PLC 등)
- 처리된 신호를 저장하거나, 표시하거나, 제어 시스템에 전달
- 기록계(Recorder): 디지털 저장, 트렌드 그래프 생성
- HMI (Human Machine Interface): 시각화 및 운영자 인터페이스
- PLC (Programmable Logic Controller): 제어 신호 처리, 자동제어
- 서버 시스템: 장기 저장, 네트워크 전송
- 연결 방식: Ethernet, RS-485, 4–20 mA 등 산업 통신 표준 사용
</br></br>

![fig1_blockDiagram_INC](https://github.com/user-attachments/assets/e4b74a13-3e1e-4951-8262-9bef78735b7a)

