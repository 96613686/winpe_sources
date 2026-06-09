# ATL::CComAutoCriticalSection::~CComAutoCriticalSection(void)

- ea: `0x18000353c`
- end: `0x180003543`
- name: `??1CComAutoCriticalSection@ATL@@QEAA@XZ`
- size: `7`
- prototype: `void __stdcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18002ecb4`
- `0x18002ece0`
- `0x18002ed5a`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000353c`

## pseudocode

```c
// attributes: thunk
void __stdcall ATL::CComAutoCriticalSection::~CComAutoCriticalSection(LPCRITICAL_SECTION lpCriticalSection)
{
  DeleteCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x18000353c  jmp     cs:__imp_DeleteCriticalSection
```
