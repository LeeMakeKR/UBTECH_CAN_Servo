# UBTECH CAN 서보 테스트 계획서

## 📋 테스트 개요

**테스트 대상**: UBTECH CAN 프로토콜 서보 (AA 00 00)  
**통신 방식**: CAN 2.0 (500 kbps)  
**테스트 목적**: 프로토콜 검증, 통신 안정성 확인, 명령어 동작 검증  
**작성일**: 2025-11-23



### 1.3 배선 가이드

1. **MCP2515 → Arduino 연결**
   - MCP2515 VCC → Arduino 5V
   - MCP2515 GND → Arduino GND
   - MCP2515 CS → Arduino D10
   - MCP2515 SO (MISO) → Arduino D12
   - MCP2515 SI (MOSI) → Arduino D11
   - MCP2515 SCK → Arduino D13
   - MCP2515 INT → Arduino D2

2. **전원 연결**
   - 서보 V+ → 24V 전원 (+)
   - 서보 GND → 24V 전원 (-), Arduino GND (공통 접지)
   - ⚠️ Arduino와 서보는 GND 공통 연결 필수

3. **CAN 버스 연결**
   - MCP2515 CANH → 모든 서보 CANH (병렬 연결)
   - MCP2515 CANL → 모든 서보 CANL (병렬 연결)
   - 버스 양단에 120Ω 터미네이션 저항 연결 (CANH-CANL 사이)

4. **4핀 5264 커넥터 주의사항**
   - 노치(홈) 방향 확인
   - 핀 순서: V+, GND, CANH, CANL



## 📚 참고 자료

- [Protocol_CAN_Bus.md](Protocol_CAN_Bus.md) - CAN 프로토콜 상세 문서
- [MCP2515 데이터시트](https://ww1.microchip.com/downloads/en/DeviceDoc/MCP2515-Family-Data-Sheet-DS20001801J.pdf)
- [mcp_can 라이브러리](https://github.com/coryjfowler/MCP_CAN_lib)
- CAN 2.0 규격 문서

---

## 🔄 변경 이력

| 버전 | 날짜 | 변경 내용 |
|------|------|----------|
| 1.0 | 2025-11-23 | 최초 작성 |

---

**작성자**: pashiran  
**버전**: 1.0  
**작성일**: 2025-11-23  
**최종 업데이트**: 2025-11-23
