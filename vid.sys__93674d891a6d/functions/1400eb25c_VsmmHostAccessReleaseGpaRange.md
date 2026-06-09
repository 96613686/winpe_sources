# VsmmHostAccessReleaseGpaRange

- ea: `0x1400eb25c`
- end: `0x1400eb8b3`
- name: `VsmmHostAccessReleaseGpaRange`
- size: `1623`
- prototype: ``
- caller_count: `3`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x14002a7c0`
- `0x1400cdee4`
- `0x1400da5bc`

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
- `0x1400eb25c`
- `0x1400ec584`
- `0x1400ecdec`
- `0x1400fe70c`

## import_xrefs

- `ntoskrnl!RtlTestBitNoFenceEx` at `0x1400eb3c3`
- `ntoskrnl!RtlTestBitNoFenceEx` at `0x1400eb3c3`
- `winhvr!WinHvFlushCache` at `0x1400eb867`
- `winhvr!WinHvFlushCache` at `0x1400eb867`

## string_xrefs

- `0x1400eb564`: `VsmmHostAccesspRelease`
- `0x1400eb6ad`: `VsmmHostAccesspRelease`
- `0x1400eb574`: `onecore\vm\vid\sys\vsmm\vsmmhostaccess.c`
- `0x1400eb6bd`: `onecore\vm\vid\sys\vsmm\vsmmhostaccess.c`

## pseudocode

```c
__int64 __fastcall VsmmHostAccessReleaseGpaRange(_QWORD *a1, __int64 a2, __int64 a3, int a4)
{
  unsigned __int64 v8; // r15
  BOOL v9; // r13d
  unsigned __int64 v10; // r12
  __int64 BackingPage; // r14
  unsigned __int64 v12; // rdi
  __int64 v13; // rcx
  unsigned __int64 v14; // rsi
  int v15; // ebx
  __int64 v16; // rbx
  __int64 v17; // rcx
  __int64 *v18; // rax
  __int64 v19; // rax
  int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // rax
  __int64 v26; // rax
  int v27; // edx
  __int64 v28; // rcx
  __int16 *v29; // rdx
  __int64 v30; // rcx
  __int64 *v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  int v34; // edx
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // r9
  int v38; // eax
  unsigned __int64 i; // rdi
  char v41; // [rsp+30h] [rbp-D0h]
  int v42; // [rsp+34h] [rbp-CCh] BYREF
  int v43; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v44; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v45; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 v46; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v47; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v48[30]; // [rsp+60h] [rbp-A0h] BYREF
  char v49[32]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v50[16]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v51[16]; // [rsp+180h] [rbp+80h] BYREF
  int *v52; // [rsp+190h] [rbp+90h]
  __int64 v53; // [rsp+198h] [rbp+98h]
  int *v54; // [rsp+1A0h] [rbp+A0h]
  __int64 v55; // [rsp+1A8h] [rbp+A8h]
  __int64 v56; // [rsp+1B0h] [rbp+B0h]
  __int64 v57; // [rsp+1B8h] [rbp+B8h]
  int *v58; // [rsp+1C0h] [rbp+C0h]
  __int64 v59; // [rsp+1C8h] [rbp+C8h]
  __int64 v60; // [rsp+1D0h] [rbp+D0h]
  int v61; // [rsp+1D8h] [rbp+D8h] BYREF
  int v62; // [rsp+1DCh] [rbp+DCh]
  __int64 *v63; // [rsp+1E0h] [rbp+E0h]
  __int64 v64; // [rsp+1E8h] [rbp+E8h]
  unsigned __int64 *v65; // [rsp+1F0h] [rbp+F0h]
  __int64 v66; // [rsp+1F8h] [rbp+F8h]
  __int64 *v67; // [rsp+200h] [rbp+100h]
  __int64 v68; // [rsp+208h] [rbp+108h]

  memset(v48, 0, sizeof(v48));
  v8 = 0;
  VsmmHostAccesspReleaseContextInitialize((unsigned int)v48, 1, a1[48], a4, a3, 0);
  v48[28] = a1;
  v9 = HIDWORD(v48[22]) == 0;
  v48[29] = a2;
  v44 = 0;
  v10 = 0;
  v41 = VsmmHostAccesspAcqRelBySpa(v48);
  if ( v48[21] )
  {
LABEL_2:
    BackingPage = v8 + a2;
    v12 = BackingPage + a1[49] - a1[32];
    if ( !LODWORD(v48[2]) && (v48[22] & 1) == 0 )
    {
      v13 = v48[27];
      v14 = v12 >> 9;
      if ( (v48[27] & 6) == 0 || v14 != v48[((v48[27] >> 1) & 3LL) + 24] )
      {
        if ( (unsigned __int8)VsmmHypercallMbpChunkLockAcquireSlow(&v48[24], v12 >> 9) )
          goto LABEL_12;
        v15 = VsmmHostAccesspAcqRelFlush(v48);
        if ( v15 < 0 )
          goto LABEL_53;
        v13 = v48[27];
        if ( (v48[27] & 6) == 0 || v14 != v48[((v48[27] >> 1) & 3LL) + 24] )
        {
          VsmmHypercallMbpChunkLockAcquireSlow(&v48[24], v12 >> 9);
          goto LABEL_12;
        }
      }
      v48[27] = v13 & 0xFFFFFFFFFFFFFFF7uLL;
      goto LABEL_12;
    }
    while ( 1 )
    {
LABEL_12:
      v16 = v48[20];
      if ( *(_DWORD *)(v48[20] + 268LL) != 2
        && *(_QWORD *)(v48[20] + 288LL)
        && !(unsigned __int8)RtlTestBitNoFenceEx(v48[20] + 272LL, v12 >> 9) )
      {
        VsmmMbpUpgradeChunk(v16, v12 >> 9);
      }
      v17 = *(_QWORD *)(v16 + 256);
      if ( (*(_DWORD *)(v16 + 264) & 8) != 0 )
        v18 = (__int64 *)(v17 + 8 * v12);
      else
        v18 = (__int64 *)(v17 + 16 * v12 + 8);
      if ( v9 )
        _m_prefetchw(v18);
      v19 = *v18;
      v44 = v19;
      if ( HIDWORD(v48[22]) )
        break;
      v20 = VsmmMbpHostAccessRestrictBegin(v48[20], v12, &v44, LODWORD(v48[2]));
      v15 = v20;
      if ( v20 >= 0 )
      {
        LOBYTE(v19) = v44;
        ++v10;
LABEL_28:
        if ( v41 )
        {
          v21 = v19 & 0xF;
          if ( v21 > 5 )
          {
            v22 = v21 - 6;
            if ( !v22 )
              goto LABEL_36;
            v23 = v22 - 1;
            if ( v23 )
            {
              if ( v23 - 1 < 2 )
                goto LABEL_36;
            }
LABEL_35:
            LOBYTE(v17) = *(_BYTE *)(v48[20] + 240LL);
            BackingPage = VsmmNumaGetBackingPage(v17, 0);
          }
          else
          {
            if ( v21 != 1 )
              goto LABEL_35;
LABEL_36:
            BackingPage = *(_QWORD *)(*(_QWORD *)(v48[20] + 256LL) + 16 * v12) & 0xFFFFFFFFFFLL;
          }
        }
        v24 = v48[17];
        if ( v48[17] )
        {
          if ( BackingPage != v48[17] + v48[16] )
          {
            v15 = VsmmHostAccesspAcqRelCompleteRun(v48);
            if ( v15 < 0 )
              goto LABEL_53;
            v24 = 0;
            goto LABEL_41;
          }
        }
        else
        {
LABEL_41:
          v48[16] = BackingPage;
        }
        ++v8;
        v48[17] = v24 + 1;
        if ( v8 >= v48[21] )
          goto LABEL_51;
        a2 = v48[29];
        a1 = (_QWORD *)v48[28];
        goto LABEL_2;
      }
      if ( v20 != -1073741267 )
      {
        if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
        {
          tlgCreate1Sz_char(v50, "VsmmHostAccesspRelease");
          tlgCreate1Sz_char(v51, "onecore\\vm\\vid\\sys\\vsmm\\vsmmhostaccess.c");
          v52 = &v42;
          v42 = 3315;
          v53 = 4;
          v43 = v15;
          v54 = &v43;
          v55 = 4;
          v25 = *(_QWORD *)(v48[20] + 8LL);
          v57 = 16;
          v56 = v25 + 656;
          v26 = *(_QWORD *)(v48[20] + 8LL);
          v27 = *(unsigned __int16 *)(v26 + 120);
          v28 = *(_QWORD *)(v26 + 128);
          v58 = &v61;
          v61 = v27;
          v29 = (__int16 *)byte_14005C175;
          v59 = 2;
          v60 = v28;
          v62 = 0;
          v30 = *(_QWORD *)(*(_QWORD *)(v48[20] + 8LL) + 648LL);
          v63 = &v45;
          v65 = &v46;
          v47 = v44;
          v31 = &v47;
          v45 = v30;
          v64 = 8;
          v66 = 8;
          v68 = 8;
          goto LABEL_50;
        }
        goto LABEL_53;
      }
      v15 = VsmmHostAccesspAcqRelFlush(v48);
      if ( v15 < 0 )
        goto LABEL_53;
      VsmmMbpBlockOnHostAccessRestriction(v48[20], v12);
    }
    if ( (v19 & 0xF) == 1 )
      goto LABEL_28;
    v15 = -1073741811;
    if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
    {
      tlgCreate1Sz_char(v50, "VsmmHostAccesspRelease");
      tlgCreate1Sz_char(v51, "onecore\\vm\\vid\\sys\\vsmm\\vsmmhostaccess.c");
      v52 = &v43;
      v43 = 3284;
      v53 = 4;
      v42 = -1073741811;
      v54 = &v42;
      v55 = 4;
      v32 = *(_QWORD *)(v48[20] + 8LL);
      v57 = 16;
      v56 = v32 + 656;
      v33 = *(_QWORD *)(v48[20] + 8LL);
      v34 = *(unsigned __int16 *)(v33 + 120);
      v35 = *(_QWORD *)(v33 + 128);
      v58 = &v61;
      v61 = v34;
      v29 = word_14005C1FA;
      v59 = 2;
      v60 = v35;
      v62 = 0;
      v36 = *(_QWORD *)(*(_QWORD *)(v48[20] + 8LL) + 648LL);
      v63 = &v47;
      v65 = &v46;
      v45 = v44;
      v31 = &v45;
      v47 = v36;
      v64 = v37;
      v66 = v37;
      v68 = v37;
LABEL_50:
      v67 = v31;
      v46 = v12;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, v29, 0, 0, 12, v49);
    }
LABEL_53:
    v38 = VsmmHostAccesspAcqRelFlush(v48);
    if ( v38 < 0 )
      v15 = v38;
    if ( !HIDWORD(v48[22]) )
    {
      for ( i = v48[23]; i < v10; ++i )
        VsmmMbpHostAccessRestrictComplete(
          v48[20],
          v48[29] + i + *(_QWORD *)(v48[28] + 392LL) - *(_QWORD *)(v48[28] + 256LL),
          0);
      VsmmMbpUnblockHostAccessRestrictionWaiters(v48[20]);
    }
  }
  else
  {
LABEL_51:
    v15 = VsmmHostAccesspAcqRelFlush(v48);
    if ( v15 < 0 )
      goto LABEL_53;
    v15 = 0;
  }
  if ( v48[23] && (v48[22] & 1) != 0 && (*(_BYTE *)(*(_QWORD *)(v48[20] + 8LL) + 40LL) & 0x10) != 0 )
    WinHvFlushCache();
  VsmmHypercallMbpChunkLockDestroy(&v48[24]);
  VsmmHostAccesspAcqRelContextDestroy(v48);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1400eb25c  mov     [rsp-8+arg_10], rbx
0x1400eb261  push    rbp
0x1400eb262  push    rsi
0x1400eb263  push    rdi
0x1400eb264  push    r12
0x1400eb266  push    r13
0x1400eb268  push    r14
0x1400eb26a  push    r15
0x1400eb26c  lea     rbp, [rsp-120h]
0x1400eb274  sub     rsp, 220h
0x1400eb27b  mov     rax, cs:__security_cookie
0x1400eb282  xor     rax, rsp
0x1400eb285  mov     [rbp+150h+var_40], rax
0x1400eb28c  mov     rbx, r8
0x1400eb28f  mov     r14, rdx
0x1400eb292  mov     rsi, rcx
0x1400eb295  xor     edx, edx; Val
0x1400eb297  mov     r8d, 0F0h; Size
0x1400eb29d  lea     rcx, [rsp+250h+var_1F0]; void *
0x1400eb2a2  mov     edi, r9d
0x1400eb2a5  call    memset
0x1400eb2aa  mov     r8, [rsi+180h]
0x1400eb2b1  lea     rcx, [rsp+250h+var_1F0]
0x1400eb2b6  xor     r15d, r15d
0x1400eb2b9  mov     r9d, edi
0x1400eb2bc  mov     dword ptr [rsp+250h+var_228], r15d
0x1400eb2c1  mov     [rsp+250h+var_230], rbx
0x1400eb2c6  lea     edx, [r15+1]
0x1400eb2ca  call    VsmmHostAccesspReleaseContextInitialize
0x1400eb2cf  cmp     [rbp+150h+var_13C], r15d
0x1400eb2d3  lea     rcx, [rsp+250h+var_1F0]
0x1400eb2d8  mov     r13d, r15d
0x1400eb2db  mov     [rbp+150h+var_110], rsi
0x1400eb2df  setz    r13b
0x1400eb2e3  mov     [rbp+150h+var_108], r14
0x1400eb2e7  mov     [rsp+250h+var_210], r15
0x1400eb2ec  mov     r12d, r15d
0x1400eb2ef  call    VsmmHostAccesspAcqRelBySpa
0x1400eb2f4  mov     [rsp+250h+var_220], al
0x1400eb2f8  cmp     [rbp+150h+var_148], r15
0x1400eb2fc  jbe     loc_1400EB7E9
0x1400eb302  mov     rdi, [rsi+188h]
0x1400eb309  add     r14, r15
0x1400eb30c  sub     rdi, [rsi+100h]
0x1400eb313  xor     esi, esi
0x1400eb315  add     rdi, r14
0x1400eb318  cmp     [rsp+250h+var_1E0], esi
0x1400eb31c  jnz     short loc_1400EB399
0x1400eb31e  test    [rbp+150h+var_140], 1
0x1400eb322  jnz     short loc_1400EB399
0x1400eb324  mov     rcx, [rbp+150h+var_118]
0x1400eb328  mov     rsi, rdi
0x1400eb32b  shr     rsi, 9
0x1400eb32f  test    cl, 6
0x1400eb332  jbe     short loc_1400EB34E
0x1400eb334  mov     rax, rcx
0x1400eb337  shr     rax, 1
0x1400eb33a  and     eax, 3
0x1400eb33d  cmp     rsi, [rbp+rax*8+150h+var_130]
0x1400eb342  jnz     short loc_1400EB34E
0x1400eb344  and     rcx, 0FFFFFFFFFFFFFFF7h
0x1400eb348  mov     [rbp+150h+var_118], rcx
0x1400eb34c  jmp     short loc_1400EB397
0x1400eb34e  mov     rdx, rsi
0x1400eb351  lea     rcx, [rbp+150h+var_130]
0x1400eb355  call    VsmmHypercallMbpChunkLockAcquireSlow
0x1400eb35a  test    al, al
0x1400eb35c  jnz     short loc_1400EB397
0x1400eb35e  lea     rcx, [rsp+250h+var_1F0]
0x1400eb363  call    VsmmHostAccesspAcqRelFlush
0x1400eb368  mov     ebx, eax
0x1400eb36a  test    eax, eax
0x1400eb36c  js      loc_1400EB7FF
0x1400eb372  mov     rcx, [rbp+150h+var_118]
0x1400eb376  test    cl, 6
0x1400eb379  jbe     short loc_1400EB38B
0x1400eb37b  mov     rax, rcx
0x1400eb37e  shr     rax, 1
0x1400eb381  and     eax, 3
0x1400eb384  cmp     rsi, [rbp+rax*8+150h+var_130]
0x1400eb389  jz      short loc_1400EB344
0x1400eb38b  mov     rdx, rsi
0x1400eb38e  lea     rcx, [rbp+150h+var_130]
0x1400eb392  call    VsmmHypercallMbpChunkLockAcquireSlow
0x1400eb397  xor     esi, esi
0x1400eb399  mov     rbx, [rbp+150h+var_150]
0x1400eb39d  cmp     dword ptr [rbx+10Ch], 2
0x1400eb3a4  jz      short loc_1400EB3E1
0x1400eb3a6  mov     rax, [rbx+120h]
0x1400eb3ad  test    rax, rax
0x1400eb3b0  jz      short loc_1400EB3E0
0x1400eb3b2  mov     rsi, rdi
0x1400eb3b5  lea     rcx, [rbx+110h]
0x1400eb3bc  shr     rsi, 9
0x1400eb3c0  mov     rdx, rsi
0x1400eb3c3  call    cs:__imp_RtlTestBitNoFenceEx
0x1400eb3ca  nop     dword ptr [rax+rax+00h]
0x1400eb3cf  test    al, al
0x1400eb3d1  jnz     short loc_1400EB3DE
0x1400eb3d3  mov     rdx, rsi
0x1400eb3d6  mov     rcx, rbx
0x1400eb3d9  call    VsmmMbpUpgradeChunk
0x1400eb3de  xor     esi, esi
0x1400eb3e0  nop
0x1400eb3e1  mov     eax, [rbx+108h]
0x1400eb3e7  mov     r9d, 8
0x1400eb3ed  mov     rcx, [rbx+100h]
0x1400eb3f4  test    r9b, al
0x1400eb3f7  jnz     short loc_1400EB408
0x1400eb3f9  mov     rax, rdi
0x1400eb3fc  shl     rax, 4
0x1400eb400  add     rax, r9
0x1400eb403  add     rax, rcx
0x1400eb406  jmp     short loc_1400EB40C
0x1400eb408  lea     rax, [rcx+rdi*8]
0x1400eb40c  test    r13d, r13d
0x1400eb40f  jz      short loc_1400EB414
0x1400eb411  prefetchw byte ptr [rax]
0x1400eb414  mov     rax, [rax]
0x1400eb417  mov     [rsp+250h+var_210], rax
0x1400eb41c  cmp     [rbp+150h+var_13C], esi
0x1400eb41f  jnz     short loc_1400EB477
0x1400eb421  mov     r9d, [rsp+250h+var_1E0]
0x1400eb426  lea     r8, [rsp+250h+var_210]
0x1400eb42b  mov     rcx, [rbp+150h+var_150]
0x1400eb42f  mov     rdx, rdi
0x1400eb432  call    VsmmMbpHostAccessRestrictBegin
0x1400eb437  mov     ebx, eax
0x1400eb439  test    eax, eax
0x1400eb43b  jns     short loc_1400EB46D
0x1400eb43d  cmp     eax, 0C000022Dh
0x1400eb442  jnz     loc_1400EB53C
0x1400eb448  lea     rcx, [rsp+250h+var_1F0]
0x1400eb44d  call    VsmmHostAccesspAcqRelFlush
0x1400eb452  mov     ebx, eax
0x1400eb454  test    eax, eax
0x1400eb456  js      loc_1400EB801
0x1400eb45c  mov     rcx, [rbp+150h+var_150]
0x1400eb460  mov     rdx, rdi
0x1400eb463  call    VsmmMbpBlockOnHostAccessRestriction
0x1400eb468  jmp     loc_1400EB399
0x1400eb46d  mov     rax, [rsp+250h+var_210]
0x1400eb472  inc     r12
0x1400eb475  jmp     short loc_1400EB485
0x1400eb477  mov     cl, al
0x1400eb479  and     cl, 0Fh
0x1400eb47c  cmp     cl, 1
0x1400eb47f  jnz     loc_1400EB680
0x1400eb485  cmp     [rsp+250h+var_220], sil
0x1400eb48a  jz      short loc_1400EB4EA
0x1400eb48c  mov     r8, [rbp+150h+var_150]
0x1400eb490  and     eax, 0Fh
0x1400eb493  cmp     eax, 5
0x1400eb496  ja      short loc_1400EB4A8
0x1400eb498  jz      short loc_1400EB4BC
0x1400eb49a  test    eax, eax
0x1400eb49c  jz      short loc_1400EB4BC
0x1400eb49e  sub     eax, 1
0x1400eb4a1  jz      short loc_1400EB4CF
0x1400eb4a3  sub     eax, 1
0x1400eb4a6  jmp     short loc_1400EB4BC
0x1400eb4a8  sub     eax, 6
0x1400eb4ab  jz      short loc_1400EB4CF
0x1400eb4ad  sub     eax, 1
0x1400eb4b0  jz      short loc_1400EB4BC
0x1400eb4b2  sub     eax, 1
0x1400eb4b5  jz      short loc_1400EB4CF
0x1400eb4b7  cmp     eax, 1
0x1400eb4ba  jz      short loc_1400EB4CF
0x1400eb4bc  mov     cl, [r8+0F0h]
0x1400eb4c3  xor     edx, edx
0x1400eb4c5  call    VsmmNumaGetBackingPage
0x1400eb4ca  mov     r14, rax
0x1400eb4cd  jmp     short loc_1400EB4EA
0x1400eb4cf  mov     rax, [r8+100h]
0x1400eb4d6  add     rdi, rdi
0x1400eb4d9  mov     r14, [rax+rdi*8]
0x1400eb4dd  mov     rax, 0FFFFFFFFFFh
0x1400eb4e7  and     r14, rax
0x1400eb4ea  mov     rdx, [rbp+150h+var_168]
0x1400eb4ee  test    rdx, rdx
0x1400eb4f1  jz      short loc_1400EB516
0x1400eb4f3  mov     rcx, [rbp+150h+var_170]
0x1400eb4f7  add     rcx, rdx
0x1400eb4fa  cmp     r14, rcx
0x1400eb4fd  jz      short loc_1400EB51A
0x1400eb4ff  lea     rcx, [rsp+250h+var_1F0]
0x1400eb504  call    VsmmHostAccesspAcqRelCompleteRun
0x1400eb509  mov     ebx, eax
0x1400eb50b  test    eax, eax
0x1400eb50d  js      loc_1400EB801
0x1400eb513  mov     rdx, rsi
0x1400eb516  mov     [rbp+150h+var_170], r14
0x1400eb51a  inc     r15
0x1400eb51d  lea     rax, [rdx+1]
0x1400eb521  mov     [rbp+150h+var_168], rax
0x1400eb525  cmp     r15, [rbp+150h+var_148]
0x1400eb529  jnb     loc_1400EB7EB
0x1400eb52f  mov     r14, [rbp+150h+var_108]
0x1400eb533  mov     rsi, [rbp+150h+var_110]
0x1400eb537  jmp     loc_1400EB302
0x1400eb53c  mov     eax, cs:dword_140065110
0x1400eb542  cmp     eax, 2
0x1400eb545  jbe     loc_1400EB801
0x1400eb54b  mov     edx, 100h
0x1400eb550  lea     rcx, dword_140065110
0x1400eb557  call    _tlgKeywordOn
0x1400eb55c  test    al, al
0x1400eb55e  jz      loc_1400EB801
0x1400eb564  lea     rdx, aVsmmhostaccess_2; "VsmmHostAccesspRelease"
0x1400eb56b  lea     rcx, [rbp+150h+var_E0]
0x1400eb56f  call    _tlgCreate1Sz_char
0x1400eb574  lea     rdx, aOnecoreVmVidSy_33; "onecore\\vm\\vid\\sys\\vsmm\\vsmmhostac"...
0x1400eb57b  lea     rcx, [rbp+150h+var_D0]
0x1400eb582  call    _tlgCreate1Sz_char
0x1400eb587  mov     r8, [rbp+150h+var_150]
0x1400eb58b  lea     rax, [rsp+250h+var_21C]
0x1400eb590  mov     [rbp+150h+var_C0], rax
0x1400eb597  lea     rcx, [rsp+250h+var_218]
0x1400eb59c  mov     [rsp+250h+var_21C], 0CF3h
0x1400eb5a4  mov     [rbp+150h+var_B8], 4
0x1400eb5af  mov     [rsp+250h+var_218], ebx
0x1400eb5b3  mov     [rbp+150h+var_B0], rcx
0x1400eb5ba  mov     [rbp+150h+var_A8], 4
0x1400eb5c5  mov     rax, [r8+8]
0x1400eb5c9  add     rax, 290h
0x1400eb5cf  mov     [rbp+150h+var_98], 10h
0x1400eb5da  mov     [rbp+150h+var_A0], rax
0x1400eb5e1  mov     rax, [r8+8]
0x1400eb5e5  movzx   edx, word ptr [rax+78h]
0x1400eb5e9  mov     rcx, [rax+80h]
0x1400eb5f0  lea     rax, [rbp+150h+var_78]
0x1400eb5f7  mov     [rbp+150h+var_90], rax
0x1400eb5fe  mov     [rbp+150h+var_78], edx
0x1400eb604  lea     rdx, byte_14005C175
0x1400eb60b  mov     [rbp+150h+var_88], 2
0x1400eb616  mov     [rbp+150h+var_80], rcx
0x1400eb61d  mov     [rbp+150h+var_74], esi
0x1400eb623  mov     rax, [r8+8]
0x1400eb627  mov     rcx, [rax+288h]
0x1400eb62e  lea     rax, [rsp+250h+var_208]
0x1400eb633  mov     [rbp+150h+var_70], rax
0x1400eb63a  lea     rax, [rsp+250h+var_200]
0x1400eb63f  mov     [rbp+150h+var_60], rax
0x1400eb646  mov     rax, [rsp+250h+var_210]
0x1400eb64b  mov     [rsp+250h+var_1F8], rax
0x1400eb650  lea     rax, [rsp+250h+var_1F8]
0x1400eb655  mov     [rsp+250h+var_208], rcx
0x1400eb65a  mov     [rbp+150h+var_68], 8
0x1400eb665  mov     [rbp+150h+var_58], 8
0x1400eb670  mov     [rbp+150h+var_48], 8
0x1400eb67b  jmp     loc_1400EB7B8
0x1400eb680  mov     eax, cs:dword_140065110
0x1400eb686  mov     ebx, 0C000000Dh
0x1400eb68b  cmp     eax, 2
0x1400eb68e  jbe     loc_1400EB801
0x1400eb694  mov     edx, 100h
0x1400eb699  lea     rcx, dword_140065110
0x1400eb6a0  call    _tlgKeywordOn
0x1400eb6a5  test    al, al
0x1400eb6a7  jz      loc_1400EB801
0x1400eb6ad  lea     rdx, aVsmmhostaccess_2; "VsmmHostAccesspRelease"
0x1400eb6b4  lea     rcx, [rbp+150h+var_E0]
0x1400eb6b8  call    _tlgCreate1Sz_char
0x1400eb6bd  lea     rdx, aOnecoreVmVidSy_33; "onecore\\vm\\vid\\sys\\vsmm\\vsmmhostac"...
0x1400eb6c4  lea     rcx, [rbp+150h+var_D0]
0x1400eb6cb  call    _tlgCreate1Sz_char
0x1400eb6d0  mov     r8, [rbp+150h+var_150]
0x1400eb6d4  lea     rax, [rsp+250h+var_218]
0x1400eb6d9  mov     [rbp+150h+var_C0], rax
0x1400eb6e0  lea     rcx, [rsp+250h+var_21C]
0x1400eb6e5  mov     [rsp+250h+var_218], 0CD4h
0x1400eb6ed  mov     [rbp+150h+var_B8], 4
0x1400eb6f8  mov     [rsp+250h+var_21C], ebx
0x1400eb6fc  mov     [rbp+150h+var_B0], rcx
0x1400eb703  mov     [rbp+150h+var_A8], 4
0x1400eb70e  mov     rax, [r8+8]
0x1400eb712  add     rax, 290h
0x1400eb718  mov     [rbp+150h+var_98], 10h
0x1400eb723  mov     [rbp+150h+var_A0], rax
0x1400eb72a  mov     rax, [r8+8]
0x1400eb72e  movzx   edx, word ptr [rax+78h]
0x1400eb732  mov     rcx, [rax+80h]
0x1400eb739  lea     rax, [rbp+150h+var_78]
0x1400eb740  mov     [rbp+150h+var_90], rax
0x1400eb747  mov     [rbp+150h+var_78], edx
0x1400eb74d  lea     rdx, word_14005C1FA
0x1400eb754  mov     [rbp+150h+var_88], 2
0x1400eb75f  mov     [rbp+150h+var_80], rcx
0x1400eb766  mov     [rbp+150h+var_74], esi
0x1400eb76c  mov     rax, [r8+8]
0x1400eb770  mov     rcx, [rax+288h]
0x1400eb777  lea     rax, [rsp+250h+var_1F8]
0x1400eb77c  mov     [rbp+150h+var_70], rax
0x1400eb783  lea     rax, [rsp+250h+var_200]
0x1400eb788  mov     [rbp+150h+var_60], rax
0x1400eb78f  mov     rax, [rsp+250h+var_210]
0x1400eb794  mov     [rsp+250h+var_208], rax
0x1400eb799  lea     rax, [rsp+250h+var_208]
0x1400eb79e  mov     [rsp+250h+var_1F8], rcx
  ... truncated ...
```
