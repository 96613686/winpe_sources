# _RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCs7vXzV21FY6F_8gdi_rust.llvm.1180095224807683263

- ea: `0x140018ab0`
- end: `0x140018bee`
- name: `_RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCs7vXzV21FY6F_8gdi_rust.llvm.1180095224807683263`
- size: `318`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x14000f720`
- `0x14000f800`
- `0x14000fca0`
- `0x1400101f0`

## callees

- `0x14000fda0`
- `0x14000fdb0`
- `0x14001790a`
- `0x140017940`
- `0x140017b00`
- `0x140018ab0`

## pseudocode

```c
__int64 __fastcall RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCs7vXzV21FY6F_8gdi_rust_llvm_1180095224807683263(
        __int64 *a1,
        __int64 *a2,
        unsigned __int64 a3,
        unsigned __int64 a4,
        unsigned __int64 a5)
{
  unsigned __int128 v6; // rax
  unsigned __int64 v7; // r8
  __int64 v8; // r15
  __int64 v9; // rbx
  unsigned __int64 v10; // r13
  __int64 *v11; // r12
  const void *v12; // r14
  __int64 v13; // rbp
  __int64 v14; // rax
  unsigned __int64 v15; // rsi
  __int64 *v16; // rbx
  __int64 v17; // r14
  __int64 v18; // rax
  void *v19; // rdi
  bool v20; // zf
  size_t v21; // rbx

  v6 = a3 * (unsigned __int128)a5;
  BYTE8(v6) = *((_QWORD *)&v6 + 1) != 0;
  v7 = 0x8000000000000000uLL - a4;
  LOBYTE(v7) = BYTE8(v6) | ((unsigned __int64)v6 > 0x8000000000000000uLL - a4);
  v8 = 1;
  if ( !(_BYTE)v7 )
  {
    v9 = *a2;
    if ( *a2 )
    {
      if ( a4 <= 0x10 )
      {
        v10 = a4;
        v11 = a1;
        v12 = (const void *)a2[1];
        if ( (_QWORD)v6 == 112 )
        {
          v13 = 112;
          v14 = RNvNtCsdwtLm5uWta6_10gdi_region3ffi26ScanLookAsideList_Allocate(a1, *((_QWORD *)&v6 + 1), v7, a4);
        }
        else
        {
          v13 = v6;
          v14 = Win32AllocPool_0(v6, 1852011335);
        }
        v19 = (void *)v14;
        v20 = v14 == 0;
        a1 = v11;
        *(_QWORD *)&v6 = v13;
        a4 = v10;
        if ( !v20 )
        {
          v21 = a5 * v9;
          memmove(v19, v12, v21);
          if ( v21 == 112 )
            RNvNtCsdwtLm5uWta6_10gdi_region3ffi22ScanLookAsideList_Free(v12);
          else
            Win32FreePool_0(v12);
          a1 = v11;
          *(_QWORD *)&v6 = v13;
LABEL_18:
          a1[1] = (__int64)v19;
          *((_QWORD *)&v6 + 1) = 16;
          v8 = 0;
          goto LABEL_20;
        }
      }
    }
    else if ( a4 <= 0x10 )
    {
      v15 = a4;
      v16 = a1;
      if ( (_QWORD)v6 == 112 )
      {
        v17 = 112;
        v18 = RNvNtCsdwtLm5uWta6_10gdi_region3ffi26ScanLookAsideList_Allocate(a1, *((_QWORD *)&v6 + 1), v7, a4);
      }
      else
      {
        v17 = v6;
        v18 = Win32AllocPool_0(v6, 1852011335);
      }
      v19 = (void *)v18;
      v20 = v18 == 0;
      a1 = v16;
      *(_QWORD *)&v6 = v17;
      a4 = v15;
      if ( !v20 )
        goto LABEL_18;
    }
    a1[1] = a4;
    *((_QWORD *)&v6 + 1) = 16;
    goto LABEL_20;
  }
  *((_QWORD *)&v6 + 1) = 8;
  *(_QWORD *)&v6 = 0;
LABEL_20:
  *(__int64 *)((char *)a1 + *((_QWORD *)&v6 + 1)) = v6;
  *a1 = v8;
  return v6;
}

```

## disassembly

```asm
0x140018ab0  push    r15
0x140018ab2  push    r14
0x140018ab4  push    r13
0x140018ab6  push    r12
0x140018ab8  push    rsi
0x140018ab9  push    rdi
0x140018aba  push    rbp
0x140018abb  push    rbx
0x140018abc  sub     rsp, 28h
0x140018ac0  mov     r10, rdx
0x140018ac3  mov     rsi, [rsp+68h+arg_20]
0x140018acb  mov     rax, rsi
0x140018ace  mul     r8
0x140018ad1  seto    dl
0x140018ad4  mov     r8, 8000000000000000h
0x140018ade  sub     r8, r9
0x140018ae1  cmp     rax, r8
0x140018ae4  setnbe  r8b
0x140018ae8  or      r8b, dl
0x140018aeb  mov     r15d, 1
0x140018af1  jz      short loc_140018AFF
0x140018af3  mov     edx, 8
0x140018af8  xor     eax, eax
0x140018afa  jmp     loc_140018BD6
0x140018aff  mov     rbx, [r10]
0x140018b02  test    rbx, rbx
0x140018b05  jz      short loc_140018B2B
0x140018b07  cmp     r9, 10h
0x140018b0b  ja      loc_140018BCD
0x140018b11  mov     r13, r9
0x140018b14  mov     r12, rcx
0x140018b17  mov     r14, [r10+8]
0x140018b1b  cmp     rax, 70h ; 'p'
0x140018b1f  jnz     short loc_140018B4B
0x140018b21  mov     rbp, rax
0x140018b24  call    _RNvNtCsdwtLm5uWta6_10gdi_region3ffi26ScanLookAsideList_Allocate
0x140018b29  jmp     short loc_140018B5B
0x140018b2b  cmp     r9, 10h
0x140018b2f  ja      loc_140018BCD
0x140018b35  mov     rsi, r9
0x140018b38  mov     rbx, rcx
0x140018b3b  cmp     rax, 70h ; 'p'
0x140018b3f  jnz     short loc_140018B9E
0x140018b41  mov     r14, rax
0x140018b44  call    _RNvNtCsdwtLm5uWta6_10gdi_region3ffi26ScanLookAsideList_Allocate
0x140018b49  jmp     short loc_140018BAE
0x140018b4b  mov     rbp, rax
0x140018b4e  mov     rcx, rax
0x140018b51  mov     edx, 6E637347h
0x140018b56  call    Win32AllocPool_0
0x140018b5b  mov     rdi, rax
0x140018b5e  test    rax, rax
0x140018b61  mov     rcx, r12
0x140018b64  mov     rax, rbp
0x140018b67  mov     r9, r13
0x140018b6a  jz      short loc_140018BCD
0x140018b6c  mov     r15, rax
0x140018b6f  imul    rbx, rsi
0x140018b73  mov     rcx, rdi; void *
0x140018b76  mov     rdx, r14; Src
0x140018b79  mov     r8, rbx; Size
0x140018b7c  call    memmove
0x140018b81  mov     rcx, r14
0x140018b84  cmp     rbx, 70h ; 'p'
0x140018b88  jnz     short loc_140018B91
0x140018b8a  call    _RNvNtCsdwtLm5uWta6_10gdi_region3ffi22ScanLookAsideList_Free
0x140018b8f  jmp     short loc_140018B96
0x140018b91  call    Win32FreePool_0
0x140018b96  mov     rcx, r12
0x140018b99  mov     rax, r15
0x140018b9c  jmp     short loc_140018BBF
0x140018b9e  mov     r14, rax
0x140018ba1  mov     rcx, rax
0x140018ba4  mov     edx, 6E637347h
0x140018ba9  call    Win32AllocPool_0
0x140018bae  mov     rdi, rax
0x140018bb1  test    rax, rax
0x140018bb4  mov     rcx, rbx
0x140018bb7  mov     rax, r14
0x140018bba  mov     r9, rsi
0x140018bbd  jz      short loc_140018BCD
0x140018bbf  mov     [rcx+8], rdi
0x140018bc3  mov     edx, 10h
0x140018bc8  xor     r15d, r15d
0x140018bcb  jmp     short loc_140018BD6
0x140018bcd  mov     [rcx+8], r9
0x140018bd1  mov     edx, 10h
0x140018bd6  mov     [rcx+rdx], rax
0x140018bda  mov     [rcx], r15
0x140018bdd  add     rsp, 28h
0x140018be1  pop     rbx
0x140018be2  pop     rbp
0x140018be3  pop     rdi
0x140018be4  pop     rsi
0x140018be5  pop     r12
0x140018be7  pop     r13
0x140018be9  pop     r14
0x140018beb  pop     r15
0x140018bed  retn
```
