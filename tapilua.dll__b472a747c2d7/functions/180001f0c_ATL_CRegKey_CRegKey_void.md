# ATL::CRegKey::~CRegKey(void)

- ea: `0x180001f0c`
- end: `0x180001f30`
- name: `??1CRegKey@ATL@@QEAA@XZ`
- size: `36`
- prototype: `void __fastcall(HKEY *this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800050ff`
- `0x180005135`
- `0x180005147`

## callees

- `0x180001f0c`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180001f1d`
- `ADVAPI32!RegCloseKey` at `0x180001f1d`

## pseudocode

```c
void __fastcall ATL::CRegKey::~CRegKey(HKEY *this)
{
  HKEY v2; // rcx

  v2 = *this;
  if ( v2 )
  {
    RegCloseKey(v2);
    *this = 0;
  }
}

```

## disassembly

```asm
0x180001f0c  push    rbx
0x180001f0e  sub     rsp, 20h
0x180001f12  mov     rbx, rcx
0x180001f15  mov     rcx, [rcx]; hKey
0x180001f18  test    rcx, rcx
0x180001f1b  jz      short loc_180001F2A
0x180001f1d  call    cs:__imp_RegCloseKey
0x180001f23  mov     qword ptr [rbx], 0
0x180001f2a  add     rsp, 20h
0x180001f2e  pop     rbx
0x180001f2f  retn
```
