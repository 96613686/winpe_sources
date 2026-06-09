# _RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCs1EG24RjTlfM_9gdi_alloc15TaggedAllocatorKm63746547_EE11finish_growCs1fYFp9lPHeY_14handle_manager.llvm.11613849813322307182

- ea: `0x140018f20`
- end: `0x140019028`
- name: `_RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCs1EG24RjTlfM_9gdi_alloc15TaggedAllocatorKm63746547_EE11finish_growCs1fYFp9lPHeY_14handle_manager.llvm.11613849813322307182`
- size: `264`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x14000a5f0`
- `0x140013e50`
- `0x140019140`

## callees

- `0x14001790a`
- `0x140017940`
- `0x140017b00`
- `0x140018f20`

## pseudocode

```c
__int64 __fastcall RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCs1EG24RjTlfM_9gdi_alloc15TaggedAllocatorKm63746547_EE11finish_growCs1fYFp9lPHeY_14handle_manager_llvm_11613849813322307182(
        __int64 *a1,
        __int64 *a2,
        unsigned __int64 a3,
        unsigned __int64 a4,
        unsigned __int64 a5)
{
  __int64 result; // rax
  __int64 v6; // r15
  __int64 v7; // rdx
  __int64 v8; // rbx
  const void *v9; // r14
  __int64 *v10; // r12
  __int64 v11; // r13
  unsigned __int64 v12; // rdi
  __int64 v13; // rax
  void *v14; // rdi
  __int64 *v15; // rdi
  __int64 v16; // rsi
  unsigned __int64 v17; // rbx
  __int64 v18; // rax

  result = a3 * a5;
  v6 = 1;
  if ( (a3 * (unsigned __int128)a5) >> 64 == 0 && a3 * a5 <= 0x8000000000000000uLL - a4 )
  {
    v8 = *a2;
    if ( *a2 )
    {
      if ( a4 <= 0x10 )
      {
        v9 = (const void *)a2[1];
        v10 = a1;
        v11 = a3 * a5;
        v12 = a4;
        v13 = Win32AllocPool_0(result, 1668572487);
        a4 = v12;
        a1 = v10;
        v14 = (void *)v13;
        result = v11;
        if ( v14 )
        {
          memmove(v14, v9, a5 * v8);
          Win32FreePool_0((__int64)v9);
          result = v11;
          a1 = v10;
LABEL_9:
          a1[1] = (__int64)v14;
          v7 = 2;
          v6 = 0;
          goto LABEL_11;
        }
      }
    }
    else if ( a4 <= 0x10 )
    {
      v15 = a1;
      v16 = a3 * a5;
      v17 = a4;
      v18 = Win32AllocPool_0(result, 1668572487);
      a4 = v17;
      a1 = v15;
      v14 = (void *)v18;
      result = v16;
      if ( v14 )
        goto LABEL_9;
    }
    a1[1] = a4;
    v7 = 2;
    goto LABEL_11;
  }
  v7 = 1;
  result = 0;
LABEL_11:
  a1[v7] = result;
  *a1 = v6;
  return result;
}

```

## disassembly

```asm
0x140018f20  push    r15
0x140018f22  push    r14
0x140018f24  push    r13
0x140018f26  push    r12
0x140018f28  push    rsi
0x140018f29  push    rdi
0x140018f2a  push    rbx
0x140018f2b  sub     rsp, 20h
0x140018f2f  mov     r10, rdx
0x140018f32  mov     rsi, [rsp+58h+arg_20]
0x140018f3a  mov     rax, rsi
0x140018f3d  mul     r8
0x140018f40  seto    dl
0x140018f43  mov     r8, 8000000000000000h
0x140018f4d  sub     r8, r9
0x140018f50  cmp     rax, r8
0x140018f53  setnbe  r8b
0x140018f57  or      r8b, dl
0x140018f5a  mov     r15d, 1
0x140018f60  jz      short loc_140018F6E
0x140018f62  mov     edx, 8
0x140018f67  xor     eax, eax
0x140018f69  jmp     loc_140019011
0x140018f6e  mov     rbx, [r10]
0x140018f71  test    rbx, rbx
0x140018f74  jz      short loc_140018FCD
0x140018f76  cmp     r9, 10h
0x140018f7a  ja      loc_140019008
0x140018f80  mov     r14, [r10+8]
0x140018f84  mov     r12, rcx
0x140018f87  mov     rcx, rax
0x140018f8a  mov     edx, 63746547h
0x140018f8f  mov     r13, rax
0x140018f92  mov     rdi, r9
0x140018f95  call    Win32AllocPool_0
0x140018f9a  mov     r9, rdi
0x140018f9d  mov     rcx, r12
0x140018fa0  mov     rdi, rax
0x140018fa3  mov     rax, r13
0x140018fa6  test    rdi, rdi
0x140018fa9  jz      short loc_140019008
0x140018fab  imul    rbx, rsi
0x140018faf  mov     rcx, rdi; void *
0x140018fb2  mov     rdx, r14; Src
0x140018fb5  mov     r8, rbx; Size
0x140018fb8  call    memmove
0x140018fbd  mov     rcx, r14
0x140018fc0  call    Win32FreePool_0
0x140018fc5  mov     rax, r13
0x140018fc8  mov     rcx, r12
0x140018fcb  jmp     short loc_140018FFA
0x140018fcd  cmp     r9, 10h
0x140018fd1  ja      short loc_140019008
0x140018fd3  mov     rdi, rcx
0x140018fd6  mov     rcx, rax
0x140018fd9  mov     edx, 63746547h
0x140018fde  mov     rsi, rax
0x140018fe1  mov     rbx, r9
0x140018fe4  call    Win32AllocPool_0
0x140018fe9  mov     r9, rbx
0x140018fec  mov     rcx, rdi
0x140018fef  mov     rdi, rax
0x140018ff2  mov     rax, rsi
0x140018ff5  test    rdi, rdi
0x140018ff8  jz      short loc_140019008
0x140018ffa  mov     [rcx+8], rdi
0x140018ffe  mov     edx, 10h
0x140019003  xor     r15d, r15d
0x140019006  jmp     short loc_140019011
0x140019008  mov     [rcx+8], r9
0x14001900c  mov     edx, 10h
0x140019011  mov     [rcx+rdx], rax
0x140019015  mov     [rcx], r15
0x140019018  add     rsp, 20h
0x14001901c  pop     rbx
0x14001901d  pop     rdi
0x14001901e  pop     rsi
0x14001901f  pop     r12
0x140019021  pop     r13
0x140019023  pop     r14
0x140019025  pop     r15
0x140019027  retn
```
