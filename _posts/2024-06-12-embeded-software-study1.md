---
title: 임베디드 소프트웨어 기초 용어 정리
author: mong
date: YYYY-MM-DD HH:MM:SS +09:00
categories: [Embeded SoftWare, 스터디]
tags:
  [
    Firmware,
    Embeded Software,
  ]
---

# 1. RTOS의 개념

## 1.1 Thread & Synchronization
- **Thread**: 프로그램 내에서 독립적으로 실행되는 실행 단위. RTOS에서는 여러 스레드가 동시에 실행되면서 각각의 작업을 처리함.
- **Synchronization**: 이러한 스레드들이 자원을 안전하게 공유하고 순서를 정확하게 유지할 수 있도록 돕는 메커니즘.

## 1.2 Semaphore
- 여러 스레드가 공유 자원에 접근하는 것을 제어하기 위해 사용됨.
- 카운터를 사용하여 접근을 제어함.

## 1.3 Mutex
- 상호 배제(Mutual Exclusion)를 위해 사용되는 동기화 기법. 한 번에 하나의 스레드만 접근할 수 있도록 함.
- **비교**: 세마포어는 카운터를 사용하여 여러 스레드의 접근을 제어하는 반면, Mutex는 단 하나의 스레드만 접근할 수 있도록 제한함.

## 1.4 Message Queue
- 스레드 간 통신을 위해 사용되는 데이터 구조(FIFO).

## 1.5 ISR (Interrupt Service Routine)
- 인터럽트가 발생했을 때 실행되는 루틴으로, 하드웨어 인터럽트를 처리하기 위해 사용됨.
- 일반 스레드와 달리, 인터럽트에 의해 강제적으로 호출되며, 우선순위가 높음.

# 2. Processor & Peripherals

## 2.1 CPU
- 중앙처리장치

## 2.2 Register
- CPU 내에 있는 소형의 고속 메모리 장치로, 연산에 필요한 데이터나 명령어를 일시적으로 저장함.

## 2.3 Memory
- 데이터를 저장하는 장치로, 휘발성 메모리(RAM)와 비휘발성 메모리(ROM)로 나눌 수 있음.

## 2.4 GPIO (General Purpose Input/Output)
- 다목적 입출력 핀
- 디지털 신호의 입출력 기능 제공

## 2.5 UART (Universal Asynchronous Receiver/Transmitter)
- 비동기 직렬 통신

## 2.6 I2C (Inter-Integrated Circuit)
- I2C의 특징은 아래 표를 참조.

## 2.7 SPI (Serial Peripheral Interface)
- SPI의 특징은 아래 표를 참조.

| 특징 | I2C | SPI |
| --- | --- | --- |
| 배선 | SDA, SCL (2개) | SCK, MOSI, MISO, SS (4개 이상) |
| 속도 | 상대적으로 낮음 | 상대적으로 높음 |
| 통신 방식 | 반이중(Half-Duplex) | 전이중(Full-Duplex) |
| 다중 마스터 지원 | 가능 | 불가능 |
| 프로토콜 오버헤드 | 있음 | 없음 |
| 사용 용도 | 저속, 저전력 센서 통신 | 고속 데이터 전송 |
| 하드웨어 복잡성 | 낮음 | 높음 |

## 2.8 ADC (Analog to Digital Converter)/DAC (Digital to Analog Converter)
- ADC: 아날로그 신호를 디지털 데이터로 변환하는 장치.
- DAC: 디지털 데이터를 아날로그 신호로 변환하는 장치.