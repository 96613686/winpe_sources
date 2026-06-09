# ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)

- ea: `0x180024cf0`
- end: `0x180024d09`
- name: `??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `25`
- prototype: `void __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `11`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180024c80`
- `0x180024d84`
- `0x180024dac`
- `0x18002d18c`
- `0x18002fe74`
- `0x180030de0`
- `0x180032104`
- `0x180033ea0`
- `0x180037080`
- `0x180037d78`
- `0x180040898`

## callees

- `0x180024cf0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180024cfe`
- `KERNEL32!DeleteCriticalSection` at `0x180024cfe`

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
0x180024cf0  sub     rsp, 28h
0x180024cf4  cmp     byte ptr [rcx+28h], 0
0x180024cf8  jz      short loc_180024D04
0x180024cfa  mov     byte ptr [rcx+28h], 0
0x180024cfe  call    cs:__imp_DeleteCriticalSection
0x180024d04  add     rsp, 28h
0x180024d08  retn
```
