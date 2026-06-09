# ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)

- ea: `0x180003bcc`
- end: `0x180003be5`
- name: `??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `25`
- prototype: `void __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800034ec`
- `0x180003a9c`
- `0x180003b18`
- `0x180003b80`

## callees

- `0x180003bcc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003bda`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003bda`

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
0x180003bcc  sub     rsp, 28h
0x180003bd0  cmp     byte ptr [rcx+28h], 0
0x180003bd4  jz      short loc_180003BE0
0x180003bd6  mov     byte ptr [rcx+28h], 0
0x180003bda  call    cs:__imp_DeleteCriticalSection
0x180003be0  add     rsp, 28h
0x180003be4  retn
```
