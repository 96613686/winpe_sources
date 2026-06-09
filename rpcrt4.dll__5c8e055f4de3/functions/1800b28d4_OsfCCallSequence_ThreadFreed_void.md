# OsfCCallSequence::ThreadFreed(void)

- ea: `0x1800b28d4`
- end: `0x1800b2927`
- name: `?ThreadFreed@OsfCCallSequence@@QEAAXXZ`
- size: `83`
- prototype: `void __fastcall(OsfCCallSequence *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001d750`
- `0x18004abb4`

## callees

- `0x1800ab4bc`
- `0x1800b28d4`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x1800b28fc`
- `ntdll!RtlLeaveCriticalSection` at `0x1800b2916`
- `ntdll!RtlLeaveCriticalSection` at `0x1800b28fc`
- `ntdll!RtlLeaveCriticalSection` at `0x1800b2916`
- `ntdll!RtlEnterCriticalSection` at `0x1800b28e8`
- `ntdll!RtlEnterCriticalSection` at `0x1800b28e8`

## pseudocode

```c

```
