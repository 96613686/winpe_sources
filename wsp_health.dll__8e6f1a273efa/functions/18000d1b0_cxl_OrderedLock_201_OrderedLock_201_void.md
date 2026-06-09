# cxl::OrderedLock<201>::~OrderedLock<201>(void)

- ea: `0x18000d1b0`
- end: `0x18000d1b7`
- name: `??1?$OrderedLock@$0MJ@@cxl@@QEAA@XZ`
- size: `7`
- prototype: `void __stdcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x18000d280`
- `0x18000e124`
- `0x180058d98`
- `0x1800868f3`
- `0x1800869b1`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d1b0`

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
0x18000d1b0  jmp     cs:__imp_DeleteCriticalSection
```
