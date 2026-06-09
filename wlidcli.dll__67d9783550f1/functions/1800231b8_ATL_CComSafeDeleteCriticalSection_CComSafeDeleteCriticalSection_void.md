# ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)

- ea: `0x1800231b8`
- end: `0x1800231d1`
- name: `??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `25`
- prototype: `void __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180023048`
- `0x180023068`
- `0x180023084`
- `0x1800385e0`

## callees

- `0x1800231b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800231c6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800231c6`

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
0x1800231b8  sub     rsp, 28h
0x1800231bc  cmp     byte ptr [rcx+28h], 0
0x1800231c0  jz      short loc_1800231CC
0x1800231c2  mov     byte ptr [rcx+28h], 0
0x1800231c6  call    cs:__imp_DeleteCriticalSection
0x1800231cc  add     rsp, 28h
0x1800231d0  retn
```
