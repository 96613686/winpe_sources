# VsmmPhuStoreHvPartitionRestore

- ea: `0x1400b1a24`
- end: `0x1400b2310`
- name: `VsmmPhuStoreHvPartitionRestore`
- size: `2284`
- prototype: `__int64 __fastcall(__int64, int *, __int128 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x14008d084`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x14000a4e0`
- `0x140021650`
- `0x140022010`
- `0x14002f524`
- `0x14009e0d8`
- `0x1400ad2cc`
- `0x1400b1a24`
- `0x1400b5658`

## import_xrefs

- `winhvr!WinHvGetPartitionProperty` at `0x1400b2088`
- `winhvr!WinHvGetPartitionProperty` at `0x1400b2088`
- `winhvr!WinHvCreatePartition` at `0x1400b2100`
- `winhvr!WinHvCreatePartition` at `0x1400b2100`
- `winhvr!WinHvSetInterceptRoutine` at `0x1400b22ab`
- `winhvr!WinHvSetInterceptRoutine` at `0x1400b22ab`
- `winhvr!WinHvSetLowMemoryPolicyRoutine` at `0x1400b22c8`
- `winhvr!WinHvSetLowMemoryPolicyRoutine` at `0x1400b22c8`

## pseudocode

```c
__int64 __fastcall VsmmPhuStoreHvPartitionRestore(__int64 a1, int *a2, __int128 *a3)
{
  __int128 v3; // xmm1
  int v4; // eax
  __int128 v8; // xmm0
  unsigned __int64 v9; // rbx
  __int64 v10; // rax
  __int64 v11; // r9
  __int64 v12; // rdx
  __int64 v13; // r9
  unsigned __int64 v14; // r15
  __int64 v15; // rcx
  unsigned int v16; // r14d
  __int64 v17; // r9
  __int64 v18; // r8
  int v19; // eax
  __int64 v20; // r8
  int PartitionProperty; // eax
  __int64 v22; // rdx
  int v23; // r11d
  int v25; // [rsp+50h] [rbp-B0h] BYREF
  int v26; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v27; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v28; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v29; // [rsp+68h] [rbp-98h] BYREF
  __int64 v30; // [rsp+70h] [rbp-90h] BYREF
  int v31; // [rsp+78h] [rbp-88h] BYREF
  int v32; // [rsp+7Ch] [rbp-84h] BYREF
  int v33; // [rsp+80h] [rbp-80h] BYREF
  int v34; // [rsp+84h] [rbp-7Ch] BYREF
  int v35; // [rsp+88h] [rbp-78h] BYREF
  int v36; // [rsp+8Ch] [rbp-74h] BYREF
  int v37; // [rsp+90h] [rbp-70h] BYREF
  int v38; // [rsp+94h] [rbp-6Ch] BYREF
  unsigned __int64 v39; // [rsp+98h] [rbp-68h] BYREF
  __int128 Buf2; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v41; // [rsp+B0h] [rbp-50h]
  __int128 v42; // [rsp+C0h] [rbp-40h]
  __int64 v43; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v44; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v45; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v46; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v47; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v48; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v49; // [rsp+100h] [rbp+0h] BYREF
  __int64 v50; // [rsp+108h] [rbp+8h] BYREF
  __int64 v51; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int64 v52; // [rsp+118h] [rbp+18h] BYREF
  __int128 v53; // [rsp+120h] [rbp+20h] BYREF
  __int128 v54; // [rsp+130h] [rbp+30h] BYREF
  __int64 v55; // [rsp+140h] [rbp+40h]
  _BYTE v56[32]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v57[16]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v58[16]; // [rsp+180h] [rbp+80h] BYREF
  int *v59; // [rsp+190h] [rbp+90h]
  __int64 v60; // [rsp+198h] [rbp+98h]
  int *v61; // [rsp+1A0h] [rbp+A0h]
  __int64 v62; // [rsp+1A8h] [rbp+A8h]
  __int64 *v63; // [rsp+1B0h] [rbp+B0h]
  __int64 v64; // [rsp+1B8h] [rbp+B8h]
  __int64 *v65; // [rsp+1C0h] [rbp+C0h]
  __int64 v66; // [rsp+1C8h] [rbp+C8h]
  int *v67; // [rsp+1D0h] [rbp+D0h]
  __int64 v68; // [rsp+1D8h] [rbp+D8h] BYREF
  __int64 *v69; // [rsp+1E0h] [rbp+E0h]
  __int64 v70; // [rsp+1E8h] [rbp+E8h]
  __int64 *v71; // [rsp+1F0h] [rbp+F0h]
  __int64 v72; // [rsp+1F8h] [rbp+F8h]
  __int64 *v73; // [rsp+200h] [rbp+100h]
  __int64 v74; // [rsp+208h] [rbp+108h]
  unsigned __int64 *v75; // [rsp+210h] [rbp+110h]
  __int64 v76; // [rsp+218h] [rbp+118h]
  __int64 *v77; // [rsp+220h] [rbp+120h]
  __int64 v78; // [rsp+228h] [rbp+128h]
  __int64 *v79; // [rsp+230h] [rbp+130h]
  __int64 v80; // [rsp+238h] [rbp+138h]
  int *v81; // [rsp+240h] [rbp+140h]
  __int64 v82; // [rsp+248h] [rbp+148h]
  int *v83; // [rsp+250h] [rbp+150h]
  __int64 v84; // [rsp+258h] [rbp+158h]
  __int64 *v85; // [rsp+260h] [rbp+160h]
  __int64 v86; // [rsp+268h] [rbp+168h]
  __int64 *v87; // [rsp+270h] [rbp+170h]
  __int64 v88; // [rsp+278h] [rbp+178h]
  int *v89; // [rsp+280h] [rbp+180h]
  __int64 v90; // [rsp+288h] [rbp+188h]
  int *v91; // [rsp+290h] [rbp+190h]
  __int64 v92; // [rsp+298h] [rbp+198h]
  __int64 *v93; // [rsp+2A0h] [rbp+1A0h]
  __int64 v94; // [rsp+2A8h] [rbp+1A8h]
  unsigned __int64 *v95; // [rsp+2B0h] [rbp+1B0h]
  __int64 v96; // [rsp+2B8h] [rbp+1B8h]
  unsigned __int64 *v97; // [rsp+2C0h] [rbp+1C0h]
  __int64 v98; // [rsp+2C8h] [rbp+1C8h]
  __int64 *v99; // [rsp+2D0h] [rbp+1D0h]
  __int64 v100; // [rsp+2D8h] [rbp+1D8h]
  __int128 *v101; // [rsp+2E0h] [rbp+1E0h]
  __int64 v102; // [rsp+2E8h] [rbp+1E8h]
  char *v103; // [rsp+2F0h] [rbp+1F0h]
  __int64 v104; // [rsp+2F8h] [rbp+1F8h]
  __int64 *v105; // [rsp+300h] [rbp+200h]
  __int64 v106; // [rsp+308h] [rbp+208h]
  __int64 *v107; // [rsp+310h] [rbp+210h]
  __int64 v108; // [rsp+318h] [rbp+218h]
  __int64 *v109; // [rsp+320h] [rbp+220h]
  __int64 v110; // [rsp+328h] [rbp+228h]

  v3 = a3[1];
  v55 = 0;
  v4 = *a2;
  v54 = 0;
  v27 = 0;
  v8 = *a3;
  v41 = v3;
  Buf2 = v8;
  v42 = a3[2];
  if ( (*(_QWORD *)&v4 & 0x800000LL) != 0 )
    v9 = v8 | 0x800000;
  else
    v9 = v8 & 0xFFFFFFFFFF7FFFFFuLL;
  v10 = (unsigned int)a2[3];
  v11 = (unsigned int)a2[9];
  v12 = 0;
  v13 = v10 | (v11 << 32);
  *(_QWORD *)&Buf2 = v9;
  v14 = HIDWORD(*((_QWORD *)&Buf2 + 1)) | ((unsigned __int64)DWORD1(v42) << 32);
  do
  {
    v15 = qword_140040740[v12];
    if ( (v13 & v15) != (v14 & v15) )
    {
      if ( (v13 & v15) != 0 )
        v14 |= v15;
      else
        v14 &= ~v15;
    }
    ++v12;
  }
  while ( v12 != 9 );
  v16 = -1070137295;
  if ( v14 != (HIDWORD(*((_QWORD *)&Buf2 + 1)) | ((unsigned __int64)DWORD1(v42) << 32))
    && (unsigned int)dword_140064110 > 2
    && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
  {
    tlgCreate1Sz_char(v57, "VsmmPhuStoreHvPartitionRestore");
    tlgCreate1Sz_char(v58, "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c");
    v29 = v17;
    v59 = &v25;
    v28 = v18;
    v61 = &v26;
    v25 = 3549;
    v63 = (__int64 *)(a1 + 656);
    v60 = 4;
    v65 = &v68;
    v67 = *(int **)(a1 + 128);
    v68 = *(unsigned __int16 *)(a1 + 120);
    v30 = *(_QWORD *)(a1 + 648);
    v69 = &v30;
    v71 = &v29;
    v73 = &v28;
    v75 = &v39;
    v26 = -1070137295;
    v62 = 4;
    v64 = 16;
    v66 = 2;
    v70 = 8;
    v72 = 8;
    v74 = 8;
    v39 = v14;
    v76 = 8;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, &word_14004FC0E, 0, 0, 13, v56);
  }
  v19 = *(_DWORD *)(a1 + 32);
  DWORD1(v42) = HIDWORD(v14);
  HIDWORD(Buf2) = v14;
  if ( (v19 & 0x1E0) != 0 )
  {
    if ( (*a2 & 0x800LL) != 0 )
      v9 |= 0x800u;
    else
      v9 &= ~0x800uLL;
    *(_QWORD *)&Buf2 = v9;
  }
  if ( (*(_BYTE *)(a1 + 16) & 0x20) != 0 )
  {
    if ( (*a2 & 0x10000000) != 0 )
      v9 |= 0x10000000u;
    else
      v9 &= ~0x10000000uLL;
    *(_QWORD *)&Buf2 = v9;
  }
  if ( memcmp(a2, &Buf2, 0x30u) )
  {
    if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
    {
      tlgCreate1Sz_char(v57, "VsmmPhuStoreHvPartitionRestore");
      tlgCreate1Sz_char(v58, "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c");
      v26 = 3625;
      v59 = &v26;
      v61 = &v25;
      v44 = *(_QWORD *)a2;
      v63 = &v44;
      v31 = a2[2];
      v65 = (__int64 *)&v31;
      v32 = a2[3];
      v67 = &v32;
      v45 = *((_QWORD *)a2 + 2);
      v69 = &v45;
      v46 = *((_QWORD *)a2 + 3);
      v71 = &v46;
      v33 = a2[8];
      v73 = (__int64 *)&v33;
      v34 = a2[9];
      v75 = (unsigned __int64 *)&v34;
      v47 = *((_QWORD *)a2 + 5);
      v77 = &v47;
      v48 = *(_QWORD *)a3;
      v79 = &v48;
      v35 = *((_DWORD *)a3 + 2);
      v81 = &v35;
      v36 = *((_DWORD *)a3 + 3);
      v83 = &v36;
      v49 = *((_QWORD *)a3 + 2);
      v85 = &v49;
      v50 = *((_QWORD *)a3 + 3);
      v87 = &v50;
      v37 = *((_DWORD *)a3 + 8);
      v89 = &v37;
      v38 = *((_DWORD *)a3 + 9);
      v60 = 4;
      v25 = -1070137295;
      v62 = 4;
      v64 = 8;
      v66 = 4;
      v68 = 4;
      v70 = 8;
      v72 = 8;
      v74 = 4;
      v76 = 4;
      v78 = 8;
      v80 = 8;
      v82 = 4;
      v84 = 4;
      v86 = 8;
      v88 = 8;
      v90 = 4;
      v91 = &v38;
      v51 = *((_QWORD *)a3 + 5);
      v93 = &v51;
      v95 = &v52;
      LODWORD(v39) = DWORD2(Buf2);
      v97 = &v39;
      v99 = &v28;
      v53 = v41;
      v101 = &v53;
      v103 = (char *)&v53 + 8;
      LODWORD(v29) = v42;
      v105 = &v29;
      v107 = &v30;
      v43 = *((_QWORD *)&v42 + 1);
      v109 = &v43;
      v92 = 4;
      v94 = 8;
      v52 = v9;
      v96 = 8;
      v98 = 4;
      LODWORD(v28) = v14;
      v100 = 4;
      v102 = 8;
      v104 = 8;
      v106 = 4;
      LODWORD(v30) = HIDWORD(v14);
      v108 = 4;
      v110 = 8;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, word_14004F89A, v20, 0, 30, v56);
    }
    return v16;
  }
  v27 = 0;
  PartitionProperty = WinHvGetPartitionProperty(*((_QWORD *)a2 + 7), 327701, &v27);
  v16 = PartitionProperty;
  if ( PartitionProperty < 0 )
  {
    if ( PartitionProperty != -1070268386 )
    {
      VidTraceErrorStatusInternal0(
        "VsmmPhuStoreHvPartitionRestore",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
        3648);
      return v16;
    }
    v27 = 0;
    goto LABEL_31;
  }
  if ( !v27 )
  {
LABEL_31:
    VsmmPhuStorepCreationPropertiesDeserialize(a2, &v54);
    v16 = WinHvCreatePartition(
            *(_QWORD *)a2,
            4,
            0x80000000LL,
            (unsigned int)a2[2],
            &v54,
            a2 + 14,
            VsmmPhuStorepHvPartitionInactiveInterceptRoutine,
            0,
            VsmmPhuStorepHvPartitionInactiveLowMemoryPolicyRoutine,
            0);
    if ( (v16 & 0x80000000) == 0 )
    {
      *(_QWORD *)(a1 + 648) = *((_QWORD *)a2 + 7);
      *(_BYTE *)(a1 + 3221) = (*((_BYTE *)a2 + 49) & 4) != 0;
      *(_BYTE *)(a1 + 8761) = *((_BYTE *)a2 + 49) & 1;
      *(_BYTE *)(a1 + 8762) = (*((_BYTE *)a2 + 49) & 2) != 0;
      *(_QWORD *)(a1 + 8768) = *((_QWORD *)a2 + 13);
      VsmmVsmSetPartitionConfig(a1, v22, a2 + 16);
      WinHvSetInterceptRoutine(*(_QWORD *)(a1 + 648), VidInterceptIsrCallback, a1);
      WinHvSetLowMemoryPolicyRoutine(*(_QWORD *)(a1 + 648), VidHvMemLowMemPolicyCallback, a1);
      *((_BYTE *)a2 + 48) = 0;
      v16 = 0;
      *(_BYTE *)(a1 + 8760) = 1;
    }
    else
    {
      VidTraceErrorStatusInternal0(
        "VsmmPhuStoreHvPartitionRestore",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
        3691);
    }
    return v16;
  }
  while ( !(unsigned int)VsmmPartitionAttachDevice(a1) )
  {
    if ( !--v27 )
      goto LABEL_31;
  }
  v16 = -1073741637;
  if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
  {
    tlgCreate1Sz_char(v57, "VsmmPhuStoreHvPartitionRestore");
    tlgCreate1Sz_char(v58, "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c");
    LODWORD(v30) = 3663;
    v59 = (int *)&v30;
    v60 = 4;
    v61 = (int *)&v29;
    LODWORD(v29) = -1073741637;
    v63 = &v28;
    v62 = 4;
    LODWORD(v28) = v23;
    v64 = 4;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, qword_14004FBC0, 0, 0, 7, v56);
  }
  return v16;
}

```

## disassembly

```asm
0x1400b1a24  mov     [rsp-8+arg_10], rbx
0x1400b1a29  push    rbp
0x1400b1a2a  push    rsi
0x1400b1a2b  push    rdi
0x1400b1a2c  push    r12
0x1400b1a2e  push    r13
0x1400b1a30  push    r14
0x1400b1a32  push    r15
0x1400b1a34  lea     rbp, [rsp-240h]
0x1400b1a3c  sub     rsp, 340h
0x1400b1a43  mov     rax, cs:__security_cookie
0x1400b1a4a  xor     rax, rsp
0x1400b1a4d  mov     [rbp+270h+var_40], rax
0x1400b1a54  movups  xmm1, xmmword ptr [r8+10h]
0x1400b1a59  xor     eax, eax
0x1400b1a5b  xor     r13d, r13d
0x1400b1a5e  xorps   xmm0, xmm0
0x1400b1a61  mov     [rbp+270h+var_230], rax
0x1400b1a65  mov     eax, [rdx]
0x1400b1a67  mov     rsi, rcx
0x1400b1a6a  movups  [rbp+270h+var_240], xmm0
0x1400b1a6e  mov     ecx, 800000h
0x1400b1a73  mov     r12, r8
0x1400b1a76  mov     [rsp+370h+var_318], r13
0x1400b1a7b  mov     rdi, rdx
0x1400b1a7e  movups  xmm0, xmmword ptr [r8]
0x1400b1a82  movups  [rbp+270h+var_2C0], xmm1
0x1400b1a86  movups  [rbp+270h+Buf2], xmm0
0x1400b1a8a  mov     rbx, qword ptr [rbp+270h+Buf2]
0x1400b1a8e  movups  xmm0, xmmword ptr [r8+20h]
0x1400b1a93  movups  [rbp+270h+var_2B0], xmm0
0x1400b1a97  test    rcx, rax
0x1400b1a9a  jz      short loc_1400B1AA1
0x1400b1a9c  or      rbx, rcx
0x1400b1a9f  jmp     short loc_1400B1AA6
0x1400b1aa1  btr     rbx, 17h
0x1400b1aa6  mov     eax, [rdx+0Ch]
0x1400b1aa9  mov     r9d, [rdx+24h]
0x1400b1aad  mov     rdx, r13
0x1400b1ab0  mov     r8d, dword ptr [rbp+270h+var_2B0+4]
0x1400b1ab4  shl     r9, 20h
0x1400b1ab8  or      r9, rax
0x1400b1abb  shl     r8, 20h
0x1400b1abf  mov     rax, qword ptr [rbp+270h+Buf2+8]
0x1400b1ac3  shr     rax, 20h
0x1400b1ac7  or      r8, rax
0x1400b1aca  mov     qword ptr [rbp+270h+Buf2], rbx
0x1400b1ace  mov     r15, r8
0x1400b1ad1  lea     rcx, qword_140040740
0x1400b1ad8  mov     rcx, [rcx+rdx*8]
0x1400b1adc  mov     r10, rcx
0x1400b1adf  mov     rax, rcx
0x1400b1ae2  and     r10, r9
0x1400b1ae5  and     rax, r15
0x1400b1ae8  cmp     r10, rax
0x1400b1aeb  jz      short loc_1400B1AFD
0x1400b1aed  test    r10, r10
0x1400b1af0  jz      short loc_1400B1AF7
0x1400b1af2  or      r15, rcx
0x1400b1af5  jmp     short loc_1400B1AFD
0x1400b1af7  not     rcx
0x1400b1afa  and     r15, rcx
0x1400b1afd  inc     rdx
0x1400b1b00  cmp     rdx, 9
0x1400b1b04  jnz     short loc_1400B1AD1
0x1400b1b06  mov     r14d, 0C0370031h
0x1400b1b0c  cmp     r15, r8
0x1400b1b0f  jz      loc_1400B1C8B
0x1400b1b15  mov     eax, cs:dword_140064110
0x1400b1b1b  cmp     eax, 2
0x1400b1b1e  jbe     loc_1400B1C8B
0x1400b1b24  mov     edx, 100h
0x1400b1b29  lea     rcx, dword_140064110
0x1400b1b30  call    _tlgKeywordOn
0x1400b1b35  test    al, al
0x1400b1b37  jz      loc_1400B1C8B
0x1400b1b3d  lea     rdx, aVsmmphustorehv_0; "VsmmPhuStoreHvPartitionRestore"
0x1400b1b44  lea     rcx, [rbp+270h+var_200]
0x1400b1b48  call    _tlgCreate1Sz_char
0x1400b1b4d  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b1b54  lea     rcx, [rbp+270h+var_1F0]
0x1400b1b5b  call    _tlgCreate1Sz_char
0x1400b1b60  lea     rax, [rsp+370h+var_320]
0x1400b1b65  mov     [rsp+370h+var_308], r9
0x1400b1b6a  mov     [rbp+270h+var_1E0], rax
0x1400b1b71  lea     rdx, word_14004FC0E
0x1400b1b78  lea     rax, [rsp+370h+var_31C]
0x1400b1b7d  mov     [rsp+370h+var_310], r8
0x1400b1b82  mov     [rbp+270h+var_1D0], rax
0x1400b1b89  lea     rcx, dword_140064110
0x1400b1b90  lea     rax, [rsi+290h]
0x1400b1b97  mov     [rsp+370h+var_320], 0DDDh
0x1400b1b9f  mov     [rbp+270h+var_1C0], rax
0x1400b1ba6  xor     r9d, r9d
0x1400b1ba9  lea     rax, [rbp+270h+var_198]
0x1400b1bb0  mov     [rbp+270h+var_1D8], 4
0x1400b1bbb  mov     [rbp+270h+var_1B0], rax
0x1400b1bc2  xor     r8d, r8d
0x1400b1bc5  mov     rax, [rsi+80h]
0x1400b1bcc  mov     [rbp+270h+var_1A0], rax
0x1400b1bd3  movzx   eax, word ptr [rsi+78h]
0x1400b1bd7  mov     dword ptr [rbp+270h+var_198], eax
0x1400b1bdd  mov     rax, [rsi+288h]
0x1400b1be4  mov     [rsp+370h+var_300], rax
0x1400b1be9  lea     rax, [rsp+370h+var_300]
0x1400b1bee  mov     [rbp+270h+var_190], rax
0x1400b1bf5  lea     rax, [rsp+370h+var_308]
0x1400b1bfa  mov     [rbp+270h+var_180], rax
0x1400b1c01  lea     rax, [rsp+370h+var_310]
0x1400b1c06  mov     [rbp+270h+var_170], rax
0x1400b1c0d  lea     rax, [rbp+270h+var_2D8]
0x1400b1c11  mov     [rbp+270h+var_160], rax
0x1400b1c18  lea     rax, [rbp+270h+var_220]
0x1400b1c1c  mov     [rsp+370h+var_348], rax
0x1400b1c21  mov     dword ptr [rsp+370h+var_350], 0Dh
0x1400b1c29  mov     [rsp+370h+var_31C], r14d
0x1400b1c2e  mov     [rbp+270h+var_1C8], 4
0x1400b1c39  mov     [rbp+270h+var_1B8], 10h
0x1400b1c44  mov     [rbp+270h+var_1A8], 2
0x1400b1c4f  mov     dword ptr [rbp+270h+var_198+4], r13d
0x1400b1c56  mov     [rbp+270h+var_188], 8
0x1400b1c61  mov     [rbp+270h+var_178], 8
0x1400b1c6c  mov     [rbp+270h+var_168], 8
0x1400b1c77  mov     [rbp+270h+var_2D8], r15
0x1400b1c7b  mov     [rbp+270h+var_158], 8
0x1400b1c86  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400b1c8b  mov     eax, [rsi+20h]
0x1400b1c8e  mov     r13, r15
0x1400b1c91  shr     r13, 20h
0x1400b1c95  mov     dword ptr [rbp+270h+Buf2+0Ch], r15d
0x1400b1c99  mov     dword ptr [rbp+270h+var_2B0+4], r13d
0x1400b1c9d  test    rax, 1E0h
0x1400b1ca3  jz      short loc_1400B1CBF
0x1400b1ca5  mov     eax, [rdi]
0x1400b1ca7  mov     ecx, 800h
0x1400b1cac  test    rcx, rax
0x1400b1caf  jz      short loc_1400B1CB6
0x1400b1cb1  or      rbx, rcx
0x1400b1cb4  jmp     short loc_1400B1CBB
0x1400b1cb6  btr     rbx, 0Bh
0x1400b1cbb  mov     qword ptr [rbp+270h+Buf2], rbx
0x1400b1cbf  test    byte ptr [rsi+10h], 20h
0x1400b1cc3  jz      short loc_1400B1CDF
0x1400b1cc5  mov     eax, [rdi]
0x1400b1cc7  mov     ecx, 10000000h
0x1400b1ccc  test    rcx, rax
0x1400b1ccf  jz      short loc_1400B1CD6
0x1400b1cd1  or      rbx, rcx
0x1400b1cd4  jmp     short loc_1400B1CDB
0x1400b1cd6  btr     rbx, 1Ch
0x1400b1cdb  mov     qword ptr [rbp+270h+Buf2], rbx
0x1400b1cdf  mov     r8d, 30h ; '0'; Size
0x1400b1ce5  lea     rdx, [rbp+270h+Buf2]; Buf2
0x1400b1ce9  mov     rcx, rdi; Buf1
0x1400b1cec  call    memcmp
0x1400b1cf1  xor     r8d, r8d
0x1400b1cf4  test    eax, eax
0x1400b1cf6  jz      loc_1400B2072
0x1400b1cfc  mov     eax, cs:dword_140064110
0x1400b1d02  cmp     eax, 2
0x1400b1d05  jbe     loc_1400B22E2
0x1400b1d0b  mov     edx, 100h
0x1400b1d10  lea     rcx, dword_140064110
0x1400b1d17  call    _tlgKeywordOn
0x1400b1d1c  test    al, al
0x1400b1d1e  jz      loc_1400B22E2
0x1400b1d24  lea     rdx, aVsmmphustorehv_0; "VsmmPhuStoreHvPartitionRestore"
0x1400b1d2b  lea     rcx, [rbp+270h+var_200]
0x1400b1d2f  call    _tlgCreate1Sz_char
0x1400b1d34  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b1d3b  lea     rcx, [rbp+270h+var_1F0]
0x1400b1d42  call    _tlgCreate1Sz_char
0x1400b1d47  lea     rax, [rsp+370h+var_31C]
0x1400b1d4c  mov     [rsp+370h+var_31C], 0E29h
0x1400b1d54  mov     [rbp+270h+var_1E0], rax
0x1400b1d5b  lea     rax, [rsp+370h+var_320]
0x1400b1d60  mov     [rbp+270h+var_1D0], rax
0x1400b1d67  mov     rax, [rdi]
0x1400b1d6a  mov     [rbp+270h+var_298], rax
0x1400b1d6e  lea     rax, [rbp+270h+var_298]
0x1400b1d72  mov     [rbp+270h+var_1C0], rax
0x1400b1d79  mov     eax, [rdi+8]
0x1400b1d7c  mov     [rsp+370h+var_2F8], eax
0x1400b1d80  lea     rax, [rsp+370h+var_2F8]
0x1400b1d85  mov     [rbp+270h+var_1B0], rax
0x1400b1d8c  mov     eax, [rdi+0Ch]
0x1400b1d8f  mov     [rsp+370h+var_2F4], eax
0x1400b1d93  lea     rax, [rsp+370h+var_2F4]
0x1400b1d98  mov     [rbp+270h+var_1A0], rax
0x1400b1d9f  mov     rax, [rdi+10h]
0x1400b1da3  mov     [rbp+270h+var_290], rax
0x1400b1da7  lea     rax, [rbp+270h+var_290]
0x1400b1dab  mov     [rbp+270h+var_190], rax
0x1400b1db2  mov     rax, [rdi+18h]
0x1400b1db6  mov     [rbp+270h+var_288], rax
0x1400b1dba  lea     rax, [rbp+270h+var_288]
0x1400b1dbe  mov     [rbp+270h+var_180], rax
0x1400b1dc5  mov     eax, [rdi+20h]
0x1400b1dc8  mov     [rbp+270h+var_2F0], eax
0x1400b1dcb  lea     rax, [rbp+270h+var_2F0]
0x1400b1dcf  mov     [rbp+270h+var_170], rax
0x1400b1dd6  mov     eax, [rdi+24h]
0x1400b1dd9  mov     [rbp+270h+var_2EC], eax
0x1400b1ddc  lea     rax, [rbp+270h+var_2EC]
0x1400b1de0  mov     [rbp+270h+var_160], rax
0x1400b1de7  mov     rax, [rdi+28h]
0x1400b1deb  mov     [rbp+270h+var_280], rax
0x1400b1def  lea     rax, [rbp+270h+var_280]
0x1400b1df3  mov     [rbp+270h+var_150], rax
0x1400b1dfa  mov     rax, [r12]
0x1400b1dfe  mov     [rbp+270h+var_278], rax
0x1400b1e02  lea     rax, [rbp+270h+var_278]
0x1400b1e06  mov     [rbp+270h+var_140], rax
0x1400b1e0d  mov     eax, [r12+8]
0x1400b1e12  mov     [rbp+270h+var_2E8], eax
0x1400b1e15  lea     rax, [rbp+270h+var_2E8]
0x1400b1e19  mov     [rbp+270h+var_130], rax
0x1400b1e20  mov     eax, [r12+0Ch]
0x1400b1e25  mov     [rbp+270h+var_2E4], eax
0x1400b1e28  lea     rax, [rbp+270h+var_2E4]
0x1400b1e2c  mov     [rbp+270h+var_120], rax
0x1400b1e33  mov     rax, [r12+10h]
0x1400b1e38  mov     [rbp+270h+var_270], rax
0x1400b1e3c  lea     rax, [rbp+270h+var_270]
0x1400b1e40  mov     [rbp+270h+var_110], rax
0x1400b1e47  mov     rax, [r12+18h]
0x1400b1e4c  mov     [rbp+270h+var_268], rax
0x1400b1e50  lea     rax, [rbp+270h+var_268]
0x1400b1e54  mov     [rbp+270h+var_100], rax
0x1400b1e5b  mov     eax, [r12+20h]
0x1400b1e60  mov     [rbp+270h+var_2E0], eax
0x1400b1e63  lea     rax, [rbp+270h+var_2E0]
0x1400b1e67  mov     [rbp+270h+var_F0], rax
0x1400b1e6e  mov     eax, [r12+24h]
0x1400b1e73  mov     [rbp+270h+var_2DC], eax
0x1400b1e76  lea     rax, [rbp+270h+var_2DC]
0x1400b1e7a  mov     [rbp+270h+var_1D8], 4
0x1400b1e85  mov     [rsp+370h+var_320], r14d
0x1400b1e8a  mov     [rbp+270h+var_1C8], 4
0x1400b1e95  mov     [rbp+270h+var_1B8], 8
0x1400b1ea0  mov     [rbp+270h+var_1A8], 4
0x1400b1eab  mov     [rbp+270h+var_198], 4
0x1400b1eb6  mov     [rbp+270h+var_188], 8
0x1400b1ec1  mov     [rbp+270h+var_178], 8
0x1400b1ecc  mov     [rbp+270h+var_168], 4
0x1400b1ed7  mov     [rbp+270h+var_158], 4
0x1400b1ee2  mov     [rbp+270h+var_148], 8
0x1400b1eed  mov     [rbp+270h+var_138], 8
0x1400b1ef8  mov     [rbp+270h+var_128], 4
0x1400b1f03  mov     [rbp+270h+var_118], 4
0x1400b1f0e  mov     [rbp+270h+var_108], 8
0x1400b1f19  mov     [rbp+270h+var_F8], 8
0x1400b1f24  mov     [rbp+270h+var_E8], 4
0x1400b1f2f  mov     [rbp+270h+var_E0], rax
0x1400b1f36  lea     rdx, word_14004F89A
0x1400b1f3d  mov     rax, [r12+28h]
0x1400b1f42  xor     r9d, r9d
0x1400b1f45  mov     [rbp+270h+var_260], rax
0x1400b1f49  lea     rax, [rbp+270h+var_260]
0x1400b1f4d  mov     [rbp+270h+var_D0], rax
0x1400b1f54  lea     rax, [rbp+270h+var_258]
0x1400b1f58  mov     [rbp+270h+var_C0], rax
0x1400b1f5f  mov     eax, dword ptr [rbp+270h+Buf2+8]
0x1400b1f62  mov     dword ptr [rbp+270h+var_2D8], eax
0x1400b1f65  lea     rax, [rbp+270h+var_2D8]
0x1400b1f69  mov     [rbp+270h+var_B0], rax
0x1400b1f70  lea     rax, [rsp+370h+var_310]
0x1400b1f75  mov     [rbp+270h+var_A0], rax
0x1400b1f7c  mov     rax, qword ptr [rbp+270h+var_2C0]
0x1400b1f80  mov     qword ptr [rbp+270h+var_250], rax
0x1400b1f84  lea     rax, [rbp+270h+var_250]
0x1400b1f88  mov     [rbp+270h+var_90], rax
0x1400b1f8f  mov     rax, qword ptr [rbp+270h+var_2C0+8]
0x1400b1f93  mov     qword ptr [rbp+270h+var_250+8], rax
0x1400b1f97  lea     rax, [rbp+270h+var_250+8]
0x1400b1f9b  mov     [rbp+270h+var_80], rax
0x1400b1fa2  mov     eax, dword ptr [rbp+270h+var_2B0]
0x1400b1fa5  mov     dword ptr [rsp+370h+var_308], eax
0x1400b1fa9  lea     rax, [rsp+370h+var_308]
0x1400b1fae  mov     [rbp+270h+var_70], rax
0x1400b1fb5  lea     rax, [rsp+370h+var_300]
0x1400b1fba  mov     [rbp+270h+var_60], rax
0x1400b1fc1  mov     rax, qword ptr [rbp+270h+var_2B0+8]
0x1400b1fc5  mov     [rbp+270h+var_2A0], rax
0x1400b1fc9  lea     rax, [rbp+270h+var_2A0]
0x1400b1fcd  mov     [rbp+270h+var_50], rax
0x1400b1fd4  lea     rax, [rbp+270h+var_220]
0x1400b1fd8  mov     [rsp+370h+var_348], rax
0x1400b1fdd  mov     dword ptr [rsp+370h+var_350], 1Eh
0x1400b1fe5  mov     [rbp+270h+var_D8], 4
0x1400b1ff0  mov     [rbp+270h+var_C8], 8
0x1400b1ffb  mov     [rbp+270h+var_258], rbx
0x1400b1fff  mov     [rbp+270h+var_B8], 8
0x1400b200a  mov     [rbp+270h+var_A8], 4
0x1400b2015  mov     dword ptr [rsp+370h+var_310], r15d
0x1400b201a  mov     [rbp+270h+var_98], 4
0x1400b2025  mov     [rbp+270h+var_88], 8
0x1400b2030  mov     [rbp+270h+var_78], 8
0x1400b203b  mov     [rbp+270h+var_68], 4
0x1400b2046  mov     dword ptr [rsp+370h+var_300], r13d
  ... truncated ...
```
