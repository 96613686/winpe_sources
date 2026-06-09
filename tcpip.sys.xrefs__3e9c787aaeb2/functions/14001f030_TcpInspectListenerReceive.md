# TcpInspectListenerReceive

- ea: `0x14001f030`
- end: `0x14001f815`
- name: `TcpInspectListenerReceive`
- size: `2021`
- prototype: `__int64 __fastcall(_QWORD *, __int16 *, __int64, _QWORD *, __int64, __int64)`
- caller_count: `2`
- callee_count: `18`
- tags: `authz_impersonation`

## callers

- `0x1400fba9c`
- `0x1400fc7b8`

## callees

- `0x1400121c0`
- `0x14001eee0`
- `0x14001f030`
- `0x14001fdc0`
- `0x1400201e0`
- `0x1400204c0`
- `0x1400205c0`
- `0x1400207f8`
- `0x140030fdc`
- `0x140048f30`
- `0x140049000`
- `0x14005d040`
- `0x1400d272c`
- `0x140154d74`
- `0x1401c0fd0`
- `0x1401c1200`
- `0x1401c1280`
- `0x1401c1580`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14001f695`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14001f695`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001f6e4`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001f6e4`
- `ntoskrnl!PsGetProcessStartKey` at `0x14001f67e`
- `ntoskrnl!PsGetProcessStartKey` at `0x14001f67e`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14001f210`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14001f2ef`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14001f210`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14001f2ef`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x14001f252`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x14001f327`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x14001f252`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x14001f327`
- `ntoskrnl!PsGetProcessId` at `0x14001f66c`
- `ntoskrnl!PsGetProcessId` at `0x14001f66c`
- `NETIO!WfpStreamEndpointCleanupBegin` at `0x14001f7ae`
- `NETIO!WfpStreamEndpointCleanupBegin` at `0x14001f7ae`

## pseudocode

```c

```
