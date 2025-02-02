# dotBYS
BreathCare device data format parser

## File format
* `00-33`: `0x34 (52)` bytes header
* `34-EOF`: 10 bytes long data chunks
* `34-3d`: first chunk, each chunk covers 60 seconds (1 minute)

## Header format
* `1e-2d`: SN
* `2e-2f`: number of data chunks (10 bytes each), big endian 16 bits

## Chunk format
Most of the bytes are zero, they might be used by some other type of machine, but mine
only uses 3 bytes (what I've found so far).
* `0x00` - not used
* `0x01` - not used
* `0x02` - not used
* `0x03` - not used
* `0x04` - not used
* `0x05` - flags, `0x01` is probably AI, don't know about HI, most probably `0x02` but not confirmed
* `0x06` - not used
* `0x07` - not used
* `0x08` - leakage - so far I expect a linear mapping from 0-255 range to 0-100 l/m could be sufficient
* `0x09` - pressure - same as leakage, linear mapping from 0-255 range to 0-20 cmH2O should do the trick

