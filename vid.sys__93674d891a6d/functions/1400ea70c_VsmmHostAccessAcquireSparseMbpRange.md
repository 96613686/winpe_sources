# VsmmHostAccessAcquireSparseMbpRange

- ea: `0x1400ea70c`
- end: `0x1400ead45`
- name: `VsmmHostAccessAcquireSparseMbpRange`
- size: `1593`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x1400063d0`

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
- `0x1400ea70c`
- `0x1400ec584`
- `0x1400ec9fc`
- `0x1400f0ff0`
- `0x1400fe62c`

## import_xrefs

- `ntoskrnl!RtlTestBitNoFenceEx` at `0x1400ea7fe`
- `ntoskrnl!RtlTestBitNoFenceEx` at `0x1400ea7fe`
- `winhvr!WinHvFlushCache` at `0x1400eacf2`
- `winhvr!WinHvFlushCache` at `0x1400eacf2`

## string_xrefs

- `0x1400eaa41`: `onecore\vm\vid\sys\vsmm\vsmmhostaccess.c`
- `0x1400eabc8`: `onecore\vm\vid\sys\vsmm\vsmmhostaccess.c`
- `0x1400eaa2e`: `VsmmHostAccesspAcquire`
- `0x1400eabb5`: `VsmmHostAccesspAcquire`

## pseudocode

```c
__int64 __fastcall VsmmHostAccessAcquireSparseMbpRange(__int64 a1, __int64 a2, __int64 a3, int a4, int a5, __int64 a6)
{
  int v10; // eax
  unsigned __int64 v11; // rdi
  char v12; // r12
  __int64 v13; // r13
  __int64 v14; // rcx
  __int64 v15; // r8
  int v16; // ebx
  __int64 v17; // r15
  __int64 v18; // rbx
  unsigned __int64 v19; // rsi
  __int64 *v20; // r8
  __int64 v21; // rcx
  unsigned int v22; // r8d
  unsigned int v23; // r8d
  unsigned int v24; // r8d
  __int64 BackingPage; // rdi
  unsigned __int64 v26; // rax
  int v27; // eax
  __int64 v28; // rdx
  int v29; // r8d
  int v30; // r10d
  int v31; // r9d
  __int64 v32; // rax
  __int64 v33; // rax
  int v34; // edx
  __int64 v35; // rcx
  __int16 *v36; // rdx
  unsigned __int64 v37; // rcx
  __int64 *v38; // rax
  int v39; // r9d
  __int64 v40; // rax
  __int64 v41; // rax
  int v42; // edx
  __int64 v43; // rcx
  __int64 v44; // rcx
  __int64 v46; // [rsp+40h] [rbp-C0h] BYREF
  int v47; // [rsp+48h] [rbp-B8h] BYREF
  _DWORD v48[2]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v49; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v50[2]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v51[30]; // [rsp+70h] [rbp-90h] BYREF
  char v52[32]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v53[16]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v54[16]; // [rsp+190h] [rbp+90h] BYREF
  int *v55; // [rsp+1A0h] [rbp+A0h]
  __int64 v56; // [rsp+1A8h] [rbp+A8h]
  int *v57; // [rsp+1B0h] [rbp+B0h]
  __int64 v58; // [rsp+1B8h] [rbp+B8h]
  __int64 v59; // [rsp+1C0h] [rbp+C0h]
  __int64 v60; // [rsp+1C8h] [rbp+C8h]
  int *v61; // [rsp+1D0h] [rbp+D0h]
  __int64 v62; // [rsp+1D8h] [rbp+D8h]
  __int64 v63; // [rsp+1E0h] [rbp+E0h]
  int v64; // [rsp+1E8h] [rbp+E8h] BYREF
  int v65; // [rsp+1ECh] [rbp+ECh]
  __int64 *v66; // [rsp+1F0h] [rbp+F0h]
  __int64 v67; // [rsp+1F8h] [rbp+F8h]
  __int64 *v68; // [rsp+200h] [rbp+100h]
  __int64 v69; // [rsp+208h] [rbp+108h]
  _DWORD *v70; // [rsp+210h] [rbp+110h]
  __int64 v71; // [rsp+218h] [rbp+118h]

  memset(v51, 0, 0xE8u);
  VsmmHostAccesspAcquireContextInitialize((unsigned int)v51, 1, a1, a4, a3, 0, a6);
  v10 = *(_BYTE *)(a1 + 264) & 1;
  v51[25] = a2;
  v11 = 0;
  LODWORD(v51[26]) = v10;
  v46 = 0;
  v12 = VsmmHostAccesspAcqRelBySpa(v51);
  v13 = *(_QWORD *)(v51[20] + 8LL);
  if ( SLODWORD(v51[2]) <= (int)VsmmHostAccessMinimumForMemoryBlock() )
    goto LABEL_2;
  v17 = 0;
  if ( !v51[21] )
  {
LABEL_51:
    v16 = VsmmHostAccesspAcqRelFlush(v51);
    if ( v16 < 0 )
    {
LABEL_52:
      if ( v16 == -1070268408 )
      {
        v16 = -1070137302;
        if ( !v12 && v51[23] != v11 && SLODWORD(v51[2]) > 1 )
          VsmmHostAccesspCheckVtlAccessInjectIntercept(v51);
      }
      goto LABEL_57;
    }
LABEL_2:
    v16 = v11;
    goto LABEL_57;
  }
  while ( 1 )
  {
    v18 = v51[20];
    v19 = *(_QWORD *)(a2 + 8 * v17);
    if ( *(_DWORD *)(v51[20] + 268LL) != 2 && *(_QWORD *)(v51[20] + 288LL) )
    {
      if ( !(unsigned __int8)RtlTestBitNoFenceEx(v51[20] + 272LL, v19 >> 9) )
        VsmmMbpUpgradeChunk(v18, v19 >> 9);
      v11 = 0;
    }
    v14 = *(_QWORD *)(v18 + 256);
    if ( (*(_DWORD *)(v18 + 264) & 8) != 0 )
      v20 = (__int64 *)(v14 + 8 * v19);
    else
      v20 = (__int64 *)(v14 + 16 * v19 + 8);
    v15 = *v20;
    if ( v12 )
    {
      if ( (v15 & 0xF) != 1 )
      {
        v16 = -1073741811;
        if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
        {
          tlgCreate1Sz_char(v53, "VsmmHostAccesspAcquire");
          tlgCreate1Sz_char(v54, "onecore\\vm\\vid\\sys\\vsmm\\vsmmhostaccess.c");
          LODWORD(v46) = v31;
          v55 = &v47;
          v47 = 1958;
          v56 = 4;
          v57 = (int *)&v46;
          v58 = 4;
          v32 = *(_QWORD *)(v51[20] + 8LL);
          v60 = 16;
          v59 = v32 + 656;
          v33 = *(_QWORD *)(v51[20] + 8LL);
          v34 = *(unsigned __int16 *)(v33 + 120);
          v35 = *(_QWORD *)(v33 + 128);
          v61 = &v64;
          v64 = v34;
          v36 = word_14005C372;
          v62 = 2;
          v63 = v35;
          v65 = v11;
          v37 = *(_QWORD *)(*(_QWORD *)(v51[20] + 8LL) + 648LL);
          v66 = (__int64 *)&v49;
          v38 = v50;
          v49 = v37;
          v50[0] = v19;
LABEL_46:
          v68 = v38;
          v48[0] = v29;
          v70 = v48;
          v71 = 8;
          v48[1] = v30;
          v69 = 8;
          v67 = 8;
          tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, v36, 0, 0, 12, v52);
          goto LABEL_57;
        }
        goto LABEL_57;
      }
      v21 = v51[20];
      v22 = v15 & 0xF;
      if ( v22 > 5 )
      {
        v23 = v22 - 6;
        if ( v23 )
        {
          v24 = v23 - 1;
          if ( !v24 || v24 - 1 >= 2 )
            goto LABEL_20;
        }
      }
      else if ( v22 != 1 )
      {
LABEL_20:
        LOBYTE(v21) = *(_BYTE *)(v51[20] + 240LL);
        BackingPage = VsmmNumaGetBackingPage(v21, 0);
        goto LABEL_27;
      }
      BackingPage = *(_QWORD *)(*(_QWORD *)(v51[20] + 256LL) + 16 * v19) & 0xFFFFFFFFFFLL;
      goto LABEL_27;
    }
    if ( (v15 & 0xF) == 0 )
      break;
    v11 = v51[27];
    if ( v51[27] )
    {
      v26 = *(_QWORD *)(v51[27] + 392LL);
      if ( v19 >= v26 && v19 <= v51[28] )
      {
        BackingPage = v19 + *(_QWORD *)(v51[27] + 256LL) - v26;
LABEL_27:
        v46 = BackingPage;
LABEL_35:
        v28 = v51[17];
        if ( v51[17] )
        {
          if ( BackingPage != v51[17] + v51[16] )
          {
            v16 = VsmmHostAccesspAcqRelCompleteRun(v51);
            if ( v16 < 0 )
            {
              v11 = 0;
              goto LABEL_52;
            }
            v28 = 0;
            goto LABEL_39;
          }
        }
        else
        {
LABEL_39:
          v51[16] = BackingPage;
        }
        v11 = 0;
        v51[17] = v28 + 1;
        goto LABEL_41;
      }
      v11 = 0;
      v16 = VsmmHostAccesspAcqRelFlush(v51);
      if ( v16 < 0 )
        goto LABEL_52;
      LOBYTE(v15) = 1;
      VsmmGpaRangeRelease(v14, v51[27], v15);
      v51[27] = 0;
    }
    v27 = VsmmGpaRangeLookupGpaByMbp(v13, v51[20], v19, v51[26], v11, (__int64)&v46, (__int64)&v51[27]);
    v16 = v27;
    if ( v27 >= 0 )
    {
      BackingPage = v46;
      v51[28] = *(_QWORD *)(v51[27] + 272LL) + *(_QWORD *)(v51[27] + 392LL) - *(_QWORD *)(v51[27] + 256LL);
      goto LABEL_35;
    }
    if ( v27 != -1073741275 )
      goto LABEL_52;
    v16 = VsmmHostAccesspAcqRelFlush(v51);
    if ( v16 < 0 )
      goto LABEL_52;
    VsmmMbpHostAccessAcquire(v51[20], v19, LODWORD(v51[2]));
    ++v51[24];
LABEL_41:
    if ( (unsigned __int64)++v17 >= v51[21] )
      goto LABEL_51;
    a2 = v51[25];
  }
  v16 = -1073741811;
  if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
  {
    tlgCreate1Sz_char(v53, "VsmmHostAccesspAcquire");
    tlgCreate1Sz_char(v54, "onecore\\vm\\vid\\sys\\vsmm\\vsmmhostaccess.c");
    v47 = v39;
    v55 = (int *)&v46;
    LODWORD(v46) = 1990;
    v56 = 4;
    v57 = &v47;
    v58 = 4;
    v40 = *(_QWORD *)(v51[20] + 8LL);
    v60 = 16;
    v59 = v40 + 656;
    v41 = *(_QWORD *)(v51[20] + 8LL);
    v42 = *(unsigned __int16 *)(v41 + 120);
    v43 = *(_QWORD *)(v41 + 128);
    v61 = &v64;
    v64 = v42;
    v36 = (__int16 *)byte_14005C2ED;
    v62 = 2;
    v63 = v43;
    v65 = v11;
    v44 = *(_QWORD *)(*(_QWORD *)(v51[20] + 8LL) + 648LL);
    v66 = v50;
    v38 = (__int64 *)&v49;
    v50[0] = v44;
    v49 = v19;
    goto LABEL_46;
  }
LABEL_57:
  if ( v51[24] > v11 && (v51[22] & 1) != 0 && (*(_BYTE *)(v13 + 40) & 0x10) != 0 )
    WinHvFlushCache();
  if ( LODWORD(v51[19]) <= 1 && v51[27] )
  {
    LOBYTE(v15) = 1;
    VsmmGpaRangeRelease(v14, v51[27], v15);
  }
  VsmmHostAccesspAcqRelContextDestroy(v51);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x1400ea70c  push    rbp
0x1400ea70e  push    rbx
0x1400ea70f  push    rsi
0x1400ea710  push    rdi
0x1400ea711  push    r12
0x1400ea713  push    r13
0x1400ea715  push    r14
0x1400ea717  push    r15
0x1400ea719  lea     rbp, [rsp-138h]
0x1400ea721  sub     rsp, 238h
0x1400ea728  mov     rax, cs:__security_cookie
0x1400ea72f  xor     rax, rsp
0x1400ea732  mov     [rbp+170h+var_50], rax
0x1400ea739  mov     rbx, r8
0x1400ea73c  mov     r14, rdx
0x1400ea73f  mov     rsi, rcx
0x1400ea742  xor     edx, edx; Val
0x1400ea744  mov     r8d, 0E8h; Size
0x1400ea74a  lea     rcx, [rsp+270h+var_200]; void *
0x1400ea74f  mov     edi, r9d
0x1400ea752  call    memset
0x1400ea757  mov     rax, [rbp+170h+arg_28]
0x1400ea75e  lea     rcx, [rsp+270h+var_200]
0x1400ea763  mov     [rsp+270h+var_240], rax
0x1400ea768  mov     r9d, edi
0x1400ea76b  mov     dword ptr [rsp+270h+var_248], 0
0x1400ea773  mov     r8, rsi
0x1400ea776  mov     edx, 1
0x1400ea77b  mov     [rsp+270h+var_250], rbx
0x1400ea780  call    VsmmHostAccesspAcquireContextInitialize
0x1400ea785  movzx   eax, byte ptr [rsi+108h]
0x1400ea78c  lea     rcx, [rsp+270h+var_200]
0x1400ea791  and     eax, 1
0x1400ea794  mov     [rbp+170h+var_138], r14
0x1400ea798  xor     edi, edi
0x1400ea79a  mov     [rbp+170h+var_130], eax
0x1400ea79d  mov     [rsp+270h+var_230], rdi
0x1400ea7a2  call    VsmmHostAccesspAcqRelBySpa
0x1400ea7a7  mov     rcx, [rbp+170h+var_160]
0x1400ea7ab  mov     r12b, al
0x1400ea7ae  mov     r13, [rcx+8]
0x1400ea7b2  call    VsmmHostAccessMinimumForMemoryBlock
0x1400ea7b7  cmp     [rbp+170h+var_1F0], eax
0x1400ea7ba  jg      short loc_1400EA7C3
0x1400ea7bc  mov     ebx, edi
0x1400ea7be  jmp     loc_1400EACDF
0x1400ea7c3  mov     r15, rdi
0x1400ea7c6  cmp     [rbp+170h+var_158], rdi
0x1400ea7ca  jbe     loc_1400EACA3
0x1400ea7d0  mov     rbx, [rbp+170h+var_160]
0x1400ea7d4  mov     rsi, [r14+r15*8]
0x1400ea7d8  cmp     dword ptr [rbx+10Ch], 2
0x1400ea7df  jz      short loc_1400EA81C
0x1400ea7e1  mov     rax, [rbx+120h]
0x1400ea7e8  test    rax, rax
0x1400ea7eb  jz      short loc_1400EA81B
0x1400ea7ed  mov     rdi, rsi
0x1400ea7f0  lea     rcx, [rbx+110h]
0x1400ea7f7  shr     rdi, 9
0x1400ea7fb  mov     rdx, rdi
0x1400ea7fe  call    cs:__imp_RtlTestBitNoFenceEx
0x1400ea805  nop     dword ptr [rax+rax+00h]
0x1400ea80a  test    al, al
0x1400ea80c  jnz     short loc_1400EA819
0x1400ea80e  mov     rdx, rdi
0x1400ea811  mov     rcx, rbx
0x1400ea814  call    VsmmMbpUpgradeChunk
0x1400ea819  xor     edi, edi
0x1400ea81b  nop
0x1400ea81c  mov     eax, [rbx+108h]
0x1400ea822  mov     rcx, [rbx+100h]
0x1400ea829  test    al, 8
0x1400ea82b  jnz     short loc_1400EA83D
0x1400ea82d  mov     r8, rsi
0x1400ea830  shl     r8, 4
0x1400ea834  add     r8, 8
0x1400ea838  add     r8, rcx
0x1400ea83b  jmp     short loc_1400EA841
0x1400ea83d  lea     r8, [rcx+rsi*8]
0x1400ea841  mov     r8, [r8]
0x1400ea844  mov     r10, r8
0x1400ea847  mov     rax, r8
0x1400ea84a  shr     r10, 20h
0x1400ea84e  and     eax, 0Fh
0x1400ea851  test    r12b, r12b
0x1400ea854  jz      short loc_1400EA8C6
0x1400ea856  cmp     rax, 1
0x1400ea85a  jnz     loc_1400EA9FD
0x1400ea860  mov     rcx, [rbp+170h+var_160]
0x1400ea864  and     r8d, 0Fh
0x1400ea868  cmp     r8d, 5
0x1400ea86c  ja      short loc_1400EA87F
0x1400ea86e  jz      short loc_1400EA897
0x1400ea870  test    r8d, r8d
0x1400ea873  jz      short loc_1400EA897
0x1400ea875  sub     r8d, eax
0x1400ea878  jz      short loc_1400EA8A9
0x1400ea87a  sub     r8d, eax
0x1400ea87d  jmp     short loc_1400EA897
0x1400ea87f  sub     r8d, 6
0x1400ea883  jz      short loc_1400EA8A9
0x1400ea885  sub     r8d, 1
0x1400ea889  jz      short loc_1400EA897
0x1400ea88b  sub     r8d, 1
0x1400ea88f  jz      short loc_1400EA8A9
0x1400ea891  cmp     r8d, 1
0x1400ea895  jz      short loc_1400EA8A9
0x1400ea897  mov     cl, [rcx+0F0h]
0x1400ea89d  xor     edx, edx
0x1400ea89f  call    VsmmNumaGetBackingPage
0x1400ea8a4  mov     rdi, rax
0x1400ea8a7  jmp     short loc_1400EA8F7
0x1400ea8a9  mov     rax, [rcx+100h]
0x1400ea8b0  add     rsi, rsi
0x1400ea8b3  mov     rdi, [rax+rsi*8]
0x1400ea8b7  mov     rax, 0FFFFFFFFFFh
0x1400ea8c1  and     rdi, rax
0x1400ea8c4  jmp     short loc_1400EA8F7
0x1400ea8c6  test    rax, rax
0x1400ea8c9  jz      loc_1400EAB84
0x1400ea8cf  mov     rdi, [rbp+170h+var_128]
0x1400ea8d3  test    rdi, rdi
0x1400ea8d6  jz      short loc_1400EA927
0x1400ea8d8  mov     rax, [rdi+188h]
0x1400ea8df  cmp     rsi, rax
0x1400ea8e2  jb      short loc_1400EA901
0x1400ea8e4  cmp     rsi, [rbp+170h+var_120]
0x1400ea8e8  ja      short loc_1400EA901
0x1400ea8ea  mov     rdi, [rdi+100h]
0x1400ea8f1  sub     rdi, rax
0x1400ea8f4  add     rdi, rsi
0x1400ea8f7  mov     [rsp+270h+var_230], rdi
0x1400ea8fc  jmp     loc_1400EA9AE
0x1400ea901  lea     rcx, [rsp+270h+var_200]
0x1400ea906  call    VsmmHostAccesspAcqRelFlush
0x1400ea90b  xor     edi, edi
0x1400ea90d  mov     ebx, eax
0x1400ea90f  test    eax, eax
0x1400ea911  js      loc_1400EACB7
0x1400ea917  mov     rdx, [rbp+170h+var_128]
0x1400ea91b  mov     r8b, 1
0x1400ea91e  call    VsmmGpaRangeRelease
0x1400ea923  mov     [rbp+170h+var_128], rdi
0x1400ea927  mov     r9d, [rbp+170h+var_130]
0x1400ea92b  lea     rax, [rbp+170h+var_128]
0x1400ea92f  mov     rdx, [rbp+170h+var_160]
0x1400ea933  mov     r8, rsi
0x1400ea936  mov     [rsp+270h+var_240], rax
0x1400ea93b  mov     rcx, r13
0x1400ea93e  lea     rax, [rsp+270h+var_230]
0x1400ea943  mov     [rsp+270h+var_248], rax
0x1400ea948  mov     dword ptr [rsp+270h+var_250], edi
0x1400ea94c  call    VsmmGpaRangeLookupGpaByMbp
0x1400ea951  mov     ebx, eax
0x1400ea953  test    eax, eax
0x1400ea955  jns     short loc_1400EA98C
0x1400ea957  cmp     eax, 0C0000225h
0x1400ea95c  jnz     loc_1400EACB7
0x1400ea962  lea     rcx, [rsp+270h+var_200]
0x1400ea967  call    VsmmHostAccesspAcqRelFlush
0x1400ea96c  mov     ebx, eax
0x1400ea96e  test    eax, eax
0x1400ea970  js      loc_1400EACB7
0x1400ea976  mov     r8d, [rbp+170h+var_1F0]
0x1400ea97a  mov     rdx, rsi
0x1400ea97d  mov     rcx, [rbp+170h+var_160]
0x1400ea981  call    VsmmMbpHostAccessAcquire
0x1400ea986  inc     [rbp+170h+var_140]
0x1400ea98a  jmp     short loc_1400EA9E7
0x1400ea98c  mov     rdx, [rbp+170h+var_128]
0x1400ea990  mov     rdi, [rsp+270h+var_230]
0x1400ea995  mov     rcx, [rdx+188h]
0x1400ea99c  sub     rcx, [rdx+100h]
0x1400ea9a3  add     rcx, [rdx+110h]
0x1400ea9aa  mov     [rbp+170h+var_120], rcx
0x1400ea9ae  mov     rdx, [rbp+170h+var_178]
0x1400ea9b2  test    rdx, rdx
0x1400ea9b5  jz      short loc_1400EA9D9
0x1400ea9b7  mov     rcx, [rbp+170h+var_180]
0x1400ea9bb  add     rcx, rdx
0x1400ea9be  cmp     rdi, rcx
0x1400ea9c1  jz      short loc_1400EA9DD
0x1400ea9c3  lea     rcx, [rsp+270h+var_200]
0x1400ea9c8  call    VsmmHostAccesspAcqRelCompleteRun
0x1400ea9cd  mov     ebx, eax
0x1400ea9cf  test    eax, eax
0x1400ea9d1  js      loc_1400EAB7D
0x1400ea9d7  xor     edx, edx
0x1400ea9d9  mov     [rbp+170h+var_180], rdi
0x1400ea9dd  lea     rax, [rdx+1]
0x1400ea9e1  xor     edi, edi
0x1400ea9e3  mov     [rbp+170h+var_178], rax
0x1400ea9e7  inc     r15
0x1400ea9ea  cmp     r15, [rbp+170h+var_158]
0x1400ea9ee  jnb     loc_1400EACA3
0x1400ea9f4  mov     r14, [rbp+170h+var_138]
0x1400ea9f8  jmp     loc_1400EA7D0
0x1400ea9fd  mov     eax, cs:dword_140065110
0x1400eaa03  mov     r9d, 0C000000Dh
0x1400eaa09  mov     ebx, r9d
0x1400eaa0c  cmp     eax, 2
0x1400eaa0f  jbe     loc_1400EACDF
0x1400eaa15  mov     edx, 100h
0x1400eaa1a  lea     rcx, dword_140065110
0x1400eaa21  call    _tlgKeywordOn
0x1400eaa26  test    al, al
0x1400eaa28  jz      loc_1400EACDF
0x1400eaa2e  lea     rdx, aVsmmhostaccess_0; "VsmmHostAccesspAcquire"
0x1400eaa35  lea     rcx, [rbp+170h+var_F0]
0x1400eaa3c  call    _tlgCreate1Sz_char
0x1400eaa41  lea     rdx, aOnecoreVmVidSy_33; "onecore\\vm\\vid\\sys\\vsmm\\vsmmhostac"...
0x1400eaa48  lea     rcx, [rbp+170h+var_E0]
0x1400eaa4f  call    _tlgCreate1Sz_char
0x1400eaa54  mov     dword ptr [rsp+270h+var_230], r9d
0x1400eaa59  lea     rax, [rsp+270h+var_228]
0x1400eaa5e  mov     r9, [rbp+170h+var_160]
0x1400eaa62  lea     rcx, [rsp+270h+var_230]
0x1400eaa67  mov     [rbp+170h+var_D0], rax
0x1400eaa6e  mov     [rsp+270h+var_228], 7A6h
0x1400eaa76  mov     [rbp+170h+var_C8], 4
0x1400eaa81  mov     [rbp+170h+var_C0], rcx
0x1400eaa88  mov     [rbp+170h+var_B8], 4
0x1400eaa93  mov     rax, [r9+8]
0x1400eaa97  add     rax, 290h
0x1400eaa9d  mov     [rbp+170h+var_A8], 10h
0x1400eaaa8  mov     [rbp+170h+var_B0], rax
0x1400eaaaf  mov     rax, [r9+8]
0x1400eaab3  movzx   edx, word ptr [rax+78h]
0x1400eaab7  mov     rcx, [rax+80h]
0x1400eaabe  lea     rax, [rbp+170h+var_88]
0x1400eaac5  mov     [rbp+170h+var_A0], rax
0x1400eaacc  mov     [rbp+170h+var_88], edx
0x1400eaad2  lea     rdx, word_14005C372
0x1400eaad9  mov     [rbp+170h+var_98], 2
0x1400eaae4  mov     [rbp+170h+var_90], rcx
0x1400eaaeb  mov     [rbp+170h+var_84], edi
0x1400eaaf1  mov     rax, [r9+8]
0x1400eaaf5  mov     rcx, [rax+288h]
0x1400eaafc  lea     rax, [rsp+270h+var_218]
0x1400eab01  mov     [rbp+170h+var_80], rax
0x1400eab08  lea     rax, [rsp+270h+var_210]
0x1400eab0d  mov     [rsp+270h+var_218], rcx
0x1400eab12  mov     [rsp+270h+var_210], rsi
0x1400eab17  mov     [rbp+170h+var_70], rax
0x1400eab1e  lea     rcx, dword_140065110
0x1400eab25  lea     rax, [rsp+270h+var_220]
0x1400eab2a  mov     [rsp+270h+var_220], r8d
0x1400eab2f  mov     [rbp+170h+var_60], rax
0x1400eab36  xor     r9d, r9d
0x1400eab39  lea     rax, [rbp+170h+var_110]
0x1400eab3d  mov     [rbp+170h+var_58], 8
0x1400eab48  mov     [rsp+270h+var_248], rax
0x1400eab4d  xor     r8d, r8d
0x1400eab50  mov     dword ptr [rsp+270h+var_250], 0Ch
0x1400eab58  mov     [rsp+270h+var_21C], r10d
0x1400eab5d  mov     [rbp+170h+var_68], 8
0x1400eab68  mov     [rbp+170h+var_78], 8
0x1400eab73  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400eab78  jmp     loc_1400EACDF
0x1400eab7d  xor     edi, edi
0x1400eab7f  jmp     loc_1400EACB7
0x1400eab84  mov     eax, cs:dword_140065110
0x1400eab8a  mov     r9d, 0C000000Dh
0x1400eab90  mov     ebx, r9d
0x1400eab93  cmp     eax, 2
0x1400eab96  jbe     loc_1400EACDF
0x1400eab9c  mov     edx, 100h
0x1400eaba1  lea     rcx, dword_140065110
0x1400eaba8  call    _tlgKeywordOn
0x1400eabad  test    al, al
0x1400eabaf  jz      loc_1400EACDF
0x1400eabb5  lea     rdx, aVsmmhostaccess_0; "VsmmHostAccesspAcquire"
0x1400eabbc  lea     rcx, [rbp+170h+var_F0]
0x1400eabc3  call    _tlgCreate1Sz_char
0x1400eabc8  lea     rdx, aOnecoreVmVidSy_33; "onecore\\vm\\vid\\sys\\vsmm\\vsmmhostac"...
0x1400eabcf  lea     rcx, [rbp+170h+var_E0]
0x1400eabd6  call    _tlgCreate1Sz_char
0x1400eabdb  mov     [rsp+270h+var_228], r9d
0x1400eabe0  lea     rax, [rsp+270h+var_230]
0x1400eabe5  mov     r9, [rbp+170h+var_160]
0x1400eabe9  lea     rcx, [rsp+270h+var_228]
0x1400eabee  mov     [rbp+170h+var_D0], rax
0x1400eabf5  mov     dword ptr [rsp+270h+var_230], 7C6h
0x1400eabfd  mov     [rbp+170h+var_C8], 4
0x1400eac08  mov     [rbp+170h+var_C0], rcx
0x1400eac0f  mov     [rbp+170h+var_B8], 4
0x1400eac1a  mov     rax, [r9+8]
0x1400eac1e  add     rax, 290h
0x1400eac24  mov     [rbp+170h+var_A8], 10h
0x1400eac2f  mov     [rbp+170h+var_B0], rax
0x1400eac36  mov     rax, [r9+8]
0x1400eac3a  movzx   edx, word ptr [rax+78h]
0x1400eac3e  mov     rcx, [rax+80h]
0x1400eac45  lea     rax, [rbp+170h+var_88]
0x1400eac4c  mov     [rbp+170h+var_A0], rax
0x1400eac53  mov     [rbp+170h+var_88], edx
0x1400eac59  lea     rdx, byte_14005C2ED
0x1400eac60  mov     [rbp+170h+var_98], 2
0x1400eac6b  mov     [rbp+170h+var_90], rcx
0x1400eac72  mov     [rbp+170h+var_84], edi
  ... truncated ...
```
