# CRegKey::SetValueDword(ushort const *,ulong)

- ea: `0x18000fc70`
- end: `0x18000fca5`
- name: `?SetValueDword@CRegKey@@QEAAKPEBGK@Z`
- size: `53`
- prototype: `unsigned int __fastcall(CRegKey *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x180010bb0`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18000fc93`
- `ADVAPI32!RegSetValueExW` at `0x18000fc93`

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
0x18000fc70  mov     r11, rsp
0x18000fc73  mov     [r11+18h], r8d
0x18000fc77  sub     rsp, 38h
0x18000fc7b  mov     rcx, [rcx]; hKey
0x18000fc7e  lea     rax, [r11+18h]
0x18000fc82  mov     r9d, 4; dwType
0x18000fc88  xor     r8d, r8d; Reserved
0x18000fc8b  mov     [r11-10h], r9d
0x18000fc8f  mov     [r11-18h], rax
0x18000fc93  call    cs:__imp_RegSetValueExW
0x18000fc9a  nop     dword ptr [rax+rax+00h]
0x18000fc9f  add     rsp, 38h
0x18000fca3  retn
```
