# LSE-StreamGuard-FPGA-Based-LSEG-Ticker-Stream-Parser-Crash-Interlock

A hardware-level streaming packet inspector and anomaly detection engine written in VHDL, targeting the Basys3 FPGA using AMD Vivado.

## Overview
Low-latency financial trading systems rely on hardware-accelerated network interface cards (NICs) to parse raw market feeds and trigger safety interlocks before software can react. **LSE StreamGuard** simulates this architecture, ingesting binary market data streams, parsing packets via state machines, and flagging price anomalies instantly in hardware logic.

## Key Features
- **Byte-Level FSM Parsing:** Frame sync and payload extraction handled entirely in combinatorial/sequential VHDL logic without CPU overhead.
- **Fixed-Point Arithmetic:** Lightweight Q16.16 fixed-point math for rapid delta-percentage calculations against rolling baselines.
- **Hardware Safety Interlock:** Instantaneous flag generation driving Basys 3 LEDs upon detecting abnormal price volatility.

## Repository Structure
- `rtl/`: Core VHDL source files (FSM parser, fixed-point math, top-level wrapper).
- `constraints/`: Basys 3 pin-mapping XDC file.
- `simulation/`: Behavioral testbenches for validating packet injection and anomaly triggers.
- `docs/`: System architecture documentation.

## Getting Started
1. Clone the repository:
   ```bash
   git clone [https://github.com/your-username/StreamParseFPGA.git](https://github.com/your-username/StreamParseFPGA.git)
