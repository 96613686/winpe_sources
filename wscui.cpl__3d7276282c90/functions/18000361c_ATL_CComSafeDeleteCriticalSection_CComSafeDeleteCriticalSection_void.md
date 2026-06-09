# ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)

- ea: `0x18000361c`
- end: `0x180003635`
- name: `??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `25`
- prototype: `void __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800035fc`

## callees

- `0x18000361c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000362a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000362a`

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
0x18000361c  sub     rsp, 28h
0x180003620  cmp     byte ptr [rcx+28h], 0
0x180003624  jz      short loc_180003630
0x180003626  mov     byte ptr [rcx+28h], 0
0x18000362a  call    cs:__imp_DeleteCriticalSection
0x180003630  add     rsp, 28h
0x180003634  retn
```
