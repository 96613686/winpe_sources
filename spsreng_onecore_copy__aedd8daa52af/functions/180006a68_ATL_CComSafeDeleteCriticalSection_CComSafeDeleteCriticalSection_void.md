# ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)

- ea: `0x180006a68`
- end: `0x180006a81`
- name: `??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `25`
- prototype: `void __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `16`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180014fec`
- `0x180015354`
- `0x180015730`
- `0x180015790`
- `0x1800157e4`
- `0x1800158b0`
- `0x1800158e8`
- `0x1800bba14`
- `0x1800c7308`
- `0x1800c7490`
- `0x1800ce9f8`
- `0x1800da574`
- `0x1800fbe90`
- `0x1800fbee4`
- `0x1800fbf34`
- `0x1800fbf7c`

## callees

- `0x180006a68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006a76`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006a76`

## pseudocode

```c
void __fastcall ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(
        ATL::CComSafeDeleteCriticalSection *this)
{
  if ( *((_BYTE *)this + 40) )
  {
    *((_BYTE *)this + 40) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)this);
  }
}

```

## disassembly

```asm
0x180006a68  sub     rsp, 28h
0x180006a6c  cmp     byte ptr [rcx+28h], 0
0x180006a70  jz      short loc_180006A7C
0x180006a72  mov     byte ptr [rcx+28h], 0
0x180006a76  call    cs:__imp_DeleteCriticalSection
0x180006a7c  add     rsp, 28h
0x180006a80  retn
```
