# CThreadProtected::~CThreadProtected(void)

- ea: `0x180009ea8`
- end: `0x180009eaf`
- name: `??1CThreadProtected@@QEAA@XZ`
- size: `7`
- prototype: `void __stdcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180010d69`
- `0x180010dd3`
- `0x180010e0d`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009ea8`

## pseudocode

```c
// attributes: thunk
void __stdcall CThreadProtected::~CThreadProtected(LPCRITICAL_SECTION lpCriticalSection)
{
  DeleteCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x180009ea8  jmp     cs:__imp_DeleteCriticalSection
```
