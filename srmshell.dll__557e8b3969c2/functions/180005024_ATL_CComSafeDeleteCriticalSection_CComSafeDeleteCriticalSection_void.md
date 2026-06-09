# ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)

- ea: `0x180005024`
- end: `0x18000503e`
- name: `??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `26`
- prototype: `void __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001c077`
- `0x18001c0fd`
- `0x18001c10f`
- `0x18001c280`
- `0x18001c7d0`

## callees

- `0x180005024`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005032`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005032`

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
0x180005024  sub     rsp, 28h
0x180005028  cmp     byte ptr [rcx+28h], 0
0x18000502c  jz      short loc_180005039
0x18000502e  mov     byte ptr [rcx+28h], 0
0x180005032  call    cs:__imp_DeleteCriticalSection
0x180005038  nop
0x180005039  add     rsp, 28h
0x18000503d  retn
```
