# CRegKey::SetValue(ushort const *,ulong,void const *,ulong)

- ea: `0x18000f080`
- end: `0x18000f0ac`
- name: `?SetValue@CRegKey@@QEAAKPEBGKPEBXK@Z`
- size: `44`
- prototype: `unsigned int(CRegKey *__hidden this, const unsigned __int16 *, unsigned int, const void *, unsigned int)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18000f09a`
- `ADVAPI32!RegSetValueExW` at `0x18000f09a`

## pseudocode

```c
LSTATUS __fastcall CRegKey::SetValue(
        HKEY *this,
        const unsigned __int16 *a2,
        DWORD a3,
        const BYTE *lpData,
        DWORD cbData)
{
  return RegSetValueExW(*this, a2, 0, a3, lpData, cbData);
}

```

## disassembly

```asm
0x18000f080  sub     rsp, 38h
0x18000f084  mov     eax, [rsp+38h+arg_20]
0x18000f088  mov     rcx, [rcx]; hKey
0x18000f08b  mov     [rsp+38h+cbData], eax; cbData
0x18000f08f  mov     [rsp+38h+lpData], r9; lpData
0x18000f094  mov     r9d, r8d; dwType
0x18000f097  xor     r8d, r8d; Reserved
0x18000f09a  call    cs:__imp_RegSetValueExW
0x18000f0a1  nop     dword ptr [rax+rax+00h]
0x18000f0a6  add     rsp, 38h
0x18000f0aa  retn
```
