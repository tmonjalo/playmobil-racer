Bluetooth name starts with `PM-RC `.

All values below are in hexadecimal.

The PM-RC protocol is just sending a BLE message
for a write operation (opcode `52`) of a 3-byte message on the handle `0019`,
identified as BLE characteristic `06d1e5e7-79ad-4a71-8faa-373789f7d93c`.

The data frame bytes are `XX YY 0f`, where commands and values are:

  XX commands   |  YY values
  ------------  |  ---------
  `23` - motor  |  `00` (max backward) to `7f` (stop) to `ff` (max forward)
  `24` - light  |  `01` (off), `02` (on)
  `25` - speed  |  `01` to `05`
  `40` - turn   |  `00` (max left) to `7f` (straight) to `ff` (max right)
