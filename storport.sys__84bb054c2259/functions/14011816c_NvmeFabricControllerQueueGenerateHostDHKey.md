# NvmeFabricControllerQueueGenerateHostDHKey

- ea: `0x14011816c`
- end: `0x1401184e2`
- name: `NvmeFabricControllerQueueGenerateHostDHKey`
- size: `886`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1401184e8`

## callees

- `0x1400290b0`
- `0x14005285c`
- `0x140102c90`
- `0x140102cc4`
- `0x140102cf4`
- `0x14011816c`
- `0x14014b500`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140118473`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401184b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140118473`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401184b8`
- `ksecdd!BCryptSetProperty` at `0x1401182cc`
- `ksecdd!BCryptSetProperty` at `0x1401182cc`
- `ksecdd!BCryptExportKey` at `0x140118365`
- `ksecdd!BCryptExportKey` at `0x140118365`
- `ksecdd!BCryptGenerateKeyPair` at `0x140118243`
- `ksecdd!BCryptGenerateKeyPair` at `0x140118243`
- `ksecdd!BCryptFinalizeKeyPair` at `0x1401182f0`
- `ksecdd!BCryptFinalizeKeyPair` at `0x1401182f0`
- `ksecdd!BCryptDestroyKey` at `0x140118488`
- `ksecdd!BCryptDestroyKey` at `0x140118488`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x14011849f`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x14011849f`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x140118212`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x140118212`

## string_xrefs

- `0x140118224`: `BCryptOpenAlgorithmProvider`

## pseudocode

```c

```
