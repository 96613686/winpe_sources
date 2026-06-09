# _RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCs1EG24RjTlfM_9gdi_alloc15TaggedAllocatorKm67646547_EE11finish_growCs7vXzV21FY6F_8gdi_rust.llvm.1180095224807683263

- ea: `0x1400189a0`
- end: `0x140018aa8`
- name: `_RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCs1EG24RjTlfM_9gdi_alloc15TaggedAllocatorKm67646547_EE11finish_growCs7vXzV21FY6F_8gdi_rust.llvm.1180095224807683263`
- size: `264`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x14000f4c0`
- `0x14000fe20`
- `0x1400101f0`

## callees

- `0x14001790a`
- `0x140017940`
- `0x140017b00`
- `0x1400189a0`

## pseudocode

```c
__int64 __fastcall RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCs1EG24RjTlfM_9gdi_alloc15TaggedAllocatorKm67646547_EE11finish_growCs7vXzV21FY6F_8gdi_rust_llvm_1180095224807683263(
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
        v13 = Win32AllocPool_0(result, 1734632775);
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
      v18 = Win32AllocPool_0(result, 1734632775);
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
0x1400189a0  push    r15
0x1400189a2  push    r14
0x1400189a4  push    r13
0x1400189a6  push    r12
0x1400189a8  push    rsi
0x1400189a9  push    rdi
0x1400189aa  push    rbx
0x1400189ab  sub     rsp, 20h
0x1400189af  mov     r10, rdx
0x1400189b2  mov     rsi, [rsp+58h+arg_20]
0x1400189ba  mov     rax, rsi
0x1400189bd  mul     r8
0x1400189c0  seto    dl
0x1400189c3  mov     r8, 8000000000000000h
0x1400189cd  sub     r8, r9
0x1400189d0  cmp     rax, r8
0x1400189d3  setnbe  r8b
0x1400189d7  or      r8b, dl
0x1400189da  mov     r15d, 1
0x1400189e0  jz      short loc_1400189EE
0x1400189e2  mov     edx, 8
0x1400189e7  xor     eax, eax
0x1400189e9  jmp     loc_140018A91
0x1400189ee  mov     rbx, [r10]
0x1400189f1  test    rbx, rbx
0x1400189f4  jz      short loc_140018A4D
0x1400189f6  cmp     r9, 10h
0x1400189fa  ja      loc_140018A88
0x140018a00  mov     r14, [r10+8]
0x140018a04  mov     r12, rcx
0x140018a07  mov     rcx, rax
0x140018a0a  mov     edx, 67646547h
0x140018a0f  mov     r13, rax
0x140018a12  mov     rdi, r9
0x140018a15  call    Win32AllocPool_0
0x140018a1a  mov     r9, rdi
0x140018a1d  mov     rcx, r12
0x140018a20  mov     rdi, rax
0x140018a23  mov     rax, r13
0x140018a26  test    rdi, rdi
0x140018a29  jz      short loc_140018A88
0x140018a2b  imul    rbx, rsi
0x140018a2f  mov     rcx, rdi; void *
0x140018a32  mov     rdx, r14; Src
0x140018a35  mov     r8, rbx; Size
0x140018a38  call    memmove
0x140018a3d  mov     rcx, r14
0x140018a40  call    Win32FreePool_0
0x140018a45  mov     rax, r13
0x140018a48  mov     rcx, r12
0x140018a4b  jmp     short loc_140018A7A
0x140018a4d  cmp     r9, 10h
0x140018a51  ja      short loc_140018A88
0x140018a53  mov     rdi, rcx
0x140018a56  mov     rcx, rax
0x140018a59  mov     edx, 67646547h
0x140018a5e  mov     rsi, rax
0x140018a61  mov     rbx, r9
0x140018a64  call    Win32AllocPool_0
0x140018a69  mov     r9, rbx
0x140018a6c  mov     rcx, rdi
0x140018a6f  mov     rdi, rax
0x140018a72  mov     rax, rsi
0x140018a75  test    rdi, rdi
0x140018a78  jz      short loc_140018A88
0x140018a7a  mov     [rcx+8], rdi
0x140018a7e  mov     edx, 10h
0x140018a83  xor     r15d, r15d
0x140018a86  jmp     short loc_140018A91
0x140018a88  mov     [rcx+8], r9
0x140018a8c  mov     edx, 10h
0x140018a91  mov     [rcx+rdx], rax
0x140018a95  mov     [rcx], r15
0x140018a98  add     rsp, 20h
0x140018a9c  pop     rbx
0x140018a9d  pop     rdi
0x140018a9e  pop     rsi
0x140018a9f  pop     r12
0x140018aa1  pop     r13
0x140018aa3  pop     r14
0x140018aa5  pop     r15
0x140018aa7  retn
```
