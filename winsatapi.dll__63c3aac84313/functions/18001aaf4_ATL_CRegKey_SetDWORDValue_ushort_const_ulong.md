# ATL::CRegKey::SetDWORDValue(ushort const *,ulong)

- ea: `0x18001aaf4`
- end: `0x18001ab22`
- name: `?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z`
- size: `46`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `5`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x180016224`
- `0x18001ed98`
- `0x18002177c`
- `0x18002bbb8`
- `0x18002be4c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001ab17`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001ab17`

## pseudocode

```c
LSTATUS __fastcall ATL::CRegKey::SetDWORDValue(HKEY *this, const unsigned __int16 *a2, int a3)
{
  int v4; // [rsp+50h] [rbp+18h] BYREF

  v4 = a3;
  return RegSetValueExW(*this, a2, 0, 4u, (const BYTE *)&v4, 4u);
}

```

## disassembly

```asm
0x18001aaf4  mov     r11, rsp
0x18001aaf7  mov     [r11+18h], r8d
0x18001aafb  sub     rsp, 38h
0x18001aaff  mov     rcx, [rcx]; hKey
0x18001ab02  lea     rax, [r11+18h]
0x18001ab06  mov     r9d, 4; dwType
0x18001ab0c  xor     r8d, r8d; Reserved
0x18001ab0f  mov     [r11-10h], r9d
0x18001ab13  mov     [r11-18h], rax
0x18001ab17  call    cs:__imp_RegSetValueExW
0x18001ab1d  add     rsp, 38h
0x18001ab21  retn
```
