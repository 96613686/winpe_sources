# ATL::CRegKey::SetMultiStringValue(ushort const *,ushort const *)

- ea: `0x180007f84`
- end: `0x180007fe7`
- name: `?SetMultiStringValue@CRegKey@ATL@@QEAAJPEBG0@Z`
- size: `99`
- prototype: `int(ATL::CRegKey *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180005e28`

## callees

- `0x1800068ec`
- `0x180007f84`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180007fdb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180007fdb`

## pseudocode

```c
LSTATUS __fastcall ATL::CRegKey::SetMultiStringValue(HKEY *this, const unsigned __int16 *a2, const BYTE *lpData)
{
  DWORD cbData; // r9d
  const BYTE *v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // rcx

  if ( !lpData )
    ATL::AtlThrowImpl(-2147467259);
  cbData = 0;
  v6 = lpData;
  do
  {
    v7 = -1;
    do
      ++v7;
    while ( *(_WORD *)&v6[2 * v7] );
    v8 = (unsigned int)(v7 + 1);
    v6 += 2 * v8;
    cbData += 2 * v8;
  }
  while ( (_DWORD)v8 != 1 );
  return RegSetValueExW(*this, a2, 0, 7u, lpData, cbData);
}

```

## disassembly

```asm
0x180007f84  push    rbx
0x180007f86  sub     rsp, 30h
0x180007f8a  xor     ebx, ebx
0x180007f8c  mov     r10, rdx
0x180007f8f  mov     r11, rcx
0x180007f92  test    r8, r8
0x180007f95  jnz     short loc_180007FA2
0x180007f97  mov     ecx, 80004005h; int
0x180007f9c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180007fa2  mov     r9d, ebx
0x180007fa5  mov     rdx, r8
0x180007fa8  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180007fac  inc     rcx
0x180007faf  cmp     [rdx+rcx*2], bx
0x180007fb3  jnz     short loc_180007FAC
0x180007fb5  inc     ecx
0x180007fb7  lea     rdx, [rdx+rcx*2]
0x180007fbb  lea     r9d, [r9+rcx*2]
0x180007fbf  cmp     ecx, 1
0x180007fc2  jnz     short loc_180007FA8
0x180007fc4  mov     [rsp+38h+cbData], r9d; cbData
0x180007fc9  mov     rdx, r10; lpValueName
0x180007fcc  mov     [rsp+38h+lpData], r8; lpData
0x180007fd1  lea     r9d, [rcx+6]; dwType
0x180007fd5  mov     rcx, [r11]; hKey
0x180007fd8  xor     r8d, r8d; Reserved
0x180007fdb  call    cs:__imp_RegSetValueExW
0x180007fe1  add     rsp, 30h
0x180007fe5  pop     rbx
0x180007fe6  retn
```
