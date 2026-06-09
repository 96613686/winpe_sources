# ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)

- ea: `0x180018ac0`
- end: `0x180018b0e`
- name: `?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z`
- size: `78`
- prototype: `int(ATL::CRegKey *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180006b4c`
- `0x180018b14`
- `0x18001b420`
- `0x18001b770`
- `0x18001bad0`
- `0x18001be50`

## callees

- `0x18001870c`
- `0x180018ac0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180018afc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180018afc`

## pseudocode

```c
LSTATUS __fastcall ATL::CRegKey::SetStringValue(HKEY *this, const unsigned __int16 *a2, const BYTE *lpData)
{
  __int64 v3; // rax

  if ( !lpData )
    ATL::AtlThrowImpl((int)this);
  v3 = -1;
  do
    ++v3;
  while ( *(_WORD *)&lpData[2 * v3] );
  return RegSetValueExW(*this, a2, 0, 1u, lpData, 2 * v3 + 2);
}

```

## disassembly

```asm
0x180018ac0  sub     rsp, 38h
0x180018ac4  xor     r9d, r9d
0x180018ac7  test    r8, r8
0x180018aca  jnz     short loc_180018AD2
0x180018acc  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180018ad2  or      rax, 0FFFFFFFFFFFFFFFFh
0x180018ad6  inc     rax
0x180018ad9  cmp     [r8+rax*2], r9w
0x180018ade  jnz     short loc_180018AD6
0x180018ae0  mov     rcx, [rcx]; hKey
0x180018ae3  lea     eax, ds:2[rax*2]
0x180018aea  mov     [rsp+38h+cbData], eax; cbData
0x180018aee  mov     r9d, 1; dwType
0x180018af4  mov     [rsp+38h+lpData], r8; lpData
0x180018af9  xor     r8d, r8d; Reserved
0x180018afc  call    cs:__imp_RegSetValueExW
0x180018b03  nop     dword ptr [rax+rax+00h]
0x180018b08  add     rsp, 38h
0x180018b0c  retn
```
