# WriteFontImage

- ea: `0x180021d54`
- end: `0x180021e20`
- name: `WriteFontImage`
- size: `204`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x1800205bc`
- `0x180020784`
- `0x18002089c`
- `0x180020c40`

## callees

- `0x180017ee0`
- `0x180019dc0`
- `0x18001ac80`
- `0x18001bff0`
- `0x180021d54`
- `0x18002a54e`

## pseudocode

```c
__int64 __fastcall WriteFontImage(__int64 a1, unsigned int a2, int a3, __int64 a4, __int64 a5)
{
  void *v8; // rbx
  int i; // edi
  unsigned int v11; // ebp

  if ( !a3 )
    return a2 != (unsigned int)T2OSSvcReadFontData(a4, a5, a1, a2) ? 0x108 : 0;
  v8 = (void *)T2malloc(0xFFFFu);
  if ( !v8 )
    return 266;
  for ( i = a2; i; i -= v11 )
  {
    v11 = 0xFFFF;
    if ( i < 0xFFFF )
      v11 = i;
    memcpy_0(v8, (const void *)(a1 + a2 - i), v11);
    XORBufferData(v8, v11);
    if ( (unsigned int)T2OSSvcReadFontData(a4, a5, v8, v11) != v11 )
    {
      T2free(v8);
      return 264;
    }
  }
  T2free(v8);
  return 0;
}

```

## disassembly

```asm
0x180021d54  push    rbx
0x180021d56  push    rbp
0x180021d57  push    rsi
0x180021d58  push    rdi
0x180021d59  push    r14
0x180021d5b  push    r15
0x180021d5d  sub     rsp, 38h
0x180021d61  mov     r14, r9
0x180021d64  mov     esi, edx
0x180021d66  mov     r15, rcx
0x180021d69  test    r8d, r8d
0x180021d6c  jz      loc_180021DF2
0x180021d72  xor     edx, edx
0x180021d74  mov     ecx, 0FFFFh; dwBytes
0x180021d79  call    T2malloc
0x180021d7e  mov     rbx, rax
0x180021d81  test    rax, rax
0x180021d84  jnz     short loc_180021D90
0x180021d86  mov     eax, 10Ah
0x180021d8b  jmp     loc_180021E13
0x180021d90  mov     edi, esi
0x180021d92  mov     rcx, rbx; lpMem
0x180021d95  test    edi, edi
0x180021d97  jz      short loc_180021DE9
0x180021d99  mov     ebp, 0FFFFh
0x180021d9e  mov     edx, esi
0x180021da0  cmp     edi, ebp
0x180021da2  cmovl   ebp, edi
0x180021da5  sub     edx, edi
0x180021da7  add     rdx, r15; Src
0x180021daa  mov     r8d, ebp; Size
0x180021dad  call    memcpy_0
0x180021db2  mov     edx, ebp
0x180021db4  mov     rcx, rbx
0x180021db7  call    XORBufferData
0x180021dbc  mov     rdx, [rsp+68h+arg_20]
0x180021dc4  mov     r9d, ebp
0x180021dc7  mov     r8, rbx
0x180021dca  mov     rcx, r14
0x180021dcd  call    T2OSSvcReadFontData
0x180021dd2  cmp     eax, ebp
0x180021dd4  jnz     short loc_180021DDA
0x180021dd6  sub     edi, ebp
0x180021dd8  jmp     short loc_180021D92
0x180021dda  mov     rcx, rbx; lpMem
0x180021ddd  call    T2free
0x180021de2  mov     eax, 108h
0x180021de7  jmp     short loc_180021E13
0x180021de9  call    T2free
0x180021dee  xor     eax, eax
0x180021df0  jmp     short loc_180021E13
0x180021df2  mov     rdx, [rsp+68h+arg_20]
0x180021dfa  mov     r9d, esi
0x180021dfd  mov     r8, r15
0x180021e00  mov     rcx, r14
0x180021e03  call    T2OSSvcReadFontData
0x180021e08  sub     eax, esi
0x180021e0a  neg     eax
0x180021e0c  sbb     eax, eax
0x180021e0e  and     eax, 108h
0x180021e13  add     rsp, 38h
0x180021e17  pop     r15
0x180021e19  pop     r14
0x180021e1b  pop     rdi
0x180021e1c  pop     rsi
0x180021e1d  pop     rbp
0x180021e1e  pop     rbx
0x180021e1f  retn
```
