# ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)

- ea: `0x18000354c`
- end: `0x180003565`
- name: `??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `25`
- prototype: `void __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `15`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002fd0`
- `0x1800033d8`
- `0x18000341c`
- `0x18000343c`
- `0x1800034d8`
- `0x1800035b0`
- `0x180003620`
- `0x180003674`
- `0x18000d130`
- `0x18000d180`
- `0x180011fe0`
- `0x180012610`
- `0x1800134f4`
- `0x180013bb4`
- `0x1800140c0`

## callees

- `0x18000354c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000355a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000355a`

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
0x18000354c  sub     rsp, 28h
0x180003550  cmp     byte ptr [rcx+28h], 0
0x180003554  jz      short loc_180003560
0x180003556  mov     byte ptr [rcx+28h], 0
0x18000355a  call    cs:__imp_DeleteCriticalSection
0x180003560  add     rsp, 28h
0x180003564  retn
```
