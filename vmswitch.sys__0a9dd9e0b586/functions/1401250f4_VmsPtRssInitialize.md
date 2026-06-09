# VmsPtRssInitialize

- ea: `0x1401250f4`
- end: `0x140125562`
- name: `VmsPtRssInitialize`
- size: `1134`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x140117fb0`

## callees

- `0x140027a64`
- `0x14002d424`
- `0x14006b084`
- `0x14006e100`
- `0x1400772fc`
- `0x14008497c`
- `0x1401250f4`
- `0x140133164`
- `0x14014064c`
- `0x140145960`
- `0x1401b1718`
- `0x1401b1920`
- `0x1401bc040`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x140125544`
- `ntoskrnl!KeReleaseMutex` at `0x140125544`
- `ntoskrnl!KeWaitForSingleObject` at `0x14012514e`
- `ntoskrnl!KeWaitForSingleObject` at `0x14012514e`
- `NDIS!NdisReleaseRWLock` at `0x1401252fe`
- `NDIS!NdisReleaseRWLock` at `0x14012532b`
- `NDIS!NdisReleaseRWLock` at `0x1401253bf`
- `NDIS!NdisReleaseRWLock` at `0x1401252fe`
- `NDIS!NdisReleaseRWLock` at `0x14012532b`
- `NDIS!NdisReleaseRWLock` at `0x1401253bf`

## string_xrefs

- `0x1401251b3`: `PtNic->HostRssConfig.IsHashReady == FALSE`
- `0x14012515a`: `PtNic->HostRssConfig.IsHashContextInitialized`
- `0x140125413`: `PtNic->HostRssConfig.IsHashContextInitialized`
- `0x1401252c0`: `(independentHostSpreading == FALSE) || PtNic->HostRssConfig.IsHashReady`
- `0x14012537f`: `(independentHostSpreading == FALSE) || PtNic->HostRssConfig.IsHashReady`

## pseudocode

```c

```
