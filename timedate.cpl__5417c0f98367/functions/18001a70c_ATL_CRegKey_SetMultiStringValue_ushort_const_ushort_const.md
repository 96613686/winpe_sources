# ATL::CRegKey::SetMultiStringValue(ushort const *,ushort const *)

- ea: `0x18001a70c`
- end: `0x18001a76f`
- name: `?SetMultiStringValue@CRegKey@ATL@@QEAAJPEBG0@Z`
- size: `99`
- prototype: `int(ATL::CRegKey *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180018528`

## callees

- `0x180018c68`
- `0x18001a70c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001a758`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001a758`

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
0x18001a70c  push    rbx
0x18001a70e  sub     rsp, 30h
0x18001a712  xor     ebx, ebx
0x18001a714  mov     r10, rdx
0x18001a717  mov     r11, rcx
0x18001a71a  test    r8, r8
0x18001a71d  jz      short loc_18001A764
0x18001a71f  mov     r9d, ebx
0x18001a722  mov     rdx, r8
0x18001a725  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001a729  inc     rcx
0x18001a72c  cmp     [rdx+rcx*2], bx
0x18001a730  jnz     short loc_18001A729
0x18001a732  inc     ecx
0x18001a734  lea     rdx, [rdx+rcx*2]
0x18001a738  lea     r9d, [r9+rcx*2]
0x18001a73c  cmp     ecx, 1
0x18001a73f  jnz     short loc_18001A725
0x18001a741  mov     [rsp+38h+cbData], r9d; cbData
0x18001a746  mov     rdx, r10; lpValueName
0x18001a749  mov     [rsp+38h+lpData], r8; lpData
0x18001a74e  lea     r9d, [rcx+6]; dwType
0x18001a752  mov     rcx, [r11]; hKey
0x18001a755  xor     r8d, r8d; Reserved
0x18001a758  call    cs:__imp_RegSetValueExW
0x18001a75e  add     rsp, 30h
0x18001a762  pop     rbx
0x18001a763  retn
0x18001a764  mov     ecx, 80004005h; int
0x18001a769  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
