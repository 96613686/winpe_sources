# wmi::CritSec::~CritSec(void)

- ea: `0x180003c48`
- end: `0x180003c4f`
- name: `??1CritSec@wmi@@QEAA@XZ`
- size: `7`
- prototype: `void __stdcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180020530`
- `0x180020546`
- `0x180020d55`
- `0x180020e63`
- `0x180020f15`
- `0x180020f2b`
- `0x180020f77`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003c48`

## pseudocode

```c
// attributes: thunk
void __stdcall wmi::CritSec::~CritSec(LPCRITICAL_SECTION lpCriticalSection)
{
  DeleteCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x180003c48  jmp     cs:__imp_DeleteCriticalSection
```
