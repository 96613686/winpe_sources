# WinHvpDepositMemory

- ea: `0x140022e50`
- end: `0x140022f82`
- name: `WinHvpDepositMemory`
- size: `306`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1400048f0`
- `0x140020c00`
- `0x1400228d0`

## callees

- `0x140022e50`
- `0x140022f88`

## pseudocode

```c
__int64 __fastcall WinHvpDepositMemory(int a1, unsigned __int64 a2, int a3, char a4, char a5, _QWORD *a6)
{
  unsigned __int64 v8; // rdi
  __int64 result; // rax
  __int64 v11; // rsi
  unsigned int v12; // edx
  int v13; // ecx
  unsigned int v14; // ebx
  unsigned int v15; // eax
  _QWORD v16[9]; // [rsp+30h] [rbp-48h] BYREF

  v8 = a2;
  if ( WinHvpConnected )
  {
    v11 = 0;
    if ( a2 )
    {
      v12 = 0;
      v13 = WinHvpMmFlags | 0x30;
      if ( !a4 )
        v13 = WinHvpMmFlags;
      v14 = v13 | 0x40;
      if ( (v13 & 0x20) == 0 )
        v14 = v13;
      while ( v8 )
      {
        v16[0] = 0;
        v15 = WinHvpDepositMemoryFromNumaNode(a1, v8, v14, a3 & 0x7FFFFFFF, a5, (__int64)v16);
        v12 = v15;
        v11 += v16[0];
        if ( v16[0] >= v8 )
          goto LABEL_24;
        if ( v15 != -1073741670 )
          break;
        if ( (v14 & 0x70) == 0x70 )
        {
          v14 &= ~0x40u;
        }
        else if ( a4 || (v14 & 0x30) != 0x30 )
        {
          if ( (v14 & 2) == 0 || a3 >= 0 )
          {
            v12 = -1073741670;
            break;
          }
          v14 = WinHvpMmFlags & 0xFFFFFFCD | 0x30;
          if ( !a4 )
            v14 = WinHvpMmFlags & 0xFFFFFFFD;
          if ( (v14 & 0x20) != 0 )
            v14 |= 0x40u;
        }
        else
        {
          v14 &= ~0x20u;
        }
        v8 -= v16[0];
      }
    }
    else
    {
LABEL_24:
      v12 = 0;
    }
    result = v12;
    *a6 = v11;
  }
  else
  {
    *a6 = 0;
    return 3224698882LL;
  }
  return result;
}

```

## disassembly

```asm
0x140022e50  push    rbx
0x140022e52  push    rbp
0x140022e53  push    rsi
0x140022e54  push    rdi
0x140022e55  push    r12
0x140022e57  push    r14
0x140022e59  push    r15
0x140022e5b  sub     rsp, 40h
0x140022e5f  cmp     cs:WinHvpConnected, 0
0x140022e66  mov     bpl, r9b
0x140022e69  mov     r14d, r8d
0x140022e6c  mov     rdi, rdx
0x140022e6f  mov     r15, rcx
0x140022e72  jnz     short loc_140022E8D
0x140022e74  mov     rax, [rsp+78h+arg_28]
0x140022e7c  mov     qword ptr [rax], 0
0x140022e83  mov     eax, 0C0350002h
0x140022e88  jmp     loc_140022F72
0x140022e8d  xor     esi, esi
0x140022e8f  test    rdx, rdx
0x140022e92  jz      loc_140022F63
0x140022e98  mov     ecx, cs:WinHvpMmFlags
0x140022e9e  xor     edx, edx
0x140022ea0  mov     r12b, [rsp+78h+arg_20]
0x140022ea8  or      ecx, 30h
0x140022eab  test    bpl, bpl
0x140022eae  cmovz   ecx, cs:WinHvpMmFlags
0x140022eb5  mov     ebx, ecx
0x140022eb7  or      ebx, 40h
0x140022eba  test    cl, 20h
0x140022ebd  cmovz   ebx, ecx
0x140022ec0  test    rdi, rdi
0x140022ec3  jz      loc_140022F65
0x140022ec9  mov     r9d, r14d
0x140022ecc  mov     [rsp+78h+var_48], 0
0x140022ed5  lea     rax, [rsp+78h+var_48]
0x140022eda  btr     r9d, 1Fh
0x140022edf  mov     [rsp+78h+var_50], rax
0x140022ee4  mov     r8d, ebx
0x140022ee7  mov     rdx, rdi
0x140022eea  mov     [rsp+78h+var_58], r12b
0x140022eef  mov     rcx, r15
0x140022ef2  call    WinHvpDepositMemoryFromNumaNode
0x140022ef7  mov     rcx, [rsp+78h+var_48]
0x140022efc  mov     edx, eax
0x140022efe  add     rsi, rcx
0x140022f01  cmp     rcx, rdi
0x140022f04  jnb     short loc_140022F63
0x140022f06  cmp     eax, 0C000009Ah
0x140022f0b  jnz     short loc_140022F65
0x140022f0d  mov     eax, ebx
0x140022f0f  and     eax, 70h
0x140022f12  cmp     al, 70h ; 'p'
0x140022f14  jnz     short loc_140022F1B
0x140022f16  and     ebx, 0FFFFFFBFh
0x140022f19  jmp     short loc_140022F54
0x140022f1b  test    bpl, bpl
0x140022f1e  jnz     short loc_140022F2E
0x140022f20  mov     eax, ebx
0x140022f22  and     eax, 30h
0x140022f25  cmp     al, 30h ; '0'
0x140022f27  jnz     short loc_140022F2E
0x140022f29  and     ebx, 0FFFFFFDFh
0x140022f2c  jmp     short loc_140022F54
0x140022f2e  test    bl, 2
0x140022f31  jz      short loc_140022F5C
0x140022f33  test    r14d, r14d
0x140022f36  jns     short loc_140022F5C
0x140022f38  mov     eax, cs:WinHvpMmFlags
0x140022f3e  and     eax, 0FFFFFFFDh
0x140022f41  mov     ebx, eax
0x140022f43  or      ebx, 30h
0x140022f46  test    bpl, bpl
0x140022f49  cmovz   ebx, eax
0x140022f4c  test    bl, 20h
0x140022f4f  jz      short loc_140022F54
0x140022f51  or      ebx, 40h
0x140022f54  sub     rdi, rcx
0x140022f57  jmp     loc_140022EC0
0x140022f5c  mov     edx, 0C000009Ah
0x140022f61  jmp     short loc_140022F65
0x140022f63  xor     edx, edx
0x140022f65  mov     rcx, [rsp+78h+arg_28]
0x140022f6d  mov     eax, edx
0x140022f6f  mov     [rcx], rsi
0x140022f72  add     rsp, 40h
0x140022f76  pop     r15
0x140022f78  pop     r14
0x140022f7a  pop     r12
0x140022f7c  pop     rdi
0x140022f7d  pop     rsi
0x140022f7e  pop     rbp
0x140022f7f  pop     rbx
0x140022f80  retn
```
