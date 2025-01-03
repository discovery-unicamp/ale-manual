## Canvas

| **Address**                         | **Size** | **Description**                                                                                                                                                         |
| :---------------------------------- | :------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `base+0x00`                         | byte     | Storing `1` triggers the canvas to write an array of up to 504 bytes representing up to 126 pixels to the screen. The register is set to `0` when writing is completed. |
| `base+0x02`                         | half     | Array size (in bytes).                                                                                                                                                  |
| `base+0x04`                         | word     | The initial position to write the array on the canvas. The canvas is represented as a 512x512x4-byte one-dimensional array representing 512x512 pixels.                 |
| `base+0x08`</br>to</br>`base+0x200` | word     | 504-byte array representing up to 126 pixels. Each pixel takes 4 bytes, one byte for each value: Red, Green, Blue, and Alpha (in this order).                           |
