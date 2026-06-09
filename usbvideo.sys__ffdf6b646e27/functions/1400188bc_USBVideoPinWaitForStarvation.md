# USBVideoPinWaitForStarvation

- ea: `0x1400188bc`
- end: `0x14001898a`
- name: `USBVideoPinWaitForStarvation`
- size: `206`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x14000a928`
- `0x1400149f0`
- `0x140018814`
- `0x14001a50c`
- `0x1400247e0`
- `0x140039650`
- `0x140039cf0`

## callees

- `0x1400188bc`

## import_xrefs

- `ntoskrnl!KeResetEvent` at `0x1400188fb`
- `ntoskrnl!KeResetEvent` at `0x1400188fb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400188dc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400188dc`
- `ntoskrnl!KeWaitForSingleObject` at `0x140018944`
- `ntoskrnl!KeWaitForSingleObject` at `0x140018944`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001890d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001896a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001890d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001896a`

## pseudocode

```c

```
