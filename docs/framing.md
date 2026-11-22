# Stream Framing & Packet Architecture

M17 data transmissions are divided into 40-millisecond transmission frames. Each frame carries synchronization sequences, link setup payloads, and digitized voice or packet data slices.

## Stream Frame Structure

A complete stream transmission begins with a Link Setup Frame (LSF) establishing sender callsign, destination address, and payload encoding mode, followed by continuous streaming frames.

| Field Name | Bit Width | Function / Purpose |
| :--- | :--- | :--- |
| Synchronization Word | 16 bits | Frame alignment and receiver clock recovery |
| Link Information Channel | 32 bits | Channel metadata and transmission sequence counter |
| Voice Data Payload | 128 bits | Compressed Codec2 digital audio speech frames |
| Forward Error Correction | 64 bits | Punctured convolutional parity bits for error recovery |

## Packet Data Modes

Beyond voice streaming, M17 natively encapsulates AX.25 or IPv6 packet payloads. Packet mode frames encapsulate arbitrary binary telemetry payloads, verifying data integrity using CRC-16-CCITT checksum calculations across packet bodies.
