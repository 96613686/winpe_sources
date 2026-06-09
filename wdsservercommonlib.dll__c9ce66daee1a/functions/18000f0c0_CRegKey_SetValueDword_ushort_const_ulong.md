# CRegKey::SetValueDword(ushort const *,ulong)

- ea: `0x18000f0c0`
- end: `0x18000f0f5`
- name: `?SetValueDword@CRegKey@@QEAAKPEBGK@Z`
- size: `53`
- prototype: `unsigned int __fastcall(CRegKey *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x18000fff0`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18000f0e3`
- `ADVAPI32!RegSetValueExW` at `0x18000f0e3`

## pseudocode

```c
LSTATUS __fastcall CRegKey::SetValueDword(HKEY *this, const unsigned __int16 *a2, int a3)
{
  int v4; // [rsp+50h] [rbp+18h] BYREF

  v4 = a3;
  return RegSetValueExW(*this, a2, 0, 4u, (const BYTE *)&v4, 4u);
}

```

## disassembly

```asm
0x18000f0c0  mov     r11, rsp
0x18000f0c3  mov     [r11+18h], r8d
0x18000f0c7  sub     rsp, 38h
0x18000f0cb  mov     rcx, [rcx]; hKey
0x18000f0ce  lea     rax, [r11+18h]
0x18000f0d2  mov     r9d, 4; dwType
0x18000f0d8  xor     r8d, r8d; Reserved
0x18000f0db  mov     [r11-10h], r9d
0x18000f0df  mov     [r11-18h], rax
0x18000f0e3  call    cs:__imp_RegSetValueExW
0x18000f0ea  nop     dword ptr [rax+rax+00h]
0x18000f0ef  add     rsp, 38h
0x18000f0f3  retn
```
