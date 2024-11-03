# dotBYS
BreathCare device data format parser

# Format analysis
* `0x34 (52)` bytes header size
* `2e-2f`: number of data chunks (10 bytes each), big endian 16 bits
* `1e-2d`: SN
* `34-3d`: first chunk, each chunk covers 60 seconds (1 minute)

