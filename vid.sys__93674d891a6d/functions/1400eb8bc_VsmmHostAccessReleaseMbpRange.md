# VsmmHostAccessReleaseMbpRange

- ea: `0x1400eb8bc`
- end: `0x1400ebf00`
- name: `VsmmHostAccessReleaseMbpRange`
- size: `1604`
- prototype: ``
- caller_count: `3`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x14001f8bc`
- `0x140029790`
- `0x1400d47d0`

## callees

- `0x1400029c0`
- `0x140006b40`
- `0x140006b68`
- `0x14000a010`
- `0x14001b3b4`
- `0x14001b440`
- `0x140021c60`
- `0x140021e00`
- `0x140074030`
- `0x140074b68`
- `0x140075c78`
- `0x1400768a0`
- `0x1400ccf88`
- `0x1400df4b8`
- `0x1400df598`
- `0x1400eb8bc`
- `0x1400ec584`
- `0x1400ecdec`
- `0x1400fe70c`

## import_xrefs

- `ntoskrnl!RtlTestBitNoFenceEx` at `0x1400eba21`
- `ntoskrnl!RtlTestBitNoFenceEx` at `0x1400eba21`
- `winhvr!WinHvFlushCache` at `0x1400ebeae`
- `winhvr!WinHvFlushCache` at `0x1400ebeae`

## string_xrefs

- `0x1400ebbd2`: `VsmmHostAccesspRelease`
- `0x1400ebcfb`: `VsmmHostAccesspRelease`
- `0x1400ebbe2`: `onecore\vm\vid\sys\vsmm\vsmmhostaccess.c`
- `0x1400ebd0b`: `onecore\vm\vid\sys\vsmm\vsmmhostaccess.c`

## pseudocode

```c
__int64 __fastcall VsmmHostAccessReleaseMbpRange(int a1, __int64 a2, __int64 a3, __int64 a4, int a5, _QWORD *a6)
{
  BOOL v9; // r13d
  unsigned __int64 v10; // r15
  char v11; // al
  unsigned __int64 v12; // r9
  unsigned __int64 v13; // r14
  unsigned __int64 v14; // rdi
  __int64 v15; // rcx
  unsigned __int64 v16; // rsi
  char v17; // al
  int v18; // eax
  int v19; // ebx
  __int64 v20; // rbx
  char v21; // al
  __int64 v22; // rcx
  __int64 *v23; // rax
  __int64 v24; // rax
  int v25; // eax
  unsigned int v26; // eax
  unsigned int v27; // eax
  unsigned int v28; // eax
  __int64 BackingPage; // rdi
  __int64 v30; // rdx
  int v31; // eax
  __int64 v32; // r9
  __int64 v33; // rax
  __int64 v34; // rax
  int v35; // edx
  __int64 v36; // rcx
  __int16 *v37; // rdx
  __int64 v38; // rcx
  __int64 *v39; // rax
  __int64 v40; // rax
  __int64 v41; // rax
  int v42; // edx
  __int64 v43; // rcx
  int v44; // r9d
  __int64 v45; // rcx
  int v46; // eax
  unsigned __int64 i; // rdi
  __int64 v48; // rdx
  char v50; // [rsp+30h] [rbp-D0h]
  int v51; // [rsp+34h] [rbp-CCh] BYREF
  int v52; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v53; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v54; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 v55; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v56; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v57[30]; // [rsp+60h] [rbp-A0h] BYREF
  char v58[32]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v59[16]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v60[16]; // [rsp+180h] [rbp+80h] BYREF
  int *v61; // [rsp+190h] [rbp+90h]
  __int64 v62; // [rsp+198h] [rbp+98h]
  int *v63; // [rsp+1A0h] [rbp+A0h]
  __int64 v64; // [rsp+1A8h] [rbp+A8h]
  __int64 v65; // [rsp+1B0h] [rbp+B0h]
  __int64 v66; // [rsp+1B8h] [rbp+B8h]
  int *v67; // [rsp+1C0h] [rbp+C0h]
  __int64 v68; // [rsp+1C8h] [rbp+C8h]
  __int64 v69; // [rsp+1D0h] [rbp+D0h]
  int v70; // [rsp+1D8h] [rbp+D8h] BYREF
  int v71; // [rsp+1DCh] [rbp+DCh]
  __int64 *v72; // [rsp+1E0h] [rbp+E0h]
  __int64 v73; // [rsp+1E8h] [rbp+E8h]
  __int64 *v74; // [rsp+1F0h] [rbp+F0h]
  __int64 v75; // [rsp+1F8h] [rbp+F8h]
  __int64 *v76; // [rsp+200h] [rbp+100h]
  __int64 v77; // [rsp+208h] [rbp+108h]

  memset(v57, 0, sizeof(v57));
  VsmmHostAccesspReleaseContextInitialize((unsigned int)v57, 0, a1, 0, a3, a5);
  v57[28] = a2;
  v53 = 0;
  v9 = HIDWORD(v57[22]) == 0;
  v10 = 0;
  v11 = VsmmHostAccesspAcqRelBySpa(v57);
  v13 = (unsigned int)v12;
  v50 = v11;
  if ( v57[21] <= v12 )
  {
LABEL_56:
    v19 = VsmmHostAccesspAcqRelFlush(v57);
    if ( v19 < 0 )
      goto LABEL_52;
    v19 = 0;
  }
  else
  {
LABEL_2:
    v14 = v13 + a2;
    if ( LODWORD(v57[2]) == (_DWORD)v12 && (v57[22] & 1) == 0 )
    {
      v15 = v57[27];
      v16 = v14 >> 9;
      if ( (v57[27] & 6) == 0 || v16 != v57[((v57[27] >> 1) & 3LL) + 24] )
      {
        v17 = VsmmHypercallMbpChunkLockAcquireSlow(&v57[24], v14 >> 9);
        LODWORD(v12) = 0;
        if ( v17 )
          goto LABEL_12;
        v18 = VsmmHostAccesspAcqRelFlush(v57);
        LODWORD(v12) = 0;
        v19 = v18;
        if ( v18 < 0 )
          goto LABEL_52;
        v15 = v57[27];
        if ( (v57[27] & 6) == 0 || v16 != v57[((v57[27] >> 1) & 3LL) + 24] )
        {
          VsmmHypercallMbpChunkLockAcquireSlow(&v57[24], v14 >> 9);
          LODWORD(v12) = 0;
          goto LABEL_12;
        }
      }
      v57[27] = v15 & 0xFFFFFFFFFFFFFFF7uLL;
      goto LABEL_12;
    }
    while ( 1 )
    {
LABEL_12:
      v20 = v57[20];
      if ( *(_DWORD *)(v57[20] + 268LL) != 2 )
      {
        if ( *(_QWORD *)(v57[20] + 288LL) )
        {
          v21 = RtlTestBitNoFenceEx(v57[20] + 272LL, v14 >> 9);
          LODWORD(v12) = 0;
          if ( !v21 )
          {
            VsmmMbpUpgradeChunk(v20, v14 >> 9);
            LODWORD(v12) = 0;
          }
        }
      }
      v22 = *(_QWORD *)(v20 + 256);
      if ( (*(_DWORD *)(v20 + 264) & 8) != 0 )
        v23 = (__int64 *)(v22 + 8 * v14);
      else
        v23 = (__int64 *)(v22 + 16 * v14 + 8);
      if ( v9 )
        _m_prefetchw(v23);
      v24 = *v23;
      v53 = v24;
      if ( HIDWORD(v57[22]) != (_DWORD)v12 )
        break;
      v25 = VsmmMbpHostAccessRestrictBegin(v57[20], v14, &v53, LODWORD(v57[2]));
      LODWORD(v12) = 0;
      v19 = v25;
      if ( v25 >= 0 )
      {
        LOBYTE(v24) = v53;
        ++v10;
LABEL_28:
        if ( v50 == (_BYTE)v12 )
        {
          BackingPage = -1;
        }
        else
        {
          v26 = v24 & 0xF;
          if ( v26 > 5 )
          {
            v27 = v26 - 6;
            if ( !v27 )
              goto LABEL_36;
            v28 = v27 - 1;
            if ( v28 )
            {
              if ( v28 - 1 < 2 )
                goto LABEL_36;
            }
LABEL_35:
            LOBYTE(v22) = *(_BYTE *)(v57[20] + 240LL);
            BackingPage = VsmmNumaGetBackingPage(v22, 0);
          }
          else
          {
            if ( v26 != 1 )
              goto LABEL_35;
LABEL_36:
            BackingPage = *(_QWORD *)(*(_QWORD *)(v57[20] + 256LL) + 16 * v14) & 0xFFFFFFFFFFLL;
          }
        }
        v30 = v57[17];
        if ( v57[17] )
        {
          if ( BackingPage != v57[17] + v57[16] )
          {
            v31 = VsmmHostAccesspAcqRelCompleteRun(v57);
            LODWORD(v12) = 0;
            v19 = v31;
            if ( v31 < 0 )
              goto LABEL_52;
            v30 = 0;
            goto LABEL_42;
          }
        }
        else
        {
LABEL_42:
          v57[16] = BackingPage;
        }
        ++v13;
        v57[17] = v30 + 1;
        if ( v13 >= v57[21] )
          goto LABEL_56;
        a2 = v57[28];
        goto LABEL_2;
      }
      if ( v25 != -1073741267 )
      {
        if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
        {
          tlgCreate1Sz_char(v59, "VsmmHostAccesspRelease");
          tlgCreate1Sz_char(v60, "onecore\\vm\\vid\\sys\\vsmm\\vsmmhostaccess.c");
          v61 = &v51;
          v51 = 3315;
          v62 = 4;
          v52 = v19;
          v63 = &v52;
          v64 = 4;
          v33 = *(_QWORD *)(v57[20] + 8LL);
          v66 = 16;
          v65 = v33 + 656;
          v34 = *(_QWORD *)(v57[20] + 8LL);
          v35 = *(unsigned __int16 *)(v34 + 120);
          v36 = *(_QWORD *)(v34 + 128);
          v67 = &v70;
          v70 = v35;
          v37 = (__int16 *)byte_14005C175;
          v68 = 2;
          v69 = v36;
          v71 = v32;
          v38 = *(_QWORD *)(*(_QWORD *)(v57[20] + 8LL) + 648LL);
          v72 = &v54;
          v74 = (__int64 *)&v55;
          v56 = v53;
          v39 = &v56;
          v54 = v38;
          goto LABEL_51;
        }
        goto LABEL_52;
      }
      v19 = VsmmHostAccesspAcqRelFlush(v57);
      if ( v19 < 0 )
        goto LABEL_52;
      VsmmMbpBlockOnHostAccessRestriction(v57[20], v14);
      LODWORD(v12) = 0;
    }
    if ( (v24 & 0xF) == 1 )
      goto LABEL_28;
    v19 = -1073741811;
    if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
    {
      tlgCreate1Sz_char(v59, "VsmmHostAccesspRelease");
      tlgCreate1Sz_char(v60, "onecore\\vm\\vid\\sys\\vsmm\\vsmmhostaccess.c");
      v61 = &v52;
      v52 = 3284;
      v62 = 4;
      v51 = -1073741811;
      v63 = &v51;
      v64 = 4;
      v40 = *(_QWORD *)(v57[20] + 8LL) + 656LL;
      v66 = 16;
      v65 = v40;
      v41 = *(_QWORD *)(v57[20] + 8LL);
      v42 = *(unsigned __int16 *)(v41 + 120);
      v43 = *(_QWORD *)(v41 + 128);
      v67 = &v70;
      v70 = v42;
      v37 = word_14005C1FA;
      v71 = v44;
      v32 = 0;
      v68 = 2;
      v69 = v43;
      v45 = *(_QWORD *)(*(_QWORD *)(v57[20] + 8LL) + 648LL);
      v72 = &v56;
      v74 = (__int64 *)&v55;
      v54 = v53;
      v39 = &v54;
      v56 = v45;
LABEL_51:
      v76 = v39;
      v77 = 8;
      v75 = 8;
      v55 = v14;
      v73 = 8;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, v37, 0, v32, 12, v58);
    }
LABEL_52:
    v46 = VsmmHostAccesspAcqRelFlush(v57);
    if ( v46 < 0 )
      v19 = v46;
    if ( !HIDWORD(v57[22]) )
    {
      for ( i = v57[23]; i < v10; ++i )
        VsmmMbpHostAccessRestrictComplete(v57[20], i + v57[28], 0);
      VsmmMbpUnblockHostAccessRestrictionWaiters(v57[20]);
    }
  }
  v48 = v57[23];
  if ( v57[23] && (v57[22] & 1) != 0 && (*(_BYTE *)(*(_QWORD *)(v57[20] + 8LL) + 40LL) & 0x10) != 0 )
  {
    WinHvFlushCache();
    v48 = v57[23];
  }
  if ( a6 )
    *a6 = v48;
  VsmmHypercallMbpChunkLockDestroy(&v57[24]);
  VsmmHostAccesspAcqRelContextDestroy(v57);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x1400eb8bc  push    rbp
0x1400eb8be  push    rbx
0x1400eb8bf  push    rsi
0x1400eb8c0  push    rdi
0x1400eb8c1  push    r12
0x1400eb8c3  push    r13
0x1400eb8c5  push    r14
0x1400eb8c7  push    r15
0x1400eb8c9  lea     rbp, [rsp-128h]
0x1400eb8d1  sub     rsp, 228h
0x1400eb8d8  mov     rax, cs:__security_cookie
0x1400eb8df  xor     rax, rsp
0x1400eb8e2  mov     [rbp+160h+var_50], rax
0x1400eb8e9  mov     r12, [rbp+160h+arg_28]
0x1400eb8f0  mov     rbx, r8
0x1400eb8f3  mov     rsi, rdx
0x1400eb8f6  mov     rdi, rcx
0x1400eb8f9  xor     edx, edx; Val
0x1400eb8fb  lea     rcx, [rsp+260h+var_200]; void *
0x1400eb900  mov     r8d, 0F0h; Size
0x1400eb906  call    memset
0x1400eb90b  mov     eax, [rbp+160h+arg_20]
0x1400eb911  lea     rcx, [rsp+260h+var_200]
0x1400eb916  mov     dword ptr [rsp+260h+var_238], eax
0x1400eb91a  xor     r9d, r9d
0x1400eb91d  mov     r8, rdi
0x1400eb920  mov     [rsp+260h+var_240], rbx
0x1400eb925  xor     edx, edx
0x1400eb927  call    VsmmHostAccesspReleaseContextInitialize
0x1400eb92c  xor     r9d, r9d
0x1400eb92f  mov     [rbp+160h+var_120], rsi
0x1400eb933  cmp     [rbp+160h+var_14C], r9d
0x1400eb937  lea     rcx, [rsp+260h+var_200]
0x1400eb93c  mov     r13d, r9d
0x1400eb93f  mov     [rsp+260h+var_220], r9
0x1400eb944  setz    r13b
0x1400eb948  mov     r15d, r9d
0x1400eb94b  call    VsmmHostAccesspAcqRelBySpa
0x1400eb950  mov     r14d, r9d
0x1400eb953  mov     [rsp+260h+var_230], al
0x1400eb957  cmp     [rbp+160h+var_158], r9
0x1400eb95b  jbe     loc_1400EBE5D
0x1400eb961  lea     rdi, [r14+rsi]
0x1400eb965  cmp     [rsp+260h+var_1F0], r9d
0x1400eb96a  jnz     loc_1400EB9F2
0x1400eb970  test    [rbp+160h+var_150], 1
0x1400eb974  jnz     short loc_1400EB9F2
0x1400eb976  mov     rcx, [rbp+160h+var_128]
0x1400eb97a  mov     rsi, rdi
0x1400eb97d  shr     rsi, 9
0x1400eb981  test    cl, 6
0x1400eb984  jbe     short loc_1400EB996
0x1400eb986  mov     rax, rcx
0x1400eb989  shr     rax, 1
0x1400eb98c  and     eax, 3
0x1400eb98f  cmp     rsi, [rbp+rax*8+160h+var_140]
0x1400eb994  jz      short loc_1400EB9D9
0x1400eb996  mov     rdx, rsi
0x1400eb999  lea     rcx, [rbp+160h+var_140]
0x1400eb99d  call    VsmmHypercallMbpChunkLockAcquireSlow
0x1400eb9a2  xor     r9d, r9d
0x1400eb9a5  test    al, al
0x1400eb9a7  jnz     short loc_1400EB9F2
0x1400eb9a9  lea     rcx, [rsp+260h+var_200]
0x1400eb9ae  call    VsmmHostAccesspAcqRelFlush
0x1400eb9b3  xor     r9d, r9d
0x1400eb9b6  mov     ebx, eax
0x1400eb9b8  test    eax, eax
0x1400eb9ba  js      loc_1400EBE42
0x1400eb9c0  mov     rcx, [rbp+160h+var_128]
0x1400eb9c4  test    cl, 6
0x1400eb9c7  jbe     short loc_1400EB9E3
0x1400eb9c9  mov     rax, rcx
0x1400eb9cc  shr     rax, 1
0x1400eb9cf  and     eax, 3
0x1400eb9d2  cmp     rsi, [rbp+rax*8+160h+var_140]
0x1400eb9d7  jnz     short loc_1400EB9E3
0x1400eb9d9  and     rcx, 0FFFFFFFFFFFFFFF7h
0x1400eb9dd  mov     [rbp+160h+var_128], rcx
0x1400eb9e1  jmp     short loc_1400EB9F2
0x1400eb9e3  mov     rdx, rsi
0x1400eb9e6  lea     rcx, [rbp+160h+var_140]
0x1400eb9ea  call    VsmmHypercallMbpChunkLockAcquireSlow
0x1400eb9ef  xor     r9d, r9d
0x1400eb9f2  mov     esi, 8
0x1400eb9f7  mov     rbx, [rbp+160h+var_160]
0x1400eb9fb  cmp     dword ptr [rbx+10Ch], 2
0x1400eba02  jz      short loc_1400EBA48
0x1400eba04  mov     rax, [rbx+120h]
0x1400eba0b  test    rax, rax
0x1400eba0e  jz      short loc_1400EBA42
0x1400eba10  mov     rsi, rdi
0x1400eba13  lea     rcx, [rbx+110h]
0x1400eba1a  shr     rsi, 9
0x1400eba1e  mov     rdx, rsi
0x1400eba21  call    cs:__imp_RtlTestBitNoFenceEx
0x1400eba28  nop     dword ptr [rax+rax+00h]
0x1400eba2d  xor     r9d, r9d
0x1400eba30  test    al, al
0x1400eba32  jnz     short loc_1400EBA42
0x1400eba34  mov     rdx, rsi
0x1400eba37  mov     rcx, rbx
0x1400eba3a  call    VsmmMbpUpgradeChunk
0x1400eba3f  xor     r9d, r9d
0x1400eba42  nop
0x1400eba43  mov     esi, 8
0x1400eba48  mov     eax, [rbx+108h]
0x1400eba4e  mov     rcx, [rbx+100h]
0x1400eba55  test    sil, al
0x1400eba58  jnz     short loc_1400EBA6A
0x1400eba5a  mov     rax, rdi
0x1400eba5d  shl     rax, 4
0x1400eba61  add     rax, 8
0x1400eba65  add     rax, rcx
0x1400eba68  jmp     short loc_1400EBA6E
0x1400eba6a  lea     rax, [rcx+rdi*8]
0x1400eba6e  test    r13d, r13d
0x1400eba71  jz      short loc_1400EBA76
0x1400eba73  prefetchw byte ptr [rax]
0x1400eba76  mov     rax, [rax]
0x1400eba79  mov     [rsp+260h+var_220], rax
0x1400eba7e  cmp     [rbp+160h+var_14C], r9d
0x1400eba82  jnz     short loc_1400EBAE0
0x1400eba84  mov     r9d, [rsp+260h+var_1F0]
0x1400eba89  lea     r8, [rsp+260h+var_220]
0x1400eba8e  mov     rcx, [rbp+160h+var_160]
0x1400eba92  mov     rdx, rdi
0x1400eba95  call    VsmmMbpHostAccessRestrictBegin
0x1400eba9a  xor     r9d, r9d
0x1400eba9d  mov     ebx, eax
0x1400eba9f  test    eax, eax
0x1400ebaa1  jns     short loc_1400EBAD6
0x1400ebaa3  cmp     eax, 0C000022Dh
0x1400ebaa8  jnz     loc_1400EBBAA
0x1400ebaae  lea     rcx, [rsp+260h+var_200]
0x1400ebab3  call    VsmmHostAccesspAcqRelFlush
0x1400ebab8  mov     ebx, eax
0x1400ebaba  test    eax, eax
0x1400ebabc  js      loc_1400EBE42
0x1400ebac2  mov     rcx, [rbp+160h+var_160]
0x1400ebac6  mov     rdx, rdi
0x1400ebac9  call    VsmmMbpBlockOnHostAccessRestriction
0x1400ebace  xor     r9d, r9d
0x1400ebad1  jmp     loc_1400EB9F7
0x1400ebad6  mov     rax, [rsp+260h+var_220]
0x1400ebadb  inc     r15
0x1400ebade  jmp     short loc_1400EBAEE
0x1400ebae0  mov     cl, al
0x1400ebae2  and     cl, 0Fh
0x1400ebae5  cmp     cl, 1
0x1400ebae8  jnz     loc_1400EBCCE
0x1400ebaee  cmp     [rsp+260h+var_230], r9b
0x1400ebaf3  jz      short loc_1400EBB55
0x1400ebaf5  mov     r8, [rbp+160h+var_160]
0x1400ebaf9  and     eax, 0Fh
0x1400ebafc  cmp     eax, 5
0x1400ebaff  ja      short loc_1400EBB11
0x1400ebb01  jz      short loc_1400EBB25
0x1400ebb03  test    eax, eax
0x1400ebb05  jz      short loc_1400EBB25
0x1400ebb07  sub     eax, 1
0x1400ebb0a  jz      short loc_1400EBB38
0x1400ebb0c  sub     eax, 1
0x1400ebb0f  jmp     short loc_1400EBB25
0x1400ebb11  sub     eax, 6
0x1400ebb14  jz      short loc_1400EBB38
0x1400ebb16  sub     eax, 1
0x1400ebb19  jz      short loc_1400EBB25
0x1400ebb1b  sub     eax, 1
0x1400ebb1e  jz      short loc_1400EBB38
0x1400ebb20  cmp     eax, 1
0x1400ebb23  jz      short loc_1400EBB38
0x1400ebb25  mov     cl, [r8+0F0h]
0x1400ebb2c  xor     edx, edx
0x1400ebb2e  call    VsmmNumaGetBackingPage
0x1400ebb33  mov     rdi, rax
0x1400ebb36  jmp     short loc_1400EBB59
0x1400ebb38  mov     rax, [r8+100h]
0x1400ebb3f  add     rdi, rdi
0x1400ebb42  mov     rdi, [rax+rdi*8]
0x1400ebb46  mov     rax, 0FFFFFFFFFFh
0x1400ebb50  and     rdi, rax
0x1400ebb53  jmp     short loc_1400EBB59
0x1400ebb55  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1400ebb59  mov     rdx, [rbp+160h+var_178]
0x1400ebb5d  test    rdx, rdx
0x1400ebb60  jz      short loc_1400EBB88
0x1400ebb62  mov     rcx, [rbp+160h+var_180]
0x1400ebb66  add     rcx, rdx
0x1400ebb69  cmp     rdi, rcx
0x1400ebb6c  jz      short loc_1400EBB8C
0x1400ebb6e  lea     rcx, [rsp+260h+var_200]
0x1400ebb73  call    VsmmHostAccesspAcqRelCompleteRun
0x1400ebb78  xor     r9d, r9d
0x1400ebb7b  mov     ebx, eax
0x1400ebb7d  test    eax, eax
0x1400ebb7f  js      loc_1400EBE42
0x1400ebb85  mov     edx, r9d
0x1400ebb88  mov     [rbp+160h+var_180], rdi
0x1400ebb8c  inc     r14
0x1400ebb8f  lea     rax, [rdx+1]
0x1400ebb93  mov     [rbp+160h+var_178], rax
0x1400ebb97  cmp     r14, [rbp+160h+var_158]
0x1400ebb9b  jnb     loc_1400EBE5D
0x1400ebba1  mov     rsi, [rbp+160h+var_120]
0x1400ebba5  jmp     loc_1400EB961
0x1400ebbaa  mov     eax, cs:dword_140065110
0x1400ebbb0  cmp     eax, 2
0x1400ebbb3  jbe     loc_1400EBE42
0x1400ebbb9  mov     edx, 100h
0x1400ebbbe  lea     rcx, dword_140065110
0x1400ebbc5  call    _tlgKeywordOn
0x1400ebbca  test    al, al
0x1400ebbcc  jz      loc_1400EBE42
0x1400ebbd2  lea     rdx, aVsmmhostaccess_2; "VsmmHostAccesspRelease"
0x1400ebbd9  lea     rcx, [rbp+160h+var_F0]
0x1400ebbdd  call    _tlgCreate1Sz_char
0x1400ebbe2  lea     rdx, aOnecoreVmVidSy_33; "onecore\\vm\\vid\\sys\\vsmm\\vsmmhostac"...
0x1400ebbe9  lea     rcx, [rbp+160h+var_E0]
0x1400ebbf0  call    _tlgCreate1Sz_char
0x1400ebbf5  mov     r8, [rbp+160h+var_160]
0x1400ebbf9  lea     rax, [rsp+260h+var_22C]
0x1400ebbfe  mov     [rbp+160h+var_D0], rax
0x1400ebc05  lea     rcx, [rsp+260h+var_228]
0x1400ebc0a  mov     [rsp+260h+var_22C], 0CF3h
0x1400ebc12  mov     [rbp+160h+var_C8], 4
0x1400ebc1d  mov     [rsp+260h+var_228], ebx
0x1400ebc21  mov     [rbp+160h+var_C0], rcx
0x1400ebc28  mov     [rbp+160h+var_B8], 4
0x1400ebc33  mov     rax, [r8+8]
0x1400ebc37  add     rax, 290h
0x1400ebc3d  mov     [rbp+160h+var_A8], 10h
0x1400ebc48  mov     [rbp+160h+var_B0], rax
0x1400ebc4f  mov     rax, [r8+8]
0x1400ebc53  movzx   edx, word ptr [rax+78h]
0x1400ebc57  mov     rcx, [rax+80h]
0x1400ebc5e  lea     rax, [rbp+160h+var_88]
0x1400ebc65  mov     [rbp+160h+var_A0], rax
0x1400ebc6c  mov     [rbp+160h+var_88], edx
0x1400ebc72  lea     rdx, byte_14005C175
0x1400ebc79  mov     [rbp+160h+var_98], 2
0x1400ebc84  mov     [rbp+160h+var_90], rcx
0x1400ebc8b  mov     [rbp+160h+var_84], r9d
0x1400ebc92  mov     rax, [r8+8]
0x1400ebc96  mov     rcx, [rax+288h]
0x1400ebc9d  lea     rax, [rsp+260h+var_218]
0x1400ebca2  mov     [rbp+160h+var_80], rax
0x1400ebca9  lea     rax, [rsp+260h+var_210]
0x1400ebcae  mov     [rbp+160h+var_70], rax
0x1400ebcb5  mov     rax, [rsp+260h+var_220]
0x1400ebcba  mov     [rsp+260h+var_208], rax
0x1400ebcbf  lea     rax, [rsp+260h+var_208]
0x1400ebcc4  mov     [rsp+260h+var_218], rcx
0x1400ebcc9  jmp     loc_1400EBDF5
0x1400ebcce  mov     eax, cs:dword_140065110
0x1400ebcd4  mov     ebx, 0C000000Dh
0x1400ebcd9  cmp     eax, 2
0x1400ebcdc  jbe     loc_1400EBE42
0x1400ebce2  mov     edx, 100h
0x1400ebce7  lea     rcx, dword_140065110
0x1400ebcee  call    _tlgKeywordOn
0x1400ebcf3  test    al, al
0x1400ebcf5  jz      loc_1400EBE42
0x1400ebcfb  lea     rdx, aVsmmhostaccess_2; "VsmmHostAccesspRelease"
0x1400ebd02  lea     rcx, [rbp+160h+var_F0]
0x1400ebd06  call    _tlgCreate1Sz_char
0x1400ebd0b  lea     rdx, aOnecoreVmVidSy_33; "onecore\\vm\\vid\\sys\\vsmm\\vsmmhostac"...
0x1400ebd12  lea     rcx, [rbp+160h+var_E0]
0x1400ebd19  call    _tlgCreate1Sz_char
0x1400ebd1e  mov     r8, [rbp+160h+var_160]
0x1400ebd22  lea     rax, [rsp+260h+var_228]
0x1400ebd27  mov     [rbp+160h+var_D0], rax
0x1400ebd2e  lea     rcx, [rsp+260h+var_22C]
0x1400ebd33  mov     [rsp+260h+var_228], 0CD4h
0x1400ebd3b  mov     [rbp+160h+var_C8], 4
0x1400ebd46  mov     [rsp+260h+var_22C], ebx
0x1400ebd4a  mov     [rbp+160h+var_C0], rcx
0x1400ebd51  mov     [rbp+160h+var_B8], 4
0x1400ebd5c  mov     rax, [r8+8]
0x1400ebd60  add     rax, 290h
0x1400ebd66  mov     [rbp+160h+var_A8], 10h
0x1400ebd71  mov     [rbp+160h+var_B0], rax
0x1400ebd78  mov     rax, [r8+8]
0x1400ebd7c  movzx   edx, word ptr [rax+78h]
0x1400ebd80  mov     rcx, [rax+80h]
0x1400ebd87  lea     rax, [rbp+160h+var_88]
0x1400ebd8e  mov     [rbp+160h+var_A0], rax
0x1400ebd95  mov     [rbp+160h+var_88], edx
0x1400ebd9b  lea     rdx, word_14005C1FA
0x1400ebda2  mov     [rbp+160h+var_84], r9d
0x1400ebda9  xor     r9d, r9d
0x1400ebdac  mov     [rbp+160h+var_98], 2
0x1400ebdb7  mov     [rbp+160h+var_90], rcx
0x1400ebdbe  mov     rax, [r8+8]
0x1400ebdc2  mov     rcx, [rax+288h]
0x1400ebdc9  lea     rax, [rsp+260h+var_208]
0x1400ebdce  mov     [rbp+160h+var_80], rax
0x1400ebdd5  lea     rax, [rsp+260h+var_210]
0x1400ebdda  mov     [rbp+160h+var_70], rax
0x1400ebde1  mov     rax, [rsp+260h+var_220]
  ... truncated ...
```
