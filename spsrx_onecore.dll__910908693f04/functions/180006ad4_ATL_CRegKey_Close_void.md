# ATL::CRegKey::Close(void)

- ea: `0x180006ad4`
- end: `0x180006afa`
- name: `?Close@CRegKey@ATL@@QEAAJXZ`
- size: `38`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800058ec`
- `0x180006598`
- `0x180006b00`
- `0x1800070c8`
- `0x1800073c8`
- `0x1800078ec`

## callees

- `0x180006ad4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006ae7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006ae7`

## pseudocode

```c
LSTATUS __fastcall ATL::CRegKey::Close(HKEY *this)
{
  LSTATUS result; // eax
  HKEY v3; // rcx

  result = 0;
  v3 = *this;
  if ( v3 )
  {
    result = RegCloseKey(v3);
    *this = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180006ad4  push    rbx
0x180006ad6  sub     rsp, 20h
0x180006ada  mov     rbx, rcx
0x180006add  xor     eax, eax
0x180006adf  mov     rcx, [rcx]; hKey
0x180006ae2  test    rcx, rcx
0x180006ae5  jz      short loc_180006AF4
0x180006ae7  call    cs:__imp_RegCloseKey
0x180006aed  mov     qword ptr [rbx], 0
0x180006af4  add     rsp, 20h
0x180006af8  pop     rbx
0x180006af9  retn
```
