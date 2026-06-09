# ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)

- ea: `0x18003ab04`
- end: `0x18003ab4a`
- name: `?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z`
- size: `70`
- prototype: `int(ATL::CRegKey *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180038990`
- `0x18005b670`
- `0x18005b690`

## callees

- `0x18000ade0`
- `0x18003ab04`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003ab3f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003ab3f`

## pseudocode

```c
LSTATUS __fastcall ATL::CRegKey::SetStringValue(HKEY *this, const unsigned __int16 *a2, const BYTE *lpData, DWORD a4)
{
  __int64 v4; // rax

  if ( !lpData )
    ATL::AtlThrowImpl(-2147467259);
  v4 = -1;
  do
    ++v4;
  while ( *(_WORD *)&lpData[2 * v4] );
  return RegSetValueExW(*this, a2, 0, a4, lpData, 2 * v4 + 2);
}

```

## disassembly

```asm
0x18003ab04  sub     rsp, 38h
0x18003ab08  xor     r10d, r10d
0x18003ab0b  test    r8, r8
0x18003ab0e  jnz     short loc_18003AB1B
0x18003ab10  mov     ecx, 80004005h; int
0x18003ab15  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18003ab1b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003ab1f  inc     rax
0x18003ab22  cmp     [r8+rax*2], r10w
0x18003ab27  jnz     short loc_18003AB1F
0x18003ab29  mov     rcx, [rcx]; hKey
0x18003ab2c  lea     eax, ds:2[rax*2]
0x18003ab33  mov     [rsp+38h+cbData], eax; cbData
0x18003ab37  mov     [rsp+38h+lpData], r8; lpData
0x18003ab3c  xor     r8d, r8d; Reserved
0x18003ab3f  call    cs:__imp_RegSetValueExW
0x18003ab45  add     rsp, 38h
0x18003ab49  retn
```
