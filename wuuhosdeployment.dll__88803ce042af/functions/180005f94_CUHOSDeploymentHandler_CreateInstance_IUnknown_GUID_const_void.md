# CUHOSDeploymentHandler::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180005f94`
- end: `0x180006044`
- name: `?CreateInstance@CUHOSDeploymentHandler@@SAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `176`
- prototype: `__int64 __fastcall(struct IUnknown *, const struct _GUID *, CUHOSDeploymentHandler **)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180005e80`
- `0x180005ef0`

## callees

- `0x180005f94`
- `0x1800169dc`
- `0x180049260`
- `0x1800492e0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005fc6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005fc6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005fb5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005fb5`

## pseudocode

```c

```
