# VhdmpFindAdapter

- ea: `0x1400b8410`
- end: `0x1400b86b4`
- name: `VhdmpFindAdapter`
- size: `676`
- prototype: `__int64 __usercall@<rax>(struct _VHD_ADAPTER_EXTENSION *@<rcx>, char *Str1, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x14001f560`
- `0x140026800`
- `0x14005dd00`
- `0x1400b65b8`
- `0x1400b71a0`
- `0x1400b7b38`
- `0x1400b8410`

## import_xrefs

- `ntoskrnl!KeSetCoalescableTimer` at `0x1400b8603`
- `ntoskrnl!KeSetCoalescableTimer` at `0x1400b8603`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400b84c1`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400b84c1`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1400b85ca`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1400b85ca`
- `ntoskrnl!_strnicmp` at `0x1400b844c`
- `ntoskrnl!_strnicmp` at `0x1400b844c`
- `ntoskrnl!KeInitializeTimer` at `0x1400b856b`
- `ntoskrnl!KeInitializeTimer` at `0x1400b856b`
- `ntoskrnl!KeInitializeDpc` at `0x1400b858f`
- `ntoskrnl!KeInitializeDpc` at `0x1400b858f`
- `storport!StorPortExtendedFunction` at `0x1400b84ad`
- `storport!StorPortExtendedFunction` at `0x1400b84ad`

## pseudocode

```c

```
