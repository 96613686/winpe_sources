# VhdmpFindAdapter

- ea: `0x1400b8400`
- end: `0x1400b86a4`
- name: `VhdmpFindAdapter`
- size: `676`
- prototype: `__int64 __usercall@<rax>(struct _VHD_ADAPTER_EXTENSION *@<rcx>, char *Str1, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x14001f980`
- `0x140026c20`
- `0x14005e100`
- `0x1400b65b8`
- `0x1400b7188`
- `0x1400b7b20`
- `0x1400b8400`

## import_xrefs

- `ntoskrnl!KeSetCoalescableTimer` at `0x1400b85f3`
- `ntoskrnl!KeSetCoalescableTimer` at `0x1400b85f3`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400b84b1`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400b84b1`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1400b85ba`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1400b85ba`
- `ntoskrnl!_strnicmp` at `0x1400b843c`
- `ntoskrnl!_strnicmp` at `0x1400b843c`
- `ntoskrnl!KeInitializeTimer` at `0x1400b855b`
- `ntoskrnl!KeInitializeTimer` at `0x1400b855b`
- `ntoskrnl!KeInitializeDpc` at `0x1400b857f`
- `ntoskrnl!KeInitializeDpc` at `0x1400b857f`
- `storport!StorPortExtendedFunction` at `0x1400b849d`
- `storport!StorPortExtendedFunction` at `0x1400b849d`

## pseudocode

```c

```
