# ESP32 as a Modbus Server: Serving Plant Points to Real Controllers (Design Stage)

**Closing the loop between field devices and real BMS/PLC controllers: an ESPHome board acts as a Modbus server (slave), publishing plant points in a documented register map so the rig's Trend IQ411, a CODESYS soft-PLC or any Modbus client can read them, the reverse of the earlier Modbus projects where the ESP was the client.**

[![YouTube](https://img.shields.io/badge/YouTube-The%20Control%20Cabinet-red?logo=youtube)](https://www.youtube.com/channel/UC5Cupmz7vlfcodpCX7k8iuQ)
[![Portfolio](https://img.shields.io/badge/Portfolio-the--control--cabinet-24292f?logo=github)](https://github.com/the-control-cabinet/the-control-cabinet)
![Domain](https://img.shields.io/badge/BMS-Modbus%20server-blue)
![Status](https://img.shields.io/badge/Status-Design%20stage-yellow)

> **The short version:**
> - **Role reversal:** in the water-metering project the ESP polls a meter (client/master); here it **is** the device (server/slave).
> - **Transport:** Modbus RTU over RS485 using ESPHome's Modbus server capability ⟨confirm the component and its options in the current ESPHome⟩; Modbus TCP via an RTU-to-TCP gateway or a custom component ⟨choose⟩.
> - **Register map:** holding/input registers with scaling (e.g. temp × 10 as INT16), documented like a manufacturer's map.
> - **Clients:** CODESYS (PLC re-implementation, #13), the Trend IQ411 (if it has a Modbus option ⟨verify⟩), Modbus Poll for testing.

**Portfolio position:** Field level · protocol. Builds on: [Modbus RTU metering](https://github.com/the-control-cabinet/mains-water-metering-modbus-rtu) · [Modbus TCP lab](https://github.com/the-control-cabinet/modbus-tcp-data-collector). Feeds: [Trend IQ411](https://github.com/the-control-cabinet/trend-iq411-commissioning) · PLC re-implementation (#13)

---

## Documents

| Doc | Contents |
|---|---|
| [01 Register map](docs/01-register-map.md) | Documented like a device manual |
| [02 Tests](docs/02-tests.md) | Client reads, scaling, error handling |

## Roadmap
- [ ] Confirm the ESPHome Modbus server options (RTU)
- [ ] Register map v1 (read-only)
- [ ] Test with Modbus Poll over the FTDI RS485 adaptor
- [ ] CODESYS client; then the Trend IQ411 if supported
- [ ] Phase 2: writable setpoint with limits

## Skills demonstrated (as built)
| Skill | Evidence |
|---|---|
| Modbus server design | Register map with scaling and status bits |
| Protocol depth | Function codes, exceptions, byte order |
| Integration | Field device → PLC/DDC controller |

📺 [The Control Cabinet on YouTube](https://www.youtube.com/channel/UC5Cupmz7vlfcodpCX7k8iuQ)

*Built and documented by James · part of [The Control Cabinet BMS portfolio](https://github.com/the-control-cabinet/the-control-cabinet). MIT Licence.*
