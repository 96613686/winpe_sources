# BiGetDeviceFromEfiPath

- ea: `0x18006ea68`
- end: `0x18006ec64`
- name: `BiGetDeviceFromEfiPath`
- size: `508`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18006dc50`

## callees

- `0x180003c78`
- `0x180004829`
- `0x18006b964`
- `0x18006ea68`
- `0x18006f578`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18006eafd`
- `ntdll!RtlAllocateHeap` at `0x18006eb7e`
- `ntdll!RtlAllocateHeap` at `0x18006eafd`
- `ntdll!RtlAllocateHeap` at `0x18006eb7e`
- `ntdll!RtlFreeHeap` at `0x18006ebfa`
- `ntdll!RtlFreeHeap` at `0x18006ec1d`
- `ntdll!RtlFreeHeap` at `0x18006ec40`
- `ntdll!RtlFreeHeap` at `0x18006ebfa`
- `ntdll!RtlFreeHeap` at `0x18006ec1d`
- `ntdll!RtlFreeHeap` at `0x18006ec40`

## string_xrefs

- `0x18006ebd2`: `BiGetDeviceFromEfiPath failed: %x`

## pseudocode

```c

```
