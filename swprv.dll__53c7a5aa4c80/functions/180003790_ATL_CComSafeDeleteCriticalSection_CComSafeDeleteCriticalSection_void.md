# ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)

- ea: `0x180003790`
- end: `0x1800037a9`
- name: `??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `25`
- prototype: `void __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800036a8`
- `0x1800037b0`
- `0x180008074`
- `0x1800080f8`
- `0x18000dc7c`
- `0x1800176bc`
- `0x180027a2c`

## callees

- `0x180003790`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000379e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000379e`

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
0x180003790  sub     rsp, 28h
0x180003794  cmp     byte ptr [rcx+28h], 0
0x180003798  jz      short loc_1800037A4
0x18000379a  mov     byte ptr [rcx+28h], 0
0x18000379e  call    cs:__imp_DeleteCriticalSection
0x1800037a4  add     rsp, 28h
0x1800037a8  retn
```
