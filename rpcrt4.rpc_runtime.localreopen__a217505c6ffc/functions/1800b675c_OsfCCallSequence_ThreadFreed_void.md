# OsfCCallSequence::ThreadFreed(void)

- ea: `0x1800b675c`
- end: `0x1800b67c2`
- name: `?ThreadFreed@OsfCCallSequence@@QEAAXXZ`
- size: `102`
- prototype: `void __fastcall(OsfCCallSequence *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001e7d0`
- `0x18005cfb0`

## callees

- `0x1800aeeb8`
- `0x1800b675c`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x1800b678a`
- `ntdll!RtlLeaveCriticalSection` at `0x1800b67aa`
- `ntdll!RtlLeaveCriticalSection` at `0x1800b678a`
- `ntdll!RtlLeaveCriticalSection` at `0x1800b67aa`
- `ntdll!RtlEnterCriticalSection` at `0x1800b6770`
- `ntdll!RtlEnterCriticalSection` at `0x1800b6770`

## pseudocode

```c

```
