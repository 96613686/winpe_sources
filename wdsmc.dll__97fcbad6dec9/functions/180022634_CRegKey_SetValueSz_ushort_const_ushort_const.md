# CRegKey::SetValueSz(ushort const *,ushort const *)

- ea: `0x180022634`
- end: `0x18002266e`
- name: `?SetValueSz@CRegKey@@QEAAKPEBG0@Z`
- size: `58`
- prototype: `unsigned int(CRegKey *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18001acc8`

## callees

- `0x180022634`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x180022663`
- `ADVAPI32!RegSetValueExW` at `0x180022663`

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
0x180022634  sub     rsp, 38h
0x180022638  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002263c  inc     rax
0x18002263f  cmp     word ptr [r8+rax*2], 0
0x180022645  jnz     short loc_18002263C
0x180022647  mov     rcx, [rcx]; hKey
0x18002264a  lea     eax, ds:2[rax*2]
0x180022651  mov     [rsp+38h+cbData], eax; cbData
0x180022655  mov     r9d, 1; dwType
0x18002265b  mov     [rsp+38h+lpData], r8; lpData
0x180022660  xor     r8d, r8d; Reserved
0x180022663  call    cs:__imp_RegSetValueExW
0x180022669  add     rsp, 38h
0x18002266d  retn
```
