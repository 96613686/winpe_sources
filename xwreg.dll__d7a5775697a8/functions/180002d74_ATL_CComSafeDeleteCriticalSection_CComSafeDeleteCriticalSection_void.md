# ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)

- ea: `0x180002d74`
- end: `0x180002d8d`
- name: `??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `25`
- prototype: `void __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `8`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002b74`
- `0x180002bb8`
- `0x180002bfc`
- `0x180002c68`
- `0x180002cac`
- `0x180002cf0`
- `0x180002d34`
- `0x180002dd8`

## callees

- `0x180002d74`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002d82`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002d82`

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
0x180002d74  sub     rsp, 28h
0x180002d78  cmp     byte ptr [rcx+28h], 0
0x180002d7c  jz      short loc_180002D88
0x180002d7e  mov     byte ptr [rcx+28h], 0
0x180002d82  call    cs:__imp_DeleteCriticalSection
0x180002d88  add     rsp, 28h
0x180002d8c  retn
```
