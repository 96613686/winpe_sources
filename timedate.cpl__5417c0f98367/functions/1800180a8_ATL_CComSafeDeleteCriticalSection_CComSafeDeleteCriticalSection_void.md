# ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)

- ea: `0x1800180a8`
- end: `0x1800180c1`
- name: `??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `25`
- prototype: `void __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180018068`
- `0x1800180ec`

## callees

- `0x1800180a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800180b6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800180b6`

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
0x1800180a8  sub     rsp, 28h
0x1800180ac  cmp     byte ptr [rcx+28h], 0
0x1800180b0  jz      short loc_1800180BC
0x1800180b2  mov     byte ptr [rcx+28h], 0
0x1800180b6  call    cs:__imp_DeleteCriticalSection
0x1800180bc  add     rsp, 28h
0x1800180c0  retn
```
