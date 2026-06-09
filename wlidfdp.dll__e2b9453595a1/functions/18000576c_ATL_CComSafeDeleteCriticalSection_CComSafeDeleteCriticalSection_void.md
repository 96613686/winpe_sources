# ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)

- ea: `0x18000576c`
- end: `0x180005785`
- name: `??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `25`
- prototype: `void __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000548c`
- `0x1800054ac`
- `0x18000579c`

## callees

- `0x18000576c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000577a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000577a`

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
0x18000576c  sub     rsp, 28h
0x180005770  cmp     byte ptr [rcx+28h], 0
0x180005774  jz      short loc_180005780
0x180005776  mov     byte ptr [rcx+28h], 0
0x18000577a  call    cs:__imp_DeleteCriticalSection
0x180005780  add     rsp, 28h
0x180005784  retn
```
