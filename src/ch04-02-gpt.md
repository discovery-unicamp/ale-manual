## General Purpose Timer

| **Address** | **Size** | **Description**                                                                                                                                                                                          |
| :---------- | :------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `base+0x00` | byte     | Storing `1` triggers the GPT device to start reading the current system time. The register is set to `0` when the reading is completed.                                                                  |
| `base+0x04` | word     | Stores the time (in milliseconds) at the moment of the last reading by the GPT.                                                                                                                          |
| `base+0x08` | word     | Storing _v_ > 0 programs the GPT to generate an external interruption after _v_ milliseconds. It also sets this register to `0` after _v_ milliseconds (immediately before generating the interruption). |
