# CRegKey::SetValueSz(ushort const *,ushort const *)

- ea: `0x18000f350`
- end: `0x18000f391`
- name: `?SetValueSz@CRegKey@@QEAAKPEBG0@Z`
- size: `65`
- prototype: `unsigned int(CRegKey *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000f350`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18000f37f`
- `ADVAPI32!RegSetValueExW` at `0x18000f37f`

## pseudocode

```c
LSTATUS __fastcall CRegKey::SetValueSz(HKEY *this, const unsigned __int16 *a2, const BYTE *lpData)
{
  __int64 v3; // rax

  v3 = -1;
  do
    ++v3;
  while ( *(_WORD *)&lpData[2 * v3] );
  return RegSetValueExW(*this, a2, 0, 1u, lpData, 2 * v3 + 2);
}

```

## disassembly

```asm
0x18000f350  sub     rsp, 38h
0x18000f354  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000f358  inc     rax
0x18000f35b  cmp     word ptr [r8+rax*2], 0
0x18000f361  jnz     short loc_18000F358
0x18000f363  mov     rcx, [rcx]; hKey
0x18000f366  lea     eax, ds:2[rax*2]
0x18000f36d  mov     [rsp+38h+cbData], eax; cbData
0x18000f371  mov     r9d, 1; dwType
0x18000f377  mov     [rsp+38h+lpData], r8; lpData
0x18000f37c  xor     r8d, r8d; Reserved
0x18000f37f  call    cs:__imp_RegSetValueExW
0x18000f386  nop     dword ptr [rax+rax+00h]
0x18000f38b  add     rsp, 38h
0x18000f38f  retn
```
