# _RINvXCs3PyRTeGQ7Na_12fallible_vecINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEINtB3_11FallibleVeclB13_E13try_splice_inINtNtNtNtCs9MWeMO1rkJG_4core4iter8adapters3map3MapINtNtNtB2O_5slice4iter7IterMutlENCNvMs1_NtCsdcpJtfrLhSH_7rgncore4scanINtB47_12ScanInternalQBv_B13_E16merge_in_x_walls0EINtNtNtB2O_3ops5range5RangejEEB49_

- ea: `0x140014dd0`
- end: `0x1400153ad`
- name: `_RINvXCs3PyRTeGQ7Na_12fallible_vecINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEINtB3_11FallibleVeclB13_E13try_splice_inINtNtNtNtCs9MWeMO1rkJG_4core4iter8adapters3map3MapINtNtNtB2O_5slice4iter7IterMutlENCNvMs1_NtCsdcpJtfrLhSH_7rgncore4scanINtB47_12ScanInternalQBv_B13_E16merge_in_x_walls0EINtNtNtB2O_3ops5range5RangejEEB49_`
- size: `1501`
- prototype: `unsigned __int64 __fastcall(__int64 *, unsigned __int64, unsigned __int64, char *, char *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140012420`

## callees

- `0x14000fda0`
- `0x140014940`
- `0x140014dd0`
- `0x14001790a`
- `0x140017a10`
- `0x140017b00`
- `0x140018450`
- `0x1400184d7`
- `0x140018690`
- `0x1400193b0`

## pseudocode

```c
unsigned __int64 __fastcall RINvXCs3PyRTeGQ7Na_12fallible_vecINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEINtB3_11FallibleVeclB13_E13try_splice_inINtNtNtNtCs9MWeMO1rkJG_4core4iter8adapters3map3MapINtNtNtB2O_5slice4iter7IterMutlENCNvMs1_NtCsdcpJtfrLhSH_7rgncore4scanINtB47_12ScanInternalQBv_B13_E16merge_in_x_walls0EINtNtNtB2O_3ops5range5RangejEEB49_(
        __int64 *a1,
        unsigned __int64 a2,
        unsigned __int64 a3,
        char *a4,
        char *a5)
{
  unsigned __int64 v5; // rbx
  unsigned __int64 v6; // r13
  unsigned __int64 v7; // rsi
  char *v8; // r15
  __int64 v10; // rax
  unsigned __int64 v11; // rdx
  unsigned __int64 v12; // rcx
  unsigned __int64 v13; // rcx
  __int64 v14; // r9
  __int64 v15; // r10
  unsigned __int64 v16; // rcx
  __int64 v17; // r9
  __int64 v18; // r10
  __int128 v19; // xmm1
  int v20; // ecx
  signed __int64 v21; // rcx
  unsigned __int64 v22; // r13
  __int64 v23; // rdx
  __int64 v24; // rbp
  char *v25; // r14
  unsigned __int64 v26; // rcx
  unsigned __int64 v27; // rax
  char *v28; // rdx
  int v29; // ecx
  unsigned __int64 v30; // r14
  __int64 v31; // rax
  __int64 v32; // r12
  _DWORD *v33; // rbx
  unsigned __int64 v34; // rdx
  __int64 v35; // rsi
  __int64 v36; // rax
  __int64 v37; // r13
  _DWORD *v38; // rcx
  __int64 v39; // rax
  unsigned __int64 v40; // r15
  __int64 v41; // rax
  unsigned __int64 v42; // r9
  __int64 v43; // r8
  int *v44; // rdx
  _DWORD *v45; // rax
  int v46; // r8d
  unsigned __int64 v47; // rcx
  __int64 v48; // rdx
  unsigned __int64 v49; // rcx
  __int64 v50; // r9
  __int128 v51; // xmm1
  unsigned __int64 v53; // rcx
  __int64 v54; // r14
  __int64 v55; // r9
  __int64 v56; // r11
  __int128 v57; // xmm1
  unsigned __int64 v58; // rbp
  unsigned __int64 v59; // rdx
  __int64 v60; // r15
  __int64 v61; // [rsp+0h] [rbp-98h] BYREF
  signed __int64 v62; // [rsp+30h] [rbp-68h]
  __int64 v63; // [rsp+38h] [rbp-60h] BYREF
  __int64 v64; // [rsp+40h] [rbp-58h]
  unsigned __int64 v65; // [rsp+48h] [rbp-50h]
  __int64 v66; // [rsp+50h] [rbp-48h]

  v5 = a1[2];
  v6 = v5 - a3;
  if ( v5 < a3 )
    RNvNtNtCs9MWeMO1rkJG_4core5slice5index16slice_index_fail(
      0,
      a3,
      v5,
      &anon_c9360f58bbc394745aa7882ed1343abe_1_llvm_18110786352924170244);
  v7 = a2;
  if ( a2 > a3 )
    goto LABEL_93;
  v8 = a4;
  if ( a2 >= a3 )
    goto LABEL_22;
  v10 = a1[1];
  v11 = a3 + ~a2;
  if ( (unsigned __int64)(a5 - a4) >> 2 < v11 )
    v11 = (unsigned __int64)(a5 - a4) >> 2;
  v12 = 0;
  if ( v5 >= v7 )
    v12 = v5 - v7;
  if ( v11 < v12 )
    v12 = v11;
  if ( v12 > 0xB && (((_BYTE)a5 - (_BYTE)a4) & 3) == 0 && v10 + 4 * v7 - (unsigned __int64)a4 >= 0x20 )
  {
    v13 = v12 + 1;
    v14 = 4 * v7;
    v15 = 8;
    if ( (v13 & 7) != 0 )
      v15 = v13 & 7;
    v16 = v13 - v15;
    v7 += v16;
    v17 = v10 + v14 + 16;
    v18 = 0;
    do
    {
      v19 = *(_OWORD *)&v8[4 * v18 + 16];
      *(_OWORD *)(v17 + 4 * v18 - 16) = *(_OWORD *)&v8[4 * v18];
      *(_OWORD *)(v17 + 4 * v18) = v19;
      v18 += 8;
    }
    while ( v16 != v18 );
    v8 += 4 * v16;
  }
  do
  {
    if ( v8 == a5 )
    {
      if ( v7 <= a3 )
      {
        a1[2] = v7;
        v30 = 0x8000000000000001uLL;
        if ( v7 == a3 )
        {
          if ( v5 != a3 )
            a1[2] = v5;
        }
        else if ( v5 != a3 )
        {
          memmove((void *)(v10 + 4 * v7), (const void *)(v10 + 4 * a3), 4 * v6);
          a1[2] = v7 + v6;
        }
        goto LABEL_71;
      }
LABEL_93:
      RNvNtNtCs9MWeMO1rkJG_4core5slice5index16slice_index_fail(
        v7,
        a3,
        v5,
        &anon_c9360f58bbc394745aa7882ed1343abe_2_llvm_18110786352924170244);
    }
    if ( v7 >= v5 )
      RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(v7, v5, &off_14001C4A8);
    v20 = *(_DWORD *)v8;
    v8 += 4;
    *(_DWORD *)(v10 + 4 * v7++) = v20;
  }
  while ( a3 != v7 );
  v7 = a3;
LABEL_22:
  v21 = a5 - v8;
  if ( a5 != v8 )
  {
    v22 = (unsigned __int64)(a5 - v8) >> 2;
    v23 = *a1;
    if ( v22 <= *a1 - v5 )
    {
      v24 = a1[1];
      goto LABEL_25;
    }
    v62 = a5 - v8;
    v53 = 2 * v23;
    if ( v5 + v22 > 2 * v23 )
      v53 = v5 + v22;
    v54 = 4;
    if ( v53 >= 5 )
      v54 = v53;
    RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCsdcpJtfrLhSH_7rgncore_llvm_18110786352924170244(
      &v63,
      v23,
      a1[1],
      v54,
      4,
      4);
    if ( (_BYTE)v63 )
    {
      v30 = v64;
      goto LABEL_71;
    }
    v24 = v64;
    a1[1] = v64;
    *a1 = v54;
    v21 = v62;
LABEL_25:
    v25 = (char *)(v24 + 4 * v7);
    memmove(&v25[v21], v25, 4 * (v5 - v7));
    v26 = v22 - 1;
    if ( !v22 )
      v26 = 0;
    if ( v26 < 0x10 || (((_BYTE)a5 - (_BYTE)v8) & 3) != 0 || (unsigned __int64)(v25 - v8) < 0x20 )
    {
      v27 = v7;
      v28 = v8;
    }
    else
    {
      v47 = v26 + 1;
      v48 = 8;
      if ( (v47 & 7) != 0 )
        v48 = v47 & 7;
      v49 = v47 - v48;
      v27 = v7 + v49;
      v28 = &v8[4 * v49];
      v50 = 0;
      do
      {
        v51 = *(_OWORD *)&v8[4 * v50 + 16];
        *(_OWORD *)(v24 + 4 * v7 + 4 * v50) = *(_OWORD *)&v8[4 * v50];
        *(_OWORD *)(v24 + 4 * v7 + 16 + 4 * v50) = v51;
        v50 += 8;
      }
      while ( v49 != v50 );
    }
    v7 += v22;
    v8 = v28;
    do
    {
      if ( v8 == a5 )
        RNvNtCs9MWeMO1rkJG_4core6option13unwrap_failed(&off_14001C490);
      v29 = *(_DWORD *)v8;
      v8 += 4;
      *(_DWORD *)(v24 + 4 * v27++) = v29;
    }
    while ( v7 != v27 );
    a1[2] = v5 + v22;
  }
  v30 = 0x8000000000000001uLL;
  v63 = 0;
  v64 = 4;
  v65 = 0;
  v31 = RINvXCs3PyRTeGQ7Na_12fallible_vecINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEINtB3_11FallibleVeclB13_E10try_extendINtNtNtNtCs9MWeMO1rkJG_4core4iter8adapters3map3MapINtNtNtB2L_5slice4iter7IterMutlENCNvMs1_NtCsdcpJtfrLhSH_7rgncore4scanINtB44_12ScanInternalQBv_B13_E16merge_in_x_walls0EEB46_(
          &v63,
          v8,
          a5);
  if ( v31 != 0x8000000000000001uLL )
  {
    if ( v63 )
    {
      v35 = v31;
      if ( v63 == 28 )
        RNvNtCsdwtLm5uWta6_10gdi_region3ffi22ScanLookAsideList_Free(v64);
      else
        Win32FreePool_0(v64);
      v31 = v35;
    }
    v30 = v31;
    goto LABEL_71;
  }
  v32 = v63;
  v33 = (_DWORD *)v64;
  v34 = v65;
  if ( v63 == 0x8000000000000000uLL )
  {
    v30 = v64;
    goto LABEL_71;
  }
  if ( !v65 )
    goto LABEL_62;
  v36 = *a1;
  v37 = a1[2];
  if ( v65 <= *a1 - v37 )
  {
    v39 = a1[1];
    goto LABEL_57;
  }
  if ( __CFADD__(v65, v37) )
  {
    v30 = 0;
    if ( !v63 )
      goto LABEL_71;
LABEL_49:
    v38 = v33;
    if ( v32 == 28 )
    {
LABEL_50:
      RNvNtCsdwtLm5uWta6_10gdi_region3ffi22ScanLookAsideList_Free(v33);
      goto LABEL_71;
    }
LABEL_70:
    Win32FreePool_0(v38);
    goto LABEL_71;
  }
  v58 = v65;
  v59 = 2 * v36;
  if ( v65 + v37 > 2 * v36 )
    v59 = v65 + v37;
  v60 = 4;
  if ( v59 >= 5 )
    v60 = v59;
  RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCsdcpJtfrLhSH_7rgncore_llvm_18110786352924170244(
    &v63,
    v36,
    a1[1],
    v60,
    4,
    4);
  if ( (_DWORD)v63 != 1 )
  {
    v39 = v64;
    a1[1] = v64;
    *a1 = v60;
    v34 = v58;
LABEL_57:
    v40 = v34;
    memmove((void *)(v39 + 4 * v7 + 4 * v34), (const void *)(v39 + 4 * v7), 4 * (v37 - v7));
    a1[2] = v40 + v37;
    v41 = a1[1];
    v42 = 4 * v40 - 4;
    if ( v42 < 0x2C || v41 + 4 * v7 - (unsigned __int64)v33 < 0x20 )
    {
      v43 = 0;
      v44 = v33;
LABEL_60:
      v45 = (_DWORD *)(4 * v7 + 4 * v43 + v41);
      do
      {
        v46 = *v44++;
        *v45++ = v46;
      }
      while ( v44 != &v33[v40] );
      goto LABEL_62;
    }
    v55 = (v42 >> 2) + 1;
    v43 = v55 & 0x7FFFFFFFFFFFFFF8LL;
    v44 = &v33[v55 & 0x7FFFFFFFFFFFFFF8LL];
    v56 = 0;
    do
    {
      v57 = *(_OWORD *)&v33[v56 + 4];
      *(_OWORD *)(v41 + 4 * v7 + 4 * v56) = *(_OWORD *)&v33[v56];
      *(_OWORD *)(v41 + 4 * v7 + 16 + 4 * v56) = v57;
      v56 += 8;
    }
    while ( v43 != v56 );
    if ( v55 != v43 )
      goto LABEL_60;
LABEL_62:
    if ( !v32 )
      goto LABEL_71;
    v38 = v33;
    if ( v32 == 28 )
      goto LABEL_50;
    goto LABEL_70;
  }
  v30 = v64;
  if ( v32 )
    goto LABEL_49;
LABEL_71:
  if ( _security_cookie != ((unsigned __int64)&v61 ^ v66) )
    JUMPOUT(0x1400153ACLL);
  return v30;
}

```

## disassembly

```asm
0x140014dd0  push    r15
0x140014dd2  push    r14
0x140014dd4  push    r13
0x140014dd6  push    r12
0x140014dd8  push    rsi
0x140014dd9  push    rdi
0x140014dda  push    rbp
0x140014ddb  push    rbx
0x140014ddc  sub     rsp, 58h
0x140014de0  mov     rax, cs:__security_cookie
0x140014de7  xor     rax, rsp
0x140014dea  mov     [rsp+98h+var_48], rax
0x140014def  mov     rbx, [rcx+10h]
0x140014df3  mov     r13, rbx
0x140014df6  sub     r13, r8
0x140014df9  jb      loc_14001536D
0x140014dff  mov     rsi, rdx
0x140014e02  cmp     rdx, r8
0x140014e05  ja      loc_140015358
0x140014e0b  mov     r15, r9
0x140014e0e  mov     rdi, rcx
0x140014e11  mov     r12, [rsp+98h+arg_20]
0x140014e19  jnb     loc_140014EF7
0x140014e1f  mov     rax, [rdi+8]
0x140014e23  mov     rcx, r12
0x140014e26  sub     rcx, r15
0x140014e29  shr     rcx, 2
0x140014e2d  mov     rdx, rsi
0x140014e30  not     rdx
0x140014e33  add     rdx, r8
0x140014e36  cmp     rcx, rdx
0x140014e39  cmovb   rdx, rcx
0x140014e3d  xor     ecx, ecx
0x140014e3f  mov     r9, rbx
0x140014e42  sub     r9, rsi
0x140014e45  cmovnb  rcx, r9
0x140014e49  cmp     rdx, rcx
0x140014e4c  cmovb   rcx, rdx
0x140014e50  cmp     rcx, 0Bh
0x140014e54  jbe     short loc_140014ED0
0x140014e56  mov     edx, r12d
0x140014e59  sub     edx, r15d
0x140014e5c  test    dl, 3
0x140014e5f  jnz     short loc_140014ED0
0x140014e61  lea     rdx, [rax+rsi*4]
0x140014e65  sub     rdx, r15
0x140014e68  cmp     rdx, 20h ; ' '
0x140014e6c  jb      short loc_140014ED0
0x140014e6e  inc     rcx
0x140014e71  lea     r9, ds:0[rsi*4]
0x140014e79  mov     edx, ecx
0x140014e7b  and     edx, 7
0x140014e7e  mov     r10d, 8
0x140014e84  cmovnz  r10, rdx
0x140014e88  sub     rcx, r10
0x140014e8b  add     rsi, rcx
0x140014e8e  lea     rdx, [r15+rcx*4]
0x140014e92  add     r9, rax
0x140014e95  add     r9, 10h
0x140014e99  xor     r10d, r10d
0x140014e9c  nop     dword ptr [rax+00h]
0x140014ea0  movups  xmm0, xmmword ptr [r15+r10*4]
0x140014ea5  movups  xmm1, xmmword ptr [r15+r10*4+10h]
0x140014eab  movups  xmmword ptr [r9+r10*4-10h], xmm0
0x140014eb1  movups  xmmword ptr [r9+r10*4], xmm1
0x140014eb6  add     r10, 8
0x140014eba  cmp     rcx, r10
0x140014ebd  jnz     short loc_140014EA0
0x140014ebf  mov     r15, rdx
0x140014ec2  nop     word ptr [rax+rax+00000000h]
0x140014ed0  cmp     r15, r12
0x140014ed3  jz      loc_14001502A
0x140014ed9  cmp     rsi, rbx
0x140014edc  jnb     loc_14001538D
0x140014ee2  mov     ecx, [r15]
0x140014ee5  add     r15, 4
0x140014ee9  mov     [rax+rsi*4], ecx
0x140014eec  inc     rsi
0x140014eef  cmp     r8, rsi
0x140014ef2  jnz     short loc_140014ED0
0x140014ef4  mov     rsi, r8
0x140014ef7  mov     r13, r12
0x140014efa  sub     r13, r15
0x140014efd  mov     rcx, r12
0x140014f00  sub     rcx, r15
0x140014f03  jz      loc_140014FA3
0x140014f09  shr     r13, 2
0x140014f0d  mov     rdx, [rdi]
0x140014f10  mov     rax, rdx
0x140014f13  sub     rax, rbx
0x140014f16  cmp     r13, rax
0x140014f19  ja      loc_140015205
0x140014f1f  mov     rbp, [rdi+8]
0x140014f23  lea     r14, ds:0[rsi*4]
0x140014f2b  add     r14, rbp
0x140014f2e  add     rcx, r14; void *
0x140014f31  mov     r8, rbx
0x140014f34  sub     r8, rsi
0x140014f37  shl     r8, 2; Size
0x140014f3b  mov     rdx, r14; Src
0x140014f3e  call    memmove
0x140014f43  lea     rcx, [r13-1]
0x140014f47  cmp     r13, rcx
0x140014f4a  cmovb   rcx, r13
0x140014f4e  cmp     rcx, 10h
0x140014f52  jb      short loc_140014F6B
0x140014f54  mov     eax, r12d
0x140014f57  sub     eax, r15d
0x140014f5a  test    al, 3
0x140014f5c  jnz     short loc_140014F6B
0x140014f5e  sub     r14, r15
0x140014f61  cmp     r14, 20h ; ' '
0x140014f65  jnb     loc_140015178
0x140014f6b  mov     rax, rsi
0x140014f6e  mov     rdx, r15
0x140014f71  add     rsi, r13
0x140014f74  mov     r15, rdx
0x140014f77  nop     word ptr [rax+rax+00000000h]
0x140014f80  cmp     r15, r12
0x140014f83  jz      loc_140015381
0x140014f89  mov     ecx, [r15]
0x140014f8c  add     r15, 4
0x140014f90  mov     [rbp+rax*4+0], ecx
0x140014f94  inc     rax
0x140014f97  cmp     rsi, rax
0x140014f9a  jnz     short loc_140014F80
0x140014f9c  add     r13, rbx
0x140014f9f  mov     [rdi+10h], r13
0x140014fa3  mov     r14, 8000000000000001h
0x140014fad  mov     [rsp+98h+var_60], 0
0x140014fb6  mov     [rsp+98h+var_58], 4
0x140014fbf  mov     [rsp+98h+var_50], 0
0x140014fc8  lea     rcx, [rsp+98h+var_60]
0x140014fcd  mov     rdx, r15
0x140014fd0  mov     r8, r12
0x140014fd3  call    _RINvXCs3PyRTeGQ7Na_12fallible_vecINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEINtB3_11FallibleVeclB13_E10try_extendINtNtNtNtCs9MWeMO1rkJG_4core4iter8adapters3map3MapINtNtNtB2L_5slice4iter7IterMutlENCNvMs1_NtCsdcpJtfrLhSH_7rgncore4scanINtB44_12ScanInternalQBv_B13_E16merge_in_x_walls0EEB46_
0x140014fd8  cmp     rax, r14
0x140014fdb  jnz     short loc_140014FFD
0x140014fdd  mov     r12, [rsp+98h+var_60]
0x140014fe2  mov     rbx, [rsp+98h+var_58]
0x140014fe7  mov     rdx, [rsp+98h+var_50]
0x140014fec  lea     rax, [r14-1]
0x140014ff0  cmp     r12, rax
0x140014ff3  jnz     short loc_140015055
0x140014ff5  mov     r14, rbx
0x140014ff8  jmp     loc_1400151D9
0x140014ffd  mov     r8, [rsp+98h+var_60]
0x140015002  test    r8, r8
0x140015005  jz      loc_1400150DA
0x14001500b  mov     rsi, rax
0x14001500e  mov     rdi, rdx
0x140015011  mov     rcx, [rsp+98h+var_58]
0x140015016  cmp     r8, 1Ch
0x14001501a  jnz     loc_1400150CF
0x140015020  call    _RNvNtCsdwtLm5uWta6_10gdi_region3ffi22ScanLookAsideList_Free
0x140015025  jmp     loc_1400150D4
0x14001502a  cmp     rsi, r8
0x14001502d  ja      loc_140015358
0x140015033  mov     [rdi+10h], rsi
0x140015037  mov     r14, 8000000000000001h
0x140015041  jnz     short loc_1400150A5
0x140015043  cmp     rbx, r8
0x140015046  jz      loc_1400151D9
0x14001504c  mov     [rdi+10h], rbx
0x140015050  jmp     loc_1400151D9
0x140015055  test    rdx, rdx
0x140015058  jz      loc_140015163
0x14001505e  mov     rax, [rdi]
0x140015061  mov     r13, [rdi+10h]
0x140015065  mov     rcx, rax
0x140015068  sub     rcx, r13
0x14001506b  cmp     rdx, rcx
0x14001506e  jbe     short loc_1400150E2
0x140015070  mov     rcx, r13
0x140015073  add     rcx, rdx
0x140015076  jnb     loc_1400152E3
0x14001507c  xor     r14d, r14d
0x14001507f  test    r12, r12
0x140015082  jz      loc_1400151D9
0x140015088  mov     rsi, rdx
0x14001508b  mov     rcx, rbx
0x14001508e  cmp     r12, 1Ch
0x140015092  jnz     loc_140015260
0x140015098  call    _RNvNtCsdwtLm5uWta6_10gdi_region3ffi22ScanLookAsideList_Free
0x14001509d  mov     rdx, rsi
0x1400150a0  jmp     loc_1400151D9
0x1400150a5  cmp     rbx, r8
0x1400150a8  jz      loc_1400151D9
0x1400150ae  lea     rcx, [rax+rsi*4]; void *
0x1400150b2  lea     rdx, [rax+r8*4]; Src
0x1400150b6  lea     r8, ds:0[r13*4]; Size
0x1400150be  call    memmove
0x1400150c3  add     r13, rsi
0x1400150c6  mov     [rdi+10h], r13
0x1400150ca  jmp     loc_1400151D9
0x1400150cf  call    Win32FreePool_0
0x1400150d4  mov     rdx, rdi
0x1400150d7  mov     rax, rsi
0x1400150da  mov     r14, rax
0x1400150dd  jmp     loc_1400151D9
0x1400150e2  mov     rax, [rdi+8]
0x1400150e6  lea     rax, [rax+rsi*4]
0x1400150ea  lea     rcx, [rax+rdx*4]; void *
0x1400150ee  mov     r8, r13
0x1400150f1  sub     r8, rsi
0x1400150f4  shl     r8, 2; Size
0x1400150f8  mov     r15, rdx
0x1400150fb  mov     rdx, rax; Src
0x1400150fe  call    memmove
0x140015103  mov     rcx, r15
0x140015106  add     r13, r15
0x140015109  mov     [rdi+10h], r13
0x14001510d  mov     rax, [rdi+8]
0x140015111  lea     r9, ds:0FFFFFFFFFFFFFFFCh[r15*4]
0x140015119  cmp     r9, 2Ch ; ','
0x14001511d  jb      short loc_140015130
0x14001511f  lea     rdx, [rax+rsi*4]
0x140015123  sub     rdx, rbx
0x140015126  cmp     rdx, 20h ; ' '
0x14001512a  jnb     loc_14001526D
0x140015130  xor     r8d, r8d
0x140015133  mov     rdx, rbx
0x140015136  lea     rcx, [rbx+rcx*4]
0x14001513a  shl     rsi, 2
0x14001513e  lea     r8, [rsi+r8*4]
0x140015142  add     rax, r8
0x140015145  nop     word ptr [rax+rax+00000000h]
0x140015150  mov     r8d, [rdx]
0x140015153  add     rdx, 4
0x140015157  mov     [rax], r8d
0x14001515a  add     rax, 4
0x14001515e  cmp     rdx, rcx
0x140015161  jnz     short loc_140015150
0x140015163  test    r12, r12
0x140015166  jz      short loc_1400151D9
0x140015168  mov     rcx, rbx
0x14001516b  cmp     r12, 1Ch
0x14001516f  jnz     short loc_1400151D4
0x140015171  call    _RNvNtCsdwtLm5uWta6_10gdi_region3ffi22ScanLookAsideList_Free
0x140015176  jmp     short loc_1400151D9
0x140015178  inc     rcx
0x14001517b  lea     r8, ds:0[rsi*4]
0x140015183  mov     eax, ecx
0x140015185  and     eax, 7
0x140015188  mov     edx, 8
0x14001518d  cmovnz  rdx, rax
0x140015191  sub     rcx, rdx
0x140015194  lea     rax, [rsi+rcx]
0x140015198  lea     rdx, [r15+rcx*4]
0x14001519c  add     r8, rbp
0x14001519f  add     r8, 10h
0x1400151a3  xor     r9d, r9d
0x1400151a6  nop     word ptr [rax+rax+00000000h]
0x1400151b0  movups  xmm0, xmmword ptr [r15+r9*4]
0x1400151b5  movups  xmm1, xmmword ptr [r15+r9*4+10h]
0x1400151bb  movups  xmmword ptr [r8+r9*4-10h], xmm0
0x1400151c1  movups  xmmword ptr [r8+r9*4], xmm1
0x1400151c6  add     r9, 8
0x1400151ca  cmp     rcx, r9
0x1400151cd  jnz     short loc_1400151B0
0x1400151cf  jmp     loc_140014F71
0x1400151d4  call    Win32FreePool_0
0x1400151d9  mov     rax, [rsp+98h+var_48]
0x1400151de  xor     rax, rsp
0x1400151e1  mov     rcx, cs:__security_cookie
0x1400151e8  cmp     rcx, rax
0x1400151eb  jnz     loc_14001539F
0x1400151f1  mov     rax, r14
0x1400151f4  add     rsp, 58h
0x1400151f8  pop     rbx
0x1400151f9  pop     rbp
0x1400151fa  pop     rdi
0x1400151fb  pop     rsi
0x1400151fc  pop     r12
0x1400151fe  pop     r13
0x140015200  pop     r14
0x140015202  pop     r15
0x140015204  retn
0x140015205  mov     [rsp+98h+var_68], rcx
0x14001520a  lea     rax, [rbx+r13]
0x14001520e  lea     rcx, [rdx+rdx]
0x140015212  cmp     rax, rcx
0x140015215  cmova   rcx, rax
0x140015219  cmp     rcx, 5
0x14001521d  mov     r14d, 4
0x140015223  cmovnb  r14, rcx
0x140015227  mov     r8, [rdi+8]
0x14001522b  mov     [rsp+98h+var_70], 4
0x140015234  mov     [rsp+98h+var_78], 4
0x14001523d  lea     rcx, [rsp+98h+var_60]
0x140015242  mov     r9, r14
0x140015245  call    _RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCsdcpJtfrLhSH_7rgncore_llvm_18110786352924170244
0x14001524a  cmp     byte ptr [rsp+98h+var_60], 0
0x14001524f  jz      short loc_1400152CD
0x140015251  mov     r14, [rsp+98h+var_58]
0x140015256  mov     rdx, [rsp+98h+var_50]
0x14001525b  jmp     loc_1400151D9
0x140015260  call    Win32FreePool_0
0x140015265  mov     rdx, rsi
0x140015268  jmp     loc_1400151D9
  ... truncated ...
```
