# 02 Tests

[← Back to README](../README.md)

| Test | Pass when |
|---|---|
| Read input registers (FC04) from Modbus Poll | Values match the ESP's sensors with correct scaling |
| Read holding (FC03) | Setpoint readable |
| Illegal address | Exception response returned |
| Bus loss | Client times out cleanly; the ESP keeps running |
| CODESYS client | Reads points into a PLC program (#13) |
