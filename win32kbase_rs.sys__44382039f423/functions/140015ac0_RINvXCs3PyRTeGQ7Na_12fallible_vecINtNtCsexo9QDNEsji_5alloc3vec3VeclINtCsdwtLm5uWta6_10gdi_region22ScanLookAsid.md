# _RINvXCs3PyRTeGQ7Na_12fallible_vecINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEINtB3_11FallibleVeclB13_E13try_splice_inINtNtNtNtCs9MWeMO1rkJG_4core4iter8adapters6cloned6ClonedINtNtNtB2O_5slice4iter4IterlEEINtNtNtB2O_3ops5range5RangejEECsdcpJtfrLhSH_7rgncore

- ea: `0x140015ac0`
- end: `0x14001609d`
- name: `_RINvXCs3PyRTeGQ7Na_12fallible_vecINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEINtB3_11FallibleVeclB13_E13try_splice_inINtNtNtNtCs9MWeMO1rkJG_4core4iter8adapters6cloned6ClonedINtNtNtB2O_5slice4iter4IterlEEINtNtNtB2O_3ops5range5RangejEECsdcpJtfrLhSH_7rgncore`
- size: `1501`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000c640`
- `0x14000cc10`

## callees

- `0x14000fda0`
- `0x140014940`
- `0x140015ac0`
- `0x14001790a`
- `0x140017a10`
- `0x140017b00`
- `0x140018450`
- `0x1400184d7`
- `0x140018690`
- `0x1400193b0`

## pseudocode

```c
unsigned __int64 __fastcall RINvXCs3PyRTeGQ7Na_12fallible_vecINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEINtB3_11FallibleVeclB13_E13try_splice_inINtNtNtNtCs9MWeMO1rkJG_4core4iter8adapters6cloned6ClonedINtNtNtB2O_5slice4iter4IterlEEINtNtNtB2O_3ops5range5RangejEECsdcpJtfrLhSH_7rgncore(
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
  int v28; // ecx
  unsigned __int64 v29; // r14
  __int64 v30; // rax
  __int64 v31; // r12
  _DWORD *v32; // rbx
  unsigned __int64 v33; // rdx
  __int64 v34; // rsi
  __int64 v35; // rax
  __int64 v36; // r13
  _DWORD *v37; // rcx
  __int64 v38; // rax
  unsigned __int64 v39; // r15
  __int64 v40; // rax
  unsigned __int64 v41; // r9
  __int64 v42; // r8
  int *v43; // rdx
  _DWORD *v44; // rax
  int v45; // r8d
  unsigned __int64 v46; // rcx
  __int64 v47; // rdx
  unsigned __int64 v48; // rcx
  __int64 v49; // r9
  __int128 v50; // xmm1
  unsigned __int64 v52; // rcx
  unsigned __int64 v53; // r14
  __int64 v54; // r9
  __int64 v55; // r11
  __int128 v56; // xmm1
  unsigned __int64 v57; // rbp
  unsigned __int64 v58; // rdx
  unsigned __int64 v59; // r15
  __int64 v60; // [rsp+0h] [rbp-98h] BYREF
  signed __int64 v61; // [rsp+30h] [rbp-68h]
  __int64 v62; // [rsp+38h] [rbp-60h] BYREF
  __int64 v63; // [rsp+40h] [rbp-58h]
  unsigned __int64 v64; // [rsp+48h] [rbp-50h]
  __int64 v65; // [rsp+50h] [rbp-48h]

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
        v29 = 0x8000000000000001uLL;
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
    v61 = a5 - v8;
    v52 = 2 * v23;
    if ( v5 + v22 > 2 * v23 )
      v52 = v5 + v22;
    v53 = 4;
    if ( v52 >= 5 )
      v53 = v52;
    RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCsdcpJtfrLhSH_7rgncore_llvm_18110786352924170244(
      &v62,
      v23,
      (const void *)a1[1],
      v53,
      4u,
      4u);
    if ( (_BYTE)v62 )
    {
      v29 = v63;
      goto LABEL_71;
    }
    v24 = v63;
    a1[1] = v63;
    *a1 = v53;
    v21 = v61;
LABEL_25:
    v25 = (char *)(v24 + 4 * v7);
    memmove(&v25[v21], v25, 4 * (v5 - v7));
    v26 = v22 - 1;
    if ( !v22 )
      v26 = 0;
    if ( v26 < 0x10 || (((_BYTE)a5 - (_BYTE)v8) & 3) != 0 || (unsigned __int64)(v25 - v8) < 0x20 )
    {
      v27 = v7;
    }
    else
    {
      v46 = v26 + 1;
      v47 = 8;
      if ( (v46 & 7) != 0 )
        v47 = v46 & 7;
      v48 = v46 - v47;
      v27 = v7 + v48;
      v49 = 0;
      do
      {
        v50 = *(_OWORD *)&v8[4 * v49 + 16];
        *(_OWORD *)(v24 + 4 * v7 + 4 * v49) = *(_OWORD *)&v8[4 * v49];
        *(_OWORD *)(v24 + 4 * v7 + 16 + 4 * v49) = v50;
        v49 += 8;
      }
      while ( v48 != v49 );
      v8 += 4 * v48;
    }
    v7 += v22;
    do
    {
      if ( v8 == a5 )
        RNvNtCs9MWeMO1rkJG_4core6option13unwrap_failed(&off_14001C490);
      v28 = *(_DWORD *)v8;
      v8 += 4;
      *(_DWORD *)(v24 + 4 * v27++) = v28;
    }
    while ( v7 != v27 );
    a1[2] = v5 + v22;
  }
  v29 = 0x8000000000000001uLL;
  v62 = 0;
  v63 = 4;
  v64 = 0;
  v30 = RINvXCs3PyRTeGQ7Na_12fallible_vecINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEINtB3_11FallibleVeclB13_E10try_extendINtNtNtNtCs9MWeMO1rkJG_4core4iter8adapters3map3MapINtNtNtB2L_5slice4iter7IterMutlENCNvMs1_NtCsdcpJtfrLhSH_7rgncore4scanINtB44_12ScanInternalQBv_B13_E16merge_in_x_walls0EEB46_(
          &v62,
          v8,
          a5);
  if ( v30 != 0x8000000000000001uLL )
  {
    if ( v62 )
    {
      v34 = v30;
      if ( v62 == 28 )
        RNvNtCsdwtLm5uWta6_10gdi_region3ffi22ScanLookAsideList_Free(v63);
      else
        Win32FreePool_0(v63);
      v30 = v34;
    }
    v29 = v30;
    goto LABEL_71;
  }
  v31 = v62;
  v32 = (_DWORD *)v63;
  v33 = v64;
  if ( v62 == 0x8000000000000000uLL )
  {
    v29 = v63;
    goto LABEL_71;
  }
  if ( !v64 )
    goto LABEL_62;
  v35 = *a1;
  v36 = a1[2];
  if ( v64 <= *a1 - v36 )
  {
    v38 = a1[1];
    goto LABEL_57;
  }
  if ( __CFADD__(v64, v36) )
  {
    v29 = 0;
    if ( !v62 )
      goto LABEL_71;
LABEL_49:
    v37 = v32;
    if ( v31 == 28 )
    {
LABEL_50:
      RNvNtCsdwtLm5uWta6_10gdi_region3ffi22ScanLookAsideList_Free(v32);
      goto LABEL_71;
    }
LABEL_70:
    Win32FreePool_0(v37);
    goto LABEL_71;
  }
  v57 = v64;
  v58 = 2 * v35;
  if ( v64 + v36 > 2 * v35 )
    v58 = v64 + v36;
  v59 = 4;
  if ( v58 >= 5 )
    v59 = v58;
  RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCsdcpJtfrLhSH_7rgncore_llvm_18110786352924170244(
    &v62,
    v35,
    (const void *)a1[1],
    v59,
    4u,
    4u);
  if ( (_DWORD)v62 != 1 )
  {
    v38 = v63;
    a1[1] = v63;
    *a1 = v59;
    v33 = v57;
LABEL_57:
    v39 = v33;
    memmove((void *)(v38 + 4 * v7 + 4 * v33), (const void *)(v38 + 4 * v7), 4 * (v36 - v7));
    a1[2] = v39 + v36;
    v40 = a1[1];
    v41 = 4 * v39 - 4;
    if ( v41 < 0x2C || v40 + 4 * v7 - (unsigned __int64)v32 < 0x20 )
    {
      v42 = 0;
      v43 = v32;
LABEL_60:
      v44 = (_DWORD *)(4 * v7 + 4 * v42 + v40);
      do
      {
        v45 = *v43++;
        *v44++ = v45;
      }
      while ( v43 != &v32[v39] );
      goto LABEL_62;
    }
    v54 = (v41 >> 2) + 1;
    v42 = v54 & 0x7FFFFFFFFFFFFFF8LL;
    v43 = &v32[v54 & 0x7FFFFFFFFFFFFFF8LL];
    v55 = 0;
    do
    {
      v56 = *(_OWORD *)&v32[v55 + 4];
      *(_OWORD *)(v40 + 4 * v7 + 4 * v55) = *(_OWORD *)&v32[v55];
      *(_OWORD *)(v40 + 4 * v7 + 16 + 4 * v55) = v56;
      v55 += 8;
    }
    while ( v42 != v55 );
    if ( v54 != v42 )
      goto LABEL_60;
LABEL_62:
    if ( !v31 )
      goto LABEL_71;
    v37 = v32;
    if ( v31 == 28 )
      goto LABEL_50;
    goto LABEL_70;
  }
  v29 = v63;
  if ( v31 )
    goto LABEL_49;
LABEL_71:
  if ( _security_cookie != ((unsigned __int64)&v60 ^ v65) )
    JUMPOUT(0x14001609CLL);
  return v29;
}

```

## disassembly

```asm
0x140015ac0  push    r15
0x140015ac2  push    r14
0x140015ac4  push    r13
0x140015ac6  push    r12
0x140015ac8  push    rsi
0x140015ac9  push    rdi
0x140015aca  push    rbp
0x140015acb  push    rbx
0x140015acc  sub     rsp, 58h
0x140015ad0  mov     rax, cs:__security_cookie
0x140015ad7  xor     rax, rsp
0x140015ada  mov     [rsp+98h+var_48], rax
0x140015adf  mov     rbx, [rcx+10h]
0x140015ae3  mov     r13, rbx
0x140015ae6  sub     r13, r8
0x140015ae9  jb      loc_14001605D
0x140015aef  mov     rsi, rdx
0x140015af2  cmp     rdx, r8
0x140015af5  ja      loc_140016048
0x140015afb  mov     r15, r9
0x140015afe  mov     rdi, rcx
0x140015b01  mov     r12, [rsp+98h+arg_20]
0x140015b09  jnb     loc_140015BE7
0x140015b0f  mov     rax, [rdi+8]
0x140015b13  mov     rcx, r12
0x140015b16  sub     rcx, r15
0x140015b19  shr     rcx, 2
0x140015b1d  mov     rdx, rsi
0x140015b20  not     rdx
0x140015b23  add     rdx, r8
0x140015b26  cmp     rcx, rdx
0x140015b29  cmovb   rdx, rcx
0x140015b2d  xor     ecx, ecx
0x140015b2f  mov     r9, rbx
0x140015b32  sub     r9, rsi
0x140015b35  cmovnb  rcx, r9
0x140015b39  cmp     rdx, rcx
0x140015b3c  cmovb   rcx, rdx
0x140015b40  cmp     rcx, 0Bh
0x140015b44  jbe     short loc_140015BC0
0x140015b46  mov     edx, r12d
0x140015b49  sub     edx, r15d
0x140015b4c  test    dl, 3
0x140015b4f  jnz     short loc_140015BC0
0x140015b51  lea     rdx, [rax+rsi*4]
0x140015b55  sub     rdx, r15
0x140015b58  cmp     rdx, 20h ; ' '
0x140015b5c  jb      short loc_140015BC0
0x140015b5e  inc     rcx
0x140015b61  lea     r9, ds:0[rsi*4]
0x140015b69  mov     edx, ecx
0x140015b6b  and     edx, 7
0x140015b6e  mov     r10d, 8
0x140015b74  cmovnz  r10, rdx
0x140015b78  sub     rcx, r10
0x140015b7b  lea     rdx, [r15+rcx*4]
0x140015b7f  add     rsi, rcx
0x140015b82  add     r9, rax
0x140015b85  add     r9, 10h
0x140015b89  xor     r10d, r10d
0x140015b8c  nop     dword ptr [rax+00h]
0x140015b90  movups  xmm0, xmmword ptr [r15+r10*4]
0x140015b95  movups  xmm1, xmmword ptr [r15+r10*4+10h]
0x140015b9b  movups  xmmword ptr [r9+r10*4-10h], xmm0
0x140015ba1  movups  xmmword ptr [r9+r10*4], xmm1
0x140015ba6  add     r10, 8
0x140015baa  cmp     rcx, r10
0x140015bad  jnz     short loc_140015B90
0x140015baf  mov     r15, rdx
0x140015bb2  nop     word ptr [rax+rax+00000000h]
0x140015bc0  cmp     r15, r12
0x140015bc3  jz      loc_140015D1A
0x140015bc9  cmp     rsi, rbx
0x140015bcc  jnb     loc_14001607D
0x140015bd2  mov     ecx, [r15]
0x140015bd5  add     r15, 4
0x140015bd9  mov     [rax+rsi*4], ecx
0x140015bdc  inc     rsi
0x140015bdf  cmp     r8, rsi
0x140015be2  jnz     short loc_140015BC0
0x140015be4  mov     rsi, r8
0x140015be7  mov     r13, r12
0x140015bea  sub     r13, r15
0x140015bed  mov     rcx, r12
0x140015bf0  sub     rcx, r15
0x140015bf3  jz      loc_140015C93
0x140015bf9  shr     r13, 2
0x140015bfd  mov     rdx, [rdi]
0x140015c00  mov     rax, rdx
0x140015c03  sub     rax, rbx
0x140015c06  cmp     r13, rax
0x140015c09  ja      loc_140015EF8
0x140015c0f  mov     rbp, [rdi+8]
0x140015c13  lea     r14, ds:0[rsi*4]
0x140015c1b  add     r14, rbp
0x140015c1e  add     rcx, r14; void *
0x140015c21  mov     r8, rbx
0x140015c24  sub     r8, rsi
0x140015c27  shl     r8, 2; Size
0x140015c2b  mov     rdx, r14; Src
0x140015c2e  call    memmove
0x140015c33  lea     rcx, [r13-1]
0x140015c37  cmp     r13, rcx
0x140015c3a  cmovb   rcx, r13
0x140015c3e  cmp     rcx, 10h
0x140015c42  jb      short loc_140015C5B
0x140015c44  mov     eax, r12d
0x140015c47  sub     eax, r15d
0x140015c4a  test    al, 3
0x140015c4c  jnz     short loc_140015C5B
0x140015c4e  sub     r14, r15
0x140015c51  cmp     r14, 20h ; ' '
0x140015c55  jnb     loc_140015E68
0x140015c5b  mov     rax, rsi
0x140015c5e  add     rsi, r13
0x140015c61  nop     word ptr [rax+rax+00000000h]
0x140015c70  cmp     r15, r12
0x140015c73  jz      loc_140016071
0x140015c79  mov     ecx, [r15]
0x140015c7c  add     r15, 4
0x140015c80  mov     [rbp+rax*4+0], ecx
0x140015c84  inc     rax
0x140015c87  cmp     rsi, rax
0x140015c8a  jnz     short loc_140015C70
0x140015c8c  add     r13, rbx
0x140015c8f  mov     [rdi+10h], r13
0x140015c93  mov     r14, 8000000000000001h
0x140015c9d  mov     [rsp+98h+var_60], 0
0x140015ca6  mov     [rsp+98h+var_58], 4
0x140015caf  mov     [rsp+98h+var_50], 0
0x140015cb8  lea     rcx, [rsp+98h+var_60]
0x140015cbd  mov     rdx, r15
0x140015cc0  mov     r8, r12
0x140015cc3  call    _RINvXCs3PyRTeGQ7Na_12fallible_vecINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEINtB3_11FallibleVeclB13_E10try_extendINtNtNtNtCs9MWeMO1rkJG_4core4iter8adapters3map3MapINtNtNtB2L_5slice4iter7IterMutlENCNvMs1_NtCsdcpJtfrLhSH_7rgncore4scanINtB44_12ScanInternalQBv_B13_E16merge_in_x_walls0EEB46_
0x140015cc8  cmp     rax, r14
0x140015ccb  jnz     short loc_140015CED
0x140015ccd  mov     r12, [rsp+98h+var_60]
0x140015cd2  mov     rbx, [rsp+98h+var_58]
0x140015cd7  mov     rdx, [rsp+98h+var_50]
0x140015cdc  lea     rax, [r14-1]
0x140015ce0  cmp     r12, rax
0x140015ce3  jnz     short loc_140015D45
0x140015ce5  mov     r14, rbx
0x140015ce8  jmp     loc_140015ECC
0x140015ced  mov     r8, [rsp+98h+var_60]
0x140015cf2  test    r8, r8
0x140015cf5  jz      loc_140015DCA
0x140015cfb  mov     rsi, rax
0x140015cfe  mov     rdi, rdx
0x140015d01  mov     rcx, [rsp+98h+var_58]
0x140015d06  cmp     r8, 1Ch
0x140015d0a  jnz     loc_140015DBF
0x140015d10  call    _RNvNtCsdwtLm5uWta6_10gdi_region3ffi22ScanLookAsideList_Free
0x140015d15  jmp     loc_140015DC4
0x140015d1a  cmp     rsi, r8
0x140015d1d  ja      loc_140016048
0x140015d23  mov     [rdi+10h], rsi
0x140015d27  mov     r14, 8000000000000001h
0x140015d31  jnz     short loc_140015D95
0x140015d33  cmp     rbx, r8
0x140015d36  jz      loc_140015ECC
0x140015d3c  mov     [rdi+10h], rbx
0x140015d40  jmp     loc_140015ECC
0x140015d45  test    rdx, rdx
0x140015d48  jz      loc_140015E53
0x140015d4e  mov     rax, [rdi]
0x140015d51  mov     r13, [rdi+10h]
0x140015d55  mov     rcx, rax
0x140015d58  sub     rcx, r13
0x140015d5b  cmp     rdx, rcx
0x140015d5e  jbe     short loc_140015DD2
0x140015d60  mov     rcx, r13
0x140015d63  add     rcx, rdx
0x140015d66  jnb     loc_140015FD3
0x140015d6c  xor     r14d, r14d
0x140015d6f  test    r12, r12
0x140015d72  jz      loc_140015ECC
0x140015d78  mov     rsi, rdx
0x140015d7b  mov     rcx, rbx
0x140015d7e  cmp     r12, 1Ch
0x140015d82  jnz     loc_140015F53
0x140015d88  call    _RNvNtCsdwtLm5uWta6_10gdi_region3ffi22ScanLookAsideList_Free
0x140015d8d  mov     rdx, rsi
0x140015d90  jmp     loc_140015ECC
0x140015d95  cmp     rbx, r8
0x140015d98  jz      loc_140015ECC
0x140015d9e  lea     rcx, [rax+rsi*4]; void *
0x140015da2  lea     rdx, [rax+r8*4]; Src
0x140015da6  lea     r8, ds:0[r13*4]; Size
0x140015dae  call    memmove
0x140015db3  add     r13, rsi
0x140015db6  mov     [rdi+10h], r13
0x140015dba  jmp     loc_140015ECC
0x140015dbf  call    Win32FreePool_0
0x140015dc4  mov     rdx, rdi
0x140015dc7  mov     rax, rsi
0x140015dca  mov     r14, rax
0x140015dcd  jmp     loc_140015ECC
0x140015dd2  mov     rax, [rdi+8]
0x140015dd6  lea     rax, [rax+rsi*4]
0x140015dda  lea     rcx, [rax+rdx*4]; void *
0x140015dde  mov     r8, r13
0x140015de1  sub     r8, rsi
0x140015de4  shl     r8, 2; Size
0x140015de8  mov     r15, rdx
0x140015deb  mov     rdx, rax; Src
0x140015dee  call    memmove
0x140015df3  mov     rcx, r15
0x140015df6  add     r13, r15
0x140015df9  mov     [rdi+10h], r13
0x140015dfd  mov     rax, [rdi+8]
0x140015e01  lea     r9, ds:0FFFFFFFFFFFFFFFCh[r15*4]
0x140015e09  cmp     r9, 2Ch ; ','
0x140015e0d  jb      short loc_140015E20
0x140015e0f  lea     rdx, [rax+rsi*4]
0x140015e13  sub     rdx, rbx
0x140015e16  cmp     rdx, 20h ; ' '
0x140015e1a  jnb     loc_140015F60
0x140015e20  xor     r8d, r8d
0x140015e23  mov     rdx, rbx
0x140015e26  lea     rcx, [rbx+rcx*4]
0x140015e2a  shl     rsi, 2
0x140015e2e  lea     r8, [rsi+r8*4]
0x140015e32  add     rax, r8
0x140015e35  nop     word ptr [rax+rax+00000000h]
0x140015e40  mov     r8d, [rdx]
0x140015e43  add     rdx, 4
0x140015e47  mov     [rax], r8d
0x140015e4a  add     rax, 4
0x140015e4e  cmp     rdx, rcx
0x140015e51  jnz     short loc_140015E40
0x140015e53  test    r12, r12
0x140015e56  jz      short loc_140015ECC
0x140015e58  mov     rcx, rbx
0x140015e5b  cmp     r12, 1Ch
0x140015e5f  jnz     short loc_140015EC7
0x140015e61  call    _RNvNtCsdwtLm5uWta6_10gdi_region3ffi22ScanLookAsideList_Free
0x140015e66  jmp     short loc_140015ECC
0x140015e68  inc     rcx
0x140015e6b  lea     r8, ds:0[rsi*4]
0x140015e73  mov     eax, ecx
0x140015e75  and     eax, 7
0x140015e78  mov     edx, 8
0x140015e7d  cmovnz  rdx, rax
0x140015e81  sub     rcx, rdx
0x140015e84  lea     rdx, [r15+rcx*4]
0x140015e88  lea     rax, [rsi+rcx]
0x140015e8c  add     r8, rbp
0x140015e8f  add     r8, 10h
0x140015e93  xor     r9d, r9d
0x140015e96  nop     word ptr [rax+rax+00000000h]
0x140015ea0  movups  xmm0, xmmword ptr [r15+r9*4]
0x140015ea5  movups  xmm1, xmmword ptr [r15+r9*4+10h]
0x140015eab  movups  xmmword ptr [r8+r9*4-10h], xmm0
0x140015eb1  movups  xmmword ptr [r8+r9*4], xmm1
0x140015eb6  add     r9, 8
0x140015eba  cmp     rcx, r9
0x140015ebd  jnz     short loc_140015EA0
0x140015ebf  mov     r15, rdx
0x140015ec2  jmp     loc_140015C5E
0x140015ec7  call    Win32FreePool_0
0x140015ecc  mov     rax, [rsp+98h+var_48]
0x140015ed1  xor     rax, rsp
0x140015ed4  mov     rcx, cs:__security_cookie
0x140015edb  cmp     rcx, rax
0x140015ede  jnz     loc_14001608F
0x140015ee4  mov     rax, r14
0x140015ee7  add     rsp, 58h
0x140015eeb  pop     rbx
0x140015eec  pop     rbp
0x140015eed  pop     rdi
0x140015eee  pop     rsi
0x140015eef  pop     r12
0x140015ef1  pop     r13
0x140015ef3  pop     r14
0x140015ef5  pop     r15
0x140015ef7  retn
0x140015ef8  mov     [rsp+98h+var_68], rcx
0x140015efd  lea     rax, [rbx+r13]
0x140015f01  lea     rcx, [rdx+rdx]
0x140015f05  cmp     rax, rcx
0x140015f08  cmova   rcx, rax
0x140015f0c  cmp     rcx, 5
0x140015f10  mov     r14d, 4
0x140015f16  cmovnb  r14, rcx
0x140015f1a  mov     r8, [rdi+8]
0x140015f1e  mov     [rsp+98h+var_70], 4
0x140015f27  mov     [rsp+98h+var_78], 4
0x140015f30  lea     rcx, [rsp+98h+var_60]
0x140015f35  mov     r9, r14
0x140015f38  call    _RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCsdcpJtfrLhSH_7rgncore_llvm_18110786352924170244
0x140015f3d  cmp     byte ptr [rsp+98h+var_60], 0
0x140015f42  jz      short loc_140015FBD
0x140015f44  mov     r14, [rsp+98h+var_58]
0x140015f49  mov     rdx, [rsp+98h+var_50]
0x140015f4e  jmp     loc_140015ECC
0x140015f53  call    Win32FreePool_0
0x140015f58  mov     rdx, rsi
0x140015f5b  jmp     loc_140015ECC
0x140015f60  shr     r9, 2
  ... truncated ...
```
