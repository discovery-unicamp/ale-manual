## Self Driving Car

| **Address** | **Size**       | **Description**                                                                                                                                              |
| :---------- | :------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `base+0x00` | byte           | Storing `1` triggers the GPS device to start reading the coordinates and rotation of the car. The register is set to `0` when the reading is completed.      |
| `base+0x01` | byte           | Storing `1` triggers the Line Camera device to capture an image. The register is set to `0` when the capture is completed.                                   |
| `base+0x02` | byte           | Storing `1` triggers the Ultrasonic Sensor device to measure the distance in front of the car. The register is set to `0` when the measurement is completed. |
| `base+0x04` | word           | Stores the Euler angle X of the car rotation at the moment of the last reading by the GPS.                                                                   |
| `base+0x08` | word           | Stores the Euler angle Y of the car rotation at the moment of the last reading by the GPS.                                                                   |
| `base+0x0C` | word           | Stores the Euler angle Z of the car rotation at the moment of the last reading by the GPS.                                                                   |
| `base+0x10` | word           | Stores the X-axis of the car position at the moment of the last reading by the GPS.                                                                          |
| `base+0x14` | word           | Stores the Y-axis of the car position at the moment of the last reading by the GPS.                                                                          |
| `base+0x18` | word           | Stores the Z-axis of the car position at the moment of the last reading by the GPS.                                                                          |
| `base+0x1C` | word           | Stores the distance (in centimeters) between the Ultrasonic sensor and the nearest obstacle. Returns `-1` if there’s no obstacle within 20m.                 |
| `base+0x20` | byte           | Sets the steering wheel direction. Negative values indicate steering to the left, positive values indicate steering to the right.                            |
| `base+0x21` | byte           | Sets the engine direction.</br>`1`: forward.</br>`0`: off.</br>`-1`: backward.                                                                               |
| `base+0x22` | byte           | Sets the hand break. (`1` = enabled)                                                                                                                         |
| `base+0x24` | 256-byte array | Stores the image captured by the Line Camera. Each byte represents the luminance of a pixel.                                                                 |
