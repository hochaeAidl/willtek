# willtek

## 1. Verilog(또는 System Verilog)를 이용한 다양한 주변장치 설계

- GPIO 입출력, UART, Timer, I2C, SPI 장치 구현
    - 12/30일까지 준비 완료
    - 기본 동작은 logic analyzer 사용 가능
    - 필요 시 cortex-M board 사용

| item | Env.| Status | 교재 |
|:---:|---|---|---|
|GPIO 입출력|기본 보드|주사위|
|UART|USB2UART cable, PC terminal| test ok| 10/26
|Timer||
|I2C|zynqboad RTC (확인요)||
|SPI|4-digit FND| test ok|10/26

- I2C, SPI의 경우 slave 장치를 만드는 것도 포함할 경우 이건 Cortex-M보드에 전선으로 연결하여 동작 실험
    - 기본 신호 검증은 logic analyzer로 진행 예정
    - UART: USB2UART converter로 대치
    - SIP: 4-digit-FND로 대치
    - I2C: DA9062(RTC)-> JP3를 통해 access 가능 -> test 필요

- AXI 버스까지 강의에 포함시 2주과정, AXI 버스 연결은 그냥 제공하고 주변장치 설계만 집중하면 1주과정
- AXI버스 이용하여 zed에 포함된 ARM에 연결하여 Vitis 프로그램 작성하여 외부 Cortex-M 보드 또는 Slave 보드와 연결하여 동작 실험
    - AXI-lite: 1주로 진행
    - AXI-stream: PS단의 meomory access -> 2주
    - AXI-standard: DMA + AI accelerator -> 3주 ~ 4주
    - **추후 변경 가능**

|특징	|AXI4-Lite	|AXI4-Stream	|AXI4 Standard|
|---|---|---|---|
복잡도	|낮음	|중간	|높음
대역폭	|낮음	|높음	|매우 높음
사용 목적	|레지스터 기반 슬레이브 장치, 간단한 제어	|고속 데이터 스트림 전송, 비디오/오디오 처리	|고성능 프로세서와 메모리 연결
버스트 전송	|지원하지 않음	|지원하지 않음|	지원


- 또는 Micro Blaze(?)를 이용하여 주변장치 동작 실험: **ARM 구현 후 추후 진행**

## 2. AI 반도체를 위한 AI 가속기 설계

- NPU 설계하고 이를 어떻게 동작 실험할건지는 검토 필요
- 시뮬레이션? 아니면 직접 프로세서 연결? 맛비 강의 먼저 쭉 훓어보고 방안 제안 필요
