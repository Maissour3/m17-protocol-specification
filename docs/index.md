# M17 Open Digital Radio Protocol Specification

The M17 standard is an open-source, patent-free digital radio communications protocol designed for amateur radio operators and emergency response telemetry. Unlike legacy proprietary commercial formats, M17 provides transparent voice encoding, flexible packet framing, and cryptographic authentication.

## Physical Layer Modulation

M17 utilizes 4-level Frequency Shift Keying (4FSK) modulation at a symbol rate of 4800 symbols per second, resulting in a raw data throughput of 9600 bits per second within a 12.5 kHz channel bandwidth allocation.

```
Symbol Mapping (4FSK):
+3 -> +2.4 kHz deviation (Bits 01)
+1 -> +0.8 kHz deviation (Bits 00)
-1 -> -0.8 kHz deviation (Bits 10)
-3 -> -2.4 kHz deviation (Bits 11)
```

## Key Specifications

- **Channel Bandwidth:** 12.5 kHz channel spacing
- **Voice Codec:** Codec2 open-source speech synthesizer (3200 bps / 1600 bps modes)
- **Error Correction:** Convolutional encoding and Golay(24,12) block error coding
- **Preamble Sync:** 40-symbol synchronization word for deterministic carrier acquisition
