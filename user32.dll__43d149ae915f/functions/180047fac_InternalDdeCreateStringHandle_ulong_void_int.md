# InternalDdeCreateStringHandle(ulong,void *,int)

- ea: `0x180047fac`
- end: `0x18004805f`
- name: `?InternalDdeCreateStringHandle@@YAPEAUHSZ__@@KPEAXH@Z`
- size: `179`
- prototype: `HSZ(unsigned int, void *, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180047f90`
- `0x18007ff50`

## callees

- `0x180047fac`
- `0x18004812c`
- `0x1800483d4`
- `0x1800882ec`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x180047fcd`
- `ntdll!RtlEnterCriticalSection` at `0x180047fcd`
- `ntdll!RtlLeaveCriticalSection` at `0x18004800d`
- `ntdll!RtlLeaveCriticalSection` at `0x18004800d`
- `api-ms-win-core-atoms-l1-1-0!AddAtomW` at `0x180047ff4`
- `api-ms-win-core-atoms-l1-1-0!AddAtomW` at `0x180047ff4`
- `api-ms-win-core-atoms-l1-1-0!AddAtomA` at `0x18004803f`
- `api-ms-win-core-atoms-l1-1-0!AddAtomA` at `0x18004803f`

## pseudocode

```c

```
