# VsmmHostAccessAcquireMbpRange

- ea: `0x1400ea0d0`
- end: `0x1400ea705`
- name: `VsmmHostAccessAcquireMbpRange`
- size: `1589`
- prototype: ``
- caller_count: `7`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x14002adc8`
- `0x140075f70`
- `0x1400bb844`
- `0x1400ca8b0`
- `0x1400cc480`
- `0x1400d4944`
- `0x1400eaec4`

## callees

- `0x1400029c0`
- `0x140006b40`
- `0x140006b68`
- `0x14000a010`
- `0x14000efa0`
- `0x14001b440`
- `0x140021c60`
- `0x140021e00`
- `0x14002e270`
- `0x140074030`
- `0x140074630`
- `0x140075c78`
- `0x1400768a0`
- `0x1400ea0d0`
- `0x1400ec584`
- `0x1400ec9fc`
- `0x1400f0ff0`
- `0x1400fe62c`

## import_xrefs

- `ntoskrnl!RtlTestBitNoFenceEx` at `0x1400ea1be`
- `ntoskrnl!RtlTestBitNoFenceEx` at `0x1400ea1be`
- `winhvr!WinHvFlushCache` at `0x1400ea6b2`
- `winhvr!WinHvFlushCache` at `0x1400ea6b2`

## string_xrefs

- `0x1400ea401`: `onecore\vm\vid\sys\vsmm\vsmmhostaccess.c`
- `0x1400ea588`: `onecore\vm\vid\sys\vsmm\vsmmhostaccess.c`
- `0x1400ea3ee`: `VsmmHostAccesspAcquire`
- `0x1400ea575`: `VsmmHostAccesspAcquire`

## pseudocode

```c
__int64 __fastcall VsmmHostAccessAcquireMbpRange(__int64 a1, __int64 a2, __int64 a3, int a4, int a5)
{
  int v9; // eax
  unsigned __int64 v10; // rdi
  char v11; // r12
  __int64 v12; // r13
  __int64 v13; // rcx
  __int64 v14; // r8
  int v15; // ebx
  __int64 v16; // r15
  __int64 v17; // rbx
  unsigned __int64 v18; // rsi
  __int64 *v19; // r8
  __int64 v20; // rcx
  unsigned int v21; // r8d
  unsigned int v22; // r8d
  unsigned int v23; // r8d
  __int64 BackingPage; // rdi
  unsigned __int64 v25; // rax
  int v26; // eax
  __int64 v27; // rdx
  int v28; // r8d
  int v29; // r10d
  int v30; // r9d
  __int64 v31; // rax
  __int64 v32; // rax
  int v33; // edx
  __int64 v34; // rcx
  __int16 *v35; // rdx
  __int64 v36; // rcx
  __int64 *v37; // rax
  int v38; // r9d
  __int64 v39; // rax
  __int64 v40; // rax
  int v41; // edx
  __int64 v42; // rcx
  __int64 v43; // rcx
  __int64 v45; // [rsp+40h] [rbp-C0h] BYREF
  int v46; // [rsp+48h] [rbp-B8h] BYREF
  _DWORD v47[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v48; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v49[2]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v50[30]; // [rsp+70h] [rbp-90h] BYREF
  char v51[32]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v52[16]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v53[16]; // [rsp+190h] [rbp+90h] BYREF
  int *v54; // [rsp+1A0h] [rbp+A0h]
  __int64 v55; // [rsp+1A8h] [rbp+A8h]
  int *v56; // [rsp+1B0h] [rbp+B0h]
  __int64 v57; // [rsp+1B8h] [rbp+B8h]
  __int64 v58; // [rsp+1C0h] [rbp+C0h]
  __int64 v59; // [rsp+1C8h] [rbp+C8h]
  int *v60; // [rsp+1D0h] [rbp+D0h]
  __int64 v61; // [rsp+1D8h] [rbp+D8h]
  __int64 v62; // [rsp+1E0h] [rbp+E0h]
  int v63; // [rsp+1E8h] [rbp+E8h] BYREF
  int v64; // [rsp+1ECh] [rbp+ECh]
  __int64 *v65; // [rsp+1F0h] [rbp+F0h]
  __int64 v66; // [rsp+1F8h] [rbp+F8h]
  __int64 *v67; // [rsp+200h] [rbp+100h]
  __int64 v68; // [rsp+208h] [rbp+108h]
  _DWORD *v69; // [rsp+210h] [rbp+110h]
  __int64 v70; // [rsp+218h] [rbp+118h]

  memset(v50, 0, 0xE8u);
  VsmmHostAccesspAcquireContextInitialize((unsigned int)v50, 0, a1, a4, a3, a5, 0);
  v9 = *(_BYTE *)(a1 + 264) & 1;
  v50[25] = a2;
  v10 = 0;
  LODWORD(v50[26]) = v9;
  v45 = 0;
  v11 = VsmmHostAccesspAcqRelBySpa(v50);
  v12 = *(_QWORD *)(v50[20] + 8LL);
  if ( SLODWORD(v50[2]) <= (int)VsmmHostAccessMinimumForMemoryBlock() )
    goto LABEL_2;
  v16 = 0;
  if ( !v50[21] )
  {
LABEL_51:
    v15 = VsmmHostAccesspAcqRelFlush(v50);
    if ( v15 < 0 )
    {
LABEL_52:
      if ( v15 == -1070268408 )
      {
        v15 = -1070137302;
        if ( !v11 && v50[23] != v10 && SLODWORD(v50[2]) > 1 )
          VsmmHostAccesspCheckVtlAccessInjectIntercept(v50);
      }
      goto LABEL_57;
    }
LABEL_2:
    v15 = v10;
    goto LABEL_57;
  }
  while ( 1 )
  {
    v17 = v50[20];
    v18 = v16 + a2;
    if ( *(_DWORD *)(v50[20] + 268LL) != 2 && *(_QWORD *)(v50[20] + 288LL) )
    {
      if ( !(unsigned __int8)RtlTestBitNoFenceEx(v50[20] + 272LL, v18 >> 9) )
        VsmmMbpUpgradeChunk(v17, v18 >> 9);
      v10 = 0;
    }
    v13 = *(_QWORD *)(v17 + 256);
    if ( (*(_DWORD *)(v17 + 264) & 8) != 0 )
      v19 = (__int64 *)(v13 + 8 * v18);
    else
      v19 = (__int64 *)(v13 + 16 * v18 + 8);
    v14 = *v19;
    if ( v11 )
    {
      if ( (v14 & 0xF) != 1 )
      {
        v15 = -1073741811;
        if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
        {
          tlgCreate1Sz_char(v52, "VsmmHostAccesspAcquire");
          tlgCreate1Sz_char(v53, "onecore\\vm\\vid\\sys\\vsmm\\vsmmhostaccess.c");
          LODWORD(v45) = v30;
          v54 = &v46;
          v46 = 1958;
          v55 = 4;
          v56 = (int *)&v45;
          v57 = 4;
          v31 = *(_QWORD *)(v50[20] + 8LL);
          v59 = 16;
          v58 = v31 + 656;
          v32 = *(_QWORD *)(v50[20] + 8LL);
          v33 = *(unsigned __int16 *)(v32 + 120);
          v34 = *(_QWORD *)(v32 + 128);
          v60 = &v63;
          v63 = v33;
          v35 = word_14005C372;
          v61 = 2;
          v62 = v34;
          v64 = v10;
          v36 = *(_QWORD *)(*(_QWORD *)(v50[20] + 8LL) + 648LL);
          v65 = &v48;
          v37 = v49;
          v48 = v36;
          v49[0] = v16 + a2;
LABEL_46:
          v67 = v37;
          v47[0] = v28;
          v69 = v47;
          v70 = 8;
          v47[1] = v29;
          v68 = 8;
          v66 = 8;
          tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, v35, 0, 0, 12, v51);
          goto LABEL_57;
        }
        goto LABEL_57;
      }
      v20 = v50[20];
      v21 = v14 & 0xF;
      if ( v21 > 5 )
      {
        v22 = v21 - 6;
        if ( v22 )
        {
          v23 = v22 - 1;
          if ( !v23 || v23 - 1 >= 2 )
            goto LABEL_20;
        }
      }
      else if ( v21 != 1 )
      {
LABEL_20:
        LOBYTE(v20) = *(_BYTE *)(v50[20] + 240LL);
        BackingPage = VsmmNumaGetBackingPage(v20, 0);
        goto LABEL_27;
      }
      BackingPage = *(_QWORD *)(*(_QWORD *)(v50[20] + 256LL) + 16 * v18) & 0xFFFFFFFFFFLL;
      goto LABEL_27;
    }
    if ( (v14 & 0xF) == 0 )
      break;
    v10 = v50[27];
    if ( v50[27] )
    {
      v25 = *(_QWORD *)(v50[27] + 392LL);
      if ( v18 >= v25 && v18 <= v50[28] )
      {
        BackingPage = v18 + *(_QWORD *)(v50[27] + 256LL) - v25;
LABEL_27:
        v45 = BackingPage;
LABEL_35:
        v27 = v50[17];
        if ( v50[17] )
        {
          if ( BackingPage != v50[17] + v50[16] )
          {
            v15 = VsmmHostAccesspAcqRelCompleteRun(v50);
            if ( v15 < 0 )
            {
              v10 = 0;
              goto LABEL_52;
            }
            v27 = 0;
            goto LABEL_39;
          }
        }
        else
        {
LABEL_39:
          v50[16] = BackingPage;
        }
        v10 = 0;
        v50[17] = v27 + 1;
        goto LABEL_41;
      }
      v10 = 0;
      v15 = VsmmHostAccesspAcqRelFlush(v50);
      if ( v15 < 0 )
        goto LABEL_52;
      LOBYTE(v14) = 1;
      VsmmGpaRangeRelease(v13, v50[27], v14);
      v50[27] = 0;
    }
    v26 = VsmmGpaRangeLookupGpaByMbp(v12, v50[20], (int)v16 + (int)a2, v50[26], v10, (__int64)&v45, (__int64)&v50[27]);
    v15 = v26;
    if ( v26 >= 0 )
    {
      BackingPage = v45;
      v50[28] = *(_QWORD *)(v50[27] + 272LL) + *(_QWORD *)(v50[27] + 392LL) - *(_QWORD *)(v50[27] + 256LL);
      goto LABEL_35;
    }
    if ( v26 != -1073741275 )
      goto LABEL_52;
    v15 = VsmmHostAccesspAcqRelFlush(v50);
    if ( v15 < 0 )
      goto LABEL_52;
    VsmmMbpHostAccessAcquire(v50[20], v16 + a2, LODWORD(v50[2]));
    ++v50[24];
LABEL_41:
    if ( (unsigned __int64)++v16 >= v50[21] )
      goto LABEL_51;
    a2 = v50[25];
  }
  v15 = -1073741811;
  if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
  {
    tlgCreate1Sz_char(v52, "VsmmHostAccesspAcquire");
    tlgCreate1Sz_char(v53, "onecore\\vm\\vid\\sys\\vsmm\\vsmmhostaccess.c");
    v46 = v38;
    v54 = (int *)&v45;
    LODWORD(v45) = 1990;
    v55 = 4;
    v56 = &v46;
    v57 = 4;
    v39 = *(_QWORD *)(v50[20] + 8LL);
    v59 = 16;
    v58 = v39 + 656;
    v40 = *(_QWORD *)(v50[20] + 8LL);
    v41 = *(unsigned __int16 *)(v40 + 120);
    v42 = *(_QWORD *)(v40 + 128);
    v60 = &v63;
    v63 = v41;
    v35 = (__int16 *)byte_14005C2ED;
    v61 = 2;
    v62 = v42;
    v64 = v10;
    v43 = *(_QWORD *)(*(_QWORD *)(v50[20] + 8LL) + 648LL);
    v65 = v49;
    v37 = &v48;
    v49[0] = v43;
    v48 = v16 + a2;
    goto LABEL_46;
  }
LABEL_57:
  if ( v50[24] > v10 && (v50[22] & 1) != 0 && (*(_BYTE *)(v12 + 40) & 0x10) != 0 )
    WinHvFlushCache();
  if ( LODWORD(v50[19]) <= 1 && v50[27] )
  {
    LOBYTE(v14) = 1;
    VsmmGpaRangeRelease(v13, v50[27], v14);
  }
  VsmmHostAccesspAcqRelContextDestroy(v50);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1400ea0d0  push    rbp
0x1400ea0d2  push    rbx
0x1400ea0d3  push    rsi
0x1400ea0d4  push    rdi
0x1400ea0d5  push    r12
0x1400ea0d7  push    r13
0x1400ea0d9  push    r14
0x1400ea0db  push    r15
0x1400ea0dd  lea     rbp, [rsp-138h]
0x1400ea0e5  sub     rsp, 238h
0x1400ea0ec  mov     rax, cs:__security_cookie
0x1400ea0f3  xor     rax, rsp
0x1400ea0f6  mov     [rbp+170h+var_50], rax
0x1400ea0fd  mov     rbx, r8
0x1400ea100  mov     r14, rdx
0x1400ea103  mov     rsi, rcx
0x1400ea106  xor     edx, edx; Val
0x1400ea108  mov     r8d, 0E8h; Size
0x1400ea10e  lea     rcx, [rsp+270h+var_200]; void *
0x1400ea113  mov     edi, r9d
0x1400ea116  call    memset
0x1400ea11b  mov     eax, [rbp+170h+arg_20]
0x1400ea121  lea     rcx, [rsp+270h+var_200]
0x1400ea126  mov     [rsp+270h+var_240], 0
0x1400ea12f  mov     r9d, edi
0x1400ea132  mov     dword ptr [rsp+270h+var_248], eax
0x1400ea136  mov     r8, rsi
0x1400ea139  xor     edx, edx
0x1400ea13b  mov     [rsp+270h+var_250], rbx
0x1400ea140  call    VsmmHostAccesspAcquireContextInitialize
0x1400ea145  movzx   eax, byte ptr [rsi+108h]
0x1400ea14c  lea     rcx, [rsp+270h+var_200]
0x1400ea151  and     eax, 1
0x1400ea154  mov     [rbp+170h+var_138], r14
0x1400ea158  xor     edi, edi
0x1400ea15a  mov     [rbp+170h+var_130], eax
0x1400ea15d  mov     [rsp+270h+var_230], rdi
0x1400ea162  call    VsmmHostAccesspAcqRelBySpa
0x1400ea167  mov     rcx, [rbp+170h+var_160]
0x1400ea16b  mov     r12b, al
0x1400ea16e  mov     r13, [rcx+8]
0x1400ea172  call    VsmmHostAccessMinimumForMemoryBlock
0x1400ea177  cmp     [rbp+170h+var_1F0], eax
0x1400ea17a  jg      short loc_1400EA183
0x1400ea17c  mov     ebx, edi
0x1400ea17e  jmp     loc_1400EA69F
0x1400ea183  mov     r15, rdi
0x1400ea186  cmp     [rbp+170h+var_158], rdi
0x1400ea18a  jbe     loc_1400EA663
0x1400ea190  mov     rbx, [rbp+170h+var_160]
0x1400ea194  lea     rsi, [r15+r14]
0x1400ea198  cmp     dword ptr [rbx+10Ch], 2
0x1400ea19f  jz      short loc_1400EA1DC
0x1400ea1a1  mov     rax, [rbx+120h]
0x1400ea1a8  test    rax, rax
0x1400ea1ab  jz      short loc_1400EA1DB
0x1400ea1ad  mov     rdi, rsi
0x1400ea1b0  lea     rcx, [rbx+110h]
0x1400ea1b7  shr     rdi, 9
0x1400ea1bb  mov     rdx, rdi
0x1400ea1be  call    cs:__imp_RtlTestBitNoFenceEx
0x1400ea1c5  nop     dword ptr [rax+rax+00h]
0x1400ea1ca  test    al, al
0x1400ea1cc  jnz     short loc_1400EA1D9
0x1400ea1ce  mov     rdx, rdi
0x1400ea1d1  mov     rcx, rbx
0x1400ea1d4  call    VsmmMbpUpgradeChunk
0x1400ea1d9  xor     edi, edi
0x1400ea1db  nop
0x1400ea1dc  mov     eax, [rbx+108h]
0x1400ea1e2  mov     rcx, [rbx+100h]
0x1400ea1e9  test    al, 8
0x1400ea1eb  jnz     short loc_1400EA1FD
0x1400ea1ed  mov     r8, rsi
0x1400ea1f0  shl     r8, 4
0x1400ea1f4  add     r8, 8
0x1400ea1f8  add     r8, rcx
0x1400ea1fb  jmp     short loc_1400EA201
0x1400ea1fd  lea     r8, [rcx+rsi*8]
0x1400ea201  mov     r8, [r8]
0x1400ea204  mov     r10, r8
0x1400ea207  mov     rax, r8
0x1400ea20a  shr     r10, 20h
0x1400ea20e  and     eax, 0Fh
0x1400ea211  test    r12b, r12b
0x1400ea214  jz      short loc_1400EA286
0x1400ea216  cmp     rax, 1
0x1400ea21a  jnz     loc_1400EA3BD
0x1400ea220  mov     rcx, [rbp+170h+var_160]
0x1400ea224  and     r8d, 0Fh
0x1400ea228  cmp     r8d, 5
0x1400ea22c  ja      short loc_1400EA23F
0x1400ea22e  jz      short loc_1400EA257
0x1400ea230  test    r8d, r8d
0x1400ea233  jz      short loc_1400EA257
0x1400ea235  sub     r8d, eax
0x1400ea238  jz      short loc_1400EA269
0x1400ea23a  sub     r8d, eax
0x1400ea23d  jmp     short loc_1400EA257
0x1400ea23f  sub     r8d, 6
0x1400ea243  jz      short loc_1400EA269
0x1400ea245  sub     r8d, 1
0x1400ea249  jz      short loc_1400EA257
0x1400ea24b  sub     r8d, 1
0x1400ea24f  jz      short loc_1400EA269
0x1400ea251  cmp     r8d, 1
0x1400ea255  jz      short loc_1400EA269
0x1400ea257  mov     cl, [rcx+0F0h]
0x1400ea25d  xor     edx, edx
0x1400ea25f  call    VsmmNumaGetBackingPage
0x1400ea264  mov     rdi, rax
0x1400ea267  jmp     short loc_1400EA2B7
0x1400ea269  mov     rax, [rcx+100h]
0x1400ea270  add     rsi, rsi
0x1400ea273  mov     rdi, [rax+rsi*8]
0x1400ea277  mov     rax, 0FFFFFFFFFFh
0x1400ea281  and     rdi, rax
0x1400ea284  jmp     short loc_1400EA2B7
0x1400ea286  test    rax, rax
0x1400ea289  jz      loc_1400EA544
0x1400ea28f  mov     rdi, [rbp+170h+var_128]
0x1400ea293  test    rdi, rdi
0x1400ea296  jz      short loc_1400EA2E7
0x1400ea298  mov     rax, [rdi+188h]
0x1400ea29f  cmp     rsi, rax
0x1400ea2a2  jb      short loc_1400EA2C1
0x1400ea2a4  cmp     rsi, [rbp+170h+var_120]
0x1400ea2a8  ja      short loc_1400EA2C1
0x1400ea2aa  mov     rdi, [rdi+100h]
0x1400ea2b1  sub     rdi, rax
0x1400ea2b4  add     rdi, rsi
0x1400ea2b7  mov     [rsp+270h+var_230], rdi
0x1400ea2bc  jmp     loc_1400EA36E
0x1400ea2c1  lea     rcx, [rsp+270h+var_200]
0x1400ea2c6  call    VsmmHostAccesspAcqRelFlush
0x1400ea2cb  xor     edi, edi
0x1400ea2cd  mov     ebx, eax
0x1400ea2cf  test    eax, eax
0x1400ea2d1  js      loc_1400EA677
0x1400ea2d7  mov     rdx, [rbp+170h+var_128]
0x1400ea2db  mov     r8b, 1
0x1400ea2de  call    VsmmGpaRangeRelease
0x1400ea2e3  mov     [rbp+170h+var_128], rdi
0x1400ea2e7  mov     r9d, [rbp+170h+var_130]
0x1400ea2eb  lea     rax, [rbp+170h+var_128]
0x1400ea2ef  mov     rdx, [rbp+170h+var_160]
0x1400ea2f3  mov     r8, rsi
0x1400ea2f6  mov     [rsp+270h+var_240], rax
0x1400ea2fb  mov     rcx, r13
0x1400ea2fe  lea     rax, [rsp+270h+var_230]
0x1400ea303  mov     [rsp+270h+var_248], rax
0x1400ea308  mov     dword ptr [rsp+270h+var_250], edi
0x1400ea30c  call    VsmmGpaRangeLookupGpaByMbp
0x1400ea311  mov     ebx, eax
0x1400ea313  test    eax, eax
0x1400ea315  jns     short loc_1400EA34C
0x1400ea317  cmp     eax, 0C0000225h
0x1400ea31c  jnz     loc_1400EA677
0x1400ea322  lea     rcx, [rsp+270h+var_200]
0x1400ea327  call    VsmmHostAccesspAcqRelFlush
0x1400ea32c  mov     ebx, eax
0x1400ea32e  test    eax, eax
0x1400ea330  js      loc_1400EA677
0x1400ea336  mov     r8d, [rbp+170h+var_1F0]
0x1400ea33a  mov     rdx, rsi
0x1400ea33d  mov     rcx, [rbp+170h+var_160]
0x1400ea341  call    VsmmMbpHostAccessAcquire
0x1400ea346  inc     [rbp+170h+var_140]
0x1400ea34a  jmp     short loc_1400EA3A7
0x1400ea34c  mov     rdx, [rbp+170h+var_128]
0x1400ea350  mov     rdi, [rsp+270h+var_230]
0x1400ea355  mov     rcx, [rdx+188h]
0x1400ea35c  sub     rcx, [rdx+100h]
0x1400ea363  add     rcx, [rdx+110h]
0x1400ea36a  mov     [rbp+170h+var_120], rcx
0x1400ea36e  mov     rdx, [rbp+170h+var_178]
0x1400ea372  test    rdx, rdx
0x1400ea375  jz      short loc_1400EA399
0x1400ea377  mov     rcx, [rbp+170h+var_180]
0x1400ea37b  add     rcx, rdx
0x1400ea37e  cmp     rdi, rcx
0x1400ea381  jz      short loc_1400EA39D
0x1400ea383  lea     rcx, [rsp+270h+var_200]
0x1400ea388  call    VsmmHostAccesspAcqRelCompleteRun
0x1400ea38d  mov     ebx, eax
0x1400ea38f  test    eax, eax
0x1400ea391  js      loc_1400EA53D
0x1400ea397  xor     edx, edx
0x1400ea399  mov     [rbp+170h+var_180], rdi
0x1400ea39d  lea     rax, [rdx+1]
0x1400ea3a1  xor     edi, edi
0x1400ea3a3  mov     [rbp+170h+var_178], rax
0x1400ea3a7  inc     r15
0x1400ea3aa  cmp     r15, [rbp+170h+var_158]
0x1400ea3ae  jnb     loc_1400EA663
0x1400ea3b4  mov     r14, [rbp+170h+var_138]
0x1400ea3b8  jmp     loc_1400EA190
0x1400ea3bd  mov     eax, cs:dword_140065110
0x1400ea3c3  mov     r9d, 0C000000Dh
0x1400ea3c9  mov     ebx, r9d
0x1400ea3cc  cmp     eax, 2
0x1400ea3cf  jbe     loc_1400EA69F
0x1400ea3d5  mov     edx, 100h
0x1400ea3da  lea     rcx, dword_140065110
0x1400ea3e1  call    _tlgKeywordOn
0x1400ea3e6  test    al, al
0x1400ea3e8  jz      loc_1400EA69F
0x1400ea3ee  lea     rdx, aVsmmhostaccess_0; "VsmmHostAccesspAcquire"
0x1400ea3f5  lea     rcx, [rbp+170h+var_F0]
0x1400ea3fc  call    _tlgCreate1Sz_char
0x1400ea401  lea     rdx, aOnecoreVmVidSy_33; "onecore\\vm\\vid\\sys\\vsmm\\vsmmhostac"...
0x1400ea408  lea     rcx, [rbp+170h+var_E0]
0x1400ea40f  call    _tlgCreate1Sz_char
0x1400ea414  mov     dword ptr [rsp+270h+var_230], r9d
0x1400ea419  lea     rax, [rsp+270h+var_228]
0x1400ea41e  mov     r9, [rbp+170h+var_160]
0x1400ea422  lea     rcx, [rsp+270h+var_230]
0x1400ea427  mov     [rbp+170h+var_D0], rax
0x1400ea42e  mov     [rsp+270h+var_228], 7A6h
0x1400ea436  mov     [rbp+170h+var_C8], 4
0x1400ea441  mov     [rbp+170h+var_C0], rcx
0x1400ea448  mov     [rbp+170h+var_B8], 4
0x1400ea453  mov     rax, [r9+8]
0x1400ea457  add     rax, 290h
0x1400ea45d  mov     [rbp+170h+var_A8], 10h
0x1400ea468  mov     [rbp+170h+var_B0], rax
0x1400ea46f  mov     rax, [r9+8]
0x1400ea473  movzx   edx, word ptr [rax+78h]
0x1400ea477  mov     rcx, [rax+80h]
0x1400ea47e  lea     rax, [rbp+170h+var_88]
0x1400ea485  mov     [rbp+170h+var_A0], rax
0x1400ea48c  mov     [rbp+170h+var_88], edx
0x1400ea492  lea     rdx, word_14005C372
0x1400ea499  mov     [rbp+170h+var_98], 2
0x1400ea4a4  mov     [rbp+170h+var_90], rcx
0x1400ea4ab  mov     [rbp+170h+var_84], edi
0x1400ea4b1  mov     rax, [r9+8]
0x1400ea4b5  mov     rcx, [rax+288h]
0x1400ea4bc  lea     rax, [rsp+270h+var_218]
0x1400ea4c1  mov     [rbp+170h+var_80], rax
0x1400ea4c8  lea     rax, [rsp+270h+var_210]
0x1400ea4cd  mov     [rsp+270h+var_218], rcx
0x1400ea4d2  mov     [rsp+270h+var_210], rsi
0x1400ea4d7  mov     [rbp+170h+var_70], rax
0x1400ea4de  lea     rcx, dword_140065110
0x1400ea4e5  lea     rax, [rsp+270h+var_220]
0x1400ea4ea  mov     [rsp+270h+var_220], r8d
0x1400ea4ef  mov     [rbp+170h+var_60], rax
0x1400ea4f6  xor     r9d, r9d
0x1400ea4f9  lea     rax, [rbp+170h+var_110]
0x1400ea4fd  mov     [rbp+170h+var_58], 8
0x1400ea508  mov     [rsp+270h+var_248], rax
0x1400ea50d  xor     r8d, r8d
0x1400ea510  mov     dword ptr [rsp+270h+var_250], 0Ch
0x1400ea518  mov     [rsp+270h+var_21C], r10d
0x1400ea51d  mov     [rbp+170h+var_68], 8
0x1400ea528  mov     [rbp+170h+var_78], 8
0x1400ea533  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400ea538  jmp     loc_1400EA69F
0x1400ea53d  xor     edi, edi
0x1400ea53f  jmp     loc_1400EA677
0x1400ea544  mov     eax, cs:dword_140065110
0x1400ea54a  mov     r9d, 0C000000Dh
0x1400ea550  mov     ebx, r9d
0x1400ea553  cmp     eax, 2
0x1400ea556  jbe     loc_1400EA69F
0x1400ea55c  mov     edx, 100h
0x1400ea561  lea     rcx, dword_140065110
0x1400ea568  call    _tlgKeywordOn
0x1400ea56d  test    al, al
0x1400ea56f  jz      loc_1400EA69F
0x1400ea575  lea     rdx, aVsmmhostaccess_0; "VsmmHostAccesspAcquire"
0x1400ea57c  lea     rcx, [rbp+170h+var_F0]
0x1400ea583  call    _tlgCreate1Sz_char
0x1400ea588  lea     rdx, aOnecoreVmVidSy_33; "onecore\\vm\\vid\\sys\\vsmm\\vsmmhostac"...
0x1400ea58f  lea     rcx, [rbp+170h+var_E0]
0x1400ea596  call    _tlgCreate1Sz_char
0x1400ea59b  mov     [rsp+270h+var_228], r9d
0x1400ea5a0  lea     rax, [rsp+270h+var_230]
0x1400ea5a5  mov     r9, [rbp+170h+var_160]
0x1400ea5a9  lea     rcx, [rsp+270h+var_228]
0x1400ea5ae  mov     [rbp+170h+var_D0], rax
0x1400ea5b5  mov     dword ptr [rsp+270h+var_230], 7C6h
0x1400ea5bd  mov     [rbp+170h+var_C8], 4
0x1400ea5c8  mov     [rbp+170h+var_C0], rcx
0x1400ea5cf  mov     [rbp+170h+var_B8], 4
0x1400ea5da  mov     rax, [r9+8]
0x1400ea5de  add     rax, 290h
0x1400ea5e4  mov     [rbp+170h+var_A8], 10h
0x1400ea5ef  mov     [rbp+170h+var_B0], rax
0x1400ea5f6  mov     rax, [r9+8]
0x1400ea5fa  movzx   edx, word ptr [rax+78h]
0x1400ea5fe  mov     rcx, [rax+80h]
0x1400ea605  lea     rax, [rbp+170h+var_88]
0x1400ea60c  mov     [rbp+170h+var_A0], rax
0x1400ea613  mov     [rbp+170h+var_88], edx
0x1400ea619  lea     rdx, byte_14005C2ED
0x1400ea620  mov     [rbp+170h+var_98], 2
0x1400ea62b  mov     [rbp+170h+var_90], rcx
0x1400ea632  mov     [rbp+170h+var_84], edi
  ... truncated ...
```
