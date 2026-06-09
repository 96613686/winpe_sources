# SymCryptIntCreate

- ea: `0x180025514`
- end: `0x18002554d`
- name: `SymCryptIntCreate`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18004f740`

## callees

- `0x180025514`
- `0x18002c2e0`

## pseudocode

```c
_DWORD *__fastcall SymCryptIntCreate(__int64 a1, __int64 a2, unsigned int a3)
{
  unsigned int v3; // eax
  unsigned __int64 v4; // rdx
  int v5; // r8d
  _DWORD *v6; // r9
  _DWORD *v7; // r10

  v3 = SymCryptFdefSizeofIntFromDigits(a3);
  if ( v3 && v4 >= v3 )
  {
    v7 = v6;
    *v6 = 1732837376;
    v6[1] = v5;
    v6[2] = v3;
  }
  return v7;
}

```

## disassembly

```asm
0x180025514  sub     rsp, 28h
0x180025518  mov     r9, rcx
0x18002551b  xor     r10d, r10d
0x18002551e  mov     ecx, r8d
0x180025521  call    SymCryptFdefSizeofIntFromDigits
0x180025526  mov     r11d, eax
0x180025529  test    eax, eax
0x18002552b  jz      short loc_180025544
0x18002552d  cmp     rdx, r11
0x180025530  jb      short loc_180025544
0x180025532  mov     r10, r9
0x180025535  mov     dword ptr [r9], 67490000h
0x18002553c  mov     [r9+4], r8d
0x180025540  mov     [r9+8], r11d
0x180025544  mov     rax, r10
0x180025547  add     rsp, 28h
0x18002554b  retn
```
