# Smb2SelectCommonCipherForConnection

- ea: `0x14002484c`
- end: `0x140024c79`
- name: `Smb2SelectCommonCipherForConnection`
- size: `1069`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140090290`

## callees

- `0x1400222ec`
- `0x140022958`
- `0x1400243b4`
- `0x14002484c`
- `0x140024e34`
- `0x140024ee0`
- `0x140038490`
- `0x140038680`
- `0x140059c50`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140024921`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140024921`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140024962`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140024962`
- `srvnet!SmbCryptoAllocateAndPopulateCipherSuiteOrder` at `0x140024a67`
- `srvnet!SmbCryptoAllocateAndPopulateCipherSuiteOrder` at `0x140024b3f`
- `srvnet!SmbCryptoAllocateAndPopulateCipherSuiteOrder` at `0x140024a67`
- `srvnet!SmbCryptoAllocateAndPopulateCipherSuiteOrder` at `0x140024b3f`
- `srvnet!SmbCryptoFreeCipherSuiteOrderBuffer` at `0x140024c34`
- `srvnet!SmbCryptoFreeCipherSuiteOrderBuffer` at `0x140024c49`
- `srvnet!SmbCryptoFreeCipherSuiteOrderBuffer` at `0x140024c34`
- `srvnet!SmbCryptoFreeCipherSuiteOrderBuffer` at `0x140024c49`

## pseudocode

```c

```
