# SymCryptFdefDivisorCreate

- ea: `0x18002c0f4`
- end: `0x18002c154`
- name: `SymCryptFdefDivisorCreate`
- size: `96`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180023390`
- `0x180028790`
- `0x18002bc28`

## callees

- `0x18002c0f4`
- `0x18002c2b8`
- `0x18002c2e0`

## pseudocode

```c
__int64 __fastcall SymCryptFdefDivisorCreate(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v3; // eax
  unsigned __int64 v4; // rdx
  unsigned int v5; // r8d
  _DWORD *v6; // r9
  __int64 v7; // r11
  unsigned int v8; // eax
  __int64 v9; // rdx
  int v10; // r8d
  _DWORD *v11; // r9

  v3 = SymCryptFdefSizeofDivisorFromDigits((unsigned int)a3, a2, a3, a1);
  if ( v3 )
  {
    if ( v4 >= v3 )
    {
      *v6 = 1732509696;
      v6[1] = v5;
      v6[2] = v3;
      v8 = SymCryptFdefSizeofIntFromDigits(v5);
      if ( v8 )
      {
        if ( v9 - 32 >= (unsigned __int64)v8 )
        {
          v11[8] = 1732837376;
          v11[9] = v10;
          v11[10] = v8;
        }
      }
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18002c0f4  sub     rsp, 28h
0x18002c0f8  mov     r9, rcx
0x18002c0fb  xor     r11d, r11d
0x18002c0fe  mov     ecx, r8d
0x18002c101  call    SymCryptFdefSizeofDivisorFromDigits
0x18002c106  mov     r10d, eax
0x18002c109  test    eax, eax
0x18002c10b  jz      short loc_18002C14B
0x18002c10d  cmp     rdx, r10
0x18002c110  jb      short loc_18002C14B
0x18002c112  mov     ecx, r8d
0x18002c115  mov     dword ptr [r9], 67440000h
0x18002c11c  mov     r11, r9
0x18002c11f  mov     [r9+4], r8d
0x18002c123  mov     [r9+8], r10d
0x18002c127  call    SymCryptFdefSizeofIntFromDigits
0x18002c12c  test    eax, eax
0x18002c12e  jz      short loc_18002C14B
0x18002c130  add     rdx, 0FFFFFFFFFFFFFFE0h
0x18002c134  mov     ecx, eax
0x18002c136  cmp     rdx, rcx
0x18002c139  jb      short loc_18002C14B
0x18002c13b  mov     dword ptr [r9+20h], 67490000h
0x18002c143  mov     [r9+24h], r8d
0x18002c147  mov     [r9+28h], eax
0x18002c14b  mov     rax, r11
0x18002c14e  add     rsp, 28h
0x18002c152  retn
```
