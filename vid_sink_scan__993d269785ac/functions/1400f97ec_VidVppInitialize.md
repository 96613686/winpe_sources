# VidVppInitialize

- ea: `0x1400f97ec`
- end: `0x1400f9914`
- name: `VidVppInitialize`
- size: `296`
- prototype: `void __fastcall(char *DeferredContext, __int64, int, char, _OWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140098628`

## callees

- `0x140021800`
- `0x140074c48`

## import_xrefs

- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400f98ee`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400f98ee`
- `ntoskrnl!ExRundownCompleted` at `0x1400f98fd`
- `ntoskrnl!ExRundownCompleted` at `0x1400f98fd`
- `ntoskrnl!KeInitializeEvent` at `0x1400f985c`
- `ntoskrnl!KeInitializeEvent` at `0x1400f985c`
- `ntoskrnl!KeInitializeDpc` at `0x1400f9889`
- `ntoskrnl!KeInitializeDpc` at `0x1400f9889`

## pseudocode

```c

```
