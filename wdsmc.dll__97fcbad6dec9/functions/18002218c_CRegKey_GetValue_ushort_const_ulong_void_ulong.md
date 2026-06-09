# CRegKey::GetValue(ushort const *,ulong,void *,ulong)

- ea: `0x18002218c`
- end: `0x1800221ce`
- name: `?GetValue@CRegKey@@QEAAKPEBGKPEAXK@Z`
- size: `66`
- prototype: `unsigned int __fastcall(CRegKey *__hidden this, const unsigned __int16 *, unsigned int, void *, unsigned int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180001110`
- `0x18001b118`
- `0x1800221d4`
- `0x180022210`
- `0x180022328`
- `0x180022a34`

## callees

- `0x18002218c`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x1800221b2`
- `ADVAPI32!RegQueryValueExW` at `0x1800221b2`

## pseudocode

```c
LSTATUS __fastcall CRegKey::GetValue(HKEY *this, const unsigned __int16 *a2, int a3, BYTE *a4, unsigned int a5)
{
  HKEY v5; // rcx
  LSTATUS result; // eax
  DWORD v8; // [rsp+40h] [rbp+8h] BYREF

  v5 = *this;
  v8 = 0;
  result = RegQueryValueExW(v5, a2, 0, &v8, a4, &a5);
  if ( !result && v8 != a3 )
    return 1804;
  return result;
}

```

## disassembly

```asm
0x18002218c  mov     r11, rsp
0x18002218f  push    rbx
0x180022190  sub     rsp, 30h
0x180022194  mov     rcx, [rcx]; hKey
0x180022197  lea     rax, [r11+28h]
0x18002219b  and     [rsp+38h+arg_0], 0
0x1800221a0  mov     ebx, r8d
0x1800221a3  mov     [r11-10h], rax
0x1800221a7  xor     r8d, r8d; lpReserved
0x1800221aa  mov     [r11-18h], r9
0x1800221ae  lea     r9, [r11+8]; lpType
0x1800221b2  call    cs:__imp_RegQueryValueExW
0x1800221b8  test    eax, eax
0x1800221ba  jnz     short loc_1800221C8
0x1800221bc  cmp     [rsp+38h+arg_0], ebx
0x1800221c0  mov     ecx, 70Ch
0x1800221c5  cmovnz  eax, ecx
0x1800221c8  add     rsp, 30h
0x1800221cc  pop     rbx
0x1800221cd  retn
```
