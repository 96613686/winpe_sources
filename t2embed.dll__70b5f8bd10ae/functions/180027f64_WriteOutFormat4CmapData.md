# WriteOutFormat4CmapData

- ea: `0x180027f64`
- end: `0x18002810d`
- name: `WriteOutFormat4CmapData`
- size: `425`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001d5f8`

## callees

- `0x180011640`
- `0x180011f00`
- `0x180027f64`

## pseudocode

```c
__int16 __fastcall WriteOutFormat4CmapData(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned __int16 a5,
        unsigned __int16 a6,
        unsigned int a7,
        _DWORD *a8)
{
  __int16 result; // ax
  unsigned __int16 v12; // bx
  unsigned int v13; // edi
  int v14; // ebp
  int v15; // ebx
  unsigned __int16 i; // di
  int v17; // ebx
  unsigned __int16 j; // di
  int v19; // ebx
  unsigned __int16 k; // di
  int v21; // ebx
  unsigned __int16 m; // di
  unsigned __int16 v23[36]; // [rsp+30h] [rbp-48h] BYREF

  v23[0] = 0;
  result = WriteGeneric(a1, a2, 0xEu, (unsigned __int8 *)&CMAP_FORMAT4_CONTROL, a7, v23);
  if ( !result )
  {
    v12 = 0;
    v13 = a7 + v23[0];
    while ( v12 < a5 )
    {
      result = WriteWord(a1, *(_WORD *)(a3 + 8LL * v12), v13 + 2 * v12);
      if ( result )
        return result;
      ++v12;
    }
    v14 = 2 * a5;
    result = WriteWord(a1, 0, v13 + v14);
    if ( !result )
    {
      v15 = v13 + v14 + 2;
      for ( i = 0; i < a5; ++i )
      {
        result = WriteWord(a1, *(_WORD *)(a3 + 8LL * i + 2), v15 + 2 * (unsigned int)i);
        if ( result )
          return result;
      }
      v17 = v14 + v15;
      for ( j = 0; j < a5; ++j )
      {
        result = WriteWord(a1, *(_WORD *)(a3 + 8LL * j + 4), v17 + 2 * (unsigned int)j);
        if ( result )
          return result;
      }
      v19 = v14 + v17;
      for ( k = 0; k < a5; ++k )
      {
        result = WriteWord(a1, *(_WORD *)(a3 + 8LL * k + 6), v19 + 2 * (unsigned int)k);
        if ( result )
          return result;
      }
      v21 = v14 + v19;
      for ( m = 0; m < a6; ++m )
      {
        result = WriteWord(a1, *(_WORD *)(a4 + 2LL * m), v21 + 2 * (unsigned int)m);
        if ( result )
          return result;
      }
      *a8 = v21 + 2 * a6 - a7;
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180027f64  push    rbx
0x180027f66  push    rbp
0x180027f67  push    rdi
0x180027f68  push    r12
0x180027f6a  push    r13
0x180027f6c  push    r14
0x180027f6e  push    r15
0x180027f70  sub     rsp, 40h
0x180027f74  mov     r12d, [rsp+78h+arg_30]
0x180027f7c  lea     rax, [rsp+78h+var_48]
0x180027f81  xor     ebp, ebp
0x180027f83  mov     [rsp+78h+var_50], rax
0x180027f88  mov     r13, r9
0x180027f8b  mov     [rsp+78h+var_48], bp
0x180027f90  mov     r15, r8
0x180027f93  mov     [rsp+78h+var_58], r12d
0x180027f98  lea     r9, CMAP_FORMAT4_CONTROL
0x180027f9f  mov     r14, rcx
0x180027fa2  lea     r8d, [rbp+0Eh]
0x180027fa6  call    WriteGeneric
0x180027fab  test    ax, ax
0x180027fae  jnz     loc_1800280FD
0x180027fb4  movzx   edi, [rsp+78h+var_48]
0x180027fb9  mov     ebx, ebp
0x180027fbb  add     edi, r12d
0x180027fbe  mov     rcx, r14
0x180027fc1  cmp     bx, [rsp+78h+arg_20]
0x180027fc9  jnb     short loc_180027FED
0x180027fcb  movzx   eax, bx
0x180027fce  movzx   edx, bx
0x180027fd1  lea     r8d, [rdi+rax*2]
0x180027fd5  movzx   edx, word ptr [r15+rdx*8]
0x180027fda  call    WriteWord
0x180027fdf  test    ax, ax
0x180027fe2  jnz     loc_1800280FD
0x180027fe8  inc     bx
0x180027feb  jmp     short loc_180027FBE
0x180027fed  movzx   eax, [rsp+78h+arg_20]
0x180027ff5  xor     edx, edx
0x180027ff7  add     eax, eax
0x180027ff9  mov     ebp, eax
0x180027ffb  lea     ebx, [rdi+rax]
0x180027ffe  mov     r8d, ebx
0x180028001  call    WriteWord
0x180028006  xor     edx, edx
0x180028008  test    ax, ax
0x18002800b  jnz     loc_1800280FD
0x180028011  add     ebx, 2
0x180028014  mov     edi, edx
0x180028016  cmp     di, [rsp+78h+arg_20]
0x18002801e  jnb     short loc_180028048
0x180028020  movzx   eax, di
0x180028023  mov     rcx, r14
0x180028026  movzx   edx, di
0x180028029  lea     r8d, [rbx+rax*2]
0x18002802d  movzx   edx, word ptr [r15+rdx*8+2]
0x180028033  call    WriteWord
0x180028038  xor     edx, edx
0x18002803a  test    ax, ax
0x18002803d  jnz     loc_1800280FD
0x180028043  inc     di
0x180028046  jmp     short loc_180028016
0x180028048  add     ebx, ebp
0x18002804a  mov     edi, edx
0x18002804c  cmp     di, [rsp+78h+arg_20]
0x180028054  jnb     short loc_18002807E
0x180028056  movzx   eax, di
0x180028059  mov     rcx, r14
0x18002805c  movzx   edx, di
0x18002805f  lea     r8d, [rbx+rax*2]
0x180028063  movzx   edx, word ptr [r15+rdx*8+4]
0x180028069  call    WriteWord
0x18002806e  xor     edx, edx
0x180028070  test    ax, ax
0x180028073  jnz     loc_1800280FD
0x180028079  inc     di
0x18002807c  jmp     short loc_18002804C
0x18002807e  add     ebx, ebp
0x180028080  mov     edi, edx
0x180028082  cmp     di, [rsp+78h+arg_20]
0x18002808a  jnb     short loc_1800280B0
0x18002808c  movzx   eax, di
0x18002808f  mov     rcx, r14
0x180028092  movzx   edx, di
0x180028095  lea     r8d, [rbx+rax*2]
0x180028099  movzx   edx, word ptr [r15+rdx*8+6]
0x18002809f  call    WriteWord
0x1800280a4  xor     edx, edx
0x1800280a6  test    ax, ax
0x1800280a9  jnz     short loc_1800280FD
0x1800280ab  inc     di
0x1800280ae  jmp     short loc_180028082
0x1800280b0  add     ebx, ebp
0x1800280b2  mov     edi, edx
0x1800280b4  cmp     di, [rsp+78h+arg_28]
0x1800280bc  jnb     short loc_1800280E2
0x1800280be  movzx   eax, di
0x1800280c1  mov     rcx, r14
0x1800280c4  movzx   edx, di
0x1800280c7  lea     r8d, [rbx+rax*2]
0x1800280cb  movzx   edx, word ptr [r13+rdx*2+0]
0x1800280d1  call    WriteWord
0x1800280d6  xor     edx, edx
0x1800280d8  test    ax, ax
0x1800280db  jnz     short loc_1800280FD
0x1800280dd  inc     di
0x1800280e0  jmp     short loc_1800280B4
0x1800280e2  mov     rax, [rsp+78h+arg_38]
0x1800280ea  movzx   ecx, [rsp+78h+arg_28]
0x1800280f2  add     ecx, ecx
0x1800280f4  sub     ecx, r12d
0x1800280f7  add     ecx, ebx
0x1800280f9  mov     [rax], ecx
0x1800280fb  mov     eax, edx
0x1800280fd  add     rsp, 40h
0x180028101  pop     r15
0x180028103  pop     r14
0x180028105  pop     r13
0x180028107  pop     r12
0x180028109  pop     rdi
0x18002810a  pop     rbp
0x18002810b  pop     rbx
0x18002810c  retn
```
