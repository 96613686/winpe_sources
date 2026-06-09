# ATL::CRegKey::SetMultiStringValue(ushort const *,ushort const *)

- ea: `0x18003aa98`
- end: `0x18003aafb`
- name: `?SetMultiStringValue@CRegKey@ATL@@QEAAJPEBG0@Z`
- size: `99`
- prototype: `int(ATL::CRegKey *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180038990`
- `0x18005b650`

## callees

- `0x18000ade0`
- `0x18003aa98`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003aaef`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003aaef`

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
0x18003aa98  push    rbx
0x18003aa9a  sub     rsp, 30h
0x18003aa9e  xor     ebx, ebx
0x18003aaa0  mov     r10, rdx
0x18003aaa3  mov     r11, rcx
0x18003aaa6  test    r8, r8
0x18003aaa9  jnz     short loc_18003AAB6
0x18003aaab  mov     ecx, 80004005h; int
0x18003aab0  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18003aab6  mov     r9d, ebx
0x18003aab9  mov     rdx, r8
0x18003aabc  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003aac0  inc     rcx
0x18003aac3  cmp     [rdx+rcx*2], bx
0x18003aac7  jnz     short loc_18003AAC0
0x18003aac9  inc     ecx
0x18003aacb  lea     rdx, [rdx+rcx*2]
0x18003aacf  lea     r9d, [r9+rcx*2]
0x18003aad3  cmp     ecx, 1
0x18003aad6  jnz     short loc_18003AABC
0x18003aad8  mov     [rsp+38h+cbData], r9d; cbData
0x18003aadd  mov     rdx, r10; lpValueName
0x18003aae0  mov     [rsp+38h+lpData], r8; lpData
0x18003aae5  lea     r9d, [rcx+6]; dwType
0x18003aae9  mov     rcx, [r11]; hKey
0x18003aaec  xor     r8d, r8d; Reserved
0x18003aaef  call    cs:__imp_RegSetValueExW
0x18003aaf5  add     rsp, 30h
0x18003aaf9  pop     rbx
0x18003aafa  retn
```
