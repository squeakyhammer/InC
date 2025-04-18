## 1. 연산증폭기(Operation Amplifier, OP-AMP)
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
  
