# VsmmHostAccessReleaseSparseGpa

- ea: `0x1400ebf08`
- end: `0x1400ec57c`
- name: `VsmmHostAccessReleaseSparseGpa`
- size: `1652`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x1400da320`
- `0x1400f3584`

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
- `0x1400ebf08`
- `0x1400ec584`
- `0x1400ecdec`
- `0x1400fe70c`

## import_xrefs

- `ntoskrnl!RtlTestBitNoFenceEx` at `0x1400ec07a`
- `ntoskrnl!RtlTestBitNoFenceEx` at `0x1400ec07a`
- `winhvr!WinHvFlushCache` at `0x1400ec523`
- `winhvr!WinHvFlushCache` at `0x1400ec523`

## string_xrefs

- `0x1400ec21c`: `VsmmHostAccesspRelease`
- `0x1400ec365`: `VsmmHostAccesspRelease`
- `0x1400ec22c`: `onecore\vm\vid\sys\vsmm\vsmmhostaccess.c`
- `0x1400ec375`: `onecore\vm\vid\sys\vsmm\vsmmhostaccess.c`

## pseudocode

```c
__int64 __fastcall VsmmHostAccessReleaseSparseGpa(_QWORD *a1, __int64 a2, unsigned int a3, int a4, int a5, _QWORD *a6)
{
  unsigned __int64 v10; // r12
  unsigned __int64 v11; // r15
  __int64 BackingPage; // r14
  unsigned __int64 v13; // rdi
  __int64 v14; // rcx
  unsigned __int64 v15; // rsi
  int v16; // ebx
  __int64 v17; // rbx
  __int64 v18; // rcx
  __int64 *v19; // rax
  __int64 v20; // rax
  int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  __int64 v25; // rdx
  __int64 v26; // rax
  __int64 v27; // rax
  int v28; // edx
  __int64 v29; // rcx
  __int16 *v30; // rdx
  __int64 v31; // rcx
  __int64 *v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  int v35; // edx
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // r9
  int v39; // eax
  unsigned __int64 i; // rdi
  __int64 v41; // rdx
  char v43; // [rsp+30h] [rbp-D0h]
  int v44; // [rsp+34h] [rbp-CCh] BYREF
  int v45; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v46; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v47; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 v48; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v49; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v50[30]; // [rsp+60h] [rbp-A0h] BYREF
  char v51[32]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v52[16]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v53[16]; // [rsp+180h] [rbp+80h] BYREF
  int *v54; // [rsp+190h] [rbp+90h]
  __int64 v55; // [rsp+198h] [rbp+98h]
  int *v56; // [rsp+1A0h] [rbp+A0h]
  __int64 v57; // [rsp+1A8h] [rbp+A8h]
  __int64 v58; // [rsp+1B0h] [rbp+B0h]
  __int64 v59; // [rsp+1B8h] [rbp+B8h]
  int *v60; // [rsp+1C0h] [rbp+C0h]
  __int64 v61; // [rsp+1C8h] [rbp+C8h]
  __int64 v62; // [rsp+1D0h] [rbp+D0h]
  int v63; // [rsp+1D8h] [rbp+D8h] BYREF
  int v64; // [rsp+1DCh] [rbp+DCh]
  __int64 *v65; // [rsp+1E0h] [rbp+E0h]
  __int64 v66; // [rsp+1E8h] [rbp+E8h]
  unsigned __int64 *v67; // [rsp+1F0h] [rbp+F0h]
  __int64 v68; // [rsp+1F8h] [rbp+F8h]
  __int64 *v69; // [rsp+200h] [rbp+100h]
  __int64 v70; // [rsp+208h] [rbp+108h]

  memset(v50, 0, sizeof(v50));
  VsmmHostAccesspReleaseContextInitialize((unsigned int)v50, 2, a1[48], a4, a3, 0);
  v50[28] = a1;
  v50[29] = a2;
  v44 = HIDWORD(v50[22]) == 0;
  v10 = 0;
  v46 = 0;
  v11 = 0;
  v43 = VsmmHostAccesspAcqRelBySpa(v50);
  if ( v50[21] )
  {
LABEL_2:
    BackingPage = *(_QWORD *)(a2 + 8 * v11);
    v13 = BackingPage + a1[49] - a1[32];
    if ( !LODWORD(v50[2]) && (v50[22] & 1) == 0 )
    {
      v14 = v50[27];
      v15 = v13 >> 9;
      if ( (v50[27] & 6) == 0 || v15 != v50[((v50[27] >> 1) & 3LL) + 24] )
      {
        if ( (unsigned __int8)VsmmHypercallMbpChunkLockAcquireSlow(&v50[24], v13 >> 9) )
          goto LABEL_12;
        v16 = VsmmHostAccesspAcqRelFlush(v50);
        if ( v16 < 0 )
          goto LABEL_53;
        v14 = v50[27];
        if ( (v50[27] & 6) == 0 || v15 != v50[((v50[27] >> 1) & 3LL) + 24] )
        {
          VsmmHypercallMbpChunkLockAcquireSlow(&v50[24], v13 >> 9);
          goto LABEL_12;
        }
      }
      v50[27] = v14 & 0xFFFFFFFFFFFFFFF7uLL;
      goto LABEL_12;
    }
    while ( 1 )
    {
LABEL_12:
      v17 = v50[20];
      if ( *(_DWORD *)(v50[20] + 268LL) != 2
        && *(_QWORD *)(v50[20] + 288LL)
        && !(unsigned __int8)RtlTestBitNoFenceEx(v50[20] + 272LL, v13 >> 9) )
      {
        VsmmMbpUpgradeChunk(v17, v13 >> 9);
      }
      v18 = *(_QWORD *)(v17 + 256);
      if ( (*(_DWORD *)(v17 + 264) & 8) != 0 )
        v19 = (__int64 *)(v18 + 8 * v13);
      else
        v19 = (__int64 *)(v18 + 16 * v13 + 8);
      if ( v44 )
        _m_prefetchw(v19);
      v20 = *v19;
      v46 = v20;
      if ( HIDWORD(v50[22]) )
        break;
      v21 = VsmmMbpHostAccessRestrictBegin(v50[20], v13, &v46, LODWORD(v50[2]));
      v16 = v21;
      if ( v21 >= 0 )
      {
        LOBYTE(v20) = v46;
        ++v10;
LABEL_28:
        if ( v43 )
        {
          v22 = v20 & 0xF;
          if ( v22 > 5 )
          {
            v23 = v22 - 6;
            if ( !v23 )
              goto LABEL_36;
            v24 = v23 - 1;
            if ( v24 )
            {
              if ( v24 - 1 < 2 )
                goto LABEL_36;
            }
LABEL_35:
            LOBYTE(v18) = *(_BYTE *)(v50[20] + 240LL);
            BackingPage = VsmmNumaGetBackingPage(v18, 0);
          }
          else
          {
            if ( v22 != 1 )
              goto LABEL_35;
LABEL_36:
            BackingPage = *(_QWORD *)(*(_QWORD *)(v50[20] + 256LL) + 16 * v13) & 0xFFFFFFFFFFLL;
          }
        }
        v25 = v50[17];
        if ( v50[17] )
        {
          if ( BackingPage != v50[17] + v50[16] )
          {
            v16 = VsmmHostAccesspAcqRelCompleteRun(v50);
            if ( v16 < 0 )
              goto LABEL_53;
            v25 = 0;
            goto LABEL_41;
          }
        }
        else
        {
LABEL_41:
          v50[16] = BackingPage;
        }
        ++v11;
        v50[17] = v25 + 1;
        if ( v11 >= v50[21] )
          goto LABEL_51;
        a2 = v50[29];
        a1 = (_QWORD *)v50[28];
        goto LABEL_2;
      }
      if ( v21 != -1073741267 )
      {
        if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
        {
          tlgCreate1Sz_char(v52, "VsmmHostAccesspRelease");
          tlgCreate1Sz_char(v53, "onecore\\vm\\vid\\sys\\vsmm\\vsmmhostaccess.c");
          v54 = &v44;
          v44 = 3315;
          v55 = 4;
          v45 = v16;
          v56 = &v45;
          v57 = 4;
          v26 = *(_QWORD *)(v50[20] + 8LL);
          v59 = 16;
          v58 = v26 + 656;
          v27 = *(_QWORD *)(v50[20] + 8LL);
          v28 = *(unsigned __int16 *)(v27 + 120);
          v29 = *(_QWORD *)(v27 + 128);
          v60 = &v63;
          v63 = v28;
          v30 = (__int16 *)byte_14005C175;
          v61 = 2;
          v62 = v29;
          v64 = 0;
          v31 = *(_QWORD *)(*(_QWORD *)(v50[20] + 8LL) + 648LL);
          v65 = &v47;
          v67 = &v48;
          v49 = v46;
          v32 = &v49;
          v47 = v31;
          v66 = 8;
          v68 = 8;
          v70 = 8;
          goto LABEL_50;
        }
        goto LABEL_53;
      }
      v16 = VsmmHostAccesspAcqRelFlush(v50);
      if ( v16 < 0 )
        goto LABEL_53;
      VsmmMbpBlockOnHostAccessRestriction(v50[20], v13);
    }
    if ( (v20 & 0xF) == 1 )
      goto LABEL_28;
    v16 = -1073741811;
    if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
    {
      tlgCreate1Sz_char(v52, "VsmmHostAccesspRelease");
      tlgCreate1Sz_char(v53, "onecore\\vm\\vid\\sys\\vsmm\\vsmmhostaccess.c");
      v54 = &v45;
      v45 = 3284;
      v55 = 4;
      v44 = -1073741811;
      v56 = &v44;
      v57 = 4;
      v33 = *(_QWORD *)(v50[20] + 8LL);
      v59 = 16;
      v58 = v33 + 656;
      v34 = *(_QWORD *)(v50[20] + 8LL);
      v35 = *(unsigned __int16 *)(v34 + 120);
      v36 = *(_QWORD *)(v34 + 128);
      v60 = &v63;
      v63 = v35;
      v30 = word_14005C1FA;
      v61 = 2;
      v62 = v36;
      v64 = 0;
      v37 = *(_QWORD *)(*(_QWORD *)(v50[20] + 8LL) + 648LL);
      v65 = &v49;
      v67 = &v48;
      v47 = v46;
      v32 = &v47;
      v49 = v37;
      v66 = v38;
      v68 = v38;
      v70 = v38;
LABEL_50:
      v69 = v32;
      v48 = v13;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, v30, 0, 0, 12, v51);
    }
LABEL_53:
    v39 = VsmmHostAccesspAcqRelFlush(v50);
    if ( v39 < 0 )
      v16 = v39;
    if ( !HIDWORD(v50[22]) )
    {
      for ( i = v50[23]; i < v10; ++i )
        VsmmMbpHostAccessRestrictComplete(
          v50[20],
          *(_QWORD *)(v50[28] + 392LL) + *(_QWORD *)(v50[29] + 8 * i) - *(_QWORD *)(v50[28] + 256LL),
          0);
      VsmmMbpUnblockHostAccessRestrictionWaiters(v50[20]);
    }
  }
  else
  {
LABEL_51:
    v16 = VsmmHostAccesspAcqRelFlush(v50);
    if ( v16 < 0 )
      goto LABEL_53;
    v16 = 0;
  }
  v41 = v50[23];
  if ( v50[23] && (v50[22] & 1) != 0 && (*(_BYTE *)(*(_QWORD *)(v50[20] + 8LL) + 40LL) & 0x10) != 0 )
  {
    WinHvFlushCache();
    v41 = v50[23];
  }
  if ( a6 )
    *a6 = v41;
  VsmmHypercallMbpChunkLockDestroy(&v50[24]);
  VsmmHostAccesspAcqRelContextDestroy(v50);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x1400ebf08  mov     [rsp-8+arg_10], rbx
0x1400ebf0d  push    rbp
0x1400ebf0e  push    rsi
0x1400ebf0f  push    rdi
0x1400ebf10  push    r12
0x1400ebf12  push    r13
0x1400ebf14  push    r14
0x1400ebf16  push    r15
0x1400ebf18  lea     rbp, [rsp-120h]
0x1400ebf20  sub     rsp, 220h
0x1400ebf27  mov     rax, cs:__security_cookie
0x1400ebf2e  xor     rax, rsp
0x1400ebf31  mov     [rbp+150h+var_40], rax
0x1400ebf38  mov     r13, [rbp+150h+arg_28]
0x1400ebf3f  mov     r14, rdx
0x1400ebf42  mov     ebx, r8d
0x1400ebf45  mov     rsi, rcx
0x1400ebf48  xor     edx, edx; Val
0x1400ebf4a  lea     rcx, [rsp+250h+var_1F0]; void *
0x1400ebf4f  mov     r8d, 0F0h; Size
0x1400ebf55  mov     edi, r9d
0x1400ebf58  call    memset
0x1400ebf5d  mov     r8, [rsi+180h]
0x1400ebf64  lea     rcx, [rsp+250h+var_1F0]
0x1400ebf69  mov     eax, ebx
0x1400ebf6b  mov     r9d, edi
0x1400ebf6e  xor     ebx, ebx
0x1400ebf70  mov     dword ptr [rsp+250h+var_228], ebx
0x1400ebf74  mov     [rsp+250h+var_230], rax
0x1400ebf79  lea     edx, [rbx+2]
0x1400ebf7c  call    VsmmHostAccesspReleaseContextInitialize
0x1400ebf81  cmp     [rbp+150h+var_13C], ebx
0x1400ebf84  lea     rcx, [rsp+250h+var_1F0]
0x1400ebf89  mov     eax, ebx
0x1400ebf8b  mov     [rbp+150h+var_110], rsi
0x1400ebf8f  setz    al
0x1400ebf92  mov     [rbp+150h+var_108], r14
0x1400ebf96  mov     [rsp+250h+var_21C], eax
0x1400ebf9a  mov     r12d, ebx
0x1400ebf9d  mov     [rsp+250h+var_210], rbx
0x1400ebfa2  call    VsmmHostAccesspAcqRelBySpa
0x1400ebfa7  mov     r15d, ebx
0x1400ebfaa  mov     [rsp+250h+var_220], al
0x1400ebfae  cmp     [rbp+150h+var_148], rbx
0x1400ebfb2  jbe     loc_1400EC4A1
0x1400ebfb8  mov     rdi, [rsi+188h]
0x1400ebfbf  sub     rdi, [rsi+100h]
0x1400ebfc6  xor     esi, esi
0x1400ebfc8  mov     r14, [r14+r15*8]
0x1400ebfcc  add     rdi, r14
0x1400ebfcf  cmp     [rsp+250h+var_1E0], esi
0x1400ebfd3  jnz     short loc_1400EC050
0x1400ebfd5  test    [rbp+150h+var_140], 1
0x1400ebfd9  jnz     short loc_1400EC050
0x1400ebfdb  mov     rcx, [rbp+150h+var_118]
0x1400ebfdf  mov     rsi, rdi
0x1400ebfe2  shr     rsi, 9
0x1400ebfe6  test    cl, 6
0x1400ebfe9  jbe     short loc_1400EC005
0x1400ebfeb  mov     rax, rcx
0x1400ebfee  shr     rax, 1
0x1400ebff1  and     eax, 3
0x1400ebff4  cmp     rsi, [rbp+rax*8+150h+var_130]
0x1400ebff9  jnz     short loc_1400EC005
0x1400ebffb  and     rcx, 0FFFFFFFFFFFFFFF7h
0x1400ebfff  mov     [rbp+150h+var_118], rcx
0x1400ec003  jmp     short loc_1400EC04E
0x1400ec005  mov     rdx, rsi
0x1400ec008  lea     rcx, [rbp+150h+var_130]
0x1400ec00c  call    VsmmHypercallMbpChunkLockAcquireSlow
0x1400ec011  test    al, al
0x1400ec013  jnz     short loc_1400EC04E
0x1400ec015  lea     rcx, [rsp+250h+var_1F0]
0x1400ec01a  call    VsmmHostAccesspAcqRelFlush
0x1400ec01f  mov     ebx, eax
0x1400ec021  test    eax, eax
0x1400ec023  js      loc_1400EC4B7
0x1400ec029  mov     rcx, [rbp+150h+var_118]
0x1400ec02d  test    cl, 6
0x1400ec030  jbe     short loc_1400EC042
0x1400ec032  mov     rax, rcx
0x1400ec035  shr     rax, 1
0x1400ec038  and     eax, 3
0x1400ec03b  cmp     rsi, [rbp+rax*8+150h+var_130]
0x1400ec040  jz      short loc_1400EBFFB
0x1400ec042  mov     rdx, rsi
0x1400ec045  lea     rcx, [rbp+150h+var_130]
0x1400ec049  call    VsmmHypercallMbpChunkLockAcquireSlow
0x1400ec04e  xor     esi, esi
0x1400ec050  mov     rbx, [rbp+150h+var_150]
0x1400ec054  cmp     dword ptr [rbx+10Ch], 2
0x1400ec05b  jz      short loc_1400EC098
0x1400ec05d  mov     rax, [rbx+120h]
0x1400ec064  test    rax, rax
0x1400ec067  jz      short loc_1400EC097
0x1400ec069  mov     rsi, rdi
0x1400ec06c  lea     rcx, [rbx+110h]
0x1400ec073  shr     rsi, 9
0x1400ec077  mov     rdx, rsi
0x1400ec07a  call    cs:__imp_RtlTestBitNoFenceEx
0x1400ec081  nop     dword ptr [rax+rax+00h]
0x1400ec086  test    al, al
0x1400ec088  jnz     short loc_1400EC095
0x1400ec08a  mov     rdx, rsi
0x1400ec08d  mov     rcx, rbx
0x1400ec090  call    VsmmMbpUpgradeChunk
0x1400ec095  xor     esi, esi
0x1400ec097  nop
0x1400ec098  mov     eax, [rbx+108h]
0x1400ec09e  mov     r9d, 8
0x1400ec0a4  mov     rcx, [rbx+100h]
0x1400ec0ab  test    r9b, al
0x1400ec0ae  jnz     short loc_1400EC0BF
0x1400ec0b0  mov     rax, rdi
0x1400ec0b3  shl     rax, 4
0x1400ec0b7  add     rax, r9
0x1400ec0ba  add     rax, rcx
0x1400ec0bd  jmp     short loc_1400EC0C3
0x1400ec0bf  lea     rax, [rcx+rdi*8]
0x1400ec0c3  cmp     [rsp+250h+var_21C], esi
0x1400ec0c7  jz      short loc_1400EC0CC
0x1400ec0c9  prefetchw byte ptr [rax]
0x1400ec0cc  mov     rax, [rax]
0x1400ec0cf  mov     [rsp+250h+var_210], rax
0x1400ec0d4  cmp     [rbp+150h+var_13C], esi
0x1400ec0d7  jnz     short loc_1400EC12F
0x1400ec0d9  mov     r9d, [rsp+250h+var_1E0]
0x1400ec0de  lea     r8, [rsp+250h+var_210]
0x1400ec0e3  mov     rcx, [rbp+150h+var_150]
0x1400ec0e7  mov     rdx, rdi
0x1400ec0ea  call    VsmmMbpHostAccessRestrictBegin
0x1400ec0ef  mov     ebx, eax
0x1400ec0f1  test    eax, eax
0x1400ec0f3  jns     short loc_1400EC125
0x1400ec0f5  cmp     eax, 0C000022Dh
0x1400ec0fa  jnz     loc_1400EC1F4
0x1400ec100  lea     rcx, [rsp+250h+var_1F0]
0x1400ec105  call    VsmmHostAccesspAcqRelFlush
0x1400ec10a  mov     ebx, eax
0x1400ec10c  test    eax, eax
0x1400ec10e  js      loc_1400EC4B9
0x1400ec114  mov     rcx, [rbp+150h+var_150]
0x1400ec118  mov     rdx, rdi
0x1400ec11b  call    VsmmMbpBlockOnHostAccessRestriction
0x1400ec120  jmp     loc_1400EC050
0x1400ec125  mov     rax, [rsp+250h+var_210]
0x1400ec12a  inc     r12
0x1400ec12d  jmp     short loc_1400EC13D
0x1400ec12f  mov     cl, al
0x1400ec131  and     cl, 0Fh
0x1400ec134  cmp     cl, 1
0x1400ec137  jnz     loc_1400EC338
0x1400ec13d  cmp     [rsp+250h+var_220], sil
0x1400ec142  jz      short loc_1400EC1A2
0x1400ec144  mov     r8, [rbp+150h+var_150]
0x1400ec148  and     eax, 0Fh
0x1400ec14b  cmp     eax, 5
0x1400ec14e  ja      short loc_1400EC160
0x1400ec150  jz      short loc_1400EC174
0x1400ec152  test    eax, eax
0x1400ec154  jz      short loc_1400EC174
0x1400ec156  sub     eax, 1
0x1400ec159  jz      short loc_1400EC187
0x1400ec15b  sub     eax, 1
0x1400ec15e  jmp     short loc_1400EC174
0x1400ec160  sub     eax, 6
0x1400ec163  jz      short loc_1400EC187
0x1400ec165  sub     eax, 1
0x1400ec168  jz      short loc_1400EC174
0x1400ec16a  sub     eax, 1
0x1400ec16d  jz      short loc_1400EC187
0x1400ec16f  cmp     eax, 1
0x1400ec172  jz      short loc_1400EC187
0x1400ec174  mov     cl, [r8+0F0h]
0x1400ec17b  xor     edx, edx
0x1400ec17d  call    VsmmNumaGetBackingPage
0x1400ec182  mov     r14, rax
0x1400ec185  jmp     short loc_1400EC1A2
0x1400ec187  mov     rax, [r8+100h]
0x1400ec18e  add     rdi, rdi
0x1400ec191  mov     r14, [rax+rdi*8]
0x1400ec195  mov     rax, 0FFFFFFFFFFh
0x1400ec19f  and     r14, rax
0x1400ec1a2  mov     rdx, [rbp+150h+var_168]
0x1400ec1a6  test    rdx, rdx
0x1400ec1a9  jz      short loc_1400EC1CE
0x1400ec1ab  mov     rcx, [rbp+150h+var_170]
0x1400ec1af  add     rcx, rdx
0x1400ec1b2  cmp     r14, rcx
0x1400ec1b5  jz      short loc_1400EC1D2
0x1400ec1b7  lea     rcx, [rsp+250h+var_1F0]
0x1400ec1bc  call    VsmmHostAccesspAcqRelCompleteRun
0x1400ec1c1  mov     ebx, eax
0x1400ec1c3  test    eax, eax
0x1400ec1c5  js      loc_1400EC4B9
0x1400ec1cb  mov     rdx, rsi
0x1400ec1ce  mov     [rbp+150h+var_170], r14
0x1400ec1d2  inc     r15
0x1400ec1d5  lea     rax, [rdx+1]
0x1400ec1d9  mov     [rbp+150h+var_168], rax
0x1400ec1dd  cmp     r15, [rbp+150h+var_148]
0x1400ec1e1  jnb     loc_1400EC4A3
0x1400ec1e7  mov     r14, [rbp+150h+var_108]
0x1400ec1eb  mov     rsi, [rbp+150h+var_110]
0x1400ec1ef  jmp     loc_1400EBFB8
0x1400ec1f4  mov     eax, cs:dword_140065110
0x1400ec1fa  cmp     eax, 2
0x1400ec1fd  jbe     loc_1400EC4B9
0x1400ec203  mov     edx, 100h
0x1400ec208  lea     rcx, dword_140065110
0x1400ec20f  call    _tlgKeywordOn
0x1400ec214  test    al, al
0x1400ec216  jz      loc_1400EC4B9
0x1400ec21c  lea     rdx, aVsmmhostaccess_2; "VsmmHostAccesspRelease"
0x1400ec223  lea     rcx, [rbp+150h+var_E0]
0x1400ec227  call    _tlgCreate1Sz_char
0x1400ec22c  lea     rdx, aOnecoreVmVidSy_33; "onecore\\vm\\vid\\sys\\vsmm\\vsmmhostac"...
0x1400ec233  lea     rcx, [rbp+150h+var_D0]
0x1400ec23a  call    _tlgCreate1Sz_char
0x1400ec23f  mov     r8, [rbp+150h+var_150]
0x1400ec243  lea     rax, [rsp+250h+var_21C]
0x1400ec248  mov     [rbp+150h+var_C0], rax
0x1400ec24f  lea     rcx, [rsp+250h+var_218]
0x1400ec254  mov     [rsp+250h+var_21C], 0CF3h
0x1400ec25c  mov     [rbp+150h+var_B8], 4
0x1400ec267  mov     [rsp+250h+var_218], ebx
0x1400ec26b  mov     [rbp+150h+var_B0], rcx
0x1400ec272  mov     [rbp+150h+var_A8], 4
0x1400ec27d  mov     rax, [r8+8]
0x1400ec281  add     rax, 290h
0x1400ec287  mov     [rbp+150h+var_98], 10h
0x1400ec292  mov     [rbp+150h+var_A0], rax
0x1400ec299  mov     rax, [r8+8]
0x1400ec29d  movzx   edx, word ptr [rax+78h]
0x1400ec2a1  mov     rcx, [rax+80h]
0x1400ec2a8  lea     rax, [rbp+150h+var_78]
0x1400ec2af  mov     [rbp+150h+var_90], rax
0x1400ec2b6  mov     [rbp+150h+var_78], edx
0x1400ec2bc  lea     rdx, byte_14005C175
0x1400ec2c3  mov     [rbp+150h+var_88], 2
0x1400ec2ce  mov     [rbp+150h+var_80], rcx
0x1400ec2d5  mov     [rbp+150h+var_74], esi
0x1400ec2db  mov     rax, [r8+8]
0x1400ec2df  mov     rcx, [rax+288h]
0x1400ec2e6  lea     rax, [rsp+250h+var_208]
0x1400ec2eb  mov     [rbp+150h+var_70], rax
0x1400ec2f2  lea     rax, [rsp+250h+var_200]
0x1400ec2f7  mov     [rbp+150h+var_60], rax
0x1400ec2fe  mov     rax, [rsp+250h+var_210]
0x1400ec303  mov     [rsp+250h+var_1F8], rax
0x1400ec308  lea     rax, [rsp+250h+var_1F8]
0x1400ec30d  mov     [rsp+250h+var_208], rcx
0x1400ec312  mov     [rbp+150h+var_68], 8
0x1400ec31d  mov     [rbp+150h+var_58], 8
0x1400ec328  mov     [rbp+150h+var_48], 8
0x1400ec333  jmp     loc_1400EC470
0x1400ec338  mov     eax, cs:dword_140065110
0x1400ec33e  mov     ebx, 0C000000Dh
0x1400ec343  cmp     eax, 2
0x1400ec346  jbe     loc_1400EC4B9
0x1400ec34c  mov     edx, 100h
0x1400ec351  lea     rcx, dword_140065110
0x1400ec358  call    _tlgKeywordOn
0x1400ec35d  test    al, al
0x1400ec35f  jz      loc_1400EC4B9
0x1400ec365  lea     rdx, aVsmmhostaccess_2; "VsmmHostAccesspRelease"
0x1400ec36c  lea     rcx, [rbp+150h+var_E0]
0x1400ec370  call    _tlgCreate1Sz_char
0x1400ec375  lea     rdx, aOnecoreVmVidSy_33; "onecore\\vm\\vid\\sys\\vsmm\\vsmmhostac"...
0x1400ec37c  lea     rcx, [rbp+150h+var_D0]
0x1400ec383  call    _tlgCreate1Sz_char
0x1400ec388  mov     r8, [rbp+150h+var_150]
0x1400ec38c  lea     rax, [rsp+250h+var_218]
0x1400ec391  mov     [rbp+150h+var_C0], rax
0x1400ec398  lea     rcx, [rsp+250h+var_21C]
0x1400ec39d  mov     [rsp+250h+var_218], 0CD4h
0x1400ec3a5  mov     [rbp+150h+var_B8], 4
0x1400ec3b0  mov     [rsp+250h+var_21C], ebx
0x1400ec3b4  mov     [rbp+150h+var_B0], rcx
0x1400ec3bb  mov     [rbp+150h+var_A8], 4
0x1400ec3c6  mov     rax, [r8+8]
0x1400ec3ca  add     rax, 290h
0x1400ec3d0  mov     [rbp+150h+var_98], 10h
0x1400ec3db  mov     [rbp+150h+var_A0], rax
0x1400ec3e2  mov     rax, [r8+8]
0x1400ec3e6  movzx   edx, word ptr [rax+78h]
0x1400ec3ea  mov     rcx, [rax+80h]
0x1400ec3f1  lea     rax, [rbp+150h+var_78]
0x1400ec3f8  mov     [rbp+150h+var_90], rax
0x1400ec3ff  mov     [rbp+150h+var_78], edx
0x1400ec405  lea     rdx, word_14005C1FA
0x1400ec40c  mov     [rbp+150h+var_88], 2
0x1400ec417  mov     [rbp+150h+var_80], rcx
0x1400ec41e  mov     [rbp+150h+var_74], esi
0x1400ec424  mov     rax, [r8+8]
0x1400ec428  mov     rcx, [rax+288h]
0x1400ec42f  lea     rax, [rsp+250h+var_1F8]
0x1400ec434  mov     [rbp+150h+var_70], rax
0x1400ec43b  lea     rax, [rsp+250h+var_200]
0x1400ec440  mov     [rbp+150h+var_60], rax
  ... truncated ...
```
