# cxl::OrderedLock<201>::~OrderedLock<201>(void)

- ea: `0x18000cde8`
- end: `0x18000cdef`
- name: `??1?$OrderedLock@$0MJ@@cxl@@QEAA@XZ`
- size: `7`
- prototype: `void __stdcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x18000ceb4`
- `0x18000dcdc`
- `0x1800576a0`
- `0x1800844e1`
- `0x18008459f`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000cde8`

## pseudocode

```c
// attributes: thunk
void __stdcall cxl::OrderedLock<201>::~OrderedLock<201>(LPCRITICAL_SECTION lpCriticalSection)
{
  DeleteCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x18000cde8  jmp     cs:__imp_DeleteCriticalSection
```
