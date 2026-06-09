# CXWCriticalSection::~CXWCriticalSection(void)

- ea: `0x18002530c`
- end: `0x180025324`
- name: `??1CXWCriticalSection@@QEAA@XZ`
- size: `24`
- prototype: `void __fastcall(CXWCriticalSection *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800252bc`

## callees

- `0x18002530c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180025319`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180025319`

## pseudocode

```c
void __fastcall CXWCriticalSection::~CXWCriticalSection(CXWCriticalSection *this)
{
  if ( !*(_DWORD *)this )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x18002530c  sub     rsp, 28h
0x180025310  cmp     dword ptr [rcx], 0
0x180025313  jnz     short loc_18002531F
0x180025315  add     rcx, 8; lpCriticalSection
0x180025319  call    cs:__imp_DeleteCriticalSection
0x18002531f  add     rsp, 28h
0x180025323  retn
```
