# VmsNblHelperCompleteNbls

- ea: `0x140018fb4`
- end: `0x140019557`
- name: `VmsNblHelperCompleteNbls`
- size: `1443`
- prototype: `__int64 __fastcall(PNET_BUFFER_LIST NetBufferList)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140018558`

## callees

- `0x14001736c`
- `0x140017410`
- `0x140018558`
- `0x140018fb4`
- `0x140027a64`
- `0x140047e40`
- `0x14008497c`
- `0x1400a1fd8`
- `0x1401b9750`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14001922d`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14001922d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400193ea`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400193ea`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400193d3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400193d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019212`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019400`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019212`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019400`
- `NDIS!NdisFreeFragmentNetBufferList` at `0x140019493`
- `NDIS!NdisFreeFragmentNetBufferList` at `0x140019493`
- `NDIS!NdisFreeCloneNetBufferList` at `0x1400192f7`
- `NDIS!NdisFreeCloneNetBufferList` at `0x1400192f7`
- `NDIS!NdisAdvanceNetBufferListDataStart` at `0x140019546`
- `NDIS!NdisAdvanceNetBufferListDataStart` at `0x140019546`

## string_xrefs

- `0x140018fca`: `VmsNblHelperCompleteNbls`
- `0x14001925c`: `VmsNblHelperCompleteNbls`

## pseudocode

```c

```
