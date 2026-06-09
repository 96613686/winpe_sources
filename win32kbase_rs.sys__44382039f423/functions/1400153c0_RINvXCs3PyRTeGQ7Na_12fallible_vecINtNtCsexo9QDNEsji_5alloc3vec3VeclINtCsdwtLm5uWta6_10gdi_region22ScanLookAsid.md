# _RINvXCs3PyRTeGQ7Na_12fallible_vecINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEINtB3_11FallibleVeclB13_E13try_splice_inINtNtNtNtCs9MWeMO1rkJG_4core4iter8adapters6cloned6ClonedINtNtB2K_5chain5ChainIB3A_INtNtNtB2O_5slice4iter4IterlEB3Z_EB3Z_EEINtNtNtB2O_3ops5range5RangejEECsdcpJtfrLhSH_7rgncore

- ea: `0x1400153c0`
- end: `0x140015aad`
- name: `_RINvXCs3PyRTeGQ7Na_12fallible_vecINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEINtB3_11FallibleVeclB13_E13try_splice_inINtNtNtNtCs9MWeMO1rkJG_4core4iter8adapters6cloned6ClonedINtNtB2K_5chain5ChainIB3A_INtNtNtB2O_5slice4iter4IterlEB3Z_EB3Z_EEINtNtNtB2O_3ops5range5RangejEECsdcpJtfrLhSH_7rgncore`
- size: `1773`
- prototype: `unsigned __int64 __fastcall(__int64 *, unsigned __int64, unsigned __int64, __int64 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000b240`

## callees

- `0x14000fda0`
- `0x140014ae0`
- `0x1400153c0`
- `0x14001790a`
- `0x140017a10`
- `0x140017b00`
- `0x140018450`
- `0x1400184d7`
- `0x140018690`
- `0x1400193b0`

## pseudocode

```c
unsigned __int64 __fastcall RINvXCs3PyRTeGQ7Na_12fallible_vecINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEINtB3_11FallibleVeclB13_E13try_splice_inINtNtNtNtCs9MWeMO1rkJG_4core4iter8adapters6cloned6ClonedINtNtB2K_5chain5ChainIB3A_INtNtNtB2O_5slice4iter4IterlEB3Z_EB3Z_EEINtNtNtB2O_3ops5range5RangejEECsdcpJtfrLhSH_7rgncore(
        __int64 *a1,
        unsigned __int64 a2,
        unsigned __int64 a3,
        __int64 *a4)
{
  unsigned __int64 v4; // r11
  unsigned __int64 v5; // r13
  unsigned __int64 v6; // rsi
  __int64 v7; // r15
  char *v8; // rbp
  char *v9; // rbx
  char *v10; // r12
  char *v11; // rdi
  __int64 v12; // rax
  char *v13; // r14
  char *v14; // rdx
  char *v15; // r9
  unsigned __int64 v17; // r14
  unsigned __int64 v18; // rax
  unsigned __int64 v19; // r13
  unsigned __int64 v20; // r13
  __int64 v21; // r13
  __int64 v22; // rdx
  unsigned __int64 v23; // rax
  char *v24; // rax
  char *v25; // r14
  __int64 v26; // rax
  char *v27; // r9
  char *v28; // r10
  char *v29; // r8
  char *v30; // rcx
  char *v31; // rdx
  __int64 v32; // rax
  __int64 v33; // rdi
  _DWORD *v34; // r15
  unsigned __int64 v35; // rdx
  __int64 v36; // rsi
  __int64 *v37; // rbp
  __int64 v38; // rax
  __int64 v39; // r9
  char *v40; // rax
  unsigned __int64 v41; // rbx
  __int64 v42; // r12
  __int64 v43; // rax
  unsigned __int64 v44; // r9
  __int64 v45; // r8
  int *v46; // rdx
  _DWORD *v47; // rax
  int v48; // r8d
  _DWORD *v49; // rcx
  __int64 v51; // r9
  __int64 v52; // r11
  __int128 v53; // xmm1
  unsigned __int64 v54; // r8
  __int64 v55; // r14
  __int64 *v56; // rcx
  unsigned __int64 v57; // rbx
  unsigned __int64 v58; // rdx
  __int64 v59; // r12
  __int64 v60; // [rsp+0h] [rbp-E8h] BYREF
  char *v61; // [rsp+30h] [rbp-B8h]
  char *v62; // [rsp+38h] [rbp-B0h]
  __int64 *v63; // [rsp+40h] [rbp-A8h]
  unsigned __int64 v64; // [rsp+48h] [rbp-A0h]
  __int64 v65; // [rsp+50h] [rbp-98h] BYREF
  char *v66; // [rsp+58h] [rbp-90h]
  char *v67; // [rsp+60h] [rbp-88h]
  char *v68; // [rsp+68h] [rbp-80h]
  char *v69; // [rsp+70h] [rbp-78h]
  char *v70; // [rsp+78h] [rbp-70h]
  char *v71; // [rsp+80h] [rbp-68h]
  __int64 v72; // [rsp+88h] [rbp-60h] BYREF
  __int64 v73; // [rsp+90h] [rbp-58h]
  unsigned __int64 v74; // [rsp+98h] [rbp-50h]
  __int64 v75; // [rsp+A0h] [rbp-48h]

  v4 = a1[2];
  v5 = v4 - a3;
  if ( v4 < a3 )
    RNvNtNtCs9MWeMO1rkJG_4core5slice5index16slice_index_fail(
      0,
      a3,
      v4,
      &anon_c9360f58bbc394745aa7882ed1343abe_1_llvm_18110786352924170244);
  v6 = a2;
  if ( a2 > a3 )
LABEL_111:
    RNvNtNtCs9MWeMO1rkJG_4core5slice5index16slice_index_fail(
      v6,
      a3,
      v4,
      &anon_c9360f58bbc394745aa7882ed1343abe_2_llvm_18110786352924170244);
  v7 = *a4;
  v8 = (char *)a4[1];
  v62 = (char *)a4[2];
  v9 = (char *)a4[3];
  v61 = (char *)a4[4];
  v10 = (char *)a4[5];
  v11 = (char *)a4[6];
  if ( a2 >= a3 )
    goto LABEL_25;
  v12 = a1[1];
  while ( 1 )
  {
    if ( v7 != 1 )
    {
      v13 = v8;
LABEL_15:
      if ( !v10 )
        goto LABEL_20;
LABEL_16:
      if ( v10 == v11 )
        goto LABEL_20;
      v14 = v10 + 4;
      v15 = v9;
      v7 = 0;
      v8 = v10;
      if ( v6 >= v4 )
LABEL_113:
        RNvNtCs9MWeMO1rkJG_4core9panicking18panic_bounds_check(v6, v4, &off_14001C4A8);
      goto LABEL_6;
    }
    if ( v8 && v8 != v62 )
    {
      v13 = v8 + 4;
      v7 = 1;
      v14 = v10;
      v15 = v9;
      if ( v6 >= v4 )
        goto LABEL_113;
      goto LABEL_6;
    }
    if ( !v9 )
      break;
    v13 = 0;
    if ( v9 == v61 )
      goto LABEL_15;
    v15 = v9 + 4;
    v7 = 1;
    v14 = v10;
    v13 = 0;
    v8 = v9;
    if ( v6 >= v4 )
      goto LABEL_113;
LABEL_6:
    *(_DWORD *)(v12 + 4 * v6++) = *(_DWORD *)v8;
    v10 = v14;
    v9 = v15;
    v8 = v13;
    if ( a3 == v6 )
    {
      v10 = v14;
      v9 = v15;
      v8 = v13;
      v6 = a3;
LABEL_25:
      v63 = a1;
      if ( v7 == 1 )
      {
        if ( v10 )
        {
          if ( v8 )
          {
            v18 = (unsigned __int64)(v62 - v8) >> 2;
            if ( v9 )
              v18 += (unsigned __int64)(v61 - v9) >> 2;
          }
          else if ( v9 )
          {
            v18 = (unsigned __int64)(v61 - v9) >> 2;
          }
          else
          {
            v18 = 0;
          }
          v20 = (unsigned __int64)(v11 - v10) >> 2;
          goto LABEL_45;
        }
        if ( v8 )
        {
          v20 = (unsigned __int64)(v62 - v8) >> 2;
          if ( v9 )
          {
            v18 = (unsigned __int64)(v61 - v9) >> 2;
LABEL_45:
            v20 += v18;
          }
LABEL_46:
          if ( v20 )
          {
            v22 = *a1;
            v23 = *a1 - v4;
            v64 = v4;
            if ( v20 > v23 )
            {
              v54 = 2 * v22;
              if ( v4 + v20 > 2 * v22 )
                v54 = v4 + v20;
              v55 = 4;
              if ( v54 >= 5 )
                v55 = v54;
              RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCsdcpJtfrLhSH_7rgncore_llvm_18110786352924170244(
                &v65,
                v22,
                a1[1],
                v55,
                4,
                4);
              if ( (_BYTE)v65 )
              {
                v17 = (unsigned __int64)v66;
                goto LABEL_87;
              }
              v24 = v66;
              v56 = v63;
              v63[1] = (__int64)v66;
              *v56 = v55;
              v4 = v64;
            }
            else
            {
              v24 = (char *)a1[1];
            }
            v25 = &v24[4 * v6];
            memmove(&v25[4 * v20], v25, 4 * (v4 - v6));
            v63[2] = v6;
            v6 += v20;
            v26 = 0;
            v27 = v62;
            v28 = v61;
            while ( 1 )
            {
              v29 = v8;
              v30 = v9;
              v31 = v10;
              if ( v7 != 1 )
                break;
              if ( v8 && v8 != v27 )
              {
                v8 += 4;
                v7 = 1;
              }
              else
              {
                if ( !v9 )
                {
                  v8 = 0;
                  if ( !v10 )
LABEL_62:
                    RNvNtCs9MWeMO1rkJG_4core6option13unwrap_failed(&off_14001C490);
                  goto LABEL_59;
                }
                v8 = 0;
                if ( v9 == v28 )
                  break;
                v9 += 4;
                v7 = 1;
                v8 = 0;
                v29 = v30;
              }
LABEL_51:
              *(_DWORD *)&v25[4 * v26++] = *(_DWORD *)v29;
              if ( v20 == v26 )
              {
                v21 = v20 + v64;
                v63[2] = v21;
                goto LABEL_66;
              }
            }
            if ( !v10 )
              goto LABEL_62;
LABEL_59:
            if ( v10 == v11 )
              goto LABEL_62;
            v10 += 4;
            v7 = 0;
            v29 = v31;
            goto LABEL_51;
          }
          v21 = v4;
LABEL_65:
          v27 = v62;
          v28 = v61;
LABEL_66:
          v17 = 0x8000000000000001uLL;
          v65 = v7;
          v66 = v8;
          v67 = v27;
          v68 = v9;
          v69 = v28;
          v70 = v10;
          v71 = v11;
          v72 = 0;
          v73 = 4;
          v74 = 0;
          v32 = RINvXCs3PyRTeGQ7Na_12fallible_vecINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEINtB3_11FallibleVeclB13_E10try_extendINtNtNtNtCs9MWeMO1rkJG_4core4iter8adapters6cloned6ClonedINtNtB2H_5chain5ChainIB3x_INtNtNtB2L_5slice4iter4IterlEB3W_EB3W_EEECsdcpJtfrLhSH_7rgncore(
                  &v72,
                  &v65);
          if ( v32 != 0x8000000000000001uLL )
          {
            if ( v72 )
            {
              v36 = v32;
              if ( v72 == 28 )
                RNvNtCsdwtLm5uWta6_10gdi_region3ffi22ScanLookAsideList_Free(v73);
              else
                Win32FreePool_0(v73);
              v32 = v36;
            }
            v17 = v32;
            goto LABEL_87;
          }
          v33 = v72;
          v34 = (_DWORD *)v73;
          v35 = v74;
          if ( v72 == 0x8000000000000000uLL )
          {
            v17 = v73;
            goto LABEL_87;
          }
          if ( v74 )
          {
            v37 = v63;
            v38 = *v63;
            v39 = v21;
            if ( v74 > *v63 - v21 )
            {
              v57 = v74;
              v58 = 2 * v38;
              if ( v21 + v74 > 2 * v38 )
                v58 = v21 + v74;
              v59 = 4;
              if ( v58 >= 5 )
                v59 = v58;
              RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCsdcpJtfrLhSH_7rgncore_llvm_18110786352924170244(
                &v65,
                v38,
                v63[1],
                v59,
                4,
                4);
              if ( (_BYTE)v65 )
              {
                v17 = (unsigned __int64)v66;
                if ( !v33 )
                  goto LABEL_87;
                v49 = v34;
                if ( v33 == 28 )
                {
LABEL_82:
                  RNvNtCsdwtLm5uWta6_10gdi_region3ffi22ScanLookAsideList_Free(v34);
                  goto LABEL_87;
                }
LABEL_86:
                Win32FreePool_0(v49);
                goto LABEL_87;
              }
              v40 = v66;
              v63[1] = (__int64)v66;
              *v37 = v59;
              v35 = v57;
              v39 = v21;
            }
            else
            {
              v40 = (char *)v63[1];
            }
            v41 = v35;
            v42 = v39;
            memmove(&v40[4 * v6 + 4 * v35], &v40[4 * v6], 4 * (v39 - v6));
            v37[2] = v41 + v42;
            v43 = v37[1];
            v44 = 4 * v41 - 4;
            if ( v44 < 0x2C || v43 + 4 * v6 - (unsigned __int64)v34 < 0x20 )
            {
              v45 = 0;
              v46 = v34;
LABEL_78:
              v47 = (_DWORD *)(4 * v45 + 4 * v6 + v43);
              do
              {
                v48 = *v46++;
                *v47++ = v48;
              }
              while ( v46 != &v34[v41] );
              goto LABEL_80;
            }
            v51 = (v44 >> 2) + 1;
            v45 = v51 & 0x7FFFFFFFFFFFFFF8LL;
            v46 = &v34[v51 & 0x7FFFFFFFFFFFFFF8LL];
            v52 = 0;
            do
            {
              v53 = *(_OWORD *)&v34[v52 + 4];
              *(_OWORD *)(v43 + 4 * v6 + 4 * v52) = *(_OWORD *)&v34[v52];
              *(_OWORD *)(v43 + 4 * v6 + 16 + 4 * v52) = v53;
              v52 += 8;
            }
            while ( v45 != v52 );
            if ( v51 != v45 )
              goto LABEL_78;
          }
LABEL_80:
          if ( !v33 )
            goto LABEL_87;
          v49 = v34;
          if ( v33 == 28 )
            goto LABEL_82;
          goto LABEL_86;
        }
        if ( !v9 )
        {
          v21 = v4;
          v7 = 1;
          v10 = 0;
          v9 = 0;
          v8 = 0;
          goto LABEL_65;
        }
        v19 = v61 - v9;
      }
      else
      {
        if ( !v10 )
        {
          v21 = v4;
          v10 = 0;
          v7 = 0;
          goto LABEL_65;
        }
        v19 = v11 - v10;
      }
      v20 = v19 >> 2;
      goto LABEL_46;
    }
  }
  v13 = 0;
  if ( v10 )
    goto LABEL_16;
LABEL_20:
  if ( v6 > a3 )
    goto LABEL_111;
  v17 = 0x8000000000000001uLL;
  a1[2] = v6;
  if ( v6 == a3 )
  {
    if ( v4 != a3 )
      a1[2] = v4;
  }
  else if ( v4 != a3 )
  {
    memmove((void *)(v12 + 4 * v6), (const void *)(v12 + 4 * a3), 4 * v5);
    a1[2] = v6 + v5;
  }
LABEL_87:
  if ( _security_cookie != ((unsigned __int64)&v60 ^ v75) )
    JUMPOUT(0x140015AACLL);
  return v17;
}

```

## disassembly

```asm
0x1400153c0  push    r15
0x1400153c2  push    r14
0x1400153c4  push    r13
0x1400153c6  push    r12
0x1400153c8  push    rsi
0x1400153c9  push    rdi
0x1400153ca  push    rbp
0x1400153cb  push    rbx
0x1400153cc  sub     rsp, 0A8h
0x1400153d3  mov     rax, cs:__security_cookie
0x1400153da  xor     rax, rsp
0x1400153dd  mov     [rsp+0E8h+var_48], rax
0x1400153e5  mov     r11, [rcx+10h]
0x1400153e9  mov     r13, r11
0x1400153ec  sub     r13, r8
0x1400153ef  jb      loc_140015A76
0x1400153f5  mov     rsi, rdx
0x1400153f8  cmp     rdx, r8
0x1400153fb  ja      loc_140015A61
0x140015401  mov     r15, [r9]
0x140015404  mov     rbp, [r9+8]
0x140015408  mov     rax, [r9+10h]
0x14001540c  mov     [rsp+0E8h+var_B0], rax
0x140015411  mov     rbx, [r9+18h]
0x140015415  mov     rax, [r9+20h]
0x140015419  mov     [rsp+0E8h+var_B8], rax
0x14001541e  mov     r12, [r9+28h]
0x140015422  mov     rdi, [r9+30h]
0x140015426  jnb     loc_14001551B
0x14001542c  mov     rax, [rcx+8]
0x140015430  jmp     short loc_14001546D
0x140015432  lea     r14, [rbp+4]
0x140015436  mov     r15d, 1
0x14001543c  mov     rdx, r12
0x14001543f  mov     r9, rbx
0x140015442  cmp     rsi, r11
0x140015445  jnb     loc_140015A8A
0x14001544b  nop     dword ptr [rax+rax+00h]
0x140015450  mov     r10d, [rbp+0]
0x140015454  mov     [rax+rsi*4], r10d
0x140015458  inc     rsi
0x14001545b  mov     r12, rdx
0x14001545e  mov     rbx, r9
0x140015461  mov     rbp, r14
0x140015464  cmp     r8, rsi
0x140015467  jz      loc_14001550F
0x14001546d  cmp     r15, 1
0x140015471  jnz     short loc_1400154B0
0x140015473  test    rbp, rbp
0x140015476  jz      short loc_14001547F
0x140015478  cmp     rbp, [rsp+0E8h+var_B0]
0x14001547d  jnz     short loc_140015432
0x14001547f  test    rbx, rbx
0x140015482  jz      short loc_1400154D5
0x140015484  mov     r14d, 0
0x14001548a  cmp     rbx, [rsp+0E8h+var_B8]
0x14001548f  jz      short loc_1400154B3
0x140015491  lea     r9, [rbx+4]
0x140015495  mov     r15d, 1
0x14001549b  mov     rdx, r12
0x14001549e  xor     r14d, r14d
0x1400154a1  mov     rbp, rbx
0x1400154a4  cmp     rsi, r11
0x1400154a7  jb      short loc_140015450
0x1400154a9  jmp     loc_140015A8A
0x1400154b0  mov     r14, rbp
0x1400154b3  test    r12, r12
0x1400154b6  jz      short loc_1400154DD
0x1400154b8  cmp     r12, rdi
0x1400154bb  jz      short loc_1400154DD
0x1400154bd  lea     rdx, [r12+4]
0x1400154c2  mov     r9, rbx
0x1400154c5  xor     r15d, r15d
0x1400154c8  mov     rbp, r12
0x1400154cb  cmp     rsi, r11
0x1400154ce  jb      short loc_140015450
0x1400154d0  jmp     loc_140015A8A
0x1400154d5  xor     r14d, r14d
0x1400154d8  test    r12, r12
0x1400154db  jnz     short loc_1400154B8
0x1400154dd  cmp     rsi, r8
0x1400154e0  ja      loc_140015A61
0x1400154e6  mov     rdi, rcx
0x1400154e9  mov     r14, 8000000000000001h
0x1400154f3  mov     [rcx+10h], rsi
0x1400154f7  jnz     loc_1400155A3
0x1400154fd  cmp     r11, r8
0x140015500  jz      loc_1400158AD
0x140015506  mov     [rdi+10h], r11
0x14001550a  jmp     loc_1400158AD
0x14001550f  mov     r12, rdx
0x140015512  mov     rbx, r9
0x140015515  mov     rbp, r14
0x140015518  mov     rsi, r8
0x14001551b  cmp     r15, 1
0x14001551f  mov     [rsp+0E8h+var_A8], rcx
0x140015524  jnz     short loc_14001555D
0x140015526  test    r12, r12
0x140015529  jz      short loc_140015571
0x14001552b  test    rbp, rbp
0x14001552e  jz      loc_1400155CD
0x140015534  mov     rax, [rsp+0E8h+var_B0]
0x140015539  sub     rax, rbp
0x14001553c  shr     rax, 2
0x140015540  test    rbx, rbx
0x140015543  jz      loc_1400155F8
0x140015549  mov     rdx, [rsp+0E8h+var_B8]
0x14001554e  sub     rdx, rbx
0x140015551  shr     rdx, 2
0x140015555  add     rax, rdx
0x140015558  jmp     loc_1400155F8
0x14001555d  test    r12, r12
0x140015560  jz      short loc_140015595
0x140015562  mov     r13, rdi
0x140015565  sub     r13, r12
0x140015568  shr     r13, 2
0x14001556c  jmp     loc_140015605
0x140015571  test    rbp, rbp
0x140015574  jz      short loc_1400155E0
0x140015576  mov     r13, [rsp+0E8h+var_B0]
0x14001557b  sub     r13, rbp
0x14001557e  shr     r13, 2
0x140015582  test    rbx, rbx
0x140015585  jz      short loc_140015605
0x140015587  mov     rax, [rsp+0E8h+var_B8]
0x14001558c  sub     rax, rbx
0x14001558f  shr     rax, 2
0x140015593  jmp     short loc_140015602
0x140015595  mov     r13, r11
0x140015598  xor     r12d, r12d
0x14001559b  xor     r15d, r15d
0x14001559e  jmp     loc_140015708
0x1400155a3  cmp     r11, r8
0x1400155a6  jz      loc_1400158AD
0x1400155ac  lea     rcx, [rax+rsi*4]; void *
0x1400155b0  lea     rdx, [rax+r8*4]; Src
0x1400155b4  lea     r8, ds:0[r13*4]; Size
0x1400155bc  call    memmove
0x1400155c1  add     r13, rsi
0x1400155c4  mov     [rdi+10h], r13
0x1400155c8  jmp     loc_1400158AD
0x1400155cd  test    rbx, rbx
0x1400155d0  jz      short loc_1400155F6
0x1400155d2  mov     rax, [rsp+0E8h+var_B8]
0x1400155d7  sub     rax, rbx
0x1400155da  shr     rax, 2
0x1400155de  jmp     short loc_1400155F8
0x1400155e0  test    rbx, rbx
0x1400155e3  jz      loc_140015993
0x1400155e9  mov     r13, [rsp+0E8h+var_B8]
0x1400155ee  sub     r13, rbx
0x1400155f1  jmp     loc_140015568
0x1400155f6  xor     eax, eax
0x1400155f8  mov     r13, rdi
0x1400155fb  sub     r13, r12
0x1400155fe  shr     r13, 2
0x140015602  add     r13, rax
0x140015605  test    r13, r13
0x140015608  jz      loc_140015705
0x14001560e  mov     rdx, [rcx]
0x140015611  mov     rax, rdx
0x140015614  sub     rax, r11
0x140015617  cmp     r13, rax
0x14001561a  mov     [rsp+0E8h+var_A0], r11
0x14001561f  ja      loc_14001593D
0x140015625  mov     rax, [rcx+8]
0x140015629  lea     r14, [rax+rsi*4]
0x14001562d  lea     rcx, [r14+r13*4]; void *
0x140015631  sub     r11, rsi
0x140015634  shl     r11, 2
0x140015638  mov     rdx, r14; Src
0x14001563b  mov     r8, r11; Size
0x14001563e  call    memmove
0x140015643  mov     rax, [rsp+0E8h+var_A8]
0x140015648  mov     [rax+10h], rsi
0x14001564c  add     rsi, r13
0x14001564f  xor     eax, eax
0x140015651  mov     r9, [rsp+0E8h+var_B0]
0x140015656  mov     r10, [rsp+0E8h+var_B8]
0x14001565b  jmp     short loc_14001567F
0x14001565d  lea     rbp, [r8+4]
0x140015661  mov     r15d, 1
0x140015667  mov     r12, rdx
0x14001566a  mov     rbx, rcx
0x14001566d  nop     dword ptr [rax]
0x140015670  mov     ecx, [r8]
0x140015673  mov     [r14+rax*4], ecx
0x140015677  inc     rax
0x14001567a  cmp     r13, rax
0x14001567d  jz      short loc_1400156EF
0x14001567f  mov     r8, rbp
0x140015682  mov     rcx, rbx
0x140015685  mov     rdx, r12
0x140015688  cmp     r15, 1
0x14001568c  jnz     short loc_1400156C0
0x14001568e  test    r8, r8
0x140015691  jz      short loc_140015698
0x140015693  cmp     r8, r9
0x140015696  jnz     short loc_14001565D
0x140015698  test    rcx, rcx
0x14001569b  jz      short loc_1400156DC
0x14001569d  mov     ebp, 0
0x1400156a2  cmp     rcx, r10
0x1400156a5  jz      short loc_1400156C3
0x1400156a7  lea     rbx, [rcx+4]
0x1400156ab  mov     r15d, 1
0x1400156b1  mov     r12, rdx
0x1400156b4  xor     ebp, ebp
0x1400156b6  mov     r8, rcx
0x1400156b9  jmp     short loc_140015670
0x1400156c0  mov     rbp, r8
0x1400156c3  test    rdx, rdx
0x1400156c6  jz      short loc_1400156E3
0x1400156c8  cmp     rdx, rdi
0x1400156cb  jz      short loc_1400156E3
0x1400156cd  lea     r12, [rdx+4]
0x1400156d1  mov     rbx, rcx
0x1400156d4  xor     r15d, r15d
0x1400156d7  mov     r8, rdx
0x1400156da  jmp     short loc_140015670
0x1400156dc  xor     ebp, ebp
0x1400156de  test    rdx, rdx
0x1400156e1  jnz     short loc_1400156C8
0x1400156e3  lea     rcx, off_14001C490; "d:\\os\\out\\rust\\cargo_home\\amd64fre"...
0x1400156ea  call    _RNvNtCs9MWeMO1rkJG_4core6option13unwrap_failed
0x1400156ef  mov     rax, [rsp+0E8h+var_A0]
0x1400156f4  add     rax, r13
0x1400156f7  mov     r13, rax
0x1400156fa  mov     rcx, [rsp+0E8h+var_A8]
0x1400156ff  mov     [rcx+10h], rax
0x140015703  jmp     short loc_140015712
0x140015705  mov     r13, r11
0x140015708  mov     r9, [rsp+0E8h+var_B0]
0x14001570d  mov     r10, [rsp+0E8h+var_B8]
0x140015712  mov     r14, 8000000000000001h
0x14001571c  mov     [rsp+0E8h+var_98], r15
0x140015721  mov     [rsp+0E8h+var_90], rbp
0x140015726  mov     [rsp+0E8h+var_88], r9
0x14001572b  mov     [rsp+0E8h+var_80], rbx
0x140015730  mov     [rsp+0E8h+var_78], r10
0x140015735  mov     [rsp+0E8h+var_70], r12
0x14001573a  mov     [rsp+0E8h+var_68], rdi
0x140015742  mov     [rsp+0E8h+var_60], 0
0x14001574e  mov     [rsp+0E8h+var_58], 4
0x14001575a  mov     [rsp+0E8h+var_50], 0
0x140015766  lea     rcx, [rsp+0E8h+var_60]
0x14001576e  lea     rdx, [rsp+0E8h+var_98]
0x140015773  call    _RINvXCs3PyRTeGQ7Na_12fallible_vecINtNtCsexo9QDNEsji_5alloc3vec3VeclINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EEINtB3_11FallibleVeclB13_E10try_extendINtNtNtNtCs9MWeMO1rkJG_4core4iter8adapters6cloned6ClonedINtNtB2H_5chain5ChainIB3x_INtNtNtB2L_5slice4iter4IterlEB3W_EB3W_EEECsdcpJtfrLhSH_7rgncore
0x140015778  cmp     rax, r14
0x14001577b  jnz     short loc_1400157A6
0x14001577d  mov     rdi, [rsp+0E8h+var_60]
0x140015785  mov     r15, [rsp+0E8h+var_58]
0x14001578d  mov     rdx, [rsp+0E8h+var_50]
0x140015795  lea     rax, [r14-1]
0x140015799  cmp     rdi, rax
0x14001579c  jnz     short loc_1400157D9
0x14001579e  mov     r14, r15
0x1400157a1  jmp     loc_1400158AD
0x1400157a6  mov     r8, [rsp+0E8h+var_60]
0x1400157ae  test    r8, r8
0x1400157b1  jz      loc_1400158A3
0x1400157b7  mov     rsi, rax
0x1400157ba  mov     rdi, rdx
0x1400157bd  mov     rcx, [rsp+0E8h+var_58]
0x1400157c5  cmp     r8, 1Ch
0x1400157c9  jnz     loc_140015898
0x1400157cf  call    _RNvNtCsdwtLm5uWta6_10gdi_region3ffi22ScanLookAsideList_Free
0x1400157d4  jmp     loc_14001589D
0x1400157d9  test    rdx, rdx
0x1400157dc  jz      loc_140015883
0x1400157e2  mov     rbp, [rsp+0E8h+var_A8]
0x1400157e7  mov     rax, [rbp+0]
0x1400157eb  mov     rcx, rax
0x1400157ee  mov     r9, r13
0x1400157f1  sub     rcx, r13
0x1400157f4  cmp     rdx, rcx
0x1400157f7  ja      loc_1400159C3
0x1400157fd  mov     rax, [rbp+8]
0x140015801  lea     rax, [rax+rsi*4]
0x140015805  lea     rcx, [rax+rdx*4]; void *
0x140015809  mov     r8, r9
0x14001580c  sub     r8, rsi
0x14001580f  shl     r8, 2; Size
0x140015813  mov     rbx, rdx
0x140015816  mov     rdx, rax; Src
0x140015819  mov     r12, r9
0x14001581c  call    memmove
0x140015821  mov     rcx, rbx
0x140015824  add     r12, rbx
0x140015827  mov     [rbp+10h], r12
0x14001582b  mov     rax, [rbp+8]
0x14001582f  lea     r9, ds:0FFFFFFFFFFFFFFFCh[rbx*4]
0x140015837  cmp     r9, 2Ch ; ','
0x14001583b  jb      short loc_14001584E
0x14001583d  lea     rdx, [rax+rsi*4]
0x140015841  sub     rdx, r15
0x140015844  cmp     rdx, 20h ; ' '
0x140015848  jnb     loc_1400158DF
0x14001584e  xor     r8d, r8d
0x140015851  mov     rdx, r15
  ... truncated ...
```
