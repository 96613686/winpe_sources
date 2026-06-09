# _RNvMs5_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE3new

- ea: `0x140012f10`
- end: `0x1400131ed`
- name: `_RNvMs5_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE3new`
- size: `733`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000c640`
- `0x14000cc10`
- `0x14000e9d0`
- `0x1400101f0`

## callees

- `0x140012f10`
- `0x140017a10`
- `0x1400193b0`

## pseudocode

```c
__int64 __fastcall RNvMs5_NtCsdcpJtfrLhSH_7rgncore4scanINtB5_11ScanBuilderINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE3new(
        __int64 a1,
        unsigned __int64 *a2,
        int a3,
        int a4,
        __int64 a5)
{
  __int64 v5; // r10
  __int64 v6; // rax
  __int64 v7; // rsi
  bool v8; // cf
  unsigned __int64 v9; // r10
  unsigned __int64 v10; // rdi
  _DWORD *v11; // rax
  __int64 v12; // r15
  __int64 v13; // rbx
  _DWORD *v14; // rax
  __int64 v15; // r14
  int v17; // ebx
  int v18; // ebp
  __int64 v19; // r14
  unsigned __int64 v20; // rcx
  unsigned __int64 *v21; // r15
  int v22; // ebx
  int v23; // ebp
  unsigned __int64 v24; // rax
  unsigned __int64 *v25; // r12
  int v26; // r13d
  unsigned __int64 *v27; // rbp
  __int64 v28; // r12
  unsigned __int64 v29; // rcx
  unsigned __int64 v30; // r14
  _DWORD *v31; // rax
  int v32; // ebp
  __int64 v33; // r15
  unsigned __int64 v34; // rdi
  unsigned __int64 *v35; // r12
  __int64 v36; // [rsp+0h] [rbp-98h] BYREF
  int v37; // [rsp+34h] [rbp-64h]
  __int64 v38; // [rsp+38h] [rbp-60h] BYREF
  _DWORD *v39; // [rsp+40h] [rbp-58h]
  __int64 v40; // [rsp+50h] [rbp-48h]

  v5 = a5 + 4;
  v6 = *a2;
  v7 = a2[2];
  if ( a5 + 4 <= *a2 - v7 )
  {
    v10 = *a2;
    if ( v6 == v7 )
      goto LABEL_17;
LABEL_5:
    v11 = (_DWORD *)a2[1];
    v12 = v7 + 1;
    v11[v7] = 0;
    a2[2] = v7 + 1;
    if ( v10 == v7 + 1 )
      goto LABEL_24;
    goto LABEL_6;
  }
  v8 = __CFADD__(v7, v5);
  v9 = v7 + v5;
  if ( v8 )
  {
LABEL_3:
    *(_DWORD *)(a1 + 8) = 14;
    *(_QWORD *)a1 = 0;
    goto LABEL_9;
  }
  v17 = a3;
  v18 = a4;
  v19 = a1;
  v20 = 2 * v6;
  if ( v9 > 2 * v6 )
    v20 = v9;
  v10 = 4;
  if ( v20 >= 5 )
    v10 = v20;
  v21 = a2;
  RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCsdcpJtfrLhSH_7rgncore_llvm_18110786352924170244(
    &v38,
    v6,
    (const void *)a2[1],
    v10,
    4u,
    4u);
  if ( (_DWORD)v38 == 1 )
  {
LABEL_22:
    a1 = v19;
    goto LABEL_3;
  }
  a2 = v21;
  v21[1] = (unsigned __int64)v39;
  *v21 = v10;
  a1 = v19;
  a4 = v18;
  a3 = v17;
  if ( v10 != v7 )
    goto LABEL_5;
LABEL_17:
  v22 = a3;
  v23 = a4;
  v19 = a1;
  v12 = v7 + 1;
  v24 = 2 * v7;
  if ( v7 + 1 > (unsigned __int64)(2 * v7) )
    v24 = v7 + 1;
  v10 = 4;
  if ( v24 >= 5 )
    v10 = v24;
  v25 = a2;
  RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCsdcpJtfrLhSH_7rgncore_llvm_18110786352924170244(
    &v38,
    v7,
    (const void *)a2[1],
    v10,
    4u,
    4u);
  if ( (_DWORD)v38 == 1 )
    goto LABEL_22;
  v11 = v39;
  a2 = v25;
  v25[1] = (unsigned __int64)v39;
  *v25 = v10;
  a1 = v19;
  a4 = v23;
  a3 = v22;
  v11[v7] = 0;
  v25[2] = v12;
  if ( v10 == v12 )
  {
LABEL_24:
    v37 = a3;
    v26 = a4;
    v27 = a2;
    v28 = a1;
    v13 = v10 + 1;
    v29 = 2 * v10;
    if ( v10 + 1 > 2 * v10 )
      v29 = v10 + 1;
    v30 = 4;
    if ( v29 >= 5 )
      v30 = v29;
    RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCsdcpJtfrLhSH_7rgncore_llvm_18110786352924170244(
      &v38,
      v10,
      v11,
      v30,
      4u,
      4u);
    if ( (_DWORD)v38 == 1 )
    {
      a1 = v28;
      goto LABEL_3;
    }
    v31 = v39;
    a2 = v27;
    v27[1] = (unsigned __int64)v39;
    *v27 = v30;
    a1 = v28;
    a4 = v26;
    v31[v12] = v37;
    v27[2] = v13;
    if ( *v27 == v13 )
      goto LABEL_31;
LABEL_7:
    v14 = (_DWORD *)a2[1];
    v15 = v13 + 1;
    goto LABEL_8;
  }
LABEL_6:
  v13 = v12 + 1;
  v11[v12] = a3;
  a2[2] = v12 + 1;
  if ( *a2 != v12 + 1 )
    goto LABEL_7;
LABEL_31:
  v32 = a4;
  v33 = a1;
  v15 = v13 + 1;
  v34 = 2 * v13;
  if ( v13 + 1 > (unsigned __int64)(2 * v13) )
    v34 = v13 + 1;
  v35 = a2;
  RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCsdcpJtfrLhSH_7rgncore_llvm_18110786352924170244(
    &v38,
    v13,
    (const void *)a2[1],
    v34,
    4u,
    4u);
  if ( (_DWORD)v38 == 1 )
  {
    a1 = v33;
    goto LABEL_3;
  }
  v14 = v39;
  a2 = v35;
  v35[1] = (unsigned __int64)v39;
  *v35 = v34;
  a1 = v33;
  a4 = v32;
LABEL_8:
  v14[v13] = a4;
  a2[2] = v15;
  *(_QWORD *)a1 = a2;
  *(_QWORD *)(a1 + 8) = a2 + 3;
  *(_QWORD *)(a1 + 16) = v7;
LABEL_9:
  if ( _security_cookie != ((unsigned __int64)&v36 ^ v40) )
    JUMPOUT(0x1400131ECLL);
  return a1;
}

```

## disassembly

```asm
0x140012f10  push    r15
0x140012f12  push    r14
0x140012f14  push    r13
0x140012f16  push    r12
0x140012f18  push    rsi
0x140012f19  push    rdi
0x140012f1a  push    rbp
0x140012f1b  push    rbx
0x140012f1c  sub     rsp, 58h
0x140012f20  mov     r10, [rsp+98h+arg_20]
0x140012f28  mov     rax, cs:__security_cookie
0x140012f2f  xor     rax, rsp
0x140012f32  mov     [rsp+98h+var_48], rax
0x140012f37  add     r10, 4
0x140012f3b  mov     rax, [rdx]
0x140012f3e  mov     rsi, [rdx+10h]
0x140012f42  mov     r11, rax
0x140012f45  sub     r11, rsi
0x140012f48  cmp     r10, r11
0x140012f4b  jbe     short loc_140012F66
0x140012f4d  add     r10, rsi
0x140012f50  jnb     loc_140012FEE
0x140012f56  mov     dword ptr [rcx+8], 0Eh
0x140012f5d  mov     qword ptr [rcx], 0
0x140012f64  jmp     short loc_140012FC2
0x140012f66  mov     rdi, rax
0x140012f69  cmp     rdi, rsi
0x140012f6c  jz      loc_140013060
0x140012f72  mov     rax, [rdx+8]
0x140012f76  lea     r15, [rsi+1]
0x140012f7a  mov     dword ptr [rax+rsi*4], 0
0x140012f81  mov     [rdx+10h], r15
0x140012f85  cmp     rdi, r15
0x140012f88  jz      loc_1400130EB
0x140012f8e  lea     rbx, [r15+1]
0x140012f92  mov     [rax+r15*4], r8d
0x140012f96  mov     [rdx+10h], rbx
0x140012f9a  cmp     [rdx], rbx
0x140012f9d  jz      loc_140013176
0x140012fa3  mov     rax, [rdx+8]
0x140012fa7  lea     r14, [rbx+1]
0x140012fab  mov     [rax+rbx*4], r9d
0x140012faf  mov     [rdx+10h], r14
0x140012fb3  mov     [rcx], rdx
0x140012fb6  add     rdx, 18h
0x140012fba  mov     [rcx+8], rdx
0x140012fbe  mov     [rcx+10h], rsi
0x140012fc2  mov     rax, [rsp+98h+var_48]
0x140012fc7  xor     rax, rsp
0x140012fca  mov     rdx, cs:__security_cookie
0x140012fd1  cmp     rdx, rax
0x140012fd4  jnz     loc_1400131DF
0x140012fda  mov     rax, rcx
0x140012fdd  add     rsp, 58h
0x140012fe1  pop     rbx
0x140012fe2  pop     rbp
0x140012fe3  pop     rdi
0x140012fe4  pop     rsi
0x140012fe5  pop     r12
0x140012fe7  pop     r13
0x140012fe9  pop     r14
0x140012feb  pop     r15
0x140012fed  retn
0x140012fee  mov     ebx, r8d
0x140012ff1  mov     ebp, r9d
0x140012ff4  mov     r14, rcx
0x140012ff7  lea     rcx, [rax+rax]
0x140012ffb  cmp     r10, rcx
0x140012ffe  cmova   rcx, r10
0x140013002  cmp     rcx, 5
0x140013006  mov     edi, 4
0x14001300b  cmovnb  rdi, rcx
0x14001300f  mov     r15, rdx
0x140013012  mov     r8, [rdx+8]
0x140013016  mov     [rsp+98h+var_70], 4
0x14001301f  mov     [rsp+98h+var_78], 4
0x140013028  lea     rcx, [rsp+98h+var_60]
0x14001302d  mov     rdx, rax
0x140013030  mov     r9, rdi
0x140013033  call    _RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCsdcpJtfrLhSH_7rgncore_llvm_18110786352924170244
0x140013038  cmp     dword ptr [rsp+98h+var_60], 1
0x14001303d  jz      short loc_1400130B5
0x14001303f  mov     rax, [rsp+98h+var_58]
0x140013044  mov     rdx, r15
0x140013047  mov     [r15+8], rax
0x14001304b  mov     [r15], rdi
0x14001304e  mov     rcx, r14
0x140013051  mov     r9d, ebp
0x140013054  mov     r8d, ebx
0x140013057  cmp     rdi, rsi
0x14001305a  jnz     loc_140012F72
0x140013060  mov     ebx, r8d
0x140013063  mov     ebp, r9d
0x140013066  mov     r14, rcx
0x140013069  lea     r15, [rsi+1]
0x14001306d  lea     rax, [rsi+rsi]
0x140013071  cmp     r15, rax
0x140013074  cmova   rax, r15
0x140013078  cmp     rax, 5
0x14001307c  mov     edi, 4
0x140013081  cmovnb  rdi, rax
0x140013085  mov     r12, rdx
0x140013088  mov     r8, [rdx+8]
0x14001308c  mov     [rsp+98h+var_70], 4
0x140013095  mov     [rsp+98h+var_78], 4
0x14001309e  lea     rcx, [rsp+98h+var_60]
0x1400130a3  mov     rdx, rsi
0x1400130a6  mov     r9, rdi
0x1400130a9  call    _RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCsdcpJtfrLhSH_7rgncore_llvm_18110786352924170244
0x1400130ae  cmp     dword ptr [rsp+98h+var_60], 1
0x1400130b3  jnz     short loc_1400130BD
0x1400130b5  mov     rcx, r14
0x1400130b8  jmp     loc_140012F56
0x1400130bd  mov     rax, [rsp+98h+var_58]
0x1400130c2  mov     rdx, r12
0x1400130c5  mov     [r12+8], rax
0x1400130ca  mov     [r12], rdi
0x1400130ce  mov     rcx, r14
0x1400130d1  mov     r9d, ebp
0x1400130d4  mov     r8d, ebx
0x1400130d7  mov     dword ptr [rax+rsi*4], 0
0x1400130de  mov     [rdx+10h], r15
0x1400130e2  cmp     rdi, r15
0x1400130e5  jnz     loc_140012F8E
0x1400130eb  mov     [rsp+98h+var_64], r8d
0x1400130f0  mov     r13d, r9d
0x1400130f3  mov     rbp, rdx
0x1400130f6  mov     r12, rcx
0x1400130f9  lea     rbx, [rdi+1]
0x1400130fd  lea     rcx, [rdi+rdi]
0x140013101  cmp     rbx, rcx
0x140013104  cmova   rcx, rbx
0x140013108  cmp     rcx, 5
0x14001310c  mov     r14d, 4
0x140013112  cmovnb  r14, rcx
0x140013116  mov     [rsp+98h+var_70], 4
0x14001311f  mov     [rsp+98h+var_78], 4
0x140013128  lea     rcx, [rsp+98h+var_60]
0x14001312d  mov     rdx, rdi
0x140013130  mov     r8, rax
0x140013133  mov     r9, r14
0x140013136  call    _RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCsdcpJtfrLhSH_7rgncore_llvm_18110786352924170244
0x14001313b  cmp     dword ptr [rsp+98h+var_60], 1
0x140013140  jnz     short loc_14001314A
0x140013142  mov     rcx, r12
0x140013145  jmp     loc_140012F56
0x14001314a  mov     rax, [rsp+98h+var_58]
0x14001314f  mov     rdx, rbp
0x140013152  mov     [rbp+8], rax
0x140013156  mov     [rbp+0], r14
0x14001315a  mov     rcx, r12
0x14001315d  mov     r9d, r13d
0x140013160  mov     r8d, [rsp+98h+var_64]
0x140013165  mov     [rax+r15*4], r8d
0x140013169  mov     [rdx+10h], rbx
0x14001316d  cmp     [rdx], rbx
0x140013170  jnz     loc_140012FA3
0x140013176  mov     ebp, r9d
0x140013179  mov     r15, rcx
0x14001317c  lea     r14, [rbx+1]
0x140013180  lea     rdi, [rbx+rbx]
0x140013184  cmp     r14, rdi
0x140013187  cmova   rdi, r14
0x14001318b  mov     r12, rdx
0x14001318e  mov     r8, [rdx+8]
0x140013192  mov     [rsp+98h+var_70], 4
0x14001319b  mov     [rsp+98h+var_78], 4
0x1400131a4  lea     rcx, [rsp+98h+var_60]
0x1400131a9  mov     rdx, rbx
0x1400131ac  mov     r9, rdi
0x1400131af  call    _RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCsdcpJtfrLhSH_7rgncore_llvm_18110786352924170244
0x1400131b4  cmp     dword ptr [rsp+98h+var_60], 1
0x1400131b9  jnz     short loc_1400131C3
0x1400131bb  mov     rcx, r15
0x1400131be  jmp     loc_140012F56
0x1400131c3  mov     rax, [rsp+98h+var_58]
0x1400131c8  mov     rdx, r12
0x1400131cb  mov     [r12+8], rax
0x1400131d0  mov     [r12], rdi
0x1400131d4  mov     rcx, r15
0x1400131d7  mov     r9d, ebp
0x1400131da  jmp     loc_140012FAB
0x1400131df  mov     rcx, [rsp+98h+var_48]
0x1400131e4  xor     rcx, rsp; StackCookie
0x1400131e7  call    __security_check_cookie
```
