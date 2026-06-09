# CRegKey::SetValueQword(ushort const *,unsigned __int64)

- ea: `0x18000f310`
- end: `0x18000f349`
- name: `?SetValueQword@CRegKey@@QEAAKPEBG_K@Z`
- size: `57`
- prototype: `unsigned int __fastcall(CRegKey *__hidden this, const unsigned __int16 *, unsigned __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18000f337`
- `ADVAPI32!RegSetValueExW` at `0x18000f337`

## pseudocode

```c
LSTATUS __fastcall CRegKey::SetValueQword(HKEY *this, const unsigned __int16 *a2, __int64 a3)
{
  __int64 Data; // [rsp+50h] [rbp+18h] BYREF

  Data = a3;
  return RegSetValueExW(*this, a2, 0, 0xBu, (const BYTE *)&Data, 8u);
}

```

## disassembly

```asm
0x18000f310  mov     [rsp+Data], r8
0x18000f315  sub     rsp, 38h
0x18000f319  mov     rcx, [rcx]; hKey
0x18000f31c  lea     rax, [rsp+38h+Data]
0x18000f321  mov     [rsp+38h+cbData], 8; cbData
0x18000f329  mov     r9d, 0Bh; dwType
0x18000f32f  xor     r8d, r8d; Reserved
0x18000f332  mov     [rsp+38h+lpData], rax; lpData
0x18000f337  call    cs:__imp_RegSetValueExW
0x18000f33e  nop     dword ptr [rax+rax+00h]
0x18000f343  add     rsp, 38h
0x18000f347  retn
```
