# CRegKey::SetValueExpSz(ushort const *,ushort const *)

- ea: `0x18000f100`
- end: `0x18000f141`
- name: `?SetValueExpSz@CRegKey@@QEAAKPEBG0@Z`
- size: `65`
- prototype: `unsigned int(CRegKey *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000f100`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18000f12f`
- `ADVAPI32!RegSetValueExW` at `0x18000f12f`

## pseudocode

```c
LSTATUS __fastcall CRegKey::SetValueExpSz(HKEY *this, const unsigned __int16 *a2, const BYTE *lpData)
{
  __int64 v3; // rax

  v3 = -1;
  do
    ++v3;
  while ( *(_WORD *)&lpData[2 * v3] );
  return RegSetValueExW(*this, a2, 0, 2u, lpData, 2 * v3 + 2);
}

```

## disassembly

```asm
0x18000f100  sub     rsp, 38h
0x18000f104  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000f108  inc     rax
0x18000f10b  cmp     word ptr [r8+rax*2], 0
0x18000f111  jnz     short loc_18000F108
0x18000f113  mov     rcx, [rcx]; hKey
0x18000f116  lea     eax, ds:2[rax*2]
0x18000f11d  mov     [rsp+38h+cbData], eax; cbData
0x18000f121  mov     r9d, 2; dwType
0x18000f127  mov     [rsp+38h+lpData], r8; lpData
0x18000f12c  xor     r8d, r8d; Reserved
0x18000f12f  call    cs:__imp_RegSetValueExW
0x18000f136  nop     dword ptr [rax+rax+00h]
0x18000f13b  add     rsp, 38h
0x18000f13f  retn
```
