# UdfSeqCacheIssuePowWriteForBuffer

- ea: `0x14001a478`
- end: `0x14001ab07`
- name: `UdfSeqCacheIssuePowWriteForBuffer`
- size: `1679`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x14000cce0`

## callees

- `0x140009980`
- `0x14000a2e8`
- `0x14001093c`
- `0x140019980`
- `0x140019ad0`
- `0x14001a3a4`
- `0x14001a478`
- `0x14001ab10`
- `0x14001b0cc`
- `0x14004ce50`

## import_xrefs

- `ntoskrnl!FsRtlAddLargeMcbEntry` at `0x14001a7ef`
- `ntoskrnl!FsRtlAddLargeMcbEntry` at `0x14001a9c3`
- `ntoskrnl!FsRtlAddLargeMcbEntry` at `0x14001a7ef`
- `ntoskrnl!FsRtlAddLargeMcbEntry` at `0x14001a9c3`

## pseudocode

```c
void __fastcall UdfSeqCacheIssuePowWriteForBuffer(__int64 a1, __int64 a2, unsigned int a3, int a4, int a5)
{
  __int64 v5; // rbx
  int v8; // r8d
  int PowInfo; // r14d
  __int64 v10; // rcx
  unsigned __int64 v11; // rbx
  __int64 v12; // rdx
  __int64 v13; // r13
  unsigned int v14; // r12d
  unsigned int j; // r15d
  unsigned __int64 v16; // r14
  _DWORD *v17; // rcx
  int v18; // edx
  int v19; // r15d
  unsigned int v20; // r15d
  bool v21; // zf
  __int64 v22; // rax
  unsigned int v23; // r14d
  __int64 v24; // rax
  __int64 v25; // rcx
  unsigned int v26; // ecx
  int v27; // r15d
  unsigned __int64 v28; // r13
  __int64 v29; // rax
  int v30; // eax
  int v31; // ecx
  unsigned int v32; // r12d
  unsigned int v33; // r15d
  unsigned int v34; // r13d
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rdx
  unsigned int v40; // ecx
  int v41; // r9d
  __int64 v42; // r13
  int v43; // r15d
  int Lbn; // [rsp+30h] [rbp-38h] BYREF
  unsigned int Lbn_4; // [rsp+34h] [rbp-34h] BYREF
  unsigned __int64 v46; // [rsp+38h] [rbp-30h] BYREF
  __int64 v47; // [rsp+40h] [rbp-28h]
  __int64 i; // [rsp+48h] [rbp-20h]
  _DWORD *v49; // [rsp+50h] [rbp-18h] BYREF
  unsigned __int64 v50; // [rsp+58h] [rbp-10h]
  unsigned int v51; // [rsp+B0h] [rbp+48h]
  unsigned int v52; // [rsp+B8h] [rbp+50h]

  v5 = a3;
  v49 = 0;
  Lbn_4 = 0;
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x20000000) != 0 )
  {
    WPP_SF_dd(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
      22,
      WPP_091ecc37555d3ea49b7bb42fddee33c5_Traceguids,
      a3,
      a4);
  }
  if ( !(unsigned __int8)UdfAcquireResource(0, a1 + 136, 0, 0) )
  {
    PowInfo = *(_DWORD *)(a2 + 656);
    goto LABEL_93;
  }
  *(_DWORD *)(a2 + 4) &= ~0x40u;
  v10 = 5 * v5;
  v11 = 0;
  LODWORD(v12) = *(_DWORD *)(a2 + 8) - *(_DWORD *)(a2 + 8 * v10 + 28);
  v13 = *(_QWORD *)(a2 + 8 * v10 + 40);
  v14 = 0;
  v52 = 0;
  v47 = v10;
  v50 = 0;
  v51 = v12;
  for ( i = v13; ; i = v13 )
  {
LABEL_8:
    if ( v14 >= (unsigned int)v12 )
    {
LABEL_91:
      PowInfo = 0;
      *(_WORD *)(a2 + 8 * v10 + 24) = 2;
      *(_DWORD *)(a2 + 692) = 0;
      *(_DWORD *)(a2 + 660) = v12;
      *(_DWORD *)(a2 + 688) = a3;
      goto LABEL_92;
    }
    while ( v14 < (unsigned int)v12 )
    {
      v11 = *(_QWORD *)(a2 + 8 * v10 + 56) + 32LL * v14;
      if ( !*(_BYTE *)(v11 + 26) )
        goto LABEL_25;
      if ( !*(_DWORD *)(v11 + 20) )
      {
        PowInfo = UdfSeqCacheLookupPowAddress(a2, *(_QWORD *)(a2 + 8 * v10 + 56) + 32LL * v14);
        if ( PowInfo < 0 )
          goto LABEL_92;
        LODWORD(v12) = v51;
      }
      for ( j = *(unsigned __int16 *)(v11 + 24); j + v14 < (unsigned int)v12; j += *(unsigned __int16 *)(v16 + 24) )
      {
        v16 = v11 + 32LL * j;
        if ( !*(_BYTE *)(v16 + 26) )
          break;
        if ( !*(_DWORD *)(v16 + 20) )
        {
          if ( (int)UdfSeqCacheLookupPowAddress(a2, v11 + 32LL * j) < 0 )
            break;
          LODWORD(v12) = v51;
        }
        if ( *(_DWORD *)(v16 + 20) != j + *(_DWORD *)(v11 + 20) )
          break;
      }
      *(_BYTE *)(a1 + 895) |= 4u;
      PowInfo = UdfSeqCacheWriteBlocksAtPsn(a1, a2, v13, *(_DWORD *)(v11 + 20), j, 1);
      if ( PowInfo < 0 )
        goto LABEL_92;
      LODWORD(v12) = v51;
      v10 = v47;
      v13 += j << *(_DWORD *)(a1 + 72);
      v14 += j;
      i = v13;
      v52 = v14;
    }
    if ( v14 == (_DWORD)v12 )
      goto LABEL_91;
LABEL_25:
    PowInfo = UdfSeqCacheGetPowInfo(a1, a4, v8, (unsigned int)&Lbn_4, (__int64)&v49);
    if ( PowInfo < 0 )
      goto LABEL_92;
    if ( a4 && *(_QWORD *)(v11 + 8) == *(_QWORD *)(a2 + 752) )
      break;
LABEL_56:
    v12 = v51;
    v27 = 0;
    v28 = 0;
    v11 = 0;
    while ( 1 )
    {
      v10 = v47;
      v46 = v28;
      if ( v27 + v14 >= (unsigned int)v12 )
        break;
      v11 = *(_QWORD *)(a2 + 8 * v47 + 56) + 32LL * (v27 + v14);
      if ( *(_BYTE *)(v11 + 26) )
        break;
      v29 = *(_QWORD *)(a2 + 752);
      LOBYTE(a5) = 0;
      if ( *(_QWORD *)(v11 + 8) == v29 )
      {
        PowInfo = UdfCacheIsReserved(v47, a2, v11, &a5);
        if ( PowInfo < 0 )
          goto LABEL_92;
        v12 = v51;
        if ( (_BYTE)a5 )
        {
          v10 = v47;
          break;
        }
      }
      v30 = *(unsigned __int16 *)(v11 + 24);
      v50 = v11;
      if ( !v28 )
        v28 = v11;
      v27 += v30;
    }
    if ( !v27 )
      goto LABEL_7;
    v31 = 0;
    v32 = Lbn_4;
    v11 = v28;
    a5 = 0;
    v33 = v49[3];
    Lbn = v33;
    while ( v11 <= v50 && v32 )
    {
      if ( *(_QWORD *)(v11 + 8) != *(_QWORD *)(a2 + 752) || *(_DWORD *)(v11 + 16) == *(_DWORD *)(a2 + 744) )
      {
        v34 = *(unsigned __int16 *)(v11 + 24);
        if ( v34 > v32 )
        {
          v34 = v32;
          v35 = 32LL * v32;
          *(_OWORD *)(v35 + v11) = *(_OWORD *)v11;
          *(_OWORD *)(v35 + v11 + 16) = *(_OWORD *)(v11 + 16);
          *(_WORD *)(v35 + v11 + 24) -= v32;
          *(_DWORD *)(v35 + v11 + 16) += v32;
          v36 = *(_QWORD *)(v11 + 8);
          *(_WORD *)(v11 + 24) = v32;
          if ( v36 != -1 )
          {
            LOBYTE(v12) = 1;
            UdfSeqCacheUpdateFileRefCount(v36, v12, 0);
            v31 = a5;
          }
        }
        if ( *(_QWORD *)(v11 + 8) == *(_QWORD *)(a2 + 752) && !*(_BYTE *)(v11 + 26) )
        {
          if ( !FsRtlAddLargeMcbEntry(*(PLARGE_MCB *)(a2 + 728), *(unsigned int *)(v11 + 16), v33, v34) )
            goto LABEL_89;
          v31 = a5;
        }
        *(_DWORD *)(v11 + 20) = v33;
        v32 -= v34;
        v37 = *(_QWORD *)(a2 + 752);
        v33 += v34;
        v31 += v34;
        Lbn = v33;
        Lbn_4 = v32;
        a5 = v31;
        if ( *(_QWORD *)(v11 + 8) == v37 )
          *(_DWORD *)(a2 + 744) = *(_DWORD *)(v11 + 16) + *(unsigned __int16 *)(v11 + 24);
      }
      else
      {
        if ( v11 != v28 )
          break;
        if ( !(unsigned __int8)UdfCacheReserveSpace(a1, a2, v11, (unsigned int)&Lbn, (__int64)&Lbn_4, 1) )
          goto LABEL_92;
        v33 = Lbn;
        v34 = 0;
        v32 = Lbn_4;
        v31 = a5;
      }
      v38 = v34;
      v28 = v46;
      v11 += 32 * v38;
    }
    v39 = *(_QWORD *)(a1 + 8LL * a4 + 912);
    v40 = v33 - *(_DWORD *)(v39 + 12);
    *(_DWORD *)(v39 + 12) = v33;
    *(_DWORD *)(a1 + 4LL * *(unsigned __int16 *)(a1 + 892) + 940) = v33;
    *(_DWORD *)(v39 + 16) -= v40;
    if ( !v32 )
    {
      v14 = v52;
      LODWORD(v12) = v51;
      v10 = v47;
      if ( v11 == v28 )
      {
LABEL_7:
        v13 = i;
        goto LABEL_8;
      }
    }
    v41 = *(_DWORD *)(v28 + 20);
    v42 = i;
    v43 = a5;
    PowInfo = UdfSeqCacheWriteBlocksAtPsn(a1, a2, i, v41, a5, 1);
    if ( PowInfo < 0 )
    {
      *(_BYTE *)(a1 + 895) |= 4u;
      goto LABEL_92;
    }
    v14 = v43 + v52;
    LODWORD(v12) = v51;
    v10 = v47;
    v13 = (unsigned int)(v43 << *(_DWORD *)(a1 + 72)) + v42;
    v52 += v43;
  }
  if ( !*(_BYTE *)(a4 + a1 + 936) || (v17 = *(_DWORD **)(a1 + 8LL * a4 + 912)) == 0 )
  {
LABEL_55:
    v14 = v52;
    goto LABEL_56;
  }
  v18 = *(_DWORD *)(a1 + 4LL * a4 + 940);
  if ( (v18 & v17[7]) == 0 || v18 == v17[3] )
  {
    *(_BYTE *)(a4 + a1 + 936) = 0;
    goto LABEL_55;
  }
  v19 = v17[5];
  *(_BYTE *)(a4 + a1 + 936) = 0;
  v49 = v17;
  Lbn = v18;
  v20 = v19 - (v18 & (v19 - 1));
  *(_DWORD *)(a1 + 4LL * a4 + 940) += v20;
  LODWORD(v46) = v20;
  while ( 1 )
  {
    v12 = v51;
    v10 = v47;
    v21 = v20 == 0;
    if ( !v20 )
      goto LABEL_51;
    if ( v52 >= v51 )
      goto LABEL_50;
    v11 = *(_QWORD *)(a2 + 8 * v47 + 56) + 32LL * v52;
    if ( *(_BYTE *)(v11 + 26) )
      goto LABEL_50;
    v22 = *(_QWORD *)(a2 + 752);
    LOBYTE(a5) = 0;
    if ( *(_QWORD *)(v11 + 8) == v22 )
    {
      PowInfo = UdfCacheIsReserved(v47, a2, v11, &a5);
      if ( PowInfo < 0 )
        goto LABEL_92;
      if ( (_BYTE)a5 )
        goto LABEL_49;
    }
    if ( *(_QWORD *)(v11 + 8) != *(_QWORD *)(a2 + 752) || *(_DWORD *)(v11 + 16) == *(_DWORD *)(a2 + 744) )
      break;
    if ( !(unsigned __int8)UdfCacheReserveSpace(a1, a2, v11, (unsigned int)&Lbn, (__int64)&v46, 0) )
      goto LABEL_92;
    v20 = v46;
  }
  v23 = *(unsigned __int16 *)(v11 + 24);
  if ( v23 > v20 )
  {
    v23 = v20;
    v24 = 32LL * v20;
    *(_OWORD *)(v24 + v11) = *(_OWORD *)v11;
    *(_OWORD *)(v24 + v11 + 16) = *(_OWORD *)(v11 + 16);
    *(_WORD *)(v24 + v11 + 24) -= v20;
    *(_DWORD *)(v24 + v11 + 16) += v20;
    v25 = *(_QWORD *)(v11 + 8);
    *(_WORD *)(v11 + 24) = v20;
    if ( v25 != -1 )
    {
      LOBYTE(v12) = 1;
      UdfSeqCacheUpdateFileRefCount(v25, v12, 0);
    }
  }
  v26 = Lbn;
  *(_DWORD *)(v11 + 20) = Lbn;
  *(_WORD *)(v11 + 26) = 257;
  if ( *(_QWORD *)(v11 + 8) != *(_QWORD *)(a2 + 752)
    || FsRtlAddLargeMcbEntry(*(PLARGE_MCB *)(a2 + 728), *(unsigned int *)(v11 + 16), v26, v23) )
  {
    v20 -= v23;
    *(_DWORD *)(a2 + 744) = *(_DWORD *)(v11 + 16) + *(unsigned __int16 *)(v11 + 24);
LABEL_49:
    LODWORD(v12) = v51;
    v10 = v47;
LABEL_50:
    v21 = v20 == 0;
LABEL_51:
    v13 = i;
    if ( !v21 )
    {
      *(_DWORD *)(a1 + 4LL * a4 + 940) -= v20;
      *(_BYTE *)(a4 + a1 + 936) = 1;
    }
    v14 = v52;
    goto LABEL_8;
  }
LABEL_89:
  PowInfo = -1073741801;
LABEL_92:
  UdfReleaseDevice(v10, a1, 0);
LABEL_93:
  *(_DWORD *)(a2 + 656) = PowInfo;
}

```

## disassembly

```asm
0x14001a478  mov     [rsp-40h+arg_18], r9d
0x14001a47d  mov     [rsp-40h+arg_10], r8d
0x14001a482  push    rbp
0x14001a483  push    rbx
0x14001a484  push    rsi
0x14001a485  push    rdi
0x14001a486  push    r12
0x14001a488  push    r13
0x14001a48a  push    r14
0x14001a48c  push    r15
0x14001a48e  mov     rbp, rsp
0x14001a491  sub     rsp, 68h
0x14001a495  mov     ebx, r8d
0x14001a498  mov     rdi, rdx
0x14001a49b  mov     rsi, rcx
0x14001a49e  mov     [rbp+var_18], 0
0x14001a4a6  mov     dword ptr [rbp+Lbn+4], 0
0x14001a4ad  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a4b4  lea     rax, WPP_GLOBAL_Control
0x14001a4bb  cmp     rcx, rax
0x14001a4be  jz      short loc_14001A4E6
0x14001a4c0  test    dword ptr [rcx+2Ch], 20000000h
0x14001a4c7  jz      short loc_14001A4E6
0x14001a4c9  mov     rcx, [rcx+18h]
0x14001a4cd  lea     r8, WPP_091ecc37555d3ea49b7bb42fddee33c5_Traceguids
0x14001a4d4  mov     dword ptr [rsp+68h+var_48], r9d
0x14001a4d9  mov     edx, 16h
0x14001a4de  mov     r9d, ebx
0x14001a4e1  call    WPP_SF_dd
0x14001a4e6  lea     rdx, [rsi+88h]
0x14001a4ed  xor     r9d, r9d
0x14001a4f0  xor     r8d, r8d
0x14001a4f3  xor     ecx, ecx
0x14001a4f5  call    UdfAcquireResource
0x14001a4fa  test    al, al
0x14001a4fc  jnz     short loc_14001A50A
0x14001a4fe  mov     r14d, [rdi+290h]
0x14001a505  jmp     loc_14001AAEE
0x14001a50a  and     dword ptr [rdi+4], 0FFFFFFBFh
0x14001a50e  lea     rcx, [rbx+rbx*4]
0x14001a512  mov     edx, [rdi+8]
0x14001a515  xor     ebx, ebx
0x14001a517  sub     edx, [rdi+rcx*8+1Ch]
0x14001a51b  mov     r13, [rdi+rcx*8+28h]
0x14001a520  xor     r12d, r12d
0x14001a523  mov     [rbp+arg_8], r12d
0x14001a527  mov     [rbp+var_28], rcx
0x14001a52b  mov     [rbp+var_10], rbx
0x14001a52f  mov     [rbp+arg_0], edx
0x14001a532  mov     [rbp+var_20], r13
0x14001a536  jmp     short loc_14001A53C
0x14001a538  mov     r13, [rbp+var_20]
0x14001a53c  cmp     r12d, edx
0x14001a53f  jnb     loc_14001AAC3
0x14001a545  cmp     r12d, edx
0x14001a548  jnb     loc_14001A620
0x14001a54e  mov     ebx, r12d
0x14001a551  shl     rbx, 5
0x14001a555  add     rbx, [rdi+rcx*8+38h]
0x14001a55a  cmp     byte ptr [rbx+1Ah], 0
0x14001a55e  jz      loc_14001A626
0x14001a564  cmp     dword ptr [rbx+14h], 0
0x14001a568  jnz     short loc_14001A583
0x14001a56a  mov     rdx, rbx
0x14001a56d  mov     rcx, rdi
0x14001a570  call    UdfSeqCacheLookupPowAddress
0x14001a575  mov     r14d, eax
0x14001a578  test    eax, eax
0x14001a57a  js      loc_14001AAE3
0x14001a580  mov     edx, [rbp+arg_0]
0x14001a583  movzx   r15d, word ptr [rbx+18h]
0x14001a588  jmp     short loc_14001A5C8
0x14001a58a  mov     r14d, r15d
0x14001a58d  shl     r14, 5
0x14001a591  add     r14, rbx
0x14001a594  cmp     byte ptr [r14+1Ah], 0
0x14001a599  jz      short loc_14001A5D0
0x14001a59b  cmp     dword ptr [r14+14h], 0
0x14001a5a0  jnz     short loc_14001A5B4
0x14001a5a2  mov     rdx, r14
0x14001a5a5  mov     rcx, rdi
0x14001a5a8  call    UdfSeqCacheLookupPowAddress
0x14001a5ad  test    eax, eax
0x14001a5af  js      short loc_14001A5D0
0x14001a5b1  mov     edx, [rbp+arg_0]
0x14001a5b4  mov     ecx, [rbx+14h]
0x14001a5b7  add     ecx, r15d
0x14001a5ba  cmp     [r14+14h], ecx
0x14001a5be  jnz     short loc_14001A5D0
0x14001a5c0  movzx   eax, word ptr [r14+18h]
0x14001a5c5  add     r15d, eax
0x14001a5c8  lea     eax, [r15+r12]
0x14001a5cc  cmp     eax, edx
0x14001a5ce  jb      short loc_14001A58A
0x14001a5d0  or      byte ptr [rsi+37Fh], 4
0x14001a5d7  mov     r8, r13
0x14001a5da  mov     r9d, [rbx+14h]
0x14001a5de  mov     rdx, rdi
0x14001a5e1  mov     [rsp+68h+var_40], 1
0x14001a5e6  mov     rcx, rsi
0x14001a5e9  mov     dword ptr [rsp+68h+var_48], r15d
0x14001a5ee  call    UdfSeqCacheWriteBlocksAtPsn
0x14001a5f3  mov     r14d, eax
0x14001a5f6  test    eax, eax
0x14001a5f8  js      loc_14001AAE3
0x14001a5fe  mov     ecx, [rsi+48h]
0x14001a601  mov     eax, r15d
0x14001a604  mov     edx, [rbp+arg_0]
0x14001a607  shl     eax, cl
0x14001a609  mov     rcx, [rbp+var_28]
0x14001a60d  add     r13, rax
0x14001a610  add     r12d, r15d
0x14001a613  mov     [rbp+var_20], r13
0x14001a617  mov     [rbp+arg_8], r12d
0x14001a61b  jmp     loc_14001A545
0x14001a620  jz      loc_14001AAC3
0x14001a626  movsxd  r15, [rbp+arg_18]
0x14001a62a  lea     rax, [rbp+var_18]
0x14001a62e  mov     edx, r15d
0x14001a631  mov     [rsp+68h+var_48], rax
0x14001a636  lea     r9, [rbp+Lbn+4]
0x14001a63a  mov     rcx, rsi
0x14001a63d  call    UdfSeqCacheGetPowInfo
0x14001a642  mov     r14d, eax
0x14001a645  test    eax, eax
0x14001a647  js      loc_14001AAE3
0x14001a64d  test    r15d, r15d
0x14001a650  jz      loc_14001A84A
0x14001a656  mov     rax, [rdi+2F0h]
0x14001a65d  cmp     [rbx+8], rax
0x14001a661  jnz     loc_14001A84A
0x14001a667  cmp     byte ptr [r15+rsi+3A8h], 0
0x14001a670  mov     r12, r15
0x14001a673  jz      loc_14001A846
0x14001a679  mov     rcx, [rsi+r15*8+390h]
0x14001a681  test    rcx, rcx
0x14001a684  jz      loc_14001A846
0x14001a68a  mov     edx, [rsi+r15*4+3ACh]
0x14001a692  test    [rcx+1Ch], edx
0x14001a695  jz      loc_14001A83D
0x14001a69b  cmp     edx, [rcx+0Ch]
0x14001a69e  jz      loc_14001A83D
0x14001a6a4  mov     r15d, [rcx+14h]
0x14001a6a8  mov     r13d, [rbp+arg_8]
0x14001a6ac  mov     byte ptr [r12+rsi+3A8h], 0
0x14001a6b5  mov     [rbp+var_18], rcx
0x14001a6b9  lea     eax, [r15-1]
0x14001a6bd  mov     dword ptr [rbp+Lbn], edx
0x14001a6c0  and     eax, edx
0x14001a6c2  sub     r15d, eax
0x14001a6c5  add     [rsi+r12*4+3ACh], r15d
0x14001a6cd  mov     dword ptr [rbp+var_30], r15d
0x14001a6d1  mov     edx, [rbp+arg_0]
0x14001a6d4  mov     rcx, [rbp+var_28]
0x14001a6d8  test    r15d, r15d
0x14001a6db  jz      loc_14001A81D
0x14001a6e1  cmp     r13d, edx
0x14001a6e4  jnb     loc_14001A81A
0x14001a6ea  mov     rbx, r13
0x14001a6ed  shl     rbx, 5
0x14001a6f1  add     rbx, [rdi+rcx*8+38h]
0x14001a6f6  cmp     byte ptr [rbx+1Ah], 0
0x14001a6fa  jnz     loc_14001A81A
0x14001a700  mov     rax, [rdi+2F0h]
0x14001a707  mov     byte ptr [rbp+arg_20], 0
0x14001a70b  cmp     [rbx+8], rax
0x14001a70f  jnz     short loc_14001A735
0x14001a711  lea     r9, [rbp+arg_20]
0x14001a715  mov     r8, rbx
0x14001a718  mov     rdx, rdi
0x14001a71b  call    UdfCacheIsReserved
0x14001a720  mov     r14d, eax
0x14001a723  test    eax, eax
0x14001a725  js      loc_14001AAE3
0x14001a72b  cmp     byte ptr [rbp+arg_20], 0
0x14001a72f  jnz     loc_14001A813
0x14001a735  mov     rax, [rdi+2F0h]
0x14001a73c  cmp     [rbx+8], rax
0x14001a740  jnz     short loc_14001A77E
0x14001a742  mov     eax, [rdi+2E8h]
0x14001a748  cmp     [rbx+10h], eax
0x14001a74b  jz      short loc_14001A77E
0x14001a74d  lea     rax, [rbp+var_30]
0x14001a751  mov     [rsp+68h+var_40], 0
0x14001a756  lea     r9, [rbp+Lbn]
0x14001a75a  mov     [rsp+68h+var_48], rax
0x14001a75f  mov     r8, rbx
0x14001a762  mov     rdx, rdi
0x14001a765  mov     rcx, rsi
0x14001a768  call    UdfCacheReserveSpace
0x14001a76d  test    al, al
0x14001a76f  jz      loc_14001AAE3
0x14001a775  mov     r15d, dword ptr [rbp+var_30]
0x14001a779  jmp     loc_14001A6D1
0x14001a77e  movzx   r14d, word ptr [rbx+18h]
0x14001a783  cmp     r14d, r15d
0x14001a786  jbe     short loc_14001A7C6
0x14001a788  movups  xmm0, xmmword ptr [rbx]
0x14001a78b  mov     eax, r15d
0x14001a78e  mov     r14d, r15d
0x14001a791  shl     rax, 5
0x14001a795  movups  xmmword ptr [rax+rbx], xmm0
0x14001a799  movups  xmm1, xmmword ptr [rbx+10h]
0x14001a79d  movups  xmmword ptr [rax+rbx+10h], xmm1
0x14001a7a2  sub     [rax+rbx+18h], r15w
0x14001a7a8  add     [rax+rbx+10h], r15d
0x14001a7ad  mov     rcx, [rbx+8]
0x14001a7b1  mov     [rbx+18h], r15w
0x14001a7b6  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14001a7ba  jz      short loc_14001A7C6
0x14001a7bc  xor     r8d, r8d
0x14001a7bf  mov     dl, 1
0x14001a7c1  call    UdfSeqCacheUpdateFileRefCount
0x14001a7c6  mov     ecx, dword ptr [rbp+Lbn]
0x14001a7c9  mov     [rbx+14h], ecx
0x14001a7cc  mov     word ptr [rbx+1Ah], 101h
0x14001a7d2  mov     rax, [rdi+2F0h]
0x14001a7d9  cmp     [rbx+8], rax
0x14001a7dd  jnz     short loc_14001A803
0x14001a7df  mov     edx, [rbx+10h]; Vbn
0x14001a7e2  mov     r8d, ecx; Lbn
0x14001a7e5  mov     rcx, [rdi+2D8h]; Mcb
0x14001a7ec  mov     r9d, r14d; SectorCount
0x14001a7ef  call    cs:__imp_FsRtlAddLargeMcbEntry
0x14001a7f6  nop     dword ptr [rax+rax+00h]
0x14001a7fb  test    al, al
0x14001a7fd  jz      loc_14001AAB2
0x14001a803  movzx   eax, word ptr [rbx+18h]
0x14001a807  sub     r15d, r14d
0x14001a80a  add     eax, [rbx+10h]
0x14001a80d  mov     [rdi+2E8h], eax
0x14001a813  mov     edx, [rbp+arg_0]
0x14001a816  mov     rcx, [rbp+var_28]
0x14001a81a  test    r15d, r15d
0x14001a81d  mov     r13, [rbp+var_20]
0x14001a821  jz      short loc_14001A834
0x14001a823  sub     [rsi+r12*4+3ACh], r15d
0x14001a82b  mov     byte ptr [r12+rsi+3A8h], 1
0x14001a834  mov     r12d, [rbp+arg_8]
0x14001a838  jmp     loc_14001A53C
0x14001a83d  mov     byte ptr [r15+rsi+3A8h], 0
0x14001a846  mov     r12d, [rbp+arg_8]
0x14001a84a  mov     edx, [rbp+arg_0]
0x14001a84d  xor     r15d, r15d
0x14001a850  xor     r13d, r13d
0x14001a853  xor     ebx, ebx
0x14001a855  mov     rcx, [rbp+var_28]
0x14001a859  lea     eax, [r15+r12]
0x14001a85d  mov     [rbp+var_30], r13
0x14001a861  cmp     eax, edx
0x14001a863  jnb     short loc_14001A8C2
0x14001a865  mov     ebx, eax
0x14001a867  shl     rbx, 5
0x14001a86b  add     rbx, [rdi+rcx*8+38h]
0x14001a870  cmp     byte ptr [rbx+1Ah], 0
0x14001a874  jnz     short loc_14001A8C2
0x14001a876  mov     rax, [rdi+2F0h]
0x14001a87d  mov     byte ptr [rbp+arg_20], 0
0x14001a881  cmp     [rbx+8], rax
0x14001a885  jnz     short loc_14001A8AA
0x14001a887  lea     r9, [rbp+arg_20]
0x14001a88b  mov     r8, rbx
0x14001a88e  mov     rdx, rdi
0x14001a891  call    UdfCacheIsReserved
0x14001a896  mov     r14d, eax
0x14001a899  test    eax, eax
0x14001a89b  js      loc_14001AAE3
0x14001a8a1  cmp     byte ptr [rbp+arg_20], 0
0x14001a8a5  mov     edx, [rbp+arg_0]
0x14001a8a8  jnz     short loc_14001A8BE
0x14001a8aa  movzx   eax, word ptr [rbx+18h]
0x14001a8ae  test    r13, r13
0x14001a8b1  mov     [rbp+var_10], rbx
0x14001a8b5  cmovz   r13, rbx
0x14001a8b9  add     r15d, eax
0x14001a8bc  jmp     short loc_14001A855
0x14001a8be  mov     rcx, [rbp+var_28]
0x14001a8c2  test    r15d, r15d
0x14001a8c5  jz      loc_14001A538
0x14001a8cb  mov     rax, [rbp+var_18]
0x14001a8cf  xor     ecx, ecx
0x14001a8d1  mov     r12d, dword ptr [rbp+Lbn+4]
0x14001a8d5  mov     rbx, r13
0x14001a8d8  mov     [rbp+arg_20], ecx
0x14001a8db  mov     r15d, [rax+0Ch]
0x14001a8df  mov     dword ptr [rbp+Lbn], r15d
0x14001a8e3  cmp     rbx, [rbp+var_10]
0x14001a8e7  ja      loc_14001AA1F
0x14001a8ed  test    r12d, r12d
0x14001a8f0  jz      loc_14001AA1F
0x14001a8f6  mov     rax, [rdi+2F0h]
0x14001a8fd  cmp     [rbx+8], rax
0x14001a901  jnz     short loc_14001A952
0x14001a903  mov     eax, [rdi+2E8h]
0x14001a909  cmp     [rbx+10h], eax
0x14001a90c  jz      short loc_14001A952
0x14001a90e  cmp     rbx, r13
0x14001a911  jnz     loc_14001AA1F
0x14001a917  lea     rax, [rbp+Lbn+4]
0x14001a91b  mov     [rsp+68h+var_40], 1
  ... truncated ...
```
