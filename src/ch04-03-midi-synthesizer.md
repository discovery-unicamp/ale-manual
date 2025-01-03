## MIDI Synthesizer

| **Address** | **Size** | **Description**                                                                             |
| :---------- | :------- | :------------------------------------------------------------------------------------------ |
| `base+0x00` | byte     | Storing _ch_ ≥ 0 triggers the synthesizer to start playing a MIDI note in the channel _ch_. |
| `base+0x02` | short    | Instrument ID.                                                                              |
| `base+0x04` | byte     | Note.                                                                                       |
| `base+0x05` | byte     | Note velocity.                                                                              |
| `base+0x06` | short    | Note duration.                                                                              |
