# ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)

- ea: `0x1800175e0`
- end: `0x1800175f9`
- name: `??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `25`
- prototype: `void __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180017600`
- `0x18001a6b0`
- `0x18001a798`

## callees

- `0x1800175e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800175ee`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800175ee`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x1800175e0  sub     rsp, 28h
0x1800175e4  cmp     byte ptr [rcx+28h], 0
0x1800175e8  jz      short loc_1800175F4
0x1800175ea  mov     byte ptr [rcx+28h], 0
0x1800175ee  call    cs:__imp_DeleteCriticalSection
0x1800175f4  add     rsp, 28h
0x1800175f8  retn
```
