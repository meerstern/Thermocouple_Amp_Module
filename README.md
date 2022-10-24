# 熱電対センサアンプ基板
Thermocouple_Amp_Module with MAX31855K & STM32G030F6P6

## 概要
  * [MAX31855K][1]を使用したK型熱電対センサ用のアンプ基板です  
  * K型熱電対の温度に応じてアナログ出力(0~3.3V)を得ることが可能です  
  * JP1のOpenでローゲインモード(既定)、Closeでハイゲインモードの切替が可能です  
  * ローゲインモードの場合、ゲイン200℃/V、オフセット1.25Vで、温度範囲は-240℃～400℃です  
  * ハイゲインモードの場合、ゲイン400℃/V、オフセット1.25Vで、温度範囲は-270℃～800℃です  

  * 計算式  $K型熱電対温度℃＝ゲイン×(電圧出力-オフセット)$  

 * 電源投入直後及び熱電対の断線や短絡等の異常時は基板上のエラーLED(赤色)が点灯します  
 * STM32G030F6P6マイコンのコードを公開しているため、ファーム書換でゲインやオフセットを変更することが可能です  
 * アナログ出力はSTM32G030F6P6マイコンのPWM出力(16bit)からローパスフィルタとバッファを介して出力しています  
 * 電源電圧が5Vであってもアナログ出力範囲は0~3.3Vです  
 * アナログ出力範囲の上限及び下限ではオフセット電圧や飽和電圧の影響で温度精度が低下する場合があります  
 * 電源電圧：3.3V~5V  
 
<img src="https://raw.githubusercontent.com/meerstern/Thermocouple_Amp_Module/master/IMG/img1.jpeg" width="360">
   
<img src="https://raw.githubusercontent.com/meerstern/Thermocouple_Amp_Module/master/IMG/img2.jpeg" width="360">
 
 
 [1]: https://www.maximintegrated.com/jp/products/interface/sensor-interface/MAX31855.html
