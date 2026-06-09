# SymCryptMlDsaTemporariesAllocateAndInitialize

- ea: `0x18002e5c0`
- end: `0x18002e717`
- name: `SymCryptMlDsaTemporariesAllocateAndInitialize`
- size: `343`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x18002697c`
- `0x180026bf8`
- `0x1800270d4`
- `0x18002d48c`
- `0x18002d6d4`
- `0x18002e158`
- `0x18002e414`

## callees

- `0x180009780`
- `0x180022c2c`
- `0x18002e5c0`

## pseudocode

```c
__int64 __fastcall SymCryptMlDsaTemporariesAllocateAndInitialize(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        int a5)
{
  __int64 v5; // rbp
  __int64 v6; // rsi
  __int64 v8; // r14
  unsigned int v9; // r13d
  unsigned int v10; // r15d
  __int64 result; // rax
  __int64 v12; // rbx
  __int64 v13; // rdx
  __int64 *v14; // r8
  __int64 i; // r9
  int v16; // ecx
  __int64 j; // r8
  int v18; // ecx
  __int64 k; // r8

  v5 = a3;
  v6 = a4;
  v8 = a2;
  v9 = (a5 + 7) & 0xFFFFFFF8;
  v10 = *(_DWORD *)(a1 + 4) * a4 + 8 * (a4 + a3 + a2 + 40) + v9 + *(_DWORD *)(a1 + 12) * a3 + *(_DWORD *)(a1 + 8) * a2;
  result = SymCryptCallbackAlloc(v10);
  v12 = result;
  if ( result )
  {
    SymCryptWipeAsm(result, v10);
    *(_DWORD *)v12 = v10;
    v13 = v12 + 320;
    *(_DWORD *)(v12 + 4) = v8;
    v14 = (__int64 *)(v12 + 272);
    *(_DWORD *)(v12 + 8) = v5;
    *(_DWORD *)(v12 + 12) = v6;
    *(_DWORD *)(v12 + 16) = v9;
    if ( (_DWORD)v8 )
    {
      *v14 = v13;
      v13 += 8 * v8;
    }
    if ( (_DWORD)v5 )
    {
      *(_QWORD *)(v12 + 280) = v13;
      v13 += 8 * v5;
    }
    if ( (_DWORD)v6 )
    {
      *(_QWORD *)(v12 + 288) = v13;
      v13 += 8 * v6;
    }
    for ( i = 0; (unsigned int)i < (unsigned int)v8; v13 += *(unsigned int *)(a1 + 8) )
    {
      v16 = *(_DWORD *)(a1 + 8);
      *(_BYTE *)v13 = *(_BYTE *)(a1 + 20);
      *(_DWORD *)(v13 + 4) = v16;
      *(_QWORD *)(*v14 + 8 * i) = v13;
      i = (unsigned int)(i + 1);
    }
    for ( j = 0; (unsigned int)j < (unsigned int)v5; v13 += *(unsigned int *)(a1 + 12) )
    {
      v18 = *(_DWORD *)(a1 + 12);
      *(_BYTE *)v13 = *(_BYTE *)(a1 + 21);
      *(_DWORD *)(v13 + 4) = v18;
      *(_QWORD *)(*(_QWORD *)(v12 + 280) + 8 * j) = v13;
      j = (unsigned int)(j + 1);
    }
    for ( k = 0; (unsigned int)k < (unsigned int)v6; v13 += *(unsigned int *)(a1 + 4) )
    {
      *(_QWORD *)(*(_QWORD *)(v12 + 288) + 8 * k) = v13;
      k = (unsigned int)(k + 1);
    }
    if ( v9 )
      *(_QWORD *)(v12 + 296) = v13;
    return v12;
  }
  return result;
}

```

## disassembly

```asm
0x18002e5c0  push    rbx
0x18002e5c2  push    rbp
0x18002e5c3  push    rsi
0x18002e5c4  push    rdi
0x18002e5c5  push    r12
0x18002e5c7  push    r13
0x18002e5c9  push    r14
0x18002e5cb  push    r15
0x18002e5cd  sub     rsp, 28h
0x18002e5d1  mov     r13d, [rsp+68h+arg_20]
0x18002e5d9  lea     r10d, [rdx+28h]
0x18002e5dd  add     r10d, r8d
0x18002e5e0  mov     ebp, r8d
0x18002e5e3  imul    r8d, [rcx+0Ch]
0x18002e5e8  mov     eax, r9d
0x18002e5eb  imul    eax, [rcx+4]
0x18002e5ef  add     r10d, r9d
0x18002e5f2  mov     r15d, edx
0x18002e5f5  mov     esi, r9d
0x18002e5f8  imul    r15d, [rcx+8]
0x18002e5fd  mov     rdi, rcx
0x18002e600  add     r13d, 7
0x18002e604  mov     r14d, edx
0x18002e607  and     r13d, 0FFFFFFF8h
0x18002e60b  add     r8d, r13d
0x18002e60e  lea     r9d, [rax+r10*8]
0x18002e612  add     r8d, r9d
0x18002e615  add     r15d, r8d
0x18002e618  mov     ecx, r15d
0x18002e61b  mov     r12d, r15d
0x18002e61e  call    SymCryptCallbackAlloc
0x18002e623  mov     rbx, rax
0x18002e626  test    rax, rax
0x18002e629  jz      loc_18002E705
0x18002e62f  mov     rdx, r12
0x18002e632  mov     rcx, rbx
0x18002e635  call    SymCryptWipeAsm
0x18002e63a  mov     [rbx], r15d
0x18002e63d  lea     rdx, [rbx+140h]
0x18002e644  mov     [rbx+4], r14d
0x18002e648  lea     r8, [rbx+110h]
0x18002e64f  mov     [rbx+8], ebp
0x18002e652  mov     [rbx+0Ch], esi
0x18002e655  mov     [rbx+10h], r13d
0x18002e659  test    r14d, r14d
0x18002e65c  jz      short loc_18002E665
0x18002e65e  mov     [r8], rdx
0x18002e661  lea     rdx, [rdx+r14*8]
0x18002e665  test    ebp, ebp
0x18002e667  jz      short loc_18002E674
0x18002e669  mov     [rbx+118h], rdx
0x18002e670  lea     rdx, [rdx+rbp*8]
0x18002e674  test    esi, esi
0x18002e676  jz      short loc_18002E683
0x18002e678  mov     [rbx+120h], rdx
0x18002e67f  lea     rdx, [rdx+rsi*8]
0x18002e683  xor     r9d, r9d
0x18002e686  test    r14d, r14d
0x18002e689  jz      short loc_18002E6AB
0x18002e68b  mov     al, [rdi+14h]
0x18002e68e  mov     ecx, [rdi+8]
0x18002e691  mov     [rdx], al
0x18002e693  mov     [rdx+4], ecx
0x18002e696  mov     rax, [r8]
0x18002e699  mov     [rax+r9*8], rdx
0x18002e69d  inc     r9d
0x18002e6a0  mov     eax, [rdi+8]
0x18002e6a3  add     rdx, rax
0x18002e6a6  cmp     r9d, r14d
0x18002e6a9  jb      short loc_18002E68B
0x18002e6ab  xor     r8d, r8d
0x18002e6ae  test    ebp, ebp
0x18002e6b0  jz      short loc_18002E6D6
0x18002e6b2  mov     al, [rdi+15h]
0x18002e6b5  mov     ecx, [rdi+0Ch]
0x18002e6b8  mov     [rdx], al
0x18002e6ba  mov     [rdx+4], ecx
0x18002e6bd  mov     rax, [rbx+118h]
0x18002e6c4  mov     [rax+r8*8], rdx
0x18002e6c8  inc     r8d
0x18002e6cb  mov     eax, [rdi+0Ch]
0x18002e6ce  add     rdx, rax
0x18002e6d1  cmp     r8d, ebp
0x18002e6d4  jb      short loc_18002E6B2
0x18002e6d6  xor     r8d, r8d
0x18002e6d9  test    esi, esi
0x18002e6db  jz      short loc_18002E6F6
0x18002e6dd  mov     rax, [rbx+120h]
0x18002e6e4  mov     [rax+r8*8], rdx
0x18002e6e8  inc     r8d
0x18002e6eb  mov     ecx, [rdi+4]
0x18002e6ee  add     rdx, rcx
0x18002e6f1  cmp     r8d, esi
0x18002e6f4  jb      short loc_18002E6DD
0x18002e6f6  test    r13d, r13d
0x18002e6f9  jz      short loc_18002E702
0x18002e6fb  mov     [rbx+128h], rdx
0x18002e702  mov     rax, rbx
0x18002e705  add     rsp, 28h
0x18002e709  pop     r15
0x18002e70b  pop     r14
0x18002e70d  pop     r13
0x18002e70f  pop     r12
0x18002e711  pop     rdi
0x18002e712  pop     rsi
0x18002e713  pop     rbp
0x18002e714  pop     rbx
0x18002e715  retn
```
