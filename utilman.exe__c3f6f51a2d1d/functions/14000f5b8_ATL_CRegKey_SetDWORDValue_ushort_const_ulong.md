# ATL::CRegKey::SetDWORDValue(ushort const *,ulong)

- ea: `0x14000f5b8`
- end: `0x14000f5ed`
- name: `?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z`
- size: `53`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `3`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x140012f54`
- `0x140015468`
- `0x1400172b0`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x14000f5db`
- `ADVAPI32!RegSetValueExW` at `0x14000f5db`

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
0x14000f5b8  mov     r11, rsp
0x14000f5bb  mov     [r11+18h], r8d
0x14000f5bf  sub     rsp, 38h
0x14000f5c3  mov     rcx, [rcx]; hKey
0x14000f5c6  lea     rax, [r11+18h]
0x14000f5ca  mov     r9d, 4; dwType
0x14000f5d0  xor     r8d, r8d; Reserved
0x14000f5d3  mov     [r11-10h], r9d
0x14000f5d7  mov     [r11-18h], rax
0x14000f5db  call    cs:__imp_RegSetValueExW
0x14000f5e2  nop     dword ptr [rax+rax+00h]
0x14000f5e7  add     rsp, 38h
0x14000f5eb  retn
```
