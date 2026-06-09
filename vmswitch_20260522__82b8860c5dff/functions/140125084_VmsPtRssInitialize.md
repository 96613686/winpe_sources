# VmsPtRssInitialize

- ea: `0x140125084`
- end: `0x1401254f2`
- name: `VmsPtRssInitialize`
- size: `1134`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x140117f40`

## callees

- `0x140027a64`
- `0x14002d424`
- `0x14006b084`
- `0x14006e100`
- `0x1400772fc`
- `0x14008497c`
- `0x140125084`
- `0x1401330f4`
- `0x1401405dc`
- `0x1401458f0`
- `0x1401b16a8`
- `0x1401b18b0`
- `0x1401bbfc0`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x1401254d4`
- `ntoskrnl!KeReleaseMutex` at `0x1401254d4`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401250de`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401250de`
- `NDIS!NdisReleaseRWLock` at `0x14012528e`
- `NDIS!NdisReleaseRWLock` at `0x1401252bb`
- `NDIS!NdisReleaseRWLock` at `0x14012534f`
- `NDIS!NdisReleaseRWLock` at `0x14012528e`
- `NDIS!NdisReleaseRWLock` at `0x1401252bb`
- `NDIS!NdisReleaseRWLock` at `0x14012534f`

## string_xrefs

- `0x140125143`: `PtNic->HostRssConfig.IsHashReady == FALSE`
- `0x1401250ea`: `PtNic->HostRssConfig.IsHashContextInitialized`
- `0x1401253a3`: `PtNic->HostRssConfig.IsHashContextInitialized`
- `0x140125250`: `(independentHostSpreading == FALSE) || PtNic->HostRssConfig.IsHashReady`
- `0x14012530f`: `(independentHostSpreading == FALSE) || PtNic->HostRssConfig.IsHashReady`

## pseudocode

```c

```
