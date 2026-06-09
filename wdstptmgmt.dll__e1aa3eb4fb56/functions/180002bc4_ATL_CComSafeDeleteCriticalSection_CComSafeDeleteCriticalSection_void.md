# ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)

- ea: `0x180002bc4`
- end: `0x180002be4`
- name: `??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002c34`
- `0x180005f80`
- `0x180005f90`
- `0x1800069e8`
- `0x180007dec`
- `0x180007e0c`
- `0x180009d9c`

## callees

- `0x180002bc4`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180002bd2`
- `KERNEL32!DeleteCriticalSection` at `0x180002bd2`

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
0x180002bc4  sub     rsp, 28h
0x180002bc8  cmp     byte ptr [rcx+28h], 0
0x180002bcc  jz      short loc_180002BDE
0x180002bce  mov     byte ptr [rcx+28h], 0
0x180002bd2  call    cs:__imp_DeleteCriticalSection
0x180002bd9  nop     dword ptr [rax+rax+00h]
0x180002bde  add     rsp, 28h
0x180002be2  retn
```
