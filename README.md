# ESP-IDF USB Serial/JTAG RX Fix

This repository contains the `esp_driver_usb_serial_jtag` component copied
from Espressif ESP-IDF v6.1 at upstream commit
`fff9895c82d744c7237be8847347bdd1b07c6643`.

The initial commit is an unmodified upstream baseline. The `main` branch adds
lossless RX backpressure: when the RX ring buffer cannot accept a USB packet,
the driver retains that packet and pauses RX interrupts until the consumer frees
enough space. The public driver API is unchanged.

The upstream Apache-2.0 license is included in `LICENSE`; original source-file
license notices are preserved.
