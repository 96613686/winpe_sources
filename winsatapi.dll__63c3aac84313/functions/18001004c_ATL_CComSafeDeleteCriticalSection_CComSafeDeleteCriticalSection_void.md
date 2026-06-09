# ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)

- ea: `0x18001004c`
- end: `0x180010065`
- name: `??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `25`
- prototype: `void __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `10`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180010004`
- `0x180010014`
- `0x1800157c0`
- `0x180015800`
- `0x180015868`
- `0x1800158bc`
- `0x1800158f0`
- `0x180015928`
- `0x18001d8f0`
- `0x1800203c4`

## callees

- `0x18001004c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001005a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001005a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x18001004c  sub     rsp, 28h
0x180010050  cmp     byte ptr [rcx+28h], 0
0x180010054  jz      short loc_180010060
0x180010056  mov     byte ptr [rcx+28h], 0
0x18001005a  call    cs:__imp_DeleteCriticalSection
0x180010060  add     rsp, 28h
0x180010064  retn
```
