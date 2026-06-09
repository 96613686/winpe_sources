# VsmmHostAccessAcquireMbpRange

- ea: `0x1400e7534`
- end: `0x1400e7b7d`
- name: `VsmmHostAccessAcquireMbpRange`
- size: `1609`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int, int)`
- caller_count: `7`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x14002abc8`
- `0x1400750b0`
- `0x1400b99a0`
- `0x1400c876c`
- `0x1400ca2e0`
- `0x1400d1fa4`
- `0x1400e832c`

## callees

- `0x1400029c0`
- `0x1400030c0`
- `0x140006bd0`
- `0x140006bf8`
- `0x1400085b0`
- `0x14000a4e0`
- `0x140021650`
- `0x140021800`
- `0x14002e080`
- `0x140073030`
- `0x140073630`
- `0x140074d1c`
- `0x1400759c4`
- `0x1400e7534`
- `0x1400e98a4`
- `0x1400e9d1c`
- `0x1400edc70`
- `0x1400f5740`

## import_xrefs

- `winhvr!WinHvFlushCache` at `0x1400e7b2a`
- `winhvr!WinHvFlushCache` at `0x1400e7b2a`

## string_xrefs

- `0x1400e7821`: `onecore\vm\vid\sys\vsmm\vsmmhostaccess.c`
- `0x1400e799e`: `onecore\vm\vid\sys\vsmm\vsmmhostaccess.c`
- `0x1400e780e`: `VsmmHostAccesspAcquire`
- `0x1400e798b`: `VsmmHostAccesspAcquire`

## pseudocode

```c
__int64 __fastcall VsmmHostAccessAcquireMbpRange(__int64 a1, __int64 a2, __int64 a3, int a4, int a5)
{
  int v9; // eax
  unsigned __int64 v10; // rbx
  char v11; // r12
  __int64 v12; // r13
  unsigned int v13; // eax
  __int64 v14; // rcx
  __int64 v15; // r8
  int v16; // edi
  __int64 v17; // r14
  unsigned __int64 v18; // rsi
  __int64 *v19; // r8
  __int64 v20; // rcx
  unsigned int v21; // r8d
  unsigned int v22; // r8d
  unsigned int v23; // r8d
  __int64 BackingPage; // rbx
  unsigned __int64 v25; // rax
  int v26; // eax
  __int64 v27; // rdx
  __int64 v28; // rax
  __int64 v29; // rax
  int v30; // edx
  __int64 v31; // rcx
  __int64 v32; // rcx
  int v33; // r8d
  int v34; // r10d
  __int64 v35; // rax
  __int64 v36; // rax
  int v37; // edx
  __int64 v38; // rcx
  __int64 v39; // rcx
  int v40; // r8d
  int v41; // r10d
  __int64 v43; // [rsp+40h] [rbp-C0h] BYREF
  int v44; // [rsp+48h] [rbp-B8h] BYREF
  int v45; // [rsp+50h] [rbp-B0h] BYREF
  int v46; // [rsp+54h] [rbp-ACh]
  __int64 v47; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v48[2]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v49[30]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v50[32]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v51[16]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v52[16]; // [rsp+190h] [rbp+90h] BYREF
  int *v53; // [rsp+1A0h] [rbp+A0h]
  __int64 v54; // [rsp+1A8h] [rbp+A8h]
  int *v55; // [rsp+1B0h] [rbp+B0h]
  __int64 v56; // [rsp+1B8h] [rbp+B8h]
  __int64 v57; // [rsp+1C0h] [rbp+C0h]
  __int64 v58; // [rsp+1C8h] [rbp+C8h]
  int *v59; // [rsp+1D0h] [rbp+D0h]
  __int64 v60; // [rsp+1D8h] [rbp+D8h]
  __int64 v61; // [rsp+1E0h] [rbp+E0h]
  int v62; // [rsp+1E8h] [rbp+E8h] BYREF
  int v63; // [rsp+1ECh] [rbp+ECh]
  __int64 *v64; // [rsp+1F0h] [rbp+F0h]
  __int64 v65; // [rsp+1F8h] [rbp+F8h]
  __int64 *v66; // [rsp+200h] [rbp+100h]
  __int64 v67; // [rsp+208h] [rbp+108h]
  int *v68; // [rsp+210h] [rbp+110h]
  __int64 v69; // [rsp+218h] [rbp+118h]

  memset(v49, 0, 0xE8u);
  VsmmHostAccesspAcquireContextInitialize((__int64)v49, 0, a1, a4, a3, a5, 0);
  v9 = *(_BYTE *)(a1 + 20) & 1;
  v49[25] = a2;
  v10 = 0;
  LODWORD(v49[26]) = v9;
  v43 = 0;
  v11 = VsmmHostAccesspAcqRelBySpa(v49);
  v12 = *(_QWORD *)(v49[20] + 8LL);
  v13 = VsmmHostAccessMinimumForMemoryBlock();
  if ( (char)VsmmHostAccessCompare(LODWORD(v49[2]), v13) <= 0 )
    goto LABEL_2;
  v17 = 0;
  if ( !v49[21] )
  {
LABEL_45:
    v16 = VsmmHostAccesspAcqRelFlush(v49);
    if ( v16 < 0 )
    {
LABEL_46:
      if ( !v11 )
        goto LABEL_47;
      goto LABEL_50;
    }
LABEL_2:
    v16 = v10;
    goto LABEL_50;
  }
  while ( 1 )
  {
    v18 = v17 + a2;
    v14 = *(_QWORD *)(v49[20] + 256LL);
    if ( (*(_DWORD *)(v49[20] + 20LL) & 8) != 0 )
      v19 = (__int64 *)(v14 + 8 * v18);
    else
      v19 = (__int64 *)(v14 + 16 * v18 + 8);
    v15 = *v19;
    if ( v11 )
    {
      if ( (v15 & 0xF) != 1 )
      {
        v16 = -1073741811;
        if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
        {
          tlgCreate1Sz_char(v51, "VsmmHostAccesspAcquire");
          tlgCreate1Sz_char(v52, "onecore\\vm\\vid\\sys\\vsmm\\vsmmhostaccess.c");
          v53 = &v44;
          v55 = (int *)&v43;
          v44 = 2023;
          v54 = 4;
          LODWORD(v43) = -1073741811;
          v56 = 4;
          v28 = *(_QWORD *)(v49[20] + 8LL) + 656LL;
          v58 = 16;
          v57 = v28;
          v29 = *(_QWORD *)(v49[20] + 8LL);
          v30 = *(unsigned __int16 *)(v29 + 120);
          v31 = *(_QWORD *)(v29 + 128);
          v59 = &v62;
          v61 = v31;
          v62 = v30;
          v60 = 2;
          v63 = v10;
          v32 = *(_QWORD *)(*(_QWORD *)(v49[20] + 8LL) + 648LL);
          v64 = &v47;
          v66 = v48;
          v68 = &v45;
          v47 = v32;
          v45 = v33;
          v65 = 8;
          v48[0] = v17 + a2;
          v67 = 8;
          v46 = v34;
          v69 = 8;
          tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, byte_14005BC4B, 0, 0, 12, v50);
        }
        goto LABEL_50;
      }
      v20 = v49[20];
      v21 = v15 & 0xF;
      if ( v21 > 5 )
      {
        v22 = v21 - 6;
        if ( v22 )
        {
          v23 = v22 - 1;
          if ( !v23 || v23 - 1 >= 2 )
            goto LABEL_15;
        }
      }
      else if ( v21 != 1 )
      {
LABEL_15:
        LOBYTE(v20) = *(_BYTE *)(v49[20] + 240LL);
        BackingPage = VsmmNumaGetBackingPage(v20, 0);
        goto LABEL_22;
      }
      BackingPage = *(_QWORD *)(*(_QWORD *)(v49[20] + 256LL) + 16 * v18) & 0xFFFFFFFFFFLL;
      goto LABEL_22;
    }
    if ( (v15 & 0xF) == 0 )
      break;
    v10 = v49[27];
    if ( v49[27] )
    {
      v25 = *(_QWORD *)(v49[27] + 392LL);
      if ( v18 >= v25 && v18 <= v49[28] )
      {
        BackingPage = v18 + *(_QWORD *)(v49[27] + 256LL) - v25;
LABEL_22:
        v43 = BackingPage;
LABEL_30:
        v27 = v49[17];
        if ( v49[17] )
        {
          if ( BackingPage != v49[17] + v49[16] )
          {
            v16 = VsmmHostAccesspAcqRelCompleteRun((__int64)v49);
            if ( v16 < 0 )
            {
              v10 = 0;
              goto LABEL_46;
            }
            v27 = 0;
            goto LABEL_34;
          }
        }
        else
        {
LABEL_34:
          v49[16] = BackingPage;
        }
        v10 = 0;
        v49[17] = v27 + 1;
        goto LABEL_36;
      }
      v10 = 0;
      if ( (int)VsmmHostAccesspAcqRelFlush(v49) < 0 )
        goto LABEL_47;
      LOBYTE(v15) = 1;
      VsmmGpaRangeRelease(v14, v49[27], v15);
      v49[27] = 0;
    }
    v26 = VsmmGpaRangeLookupGpaByMbp(v12, v49[20], (int)v17 + (int)a2, v49[26], v10, (__int64)&v43, (__int64)&v49[27]);
    if ( v26 >= 0 )
    {
      BackingPage = v43;
      v49[28] = *(_QWORD *)(v49[27] + 272LL) + *(_QWORD *)(v49[27] + 392LL) - *(_QWORD *)(v49[27] + 256LL);
      goto LABEL_30;
    }
    if ( v26 != -1073741275 || (int)VsmmHostAccesspAcqRelFlush(v49) < 0 )
      goto LABEL_47;
    VsmmMbpHostAccessAcquire(v49[20], v17 + a2, LODWORD(v49[2]));
    ++v49[24];
LABEL_36:
    if ( (unsigned __int64)++v17 >= v49[21] )
      goto LABEL_45;
    a2 = v49[25];
  }
  if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
  {
    tlgCreate1Sz_char(v51, "VsmmHostAccesspAcquire");
    tlgCreate1Sz_char(v52, "onecore\\vm\\vid\\sys\\vsmm\\vsmmhostaccess.c");
    v53 = (int *)&v43;
    v55 = &v44;
    LODWORD(v43) = 2055;
    v54 = 4;
    v44 = -1073741811;
    v56 = 4;
    v35 = *(_QWORD *)(v49[20] + 8LL) + 656LL;
    v58 = 16;
    v57 = v35;
    v36 = *(_QWORD *)(v49[20] + 8LL);
    v37 = *(unsigned __int16 *)(v36 + 120);
    v38 = *(_QWORD *)(v36 + 128);
    v59 = &v62;
    v61 = v38;
    v62 = v37;
    v60 = 2;
    v63 = v10;
    v39 = *(_QWORD *)(*(_QWORD *)(v49[20] + 8LL) + 648LL);
    v64 = v48;
    v66 = &v47;
    v68 = &v45;
    v48[0] = v39;
    v45 = v40;
    v65 = 8;
    v47 = v17 + a2;
    v67 = 8;
    v46 = v41;
    v69 = 8;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, qword_14005BCD0, 0, 0, 12, v50);
  }
LABEL_47:
  v16 = -1070137302;
  if ( v49[23] != v10 && (unsigned __int8)VsmmHostAccessCompare(LODWORD(v49[2]), 0) == 1 )
    VsmmHostAccesspCheckVtlAccessInjectIntercept(v49);
LABEL_50:
  if ( v49[24] > v10 && (v49[22] & 1) != 0 && (*(_BYTE *)(v12 + 40) & 0x10) != 0 )
    WinHvFlushCache();
  if ( LODWORD(v49[19]) <= 1 && v49[27] )
  {
    LOBYTE(v15) = 1;
    VsmmGpaRangeRelease(v14, v49[27], v15);
  }
  VsmmHostAccesspAcqRelContextDestroy(v49);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x1400e7534  push    rbp
0x1400e7536  push    rbx
0x1400e7537  push    rsi
0x1400e7538  push    rdi
0x1400e7539  push    r12
0x1400e753b  push    r13
0x1400e753d  push    r14
0x1400e753f  push    r15
0x1400e7541  lea     rbp, [rsp-138h]
0x1400e7549  sub     rsp, 238h
0x1400e7550  mov     rax, cs:__security_cookie
0x1400e7557  xor     rax, rsp
0x1400e755a  mov     [rbp+170h+var_50], rax
0x1400e7561  mov     rbx, r8
0x1400e7564  mov     r15, rdx
0x1400e7567  mov     rsi, rcx
0x1400e756a  xor     edx, edx; Val
0x1400e756c  mov     r8d, 0E8h; Size
0x1400e7572  lea     rcx, [rsp+270h+var_200]; void *
0x1400e7577  mov     edi, r9d
0x1400e757a  call    memset
0x1400e757f  mov     eax, [rbp+170h+arg_20]
0x1400e7585  lea     rcx, [rsp+270h+var_200]
0x1400e758a  mov     [rsp+270h+var_240], 0
0x1400e7593  mov     r9d, edi
0x1400e7596  mov     dword ptr [rsp+270h+var_248], eax
0x1400e759a  mov     r8, rsi
0x1400e759d  xor     edx, edx
0x1400e759f  mov     [rsp+270h+var_250], rbx
0x1400e75a4  call    VsmmHostAccesspAcquireContextInitialize
0x1400e75a9  movzx   eax, byte ptr [rsi+14h]
0x1400e75ad  lea     rcx, [rsp+270h+var_200]
0x1400e75b2  and     eax, 1
0x1400e75b5  mov     [rbp+170h+var_138], r15
0x1400e75b9  xor     ebx, ebx
0x1400e75bb  mov     [rbp+170h+var_130], eax
0x1400e75be  mov     [rsp+270h+var_230], rbx
0x1400e75c3  call    VsmmHostAccesspAcqRelBySpa
0x1400e75c8  mov     rcx, [rbp+170h+var_160]
0x1400e75cc  mov     r12b, al
0x1400e75cf  mov     r13, [rcx+8]
0x1400e75d3  call    VsmmHostAccessMinimumForMemoryBlock
0x1400e75d8  mov     ecx, [rbp+170h+var_1F0]
0x1400e75db  mov     edx, eax
0x1400e75dd  call    VsmmHostAccessCompare
0x1400e75e2  test    al, al
0x1400e75e4  jg      short loc_1400E75ED
0x1400e75e6  mov     edi, ebx
0x1400e75e8  jmp     loc_1400E7B17
0x1400e75ed  mov     r14, rbx
0x1400e75f0  cmp     [rbp+170h+var_158], rbx
0x1400e75f4  jbe     loc_1400E7ADB
0x1400e75fa  mov     rax, [rbp+170h+var_160]
0x1400e75fe  lea     rsi, [r14+r15]
0x1400e7602  mov     r11d, 8
0x1400e7608  mov     rcx, [rax+100h]
0x1400e760f  mov     eax, [rax+14h]
0x1400e7612  test    r11b, al
0x1400e7615  jnz     short loc_1400E7627
0x1400e7617  mov     r8, rsi
0x1400e761a  shl     r8, 4
0x1400e761e  add     r8, 8
0x1400e7622  add     r8, rcx
0x1400e7625  jmp     short loc_1400E762B
0x1400e7627  lea     r8, [rcx+rsi*8]
0x1400e762b  mov     r8, [r8]
0x1400e762e  mov     r10, r8
0x1400e7631  mov     rax, r8
0x1400e7634  shr     r10, 20h
0x1400e7638  and     eax, 0Fh
0x1400e763b  test    r12b, r12b
0x1400e763e  jz      short loc_1400E76B0
0x1400e7640  cmp     rax, 1
0x1400e7644  jnz     loc_1400E77E1
0x1400e764a  mov     rcx, [rbp+170h+var_160]
0x1400e764e  and     r8d, 0Fh
0x1400e7652  cmp     r8d, 5
0x1400e7656  ja      short loc_1400E7669
0x1400e7658  jz      short loc_1400E7681
0x1400e765a  test    r8d, r8d
0x1400e765d  jz      short loc_1400E7681
0x1400e765f  sub     r8d, eax
0x1400e7662  jz      short loc_1400E7693
0x1400e7664  sub     r8d, eax
0x1400e7667  jmp     short loc_1400E7681
0x1400e7669  sub     r8d, 6
0x1400e766d  jz      short loc_1400E7693
0x1400e766f  sub     r8d, 1
0x1400e7673  jz      short loc_1400E7681
0x1400e7675  sub     r8d, 1
0x1400e7679  jz      short loc_1400E7693
0x1400e767b  cmp     r8d, 1
0x1400e767f  jz      short loc_1400E7693
0x1400e7681  mov     cl, [rcx+0F0h]
0x1400e7687  xor     edx, edx
0x1400e7689  call    VsmmNumaGetBackingPage
0x1400e768e  mov     rbx, rax
0x1400e7691  jmp     short loc_1400E76E1
0x1400e7693  mov     rax, [rcx+100h]
0x1400e769a  add     rsi, rsi
0x1400e769d  mov     rbx, [rax+rsi*8]
0x1400e76a1  mov     rax, 0FFFFFFFFFFh
0x1400e76ab  and     rbx, rax
0x1400e76ae  jmp     short loc_1400E76E1
0x1400e76b0  test    rax, rax
0x1400e76b3  jz      loc_1400E7963
0x1400e76b9  mov     rbx, [rbp+170h+var_128]
0x1400e76bd  test    rbx, rbx
0x1400e76c0  jz      short loc_1400E770F
0x1400e76c2  mov     rax, [rbx+188h]
0x1400e76c9  cmp     rsi, rax
0x1400e76cc  jb      short loc_1400E76EB
0x1400e76ce  cmp     rsi, [rbp+170h+var_120]
0x1400e76d2  ja      short loc_1400E76EB
0x1400e76d4  mov     rbx, [rbx+100h]
0x1400e76db  sub     rbx, rax
0x1400e76de  add     rbx, rsi
0x1400e76e1  mov     [rsp+270h+var_230], rbx
0x1400e76e6  jmp     loc_1400E7792
0x1400e76eb  lea     rcx, [rsp+270h+var_200]
0x1400e76f0  call    VsmmHostAccesspAcqRelFlush
0x1400e76f5  xor     ebx, ebx
0x1400e76f7  test    eax, eax
0x1400e76f9  js      loc_1400E7AF4
0x1400e76ff  mov     rdx, [rbp+170h+var_128]
0x1400e7703  mov     r8b, 1
0x1400e7706  call    VsmmGpaRangeRelease
0x1400e770b  mov     [rbp+170h+var_128], rbx
0x1400e770f  mov     r9d, [rbp+170h+var_130]
0x1400e7713  lea     rax, [rbp+170h+var_128]
0x1400e7717  mov     rdx, [rbp+170h+var_160]
0x1400e771b  mov     r8, rsi
0x1400e771e  mov     [rsp+270h+var_240], rax
0x1400e7723  mov     rcx, r13
0x1400e7726  lea     rax, [rsp+270h+var_230]
0x1400e772b  mov     [rsp+270h+var_248], rax
0x1400e7730  mov     dword ptr [rsp+270h+var_250], ebx
0x1400e7734  call    VsmmGpaRangeLookupGpaByMbp
0x1400e7739  test    eax, eax
0x1400e773b  jns     short loc_1400E7770
0x1400e773d  cmp     eax, 0C0000225h
0x1400e7742  jnz     loc_1400E7AF4
0x1400e7748  lea     rcx, [rsp+270h+var_200]
0x1400e774d  call    VsmmHostAccesspAcqRelFlush
0x1400e7752  test    eax, eax
0x1400e7754  js      loc_1400E7AF4
0x1400e775a  mov     r8d, [rbp+170h+var_1F0]
0x1400e775e  mov     rdx, rsi
0x1400e7761  mov     rcx, [rbp+170h+var_160]
0x1400e7765  call    VsmmMbpHostAccessAcquire
0x1400e776a  inc     [rbp+170h+var_140]
0x1400e776e  jmp     short loc_1400E77CB
0x1400e7770  mov     rdx, [rbp+170h+var_128]
0x1400e7774  mov     rbx, [rsp+270h+var_230]
0x1400e7779  mov     rcx, [rdx+188h]
0x1400e7780  sub     rcx, [rdx+100h]
0x1400e7787  add     rcx, [rdx+110h]
0x1400e778e  mov     [rbp+170h+var_120], rcx
0x1400e7792  mov     rdx, [rbp+170h+var_178]
0x1400e7796  test    rdx, rdx
0x1400e7799  jz      short loc_1400E77BD
0x1400e779b  mov     rcx, [rbp+170h+var_180]
0x1400e779f  add     rcx, rdx
0x1400e77a2  cmp     rbx, rcx
0x1400e77a5  jz      short loc_1400E77C1
0x1400e77a7  lea     rcx, [rsp+270h+var_200]
0x1400e77ac  call    VsmmHostAccesspAcqRelCompleteRun
0x1400e77b1  mov     edi, eax
0x1400e77b3  test    eax, eax
0x1400e77b5  js      loc_1400E795C
0x1400e77bb  xor     edx, edx
0x1400e77bd  mov     [rbp+170h+var_180], rbx
0x1400e77c1  lea     rax, [rdx+1]
0x1400e77c5  xor     ebx, ebx
0x1400e77c7  mov     [rbp+170h+var_178], rax
0x1400e77cb  inc     r14
0x1400e77ce  cmp     r14, [rbp+170h+var_158]
0x1400e77d2  jnb     loc_1400E7ADB
0x1400e77d8  mov     r15, [rbp+170h+var_138]
0x1400e77dc  jmp     loc_1400E75FA
0x1400e77e1  mov     eax, cs:dword_140064110
0x1400e77e7  mov     edi, 0C000000Dh
0x1400e77ec  cmp     eax, 2
0x1400e77ef  jbe     loc_1400E7B17
0x1400e77f5  mov     edx, 100h
0x1400e77fa  lea     rcx, dword_140064110
0x1400e7801  call    _tlgKeywordOn
0x1400e7806  test    al, al
0x1400e7808  jz      loc_1400E7B17
0x1400e780e  lea     rdx, aVsmmhostaccess_0; "VsmmHostAccesspAcquire"
0x1400e7815  lea     rcx, [rbp+170h+var_F0]
0x1400e781c  call    _tlgCreate1Sz_char
0x1400e7821  lea     rdx, aOnecoreVmVidSy_33; "onecore\\vm\\vid\\sys\\vsmm\\vsmmhostac"...
0x1400e7828  lea     rcx, [rbp+170h+var_E0]
0x1400e782f  call    _tlgCreate1Sz_char
0x1400e7834  mov     r9, [rbp+170h+var_160]
0x1400e7838  lea     rax, [rsp+270h+var_228]
0x1400e783d  mov     [rbp+170h+var_D0], rax
0x1400e7844  lea     rcx, [rsp+270h+var_230]
0x1400e7849  mov     [rbp+170h+var_C0], rcx
0x1400e7850  mov     [rsp+270h+var_228], 7E7h
0x1400e7858  mov     [rbp+170h+var_C8], 4
0x1400e7863  mov     dword ptr [rsp+270h+var_230], edi
0x1400e7867  mov     [rbp+170h+var_B8], 4
0x1400e7872  mov     rax, [r9+8]
0x1400e7876  add     rax, 290h
0x1400e787c  mov     [rbp+170h+var_A8], 10h
0x1400e7887  mov     [rbp+170h+var_B0], rax
0x1400e788e  mov     rax, [r9+8]
0x1400e7892  movzx   edx, word ptr [rax+78h]
0x1400e7896  mov     rcx, [rax+80h]
0x1400e789d  lea     rax, [rbp+170h+var_88]
0x1400e78a4  mov     [rbp+170h+var_A0], rax
0x1400e78ab  mov     [rbp+170h+var_90], rcx
0x1400e78b2  mov     [rbp+170h+var_88], edx
0x1400e78b8  lea     rdx, byte_14005BC4B
0x1400e78bf  mov     [rbp+170h+var_98], 2
0x1400e78ca  mov     [rbp+170h+var_84], ebx
0x1400e78d0  mov     rax, [r9+8]
0x1400e78d4  xor     r9d, r9d
0x1400e78d7  mov     rcx, [rax+288h]
0x1400e78de  lea     rax, [rsp+270h+var_218]
0x1400e78e3  mov     [rbp+170h+var_80], rax
0x1400e78ea  lea     rax, [rsp+270h+var_210]
0x1400e78ef  mov     [rbp+170h+var_70], rax
0x1400e78f6  lea     rax, [rsp+270h+var_220]
0x1400e78fb  mov     [rbp+170h+var_60], rax
0x1400e7902  lea     rax, [rbp+170h+var_110]
0x1400e7906  mov     [rsp+270h+var_218], rcx
0x1400e790b  lea     rcx, dword_140064110
0x1400e7912  mov     [rsp+270h+var_220], r8d
0x1400e7917  xor     r8d, r8d
0x1400e791a  mov     [rsp+270h+var_248], rax
0x1400e791f  mov     dword ptr [rsp+270h+var_250], 0Ch
0x1400e7927  mov     [rbp+170h+var_78], 8
0x1400e7932  mov     [rsp+270h+var_210], rsi
0x1400e7937  mov     [rbp+170h+var_68], 8
0x1400e7942  mov     [rsp+270h+var_21C], r10d
0x1400e7947  mov     [rbp+170h+var_58], 8
0x1400e7952  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400e7957  jmp     loc_1400E7B17
0x1400e795c  xor     ebx, ebx
0x1400e795e  jmp     loc_1400E7AEF
0x1400e7963  mov     eax, cs:dword_140064110
0x1400e7969  cmp     eax, 2
0x1400e796c  jbe     loc_1400E7AF4
0x1400e7972  mov     edx, 100h
0x1400e7977  lea     rcx, dword_140064110
0x1400e797e  call    _tlgKeywordOn
0x1400e7983  test    al, al
0x1400e7985  jz      loc_1400E7AF4
0x1400e798b  lea     rdx, aVsmmhostaccess_0; "VsmmHostAccesspAcquire"
0x1400e7992  lea     rcx, [rbp+170h+var_F0]
0x1400e7999  call    _tlgCreate1Sz_char
0x1400e799e  lea     rdx, aOnecoreVmVidSy_33; "onecore\\vm\\vid\\sys\\vsmm\\vsmmhostac"...
0x1400e79a5  lea     rcx, [rbp+170h+var_E0]
0x1400e79ac  call    _tlgCreate1Sz_char
0x1400e79b1  mov     r9, [rbp+170h+var_160]
0x1400e79b5  lea     rax, [rsp+270h+var_230]
0x1400e79ba  mov     [rbp+170h+var_D0], rax
0x1400e79c1  lea     rcx, [rsp+270h+var_228]
0x1400e79c6  mov     [rbp+170h+var_C0], rcx
0x1400e79cd  mov     edi, 0C000000Dh
0x1400e79d2  mov     dword ptr [rsp+270h+var_230], 807h
0x1400e79da  mov     [rbp+170h+var_C8], 4
0x1400e79e5  mov     [rsp+270h+var_228], edi
0x1400e79e9  mov     [rbp+170h+var_B8], 4
0x1400e79f4  mov     rax, [r9+8]
0x1400e79f8  add     rax, 290h
0x1400e79fe  mov     [rbp+170h+var_A8], 10h
0x1400e7a09  mov     [rbp+170h+var_B0], rax
0x1400e7a10  mov     rax, [r9+8]
0x1400e7a14  movzx   edx, word ptr [rax+78h]
0x1400e7a18  mov     rcx, [rax+80h]
0x1400e7a1f  lea     rax, [rbp+170h+var_88]
0x1400e7a26  mov     [rbp+170h+var_A0], rax
0x1400e7a2d  mov     [rbp+170h+var_90], rcx
0x1400e7a34  mov     [rbp+170h+var_88], edx
0x1400e7a3a  lea     rdx, qword_14005BCD0
0x1400e7a41  mov     [rbp+170h+var_98], 2
0x1400e7a4c  mov     [rbp+170h+var_84], ebx
0x1400e7a52  mov     rax, [r9+8]
0x1400e7a56  xor     r9d, r9d
0x1400e7a59  mov     rcx, [rax+288h]
0x1400e7a60  lea     rax, [rsp+270h+var_210]
0x1400e7a65  mov     [rbp+170h+var_80], rax
0x1400e7a6c  lea     rax, [rsp+270h+var_218]
0x1400e7a71  mov     [rbp+170h+var_70], rax
0x1400e7a78  lea     rax, [rsp+270h+var_220]
0x1400e7a7d  mov     [rbp+170h+var_60], rax
0x1400e7a84  lea     rax, [rbp+170h+var_110]
0x1400e7a88  mov     [rsp+270h+var_210], rcx
0x1400e7a8d  lea     rcx, dword_140064110
0x1400e7a94  mov     [rsp+270h+var_220], r8d
0x1400e7a99  xor     r8d, r8d
0x1400e7a9c  mov     [rsp+270h+var_248], rax
0x1400e7aa1  mov     dword ptr [rsp+270h+var_250], 0Ch
0x1400e7aa9  mov     [rbp+170h+var_78], 8
0x1400e7ab4  mov     [rsp+270h+var_218], rsi
0x1400e7ab9  mov     [rbp+170h+var_68], 8
  ... truncated ...
```
