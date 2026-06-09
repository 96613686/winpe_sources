# _RINvXCs3PyRTeGQ7Na_12fallible_vecINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEINtB3_11FallibleVeclB13_E10try_extendINtNtNtNtCs9MWeMO1rkJG_4core4iter8adapters3map3MapINtNtNtB2L_5slice4iter7IterMutlENCNvMs1_NtCsdcpJtfrLhSH_7rgncore4scanINtB44_12ScanInternalQBv_B13_E16merge_in_x_walls0EEB46_

- ea: `0x140014940`
- end: `0x140014ad7`
- name: `_RINvXCs3PyRTeGQ7Na_12fallible_vecINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEINtB3_11FallibleVeclB13_E10try_extendINtNtNtNtCs9MWeMO1rkJG_4core4iter8adapters3map3MapINtNtNtB2L_5slice4iter7IterMutlENCNvMs1_NtCsdcpJtfrLhSH_7rgncore4scanINtB44_12ScanInternalQBv_B13_E16merge_in_x_walls0EEB46_`
- size: `407`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140014dd0`
- `0x140015ac0`

## callees

- `0x140014940`
- `0x140017a10`
- `0x1400193b0`

## pseudocode

```c
unsigned __int64 __fastcall RINvXCs3PyRTeGQ7Na_12fallible_vecINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEINtB3_11FallibleVeclB13_E10try_extendINtNtNtNtCs9MWeMO1rkJG_4core4iter8adapters3map3MapINtNtNtB2L_5slice4iter7IterMutlENCNvMs1_NtCsdcpJtfrLhSH_7rgncore4scanINtB44_12ScanInternalQBv_B13_E16merge_in_x_walls0EEB46_(
        __int64 a1,
        char *a2,
        char *a3)
{
  char *v4; // rdi
  unsigned __int64 v6; // rax
  __int64 v7; // rdx
  __int64 v8; // r14
  bool v9; // cf
  unsigned __int64 v10; // rax
  unsigned __int64 v11; // r15
  unsigned __int64 v12; // r12
  const void *v13; // r8
  unsigned __int64 v14; // rbp
  int v15; // r13d
  unsigned __int64 v16; // rcx
  __int64 v18; // [rsp+0h] [rbp-98h] BYREF
  __int64 v19; // [rsp+38h] [rbp-60h] BYREF
  const void *v20; // [rsp+40h] [rbp-58h]
  __int64 v21; // [rsp+50h] [rbp-48h]

  v4 = a2;
  v6 = (unsigned __int64)(a3 - a2) >> 2;
  v7 = *(_QWORD *)a1;
  v8 = *(_QWORD *)(a1 + 16);
  if ( v6 <= *(_QWORD *)a1 - v8 )
  {
    v12 = *(_QWORD *)a1;
    v11 = 0x8000000000000001uLL;
    if ( v4 == a3 )
      goto LABEL_21;
    goto LABEL_5;
  }
  v9 = __CFADD__(v8, v6);
  v10 = v8 + v6;
  if ( v9 )
  {
    v11 = 0;
    goto LABEL_21;
  }
  v16 = 2 * v7;
  if ( v10 > 2 * v7 )
    v16 = v10;
  v12 = 4;
  if ( v16 >= 5 )
    v12 = v16;
  RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCsdcpJtfrLhSH_7rgncore_llvm_18110786352924170244(
    &v19,
    v7,
    *(const void **)(a1 + 8),
    v12,
    4u,
    4u);
  if ( (_DWORD)v19 == 1 )
  {
LABEL_19:
    v11 = (unsigned __int64)v20;
    goto LABEL_21;
  }
  *(_QWORD *)(a1 + 8) = v20;
  *(_QWORD *)a1 = v12;
  v11 = 0x8000000000000001uLL;
  if ( v4 != a3 )
  {
LABEL_5:
    v13 = *(const void **)(a1 + 8);
    v14 = 2 * v8;
    do
    {
      v15 = *(_DWORD *)v4;
      if ( v8 == v12 )
      {
        v12 = v8 + 1;
        if ( v8 + 1 <= v14 )
          v12 = v14;
        if ( v12 < 5 )
          v12 = 4;
        RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCsdcpJtfrLhSH_7rgncore_llvm_18110786352924170244(
          &v19,
          v8,
          v13,
          v12,
          4u,
          4u);
        if ( (_DWORD)v19 == 1 )
          goto LABEL_19;
        v13 = v20;
        *(_QWORD *)(a1 + 8) = v20;
        *(_QWORD *)a1 = v12;
      }
      v4 += 4;
      *((_DWORD *)v13 + v8++) = v15;
      *(_QWORD *)(a1 + 16) = v8;
      v14 += 2LL;
    }
    while ( v4 != a3 );
  }
LABEL_21:
  if ( _security_cookie != ((unsigned __int64)&v18 ^ v21) )
    JUMPOUT(0x140014AD6LL);
  return v11;
}

```

## disassembly

```asm
0x140014940  push    r15
0x140014942  push    r14
0x140014944  push    r13
0x140014946  push    r12
0x140014948  push    rsi
0x140014949  push    rdi
0x14001494a  push    rbp
0x14001494b  push    rbx
0x14001494c  sub     rsp, 58h
0x140014950  mov     rsi, r8
0x140014953  mov     rdi, rdx
0x140014956  mov     rbx, rcx
0x140014959  mov     rax, cs:__security_cookie
0x140014960  xor     rax, rsp
0x140014963  mov     [rsp+98h+var_48], rax
0x140014968  mov     rax, r8
0x14001496b  sub     rax, rdx
0x14001496e  shr     rax, 2
0x140014972  mov     rdx, [rcx]
0x140014975  mov     r14, [rcx+10h]
0x140014979  mov     rcx, rdx
0x14001497c  sub     rcx, r14
0x14001497f  cmp     rax, rcx
0x140014982  jbe     short loc_140014995
0x140014984  add     rax, r14
0x140014987  jnb     loc_140014A33
0x14001498d  xor     r15d, r15d
0x140014990  jmp     loc_140014AA1
0x140014995  mov     r12, rdx
0x140014998  mov     r15, 8000000000000001h
0x1400149a2  cmp     rdi, rsi
0x1400149a5  jz      loc_140014AA1
0x1400149ab  mov     r8, [rbx+8]
0x1400149af  lea     rbp, [r14+r14]
0x1400149b3  jmp     short loc_1400149DC
0x1400149c0  add     rdi, 4
0x1400149c4  mov     [r8+r14*4], r13d
0x1400149c8  inc     r14
0x1400149cb  mov     [rbx+10h], r14
0x1400149cf  add     rbp, 2
0x1400149d3  cmp     rdi, rsi
0x1400149d6  jz      loc_140014AA1
0x1400149dc  mov     r13d, [rdi]
0x1400149df  cmp     r14, r12
0x1400149e2  jnz     short loc_1400149C0
0x1400149e4  lea     r12, [r14+1]
0x1400149e8  cmp     r12, rbp
0x1400149eb  cmovbe  r12, rbp
0x1400149ef  cmp     r12, 5
0x1400149f3  mov     eax, 4
0x1400149f8  cmovb   r12, rax
0x1400149fc  mov     [rsp+98h+var_70], 4
0x140014a05  mov     [rsp+98h+var_78], 4
0x140014a0e  lea     rcx, [rsp+98h+var_60]
0x140014a13  mov     rdx, r14
0x140014a16  mov     r9, r12
0x140014a19  call    _RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCsdcpJtfrLhSH_7rgncore_llvm_18110786352924170244
0x140014a1e  cmp     dword ptr [rsp+98h+var_60], 1
0x140014a23  jz      short loc_140014A76
0x140014a25  mov     r8, [rsp+98h+var_58]
0x140014a2a  mov     [rbx+8], r8
0x140014a2e  mov     [rbx], r12
0x140014a31  jmp     short loc_1400149C0
0x140014a33  lea     rcx, [rdx+rdx]
0x140014a37  cmp     rax, rcx
0x140014a3a  cmova   rcx, rax
0x140014a3e  cmp     rcx, 5
0x140014a42  mov     r12d, 4
0x140014a48  cmovnb  r12, rcx
0x140014a4c  mov     r8, [rbx+8]
0x140014a50  mov     [rsp+98h+var_70], 4
0x140014a59  mov     [rsp+98h+var_78], 4
0x140014a62  lea     rcx, [rsp+98h+var_60]
0x140014a67  mov     r9, r12
0x140014a6a  call    _RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCsdcpJtfrLhSH_7rgncore_llvm_18110786352924170244
0x140014a6f  cmp     dword ptr [rsp+98h+var_60], 1
0x140014a74  jnz     short loc_140014A82
0x140014a76  mov     r15, [rsp+98h+var_58]
0x140014a7b  mov     rdx, [rsp+98h+var_50]
0x140014a80  jmp     short loc_140014AA1
0x140014a82  mov     rax, [rsp+98h+var_58]
0x140014a87  mov     [rbx+8], rax
0x140014a8b  mov     [rbx], r12
0x140014a8e  mov     r15, 8000000000000001h
0x140014a98  cmp     rdi, rsi
0x140014a9b  jnz     loc_1400149AB
0x140014aa1  mov     rax, [rsp+98h+var_48]
0x140014aa6  xor     rax, rsp
0x140014aa9  mov     rcx, cs:__security_cookie
0x140014ab0  cmp     rcx, rax
0x140014ab3  jnz     short loc_140014AC9
0x140014ab5  mov     rax, r15
0x140014ab8  add     rsp, 58h
0x140014abc  pop     rbx
0x140014abd  pop     rbp
0x140014abe  pop     rdi
0x140014abf  pop     rsi
0x140014ac0  pop     r12
0x140014ac2  pop     r13
0x140014ac4  pop     r14
0x140014ac6  pop     r15
0x140014ac8  retn
0x140014ac9  mov     rcx, [rsp+98h+var_48]
0x140014ace  xor     rcx, rsp; StackCookie
0x140014ad1  call    __security_check_cookie
```
