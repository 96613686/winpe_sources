# WapUriGetTransformedComponentW

- ea: `0x1800068a0`
- end: `0x1800070d8`
- name: `WapUriGetTransformedComponentW`
- size: `2104`
- prototype: ``
- caller_count: `15`
- callee_count: `12`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180002a10`
- `0x180004040`
- `0x180005ab8`
- `0x1800061e4`
- `0x180006290`
- `0x180023bf0`
- `0x180024eb0`
- `0x180051cd4`
- `0x18005a2cc`
- `0x18005a454`
- `0x18005f6e8`
- `0x180068cf8`
- `0x18007e754`
- `0x18008348c`
- `0x18008d2d0`

## callees

- `0x1800068a0`
- `0x1800070e0`
- `0x180007270`
- `0x18000dc64`
- `0x18000df68`
- `0x180013820`
- `0x1800391c0`
- `0x18006aa60`
- `0x1800722f0`
- `0x180083570`
- `0x180091678`
- `0x180098010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180006916`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180006916`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180006973`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180006973`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006b88`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006b88`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006be5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006be5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006c3d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006c3d`

## pseudocode

```c
__int64 __fastcall WapUriGetTransformedComponentW(
        RTL_SRWLOCK *a1,
        int a2,
        int a3,
        __int64 a4,
        _QWORD *a5,
        unsigned __int64 *a6)
{
  __int64 v7; // rbx
  unsigned __int64 *v8; // rdx
  _BYTE *Ptr; // rax
  int v11; // edi
  _DWORD *v12; // rax
  int v13; // edx
  RTL_SRWLOCK *v14; // rax
  int v15; // edx
  RTL_SRWLOCK *v16; // r15
  __int64 v17; // r9
  __int64 v18; // rax
  unsigned __int64 v19; // rcx
  unsigned int v20; // r12d
  char *v22; // rax
  unsigned __int8 v23; // bl
  unsigned __int8 v24; // r14
  signed int v25; // esi
  __int128 v26; // xmm1
  __int128 v27; // xmm0
  __int128 v28; // xmm1
  __int128 v29; // xmm0
  __int128 v30; // xmm1
  __int128 v31; // xmm0
  __int128 v32; // xmm1
  __int128 v33; // xmm0
  __int128 v34; // xmm1
  __int128 v35; // xmm0
  __int128 v36; // xmm1
  RTL_SRWLOCK *v37; // rsi
  __int64 v38; // rcx
  unsigned __int64 v39; // r12
  __int64 v40; // rax
  __int64 v41; // r9
  RTL_SRWLOCK *v42; // r14
  _DWORD *v43; // rcx
  RTL_SRWLOCK *v44; // rax
  RTL_SRWLOCK *v45; // r11
  RTL_SRWLOCK *v46; // rcx
  RTL_SRWLOCK *v47; // rax
  unsigned __int8 v48; // r9
  int i; // r10d
  int j; // edi
  void *v51; // r8
  int *v52; // rsi
  int *v53; // rdx
  int v54; // eax
  int v55; // edi
  int v56; // ecx
  PVOID v57; // xmm1_8
  RTL_SRWLOCK **v58; // rdx
  unsigned __int64 v59; // rcx
  __int64 *v60; // r12
  RTL_SRWLOCK *v61; // rcx
  char v62; // r12
  __int64 v63; // rax
  __int64 v64; // xmm1_8
  RTL_SRWLOCK *v65; // r12
  PVOID v66; // xmm1_8
  unsigned __int64 PercentEncodeLength; // rax
  const void *v68; // rax
  unsigned __int64 v69; // r12
  __int64 v70; // [rsp+40h] [rbp-C0h] BYREF
  int v71; // [rsp+48h] [rbp-B8h]
  RTL_SRWLOCK *v72; // [rsp+50h] [rbp-B0h] BYREF
  int *v73; // [rsp+58h] [rbp-A8h]
  int v74[2]; // [rsp+60h] [rbp-A0h]
  int v75; // [rsp+68h] [rbp-98h]
  int v76; // [rsp+6Ch] [rbp-94h]
  unsigned __int64 v77; // [rsp+70h] [rbp-90h]
  RTL_SRWLOCK *Heap; // [rsp+78h] [rbp-88h]
  RTL_SRWLOCK *v79; // [rsp+80h] [rbp-80h]
  unsigned __int64 *v80; // [rsp+88h] [rbp-78h]
  __int128 v81; // [rsp+90h] [rbp-70h] BYREF
  __int64 v82; // [rsp+A0h] [rbp-60h]
  unsigned __int64 v83; // [rsp+A8h] [rbp-58h]
  _QWORD *v84; // [rsp+B0h] [rbp-50h]
  __int64 v85; // [rsp+B8h] [rbp-48h]
  _OWORD v86[2]; // [rsp+C0h] [rbp-40h] BYREF
  int v87[4]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v88; // [rsp+F0h] [rbp-10h]
  __int128 v89; // [rsp+100h] [rbp+0h]
  __int128 v90; // [rsp+110h] [rbp+10h]
  __int128 v91; // [rsp+120h] [rbp+20h]
  __int128 v92; // [rsp+130h] [rbp+30h]
  __int128 v93; // [rsp+140h] [rbp+40h]
  __int128 v94; // [rsp+150h] [rbp+50h]
  __int128 v95; // [rsp+160h] [rbp+60h]
  __int128 v96; // [rsp+170h] [rbp+70h]
  __int128 v97; // [rsp+180h] [rbp+80h]
  __int128 v98; // [rsp+190h] [rbp+90h]

  v7 = a2;
  v8 = a6;
  v84 = a5;
  Ptr = a1[4].Ptr;
  v79 = a1;
  v11 = (unsigned __int8)(1 << v7);
  v80 = a6;
  v76 = v11;
  if ( ((unsigned __int8)v11 & Ptr[240]) == 0 )
  {
    v20 = 87;
LABEL_42:
    if ( v84 )
      *v84 = 0;
    *v8 = 0;
    return v20;
  }
  AcquireSRWLockShared(a1 + 1);
  v12 = a1[4].Ptr;
  v85 = 24 * v7;
  v13 = v12[6 * v7 + 10];
  v14 = (RTL_SRWLOCK *)a1[2].Ptr;
  v15 = ~a3 & v13;
  if ( v14 == &a1[2] )
  {
    v16 = 0;
    v72 = 0;
  }
  else
  {
    do
    {
      v16 = v14 - 1;
      v72 = v14;
      if ( ((unsigned __int8)v11 & (__int64)v14[29].Ptr) != 0 && v15 == LODWORD(v16[3 * v7 + 5].Ptr) )
        break;
      v14 = (RTL_SRWLOCK *)v14->Ptr;
      v16 = 0;
    }
    while ( v14 != &a1[2] );
  }
  ReleaseSRWLockShared(a1 + 1);
  if ( v16 )
    goto LABEL_6;
  v22 = (char *)a1[4].Ptr;
  memset(v86, 0, sizeof(v86));
  v16 = 0;
  *((_DWORD *)v86 + v7) = a3;
  v23 = 0;
  v24 = v11;
  v25 = 0;
  v26 = *(_OWORD *)(v22 + 40);
  *(_OWORD *)v87 = *(_OWORD *)(v22 + 24);
  v27 = *(_OWORD *)(v22 + 56);
  v88 = v26;
  v28 = *(_OWORD *)(v22 + 72);
  v89 = v27;
  v29 = *(_OWORD *)(v22 + 88);
  v90 = v28;
  v30 = *(_OWORD *)(v22 + 104);
  v91 = v29;
  v31 = *(_OWORD *)(v22 + 120);
  v92 = v30;
  v32 = *(_OWORD *)(v22 + 136);
  v93 = v31;
  v33 = *(_OWORD *)(v22 + 152);
  v94 = v32;
  v34 = *(_OWORD *)(v22 + 168);
  v95 = v33;
  v35 = *(_OWORD *)(v22 + 184);
  v96 = v34;
  v36 = *(_OWORD *)(v22 + 200);
  v97 = v35;
  v98 = v36;
  if ( (_BYTE)v11 )
  {
    while ( v25 < 8 )
    {
      LOBYTE(v75) = 1 << v25;
      if ( ((unsigned __int8)(1 << v25) & v24) != 0 )
      {
        v81 = 0;
        v53 = &v87[6 * v25];
        v73 = v53;
        *(_QWORD *)v74 = 4LL * v25;
        v54 = *(_DWORD *)((char *)v86 + *(_QWORD *)v74);
        v71 = v54;
        v82 = 0;
        if ( v25 == 3 )
        {
          v56 = v54 & v53[4] & 0x1C000000;
          if ( v56 )
          {
            if ( v56 == 0x10000000 || v56 == 0x4000000 )
            {
              if ( (v23 & 8) != 0 && *(_QWORD *)v53 )
              {
                v70 = *(_QWORD *)v53;
                WxFreeHeapEx(&v70);
                v54 = v71;
                v53 = v73;
              }
              v23 &= ~8u;
              v57 = v79[27].Ptr;
              *(_OWORD *)v53 = *(_OWORD *)&v79[25].Ptr;
              *((_QWORD *)v53 + 2) = v57;
            }
            else
            {
              if ( v56 != 0x8000000 || (v65 = v79, !v79[29].Ptr) )
              {
LABEL_58:
                v20 = 87;
                goto LABEL_31;
              }
              if ( (v23 & 8) != 0 && *(_QWORD *)v53 )
              {
                v70 = *(_QWORD *)v53;
                WxFreeHeapEx(&v70);
                v54 = v71;
                v53 = v73;
              }
              v23 &= ~8u;
              v66 = v65[30].Ptr;
              *(_OWORD *)v53 = *(_OWORD *)&v65[28].Ptr;
              *((_QWORD *)v53 + 2) = v66;
            }
          }
        }
        v24 ^= 1 << v25;
        v71 = v53[4];
        v55 = v54 & v71;
        if ( (v54 & 0x1000000) != 0 && (v71 & 0xE003FE08) != 0 )
          v55 |= 0x1000008u;
        if ( v55 )
        {
          if ( (v55 & 0x202) != 0 || ((unsigned __int8)v55 & BYTE1(v55) & 0xF8) != 0 )
            goto LABEL_58;
          if ( (v55 & 0xF8) != 0 )
          {
            PercentEncodeLength = WapUriGetPercentEncodeLength(v25, v55, (__int64 *)v53);
            v60 = (__int64 *)v73;
            v59 = PercentEncodeLength;
            v83 = PercentEncodeLength;
            v77 = *((_QWORD *)v73 + 1);
            if ( PercentEncodeLength < v77 )
              goto LABEL_59;
          }
          else
          {
            v59 = *((_QWORD *)v53 + 1);
            v60 = (__int64 *)v73;
            v83 = v59;
            v77 = v59;
          }
          if ( v59 - 1 > 0x1869F )
            goto LABEL_58;
          if ( 2 * v59 < v59 )
            goto LABEL_106;
          Heap = (RTL_SRWLOCK *)WxAllocateHeapEx(v59, 2 * v59);
          v61 = Heap;
          if ( !Heap )
            goto LABEL_106;
          if ( (v55 & 0xE003FFFF) != 0 )
          {
            if ( (*((_BYTE *)v86 + *(_QWORD *)v74) & 4) != 0 )
            {
              if ( (*(_DWORD *)((_BYTE *)v86 + *(_QWORD *)v74) & 0x40000000) != 0 )
              {
                v20 = 87;
                goto LABEL_79;
              }
              v55 |= 4u;
            }
            v70 = *v60;
            v20 = WapUriTransformIriComponentCharacters(v25, v55, v70, v77, (__int64)Heap, v83, (_QWORD *)&v81 + 1);
            if ( v20 )
            {
              v61 = Heap;
LABEL_79:
              v72 = v61;
              WxFreeHeapEx(&v72);
              goto LABEL_31;
            }
            *(_QWORD *)&v81 = Heap;
            WapUriUpdateIriComponentEncodedFlags((unsigned int)v25, &v81);
            LODWORD(v82) = v71 & 0x1DFC0000 | v82 & *(int *)((char *)dword_18009D088 + *(_QWORD *)v74);
            v55 = *(_DWORD *)((_BYTE *)v86 + *(_QWORD *)v74) & v82;
          }
          else
          {
            v68 = (const void *)*v60;
            v69 = v77;
            v70 = (__int64)v68;
            memcpy_0(Heap, v68, 2 * v77);
            *(_QWORD *)&v81 = Heap;
            LODWORD(v82) = v71;
            *((_QWORD *)&v81 + 1) = v69;
          }
          v62 = v75;
          if ( ((unsigned __int8)v75 & v23) != 0 && v70 )
            WxFreeHeapEx(&v70);
          v63 = (__int64)v73;
          v23 |= v62;
          v64 = v82;
          *(_OWORD *)v73 = v81;
          *(_QWORD *)(v63 + 16) = v64;
          if ( v25 == 5 )
          {
            v20 = WapUriTransformPath(v63, v55);
            if ( v20 )
              goto LABEL_31;
          }
        }
      }
      if ( !v24 )
        break;
      ++v25;
    }
    LOBYTE(v11) = v76;
  }
  v37 = v79;
  *(RTL_SRWLOCK *)v74 = v79[7];
  v70 = 0;
  if ( (unsigned int)WapUriRecomposeW(*(_DWORD **)v74, v11, (__int64)v87, v17, 0, 0, 0, (unsigned __int64 *)&v70)
    || (v39 = v70, (unsigned __int64)(v70 - 1) > 0xC34FF) )
  {
LABEL_59:
    v20 = 534;
    goto LABEL_31;
  }
  v40 = WxAllocateHeapEx(v38, 2 * v70 + 248);
  v42 = (RTL_SRWLOCK *)v40;
  if ( !v40 )
  {
LABEL_106:
    v20 = 8;
    goto LABEL_31;
  }
  v43 = *(_DWORD **)v74;
  *(_QWORD *)v40 = 0;
  *(_DWORD *)v40 = 1229541973;
  *(_BYTE *)(v40 + 240) = v11;
  v20 = WapUriRecomposeW(v43, v11, (__int64)v87, v41, (void *)(v40 + 24), (char *)(v40 + 248), v39, 0);
  if ( v20 )
  {
    WapUriFreeTransformedIri(v42);
    goto LABEL_31;
  }
  AcquireSRWLockExclusive(v37 + 1);
  v44 = v72;
  v45 = v37 + 2;
  if ( !v72 )
    v44 = v37 + 2;
  v46 = (RTL_SRWLOCK *)v44->Ptr;
  v72 = v46;
  if ( v46 == v45 )
    goto LABEL_55;
  v47 = v46;
  do
  {
    v16 = v47 - 1;
    if ( LOBYTE(v47[29].Ptr) != (_BYTE)v11 )
      goto LABEL_54;
    v48 = v11;
    for ( i = 0; ; ++i )
    {
      if ( !v48 || i >= 8 )
      {
        WapUriFreeTransformedIri(v42);
        goto LABEL_30;
      }
      if ( ((unsigned __int8)(1 << i) & v48) != 0 )
        break;
LABEL_88:
      ;
    }
    if ( (*((_DWORD *)v37[4].Ptr + 6 * i + 10) & ~*((_DWORD *)v86 + i)) == LODWORD(v16[3 * i + 5].Ptr) )
    {
      v48 ^= 1 << i;
      goto LABEL_88;
    }
    v46 = v72;
LABEL_54:
    v47 = (RTL_SRWLOCK *)v46->Ptr;
    v72 = v47;
    v46 = v47;
  }
  while ( v47 != v45 );
LABEL_55:
  v58 = (RTL_SRWLOCK **)v37[3].Ptr;
  if ( *v58 != v45 )
    __fastfail(3u);
  v16 = v42;
  v42[1].Ptr = v45;
  v42[2].Ptr = v58;
  *v58 = v42 + 1;
  v37[3].Ptr = &v42[1];
LABEL_30:
  ReleaseSRWLockExclusive(v37 + 1);
  v20 = 0;
LABEL_31:
  for ( j = 0; v23; ++j )
  {
    if ( j >= 8 )
      break;
    if ( ((unsigned __int8)(1 << j) & v23) != 0 )
    {
      v23 ^= 1 << j;
      v51 = *(void **)&v87[6 * j];
      v52 = &v87[6 * j];
      if ( v51 )
      {
        if ( g_fWxHeapExtensionInitialized )
          g_WxHeapExtensionInterfaces(*(_QWORD *)&v87[6 * j]);
        else
          HeapFree(g_hWxProcessHeap, 0, v51);
        *(_QWORD *)v52 = 0;
      }
      *((_QWORD *)v52 + 1) = 0;
    }
  }
  if ( v20 )
  {
LABEL_41:
    v8 = v80;
    goto LABEL_42;
  }
LABEL_6:
  v18 = v85;
  v19 = (unsigned __int64)v16[(unsigned __int64)v85 / 8 + 4].Ptr;
  if ( v19 > 0x186A0 )
  {
    v20 = 534;
    goto LABEL_41;
  }
  *v80 = v19;
  if ( v84 )
    *v84 = *(PVOID *)((char *)&v16[3].Ptr + v18);
  return 0;
}

```

## disassembly

```asm
0x1800068a0  mov     [rsp-8+arg_10], rbx
0x1800068a5  push    rbp
0x1800068a6  push    rsi
0x1800068a7  push    rdi
0x1800068a8  push    r12
0x1800068aa  push    r13
0x1800068ac  push    r14
0x1800068ae  push    r15
0x1800068b0  lea     rbp, [rsp-0B0h]
0x1800068b8  sub     rsp, 1B0h
0x1800068bf  mov     rax, cs:__security_cookie
0x1800068c6  xor     rax, rsp
0x1800068c9  mov     [rbp+0E0h+var_40], rax
0x1800068d0  mov     rax, [rbp+0E0h+arg_20]
0x1800068d7  mov     rsi, rcx
0x1800068da  movsxd  rbx, edx
0x1800068dd  mov     edi, 1
0x1800068e2  mov     rdx, [rbp+0E0h+arg_28]
0x1800068e9  mov     r14d, r8d
0x1800068ec  mov     [rbp+0E0h+var_130], rax
0x1800068f0  mov     rax, [rsi+20h]
0x1800068f4  mov     [rbp+0E0h+var_160], rcx
0x1800068f8  mov     ecx, ebx
0x1800068fa  shl     dil, cl
0x1800068fd  mov     [rbp+0E0h+var_158], rdx
0x180006901  mov     [rsp+1E0h+var_174], edi
0x180006905  test    [rax+0F0h], dil
0x18000690c  jz      loc_180006FA7
0x180006912  lea     rcx, [rsi+8]; SRWLock
0x180006916  call    cs:__imp_AcquireSRWLockShared
0x18000691d  nop     dword ptr [rax+rax+00h]
0x180006922  lea     rax, [rbx+rbx*2]
0x180006926  mov     ecx, r14d
0x180006929  lea     r8, ds:0[rax*8]
0x180006931  not     ecx
0x180006933  mov     rax, [rsi+20h]
0x180006937  xor     r13d, r13d
0x18000693a  mov     [rbp+0E0h+var_128], r8
0x18000693e  mov     edx, [r8+rax+28h]
0x180006943  mov     rax, [rsi+10h]
0x180006947  and     edx, ecx
0x180006949  lea     rcx, [rsi+10h]
0x18000694d  cmp     rax, rcx
0x180006950  jz      loc_180006EBE
0x180006956  lea     r15, [rax-8]
0x18000695a  mov     [rsp+1E0h+var_190], rax
0x18000695f  test    [r15+0F0h], dil
0x180006966  jz      short loc_1800069E3
0x180006968  cmp     edx, [r15+r8+28h]
0x18000696d  jnz     short loc_1800069E3
0x18000696f  lea     rcx, [rsi+8]; SRWLock
0x180006973  call    cs:__imp_ReleaseSRWLockShared
0x18000697a  nop     dword ptr [rax+rax+00h]
0x18000697f  test    r15, r15
0x180006982  jz      short loc_1800069F3
0x180006984  mov     rax, [rbp+0E0h+var_128]
0x180006988  mov     rcx, [rax+r15+20h]
0x18000698d  cmp     rcx, 186A0h
0x180006994  ja      loc_1800070CD
0x18000699a  mov     rdx, [rbp+0E0h+var_158]
0x18000699e  mov     [rdx], rcx
0x1800069a1  mov     rcx, [rbp+0E0h+var_130]
0x1800069a5  test    rcx, rcx
0x1800069a8  jz      short loc_1800069B2
0x1800069aa  mov     rax, [rax+r15+18h]
0x1800069af  mov     [rcx], rax
0x1800069b2  mov     r12d, r13d
0x1800069b5  mov     eax, r12d
0x1800069b8  mov     rcx, [rbp+0E0h+var_40]
0x1800069bf  xor     rcx, rsp; StackCookie
0x1800069c2  call    __security_check_cookie
0x1800069c7  mov     rbx, [rsp+1E0h+arg_10]
0x1800069cf  add     rsp, 1B0h
0x1800069d6  pop     r15
0x1800069d8  pop     r14
0x1800069da  pop     r13
0x1800069dc  pop     r12
0x1800069de  pop     rdi
0x1800069df  pop     rsi
0x1800069e0  pop     rbp
0x1800069e1  retn
0x1800069e3  mov     rax, [rax]
0x1800069e6  mov     r15, r13
0x1800069e9  cmp     rax, rcx
0x1800069ec  jz      short loc_18000696F
0x1800069ee  jmp     loc_180006956
0x1800069f3  mov     rax, [rsi+20h]
0x1800069f7  xorps   xmm0, xmm0
0x1800069fa  movups  [rbp+0E0h+var_120], xmm0
0x1800069fe  mov     r15, r13
0x180006a01  mov     r12d, r13d
0x180006a04  movups  [rbp+0E0h+var_110], xmm0
0x180006a08  mov     dword ptr [rbp+rbx*4+0E0h+var_120], r14d
0x180006a0d  xor     bl, bl
0x180006a0f  movzx   r14d, dil
0x180006a13  mov     esi, r13d
0x180006a16  movups  xmm0, xmmword ptr [rax+18h]
0x180006a1a  movups  xmm1, xmmword ptr [rax+28h]
0x180006a1e  movups  xmmword ptr [rbp+0E0h+var_100], xmm0
0x180006a22  movups  xmm0, xmmword ptr [rax+38h]
0x180006a26  movups  [rbp+0E0h+var_F0], xmm1
0x180006a2a  movups  xmm1, xmmword ptr [rax+48h]
0x180006a2e  movups  [rbp+0E0h+var_E0], xmm0
0x180006a32  movups  xmm0, xmmword ptr [rax+58h]
0x180006a36  movups  [rbp+0E0h+var_D0], xmm1
0x180006a3a  movups  xmm1, xmmword ptr [rax+68h]
0x180006a3e  movups  [rbp+0E0h+var_C0], xmm0
0x180006a42  movups  xmm0, xmmword ptr [rax+78h]
0x180006a46  movups  [rbp+0E0h+var_B0], xmm1
0x180006a4a  movups  xmm1, xmmword ptr [rax+88h]
0x180006a51  movups  [rbp+0E0h+var_A0], xmm0
0x180006a55  movups  xmm0, xmmword ptr [rax+98h]
0x180006a5c  movups  [rbp+0E0h+var_90], xmm1
0x180006a60  movups  xmm1, xmmword ptr [rax+0A8h]
0x180006a67  movups  [rbp+0E0h+var_80], xmm0
0x180006a6b  movups  xmm0, xmmword ptr [rax+0B8h]
0x180006a72  movups  [rbp+0E0h+var_70], xmm1
0x180006a76  movups  xmm1, xmmword ptr [rax+0C8h]
0x180006a7d  movups  [rbp+0E0h+var_60], xmm0
0x180006a84  movups  [rbp+0E0h+var_50], xmm1
0x180006a8b  test    dil, dil
0x180006a8e  jz      short loc_180006AC3
0x180006a90  cmp     esi, 8
0x180006a93  jge     short loc_180006AB6
0x180006a95  mov     ecx, esi
0x180006a97  mov     edi, 1
0x180006a9c  shl     dil, cl
0x180006a9f  mov     byte ptr [rsp+1E0h+var_178], dil
0x180006aa4  test    r14b, dil
0x180006aa7  jnz     loc_180006C77
0x180006aad  test    r14b, r14b
0x180006ab0  jnz     loc_1800070A3
0x180006ab6  test    r12d, r12d
0x180006ab9  jnz     loc_180006BF4
0x180006abf  mov     edi, [rsp+1E0h+var_174]
0x180006ac3  mov     rsi, [rbp+0E0h+var_160]
0x180006ac7  lea     rcx, [rsp+1E0h+var_1A0]
0x180006acc  mov     [rsp+1E0h+var_1A8], rcx; __int64
0x180006ad1  lea     r8, [rbp+0E0h+var_100]; int
0x180006ad5  mov     [rsp+1E0h+var_1B0], r13; __int64
0x180006ada  movzx   edx, dil; int
0x180006ade  mov     [rsp+1E0h+var_1B8], r13; __int64
0x180006ae3  mov     rax, [rsi+38h]
0x180006ae7  mov     rcx, rax; int
0x180006aea  mov     qword ptr [rsp+1E0h+var_180], rax
0x180006aef  mov     [rsp+1E0h+var_1A0], r13
0x180006af4  mov     [rsp+1E0h+var_1C0], r13; void *
0x180006af9  call    WapUriRecomposeW
0x180006afe  test    eax, eax
0x180006b00  jnz     loc_180006D76
0x180006b06  mov     r12, [rsp+1E0h+var_1A0]
0x180006b0b  lea     rax, [r12-1]
0x180006b10  cmp     rax, 0C34FFh
0x180006b16  ja      loc_180006D76
0x180006b1c  lea     rdx, ds:0F8h[r12*2]
0x180006b24  call    WxAllocateHeapEx
0x180006b29  mov     r14, rax
0x180006b2c  test    rax, rax
0x180006b2f  jz      loc_1800070B5
0x180006b35  mov     rcx, qword ptr [rsp+1E0h+var_180]; int
0x180006b3a  lea     rdx, [r14+18h]
0x180006b3e  xor     eax, eax
0x180006b40  mov     [rsp+1E0h+var_1A8], r13; __int64
0x180006b45  mov     [r14], rax
0x180006b48  lea     r8, [rbp+0E0h+var_100]; int
0x180006b4c  lea     rax, [r14+0F8h]
0x180006b53  mov     [rsp+1E0h+var_1B0], r12; __int64
0x180006b58  mov     [rsp+1E0h+var_1B8], rax; __int64
0x180006b5d  mov     [rsp+1E0h+var_1C0], rdx; void *
0x180006b62  movzx   edx, dil; int
0x180006b66  mov     dword ptr [r14], 49495255h
0x180006b6d  mov     [r14+0F0h], dil
0x180006b74  call    WapUriRecomposeW
0x180006b79  mov     r12d, eax
0x180006b7c  test    eax, eax
0x180006b7e  jnz     loc_1800070C0
0x180006b84  lea     rcx, [rsi+8]; SRWLock
0x180006b88  call    cs:__imp_AcquireSRWLockExclusive
0x180006b8f  nop     dword ptr [rax+rax+00h]
0x180006b94  mov     rax, [rsp+1E0h+var_190]
0x180006b99  lea     r11, [rsi+10h]
0x180006b9d  test    rax, rax
0x180006ba0  cmovz   rax, r11
0x180006ba4  mov     rcx, [rax]
0x180006ba7  mov     [rsp+1E0h+var_190], rcx
0x180006bac  cmp     rcx, r11
0x180006baf  jz      loc_180006D39
0x180006bb5  mov     rax, rcx
0x180006bb8  lea     r15, [rax-8]
0x180006bbc  cmp     [r15+0F0h], dil
0x180006bc3  jnz     loc_180006D25
0x180006bc9  movzx   r9d, dil
0x180006bcd  mov     r10d, r13d
0x180006bd0  test    r9b, r9b
0x180006bd3  jnz     loc_180006F8A
0x180006bd9  mov     rcx, r14; lpMem
0x180006bdc  call    WapUriFreeTransformedIri
0x180006be1  lea     rcx, [rsi+8]; SRWLock
0x180006be5  call    cs:__imp_ReleaseSRWLockExclusive
0x180006bec  nop     dword ptr [rax+rax+00h]
0x180006bf1  mov     r12d, r13d
0x180006bf4  mov     edi, r13d
0x180006bf7  test    bl, bl
0x180006bf9  jz      short loc_180006C56
0x180006bfb  cmp     edi, 8
0x180006bfe  jge     short loc_180006C56
0x180006c00  mov     ecx, edi
0x180006c02  mov     edx, 1
0x180006c07  shl     dl, cl
0x180006c09  test    bl, dl
0x180006c0b  jz      short loc_180006C50
0x180006c0d  movsxd  rax, edi
0x180006c10  lea     rsi, [rbp+0E0h+var_100]
0x180006c14  xor     bl, dl
0x180006c16  lea     rcx, [rax+rax*2]
0x180006c1a  mov     r8, [rsi+rcx*8]; lpMem
0x180006c1e  lea     rsi, [rsi+rcx*8]
0x180006c22  test    r8, r8
0x180006c25  jz      short loc_180006C4C
0x180006c27  cmp     cs:?g_fWxHeapExtensionInitialized@@3HA, 0; int g_fWxHeapExtensionInitialized
0x180006c2e  jnz     loc_180006F42
0x180006c34  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x180006c3b  xor     edx, edx; dwFlags
0x180006c3d  call    cs:__imp_HeapFree
0x180006c44  nop     dword ptr [rax+rax+00h]
0x180006c49  mov     [rsi], r13
0x180006c4c  mov     [rsi+8], r13
0x180006c50  inc     edi
0x180006c52  test    bl, bl
0x180006c54  jnz     short loc_180006BFB
0x180006c56  test    r12d, r12d
0x180006c59  jz      loc_180006984
0x180006c5f  mov     rdx, [rbp+0E0h+var_158]
0x180006c63  mov     rcx, [rbp+0E0h+var_130]
0x180006c67  test    rcx, rcx
0x180006c6a  jz      short loc_180006C6F
0x180006c6c  mov     [rcx], r13
0x180006c6f  mov     [rdx], r13
0x180006c72  jmp     loc_1800069B5
0x180006c77  movsxd  rcx, esi
0x180006c7a  lea     rdx, [rbp+0E0h+var_100]
0x180006c7e  xorps   xmm0, xmm0
0x180006c81  movups  [rbp+0E0h+var_150], xmm0
0x180006c85  lea     rax, [rcx+rcx*2]
0x180006c89  lea     rdx, [rdx+rax*8]
0x180006c8d  lea     rax, ds:0[rcx*4]
0x180006c95  mov     [rsp+1E0h+var_188], rdx
0x180006c9a  xor     ecx, ecx
0x180006c9c  mov     qword ptr [rsp+1E0h+var_180], rax
0x180006ca1  mov     eax, dword ptr [rbp+rax+0E0h+var_120]
0x180006ca5  mov     [rsp+1E0h+var_198], eax
0x180006ca9  mov     [rbp+0E0h+var_140], rcx
0x180006cad  cmp     esi, 3
0x180006cb0  jz      short loc_180006CDA
0x180006cb2  mov     ecx, [rdx+10h]
0x180006cb5  xor     r14b, dil
0x180006cb8  mov     edi, ecx
0x180006cba  mov     [rsp+1E0h+var_198], ecx
0x180006cbe  and     edi, eax
0x180006cc0  bt      eax, 18h
0x180006cc4  jb      loc_180007007
0x180006cca  test    edi, edi
0x180006ccc  jnz     loc_180006D63
0x180006cd2  mov     r12d, r13d
0x180006cd5  jmp     loc_180006AAD
0x180006cda  mov     ecx, [rdx+10h]
0x180006cdd  and     ecx, eax
0x180006cdf  and     ecx, 1C000000h
0x180006ce5  jz      short loc_180006CB2
0x180006ce7  cmp     ecx, 10000000h
0x180006ced  jnz     loc_180006EEB
0x180006cf3  test    bl, 8
0x180006cf6  jnz     loc_180006FDE
0x180006cfc  mov     r12, [rbp+0E0h+var_160]
0x180006d00  and     bl, 0F7h
0x180006d03  movups  xmm0, xmmword ptr [r12+0C8h]
0x180006d0c  movsd   xmm1, qword ptr [r12+0D8h]
0x180006d16  movups  xmmword ptr [rdx], xmm0
0x180006d19  movsd   qword ptr [rdx+10h], xmm1
0x180006d1e  jmp     short loc_180006CB2
0x180006d20  mov     rcx, [rsp+1E0h+var_190]
0x180006d25  mov     rax, [rcx]
0x180006d28  mov     [rsp+1E0h+var_190], rax
0x180006d2d  mov     rcx, rax
0x180006d30  cmp     rax, r11
0x180006d33  jnz     loc_180006BB8
0x180006d39  mov     rdx, [r11+8]
0x180006d3d  cmp     [rdx], r11
0x180006d40  jnz     loc_180006ECB
0x180006d46  mov     rcx, r14
0x180006d49  lea     rax, [rcx+8]
0x180006d4d  mov     r15, rcx
0x180006d50  mov     [rax], r11
0x180006d53  mov     [rax+8], rdx
0x180006d57  mov     [rdx], rax
0x180006d5a  mov     [r11+8], rax
0x180006d5e  jmp     loc_180006BE1
0x180006d63  test    edi, 202h
0x180006d69  jz      short loc_180006D81
0x180006d6b  mov     r12d, 57h ; 'W'
  ... truncated ...
```
