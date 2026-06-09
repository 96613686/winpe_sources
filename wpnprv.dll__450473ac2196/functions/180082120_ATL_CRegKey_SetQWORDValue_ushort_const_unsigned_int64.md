# ATL::CRegKey::SetQWORDValue(ushort const *,unsigned __int64)

- ea: `0x180082120`
- end: `0x180082152`
- name: `?SetQWORDValue@CRegKey@ATL@@QEAAJPEBG_K@Z`
- size: `50`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *, unsigned __int64)`
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x1800816a0`
- `0x180082158`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180082147`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180082147`

## pseudocode

```c
LSTATUS __fastcall ATL::CRegKey::SetQWORDValue(HKEY *this, const unsigned __int16 *a2, __int64 a3)
{
  __int64 Data; // [rsp+50h] [rbp+18h] BYREF

  Data = a3;
  return RegSetValueExW(*this, a2, 0, 0xBu, (const BYTE *)&Data, 8u);
}

```

## disassembly

```asm
0x180082120  mov     [rsp+Data], r8
0x180082125  sub     rsp, 38h
0x180082129  mov     rcx, [rcx]; hKey
0x18008212c  lea     rax, [rsp+38h+Data]
0x180082131  mov     [rsp+38h+cbData], 8; cbData
0x180082139  mov     r9d, 0Bh; dwType
0x18008213f  xor     r8d, r8d; Reserved
0x180082142  mov     [rsp+38h+lpData], rax; lpData
0x180082147  call    cs:__imp_RegSetValueExW
0x18008214d  add     rsp, 38h
0x180082151  retn
```
