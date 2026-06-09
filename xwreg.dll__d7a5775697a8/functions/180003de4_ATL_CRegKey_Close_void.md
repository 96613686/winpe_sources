# ATL::CRegKey::Close(void)

- ea: `0x180003de4`
- end: `0x180003e0a`
- name: `?Close@CRegKey@ATL@@QEAAJXZ`
- size: `38`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180002dcc`
- `0x180004cc0`
- `0x180005168`
- `0x1800055a0`

## callees

- `0x180003de4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003df7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003df7`

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
0x180003de4  push    rbx
0x180003de6  sub     rsp, 20h
0x180003dea  mov     rbx, rcx
0x180003ded  xor     eax, eax
0x180003def  mov     rcx, [rcx]; hKey
0x180003df2  test    rcx, rcx
0x180003df5  jz      short loc_180003E04
0x180003df7  call    cs:__imp_RegCloseKey
0x180003dfd  mov     qword ptr [rbx], 0
0x180003e04  add     rsp, 20h
0x180003e08  pop     rbx
0x180003e09  retn
```
