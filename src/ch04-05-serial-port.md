## Serial Port

The serial port is connected to the terminal (stdout and stdin).

| **Address** | **Size** | **Description**                                                                                                                                         |
| :---------- | :------- | :------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `base+0x00` | byte     | Storing `1` triggers the serial port to write (to the stdout) the byte stored at `base+0x01`. The register is set to `0` when writing is completed.     |
| `base+0x01` | byte     | Byte to be written. ID                                                                                                                                  |
| `base+0x02` | byte     | Storing `1` triggers the serial port to read (from the stdin) a byte and store it at `base+0x03`. The register is set to `0` when reading is completed. |
| `base+0x03` | byte     | Byte read. **NULL** (`0`) when stdin is empty.                                                                                                          |
