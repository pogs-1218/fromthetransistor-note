# Overview
Icarus Verilog 와 Verilator를 함께 사용한다. Verilog 자체에 대한 것은 테스트 벤치 코드 작성과 함께 Icarus Verilog를 사용하여 테스트하고 Verilator로 C++로 작성된 테스트벤치 코드와 실행파일을 생성하여 시뮬레이션 할 수 있도록 해야한다.

semihosting은 UART를 사용한다.

Verilog로 작성된 모듈은
UART  
ARM CPU  
Controllers  
MMU  
이다. SRAM 부분이 필요한 듯 한데 필요시 포함한다. 

Verilog로 작성된 모듈은 하드웨어 레벨을 나타내고 서로간에 인스턴스화를 해서 사용한다.
전체 모듈은 Verilator를 통해 C++코드로 변환하고 빌드하여 호스트PC에서 실행한다.

Ethernet Controller와 SD Card Controller는 Verilog로 작성해야 하는데, 실제 하드웨어 장비와의 통신을 위해 DPI와 기타 브릿지코드(?)가 필요할 것 같다.

실제 장비의 동작과 비교하기 위해 QEMU를 사용한다.

전체적인 입출력은 다음과 같을 것 이다.  
[Host] C 프로그램 작성  
[Host] 컴파일 : Haskell로 작성된 자체 컴파일러 (입력: .c 파일들 / 출력: .asm 파일들)  
[Host] 어셈블러 : pythong으로 작성된 자체 컴파일러 (입력: .asm파일들 / 출력: 자체 머신코드)  


좀더 정확한 청사진을 그리기 위해서는 컴퓨터 구조와 시스템에 관해 더욱 깊이 이해하고, 기존의 시스템을 사용해 실습이 필요하다.


# References
