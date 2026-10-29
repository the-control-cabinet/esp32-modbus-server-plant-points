# 01 Register map

[← Back to README](../README.md)

| Register | Type | Point | Scaling | Units |
|---|---|---|---|---|
| 30001 | Input, INT16 | Process temperature | × 10 | °C |
| 30002 | Input, INT16 | Pump 1 run hours | × 1 | h |
| 30003 | Input, UINT16 | Status bits (pump 1 run, pump 2 run, fault, lockout) | bitfield | n/a |
| 40001 | Holding, INT16 | Setpoint (writable in phase 2 only) | × 10 | °C |

Byte/word order, function codes supported (03, 04; 06/16 in phase 2), slave ID and comms settings (9600 8N1) documented in [data/register-map.csv](../data/register-map.csv).
