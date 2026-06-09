# VsmmpReadEncryptMbpRange

- ea: `0x14001c0a8`
- end: `0x14001d039`
- name: `VsmmpReadEncryptMbpRange`
- size: `3985`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140029790`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x14000a010`
- `0x14000ba38`
- `0x14001c0a8`
- `0x140021850`
- `0x140021a54`
- `0x140021a84`
- `0x140021c60`
- `0x140021e00`
- `0x140022340`
- `0x140028280`
- `0x1400ab5cc`
- `0x1400f0ff0`
- `0x1400fb38c`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x14001c482`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14001c482`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14001ca1b`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14001ca1b`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14001c155`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14001c155`

## string_xrefs

- `0x14001c1d8`: `VsmmpReadEncryptMbpRange`
- `0x14001c342`: `VsmmpReadEncryptMbpRange`
- `0x14001c525`: `VsmmpReadEncryptMbpRange`
- `0x14001c666`: `VsmmpReadEncryptMbpRange`
- `0x14001c7ed`: `VsmmpReadEncryptMbpRange`
- `0x14001c925`: `VsmmpReadEncryptMbpRange`
- `0x14001ca69`: `VsmmpReadEncryptMbpRange`
- `0x14001ccbc`: `VsmmpReadEncryptMbpRange`
- `0x14001ce75`: `VsmmpReadEncryptMbpRange`

## pseudocode

```c
__int64 __fastcall VsmmpReadEncryptMbpRange(
        unsigned __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        unsigned __int64 a6,
        _QWORD *a7)
{
  int v8; // edi
  const void *v9; // r15
  char *v10; // r13
  __int64 v11; // r9
  __int64 v12; // rsi
  int v13; // eax
  __int64 v14; // r8
  int v15; // edi
  int v16; // r8d
  __int64 v17; // r10
  __int64 v18; // rdx
  int v19; // ecx
  __int64 v20; // rax
  unsigned int v21; // esi
  unsigned int v22; // r8d
  __int64 v23; // r10
  __int64 v24; // rdx
  int v25; // ecx
  __int64 v26; // rax
  __int64 v27; // rax
  char *v28; // rdx
  unsigned int v30; // r8d
  __int64 v31; // r10
  __int64 v32; // rdx
  int v33; // ecx
  __int64 v34; // rax
  __int64 v35; // rdx
  int v36; // ecx
  __int64 v37; // rax
  unsigned __int64 v38; // r14
  __int64 v39; // rax
  unsigned int v40; // r8d
  __int64 v41; // rdx
  int v42; // ecx
  __int64 v43; // rax
  unsigned int v44; // r8d
  __int64 v45; // rdx
  int v46; // ecx
  __int64 v47; // rax
  unsigned int v48; // r8d
  __int64 v49; // rdx
  int v50; // ecx
  __int64 v51; // rax
  int v52; // edx
  int v53; // edi
  int v54; // eax
  int v55; // edx
  unsigned int v56; // r15d
  char *v57; // r14
  __int64 v58; // rsi
  int v59; // edi
  __int64 v60; // rdx
  int v61; // ecx
  __int64 v62; // rax
  int v63; // [rsp+20h] [rbp-1E8h]
  unsigned int v64; // [rsp+50h] [rbp-1B8h] BYREF
  int DataAlignment; // [rsp+54h] [rbp-1B4h] BYREF
  __int64 v66; // [rsp+58h] [rbp-1B0h] BYREF
  __int64 v67; // [rsp+60h] [rbp-1A8h]
  __int64 v68; // [rsp+68h] [rbp-1A0h] BYREF
  __int64 v69; // [rsp+70h] [rbp-198h] BYREF
  unsigned __int64 v70; // [rsp+78h] [rbp-190h]
  int v71; // [rsp+80h] [rbp-188h]
  unsigned int v72; // [rsp+88h] [rbp-180h]
  PVOID Entry; // [rsp+90h] [rbp-178h]
  _QWORD v74[4]; // [rsp+98h] [rbp-170h] BYREF
  const void *v75; // [rsp+B8h] [rbp-150h]
  __int64 v76; // [rsp+C0h] [rbp-148h] BYREF
  _QWORD *v77; // [rsp+C8h] [rbp-140h]
  __int64 v78; // [rsp+D0h] [rbp-138h]
  __int64 v79; // [rsp+D8h] [rbp-130h]
  __int64 v80; // [rsp+E0h] [rbp-128h]
  __int128 v81; // [rsp+E8h] [rbp-120h] BYREF
  _BYTE v82[24]; // [rsp+100h] [rbp-108h] BYREF
  _BYTE v83[16]; // [rsp+120h] [rbp-E8h] BYREF
  _BYTE v84[16]; // [rsp+130h] [rbp-D8h] BYREF
  int *p_DataAlignment; // [rsp+140h] [rbp-C8h]
  __int64 v86; // [rsp+148h] [rbp-C0h]
  int *v87; // [rsp+150h] [rbp-B8h]
  __int64 v88; // [rsp+158h] [rbp-B0h]
  __int64 v89; // [rsp+160h] [rbp-A8h]
  __int64 v90; // [rsp+168h] [rbp-A0h]
  int *v91; // [rsp+170h] [rbp-98h]
  __int64 v92; // [rsp+178h] [rbp-90h]
  __int64 v93; // [rsp+180h] [rbp-88h]
  int v94; // [rsp+188h] [rbp-80h] BYREF
  int v95; // [rsp+18Ch] [rbp-7Ch]
  __int64 *v96; // [rsp+190h] [rbp-78h]
  __int64 v97; // [rsp+198h] [rbp-70h]
  __int64 *v98; // [rsp+1A0h] [rbp-68h]
  __int64 v99; // [rsp+1A8h] [rbp-60h]
  __int64 *v100; // [rsp+1B0h] [rbp-58h]
  __int64 v101; // [rsp+1B8h] [rbp-50h]

  v69 = a3;
  v8 = a2;
  v68 = a2;
  v70 = a1;
  v74[1] = a1;
  v74[2] = a2;
  v74[3] = a3;
  v72 = a4;
  v74[0] = a5;
  v77 = a7;
  v64 = 0;
  v81 = 0;
  v76 = 0;
  v9 = 0;
  v75 = 0;
  Entry = 0;
  v10 = 0;
  v11 = *(_QWORD *)(*((_QWORD *)VidDeviceExtension + 33) + 8LL * (unsigned __int8)KeGetCurrentNodeNumber());
  v67 = v11;
  v80 = v11;
  v12 = *(_QWORD *)(v70 + 8);
  v66 = v12;
  v79 = v12;
  v13 = *(_DWORD *)(v12 + 10224);
  if ( (v13 & 1) != 0 )
  {
    v21 = (a4 >> 2) & 3;
    if ( !v21 || (v13 & 4) != 0 )
    {
      if ( a6 <= 0xFFFFFFFF )
      {
        v81 = 0;
        v15 = VsmmGpaRangeLookupGpaByMbp(v66, v70, v8, 1, 0, (__int64)&v81, 0);
        if ( v15 < 0 )
        {
          if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
            goto LABEL_12;
          tlgCreate1Sz_char(v83, "VsmmpReadEncryptMbpRange");
          tlgCreate1Sz_char(v84, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
          DataAlignment = 1026;
          p_DataAlignment = &DataAlignment;
          v86 = 4;
          v64 = v15;
          v87 = (int *)&v64;
          v88 = 4;
          v35 = *(_QWORD *)(v70 + 8);
          v89 = v35 + 656;
          v90 = 16;
          v36 = *(unsigned __int16 *)(v35 + 120);
          v37 = *(_QWORD *)(v35 + 128);
          v91 = &v94;
          v92 = 2;
          v93 = v37;
          v94 = v36;
          v95 = 0;
          v69 = *(_QWORD *)(v35 + 648);
          v96 = &v69;
          v98 = &v68;
          v99 = 8;
          v63 = 11;
          v28 = byte_140057209;
          goto LABEL_11;
        }
        v38 = v69 << 12;
        v39 = VidManagedBufferListElementRequest(v66 + 10064, v69 << 12);
        v10 = (char *)v39;
        v78 = v39;
        if ( !v39 )
        {
          v14 = 3221225626LL;
          v15 = -1073741670;
          if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
            goto LABEL_12;
          tlgCreate1Sz_char(v83, "VsmmpReadEncryptMbpRange");
          tlgCreate1Sz_char(v84, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
          DataAlignment = 1043;
          p_DataAlignment = &DataAlignment;
          v86 = 4;
          v64 = v40;
          v87 = (int *)&v64;
          v88 = 4;
          v41 = *(_QWORD *)(v70 + 8);
          v89 = v41 + 656;
          v90 = 16;
          v42 = *(unsigned __int16 *)(v41 + 120);
          v43 = *(_QWORD *)(v41 + 128);
          v91 = &v94;
          v92 = 2;
          v93 = v43;
          v94 = v42;
          v95 = 0;
          v27 = *(_QWORD *)(v41 + 648);
          v28 = byte_140056F75;
          goto LABEL_10;
        }
        if ( v21 )
        {
          v9 = (const void *)VidManagedBufferListElementRequest(v66 + 9904, v38);
          v75 = v9;
          if ( !v9 )
          {
            v14 = 3221225626LL;
            v15 = -1073741670;
            if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
              goto LABEL_12;
            tlgCreate1Sz_char(v83, "VsmmpReadEncryptMbpRange");
            tlgCreate1Sz_char(v84, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
            DataAlignment = 1062;
            p_DataAlignment = &DataAlignment;
            v86 = 4;
            v64 = v44;
            v87 = (int *)&v64;
            v88 = 4;
            v45 = *(_QWORD *)(v70 + 8);
            v89 = v45 + 656;
            v90 = 16;
            v46 = *(unsigned __int16 *)(v45 + 120);
            v47 = *(_QWORD *)(v45 + 128);
            v91 = &v94;
            v92 = 2;
            v93 = v47;
            v94 = v46;
            v95 = 0;
            v27 = *(_QWORD *)(v45 + 648);
            v28 = byte_140056FE3;
            goto LABEL_10;
          }
          Entry = ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(96LL * (v21 - 1) + v67 + 224));
          if ( !Entry )
          {
            v14 = 3221225626LL;
            v15 = -1073741670;
            if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
              goto LABEL_12;
            tlgCreate1Sz_char(v83, "VsmmpReadEncryptMbpRange");
            tlgCreate1Sz_char(v84, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
            DataAlignment = 1072;
            p_DataAlignment = &DataAlignment;
            v86 = 4;
            v64 = v48;
            v87 = (int *)&v64;
            v88 = 4;
            v49 = *(_QWORD *)(v70 + 8);
            v89 = v49 + 656;
            v90 = 16;
            v50 = *(unsigned __int16 *)(v49 + 120);
            v51 = *(_QWORD *)(v49 + 128);
            v91 = &v94;
            v92 = 2;
            v93 = v51;
            v94 = v50;
            v95 = 0;
            v27 = *(_QWORD *)(v49 + 648);
            v28 = byte_140057051;
            goto LABEL_10;
          }
          v39 = (__int64)v9;
        }
        v15 = VsmmpReadMemoryBlockByteRange(v70, v68 << 12, v69 << 12, a4 & 0xFFFFFFF3, v39, v38, 0, 0, &v76);
        if ( v15 >= 0 )
        {
          v53 = (_DWORD)v69 << 12;
          if ( v21 )
          {
            DataAlignment = VsmmCryptGetDataAlignment();
            v54 = VsmmCompressionFormatToVmCompress(v21);
            if ( (int)VmCompressPack(v54, (_DWORD)v9, v53, (_DWORD)v10, v55, (__int64)&v64, (__int64)Entry) < 0 )
            {
              memmove(v10, v9, v38);
            }
            else
            {
              v56 = v64;
              v57 = &v10[v64];
              v58 = (-DataAlignment & (DataAlignment + v64 - 1)) - v64;
              v59 = DataAlignment + v58;
              memset(v57, 0, (unsigned int)(DataAlignment + v58));
              *(_DWORD *)&v57[v58] = 1;
              *(_DWORD *)&v57[v58 + 4] = 12;
              *(_DWORD *)&v57[v58 + 8] = v56;
              v53 = v56 + v59;
            }
          }
          v64 = a6;
          v12 = v66;
          v15 = VsmmCryptPack(v66, v52, (unsigned int)&v81, v74[0], (__int64)&v64, (__int64)v10, v53);
          v71 = v15;
          if ( v15 >= 0 )
          {
            *v77 = v64;
            v15 = 0;
            goto LABEL_13;
          }
          if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
          {
            tlgCreate1Sz_char(v83, "VsmmpReadEncryptMbpRange");
            tlgCreate1Sz_char(v84, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
            DataAlignment = 1234;
            p_DataAlignment = &DataAlignment;
            v86 = 4;
            LODWORD(v66) = v15;
            v87 = (int *)&v66;
            v88 = 4;
            v60 = *(_QWORD *)(v70 + 8);
            v89 = v60 + 656;
            v90 = 16;
            v61 = *(unsigned __int16 *)(v60 + 120);
            v62 = *(_QWORD *)(v60 + 128);
            v91 = &v94;
            v92 = 2;
            v93 = v62;
            v94 = v61;
            v95 = 0;
            v74[0] = *(_QWORD *)(v60 + 648);
            v96 = v74;
            v97 = 8;
            v98 = &v68;
            v99 = 8;
            v100 = &v69;
            v101 = 8;
            tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, byte_140056E71, 0, 0, 12, v82);
          }
          v11 = v67;
          goto LABEL_14;
        }
LABEL_12:
        v12 = v66;
        goto LABEL_13;
      }
      v14 = 3221225485LL;
      v15 = -1073741811;
      if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      {
        tlgCreate1Sz_char(v83, "VsmmpReadEncryptMbpRange");
        tlgCreate1Sz_char(v84, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
        DataAlignment = 1003;
        p_DataAlignment = &DataAlignment;
        v86 = 4;
        v64 = v30;
        v87 = (int *)&v64;
        v88 = 4;
        v32 = *(_QWORD *)(v31 + 8);
        v89 = v32 + 656;
        v90 = 16;
        v33 = *(unsigned __int16 *)(v32 + 120);
        v34 = *(_QWORD *)(v32 + 128);
        v91 = &v94;
        v92 = 2;
        v93 = v34;
        v94 = v33;
        v95 = 0;
        v27 = *(_QWORD *)(v32 + 648);
        v28 = byte_14005719B;
        goto LABEL_10;
      }
    }
    else
    {
      v14 = 3221225485LL;
      v15 = -1073741811;
      if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      {
        tlgCreate1Sz_char(v83, "VsmmpReadEncryptMbpRange");
        tlgCreate1Sz_char(v84, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
        DataAlignment = 993;
        p_DataAlignment = &DataAlignment;
        v86 = 4;
        v64 = v22;
        v87 = (int *)&v64;
        v88 = 4;
        v24 = *(_QWORD *)(v23 + 8);
        v89 = v24 + 656;
        v90 = 16;
        v25 = *(unsigned __int16 *)(v24 + 120);
        v26 = *(_QWORD *)(v24 + 128);
        v91 = &v94;
        v92 = 2;
        v93 = v26;
        v94 = v25;
        v95 = 0;
        v27 = *(_QWORD *)(v24 + 648);
        v28 = byte_14005712D;
LABEL_10:
        v68 = v27;
        v96 = &v68;
        v63 = 10;
LABEL_11:
        v97 = 8;
        tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, v28, 0, 0, v63, v82);
        goto LABEL_12;
      }
    }
    v12 = v66;
    goto LABEL_14;
  }
  v14 = 3221225485LL;
  v15 = -1073741811;
  if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
  {
    tlgCreate1Sz_char(v83, "VsmmpReadEncryptMbpRange");
    tlgCreate1Sz_char(v84, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
    v64 = 985;
    p_DataAlignment = (int *)&v64;
    v86 = 4;
    DataAlignment = v16;
    v87 = &DataAlignment;
    v88 = 4;
    v18 = *(_QWORD *)(v17 + 8);
    v89 = v18 + 656;
    v90 = 16;
    v19 = *(unsigned __int16 *)(v18 + 120);
    v20 = *(_QWORD *)(v18 + 128);
    v91 = &v94;
    v92 = 2;
    v93 = v20;
    v94 = v19;
    v95 = 0;
    v68 = *(_QWORD *)(v18 + 648);
    v96 = &v68;
    v97 = 8;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &byte_1400570BF, 0, 0, 10, v82);
LABEL_13:
    v11 = v67;
  }
LABEL_14:
  if ( Entry )
    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v11 + 224 + 96LL * (((a4 >> 2) & 3) - 1)), Entry);
  if ( v75 )
    VidManagedBufferListElementRelease(v12 + 9904, v75, v14, v11);
  if ( v10 )
    VidManagedBufferListElementRelease(v12 + 10064, v10, v14, v11);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x14001c0a8  push    rbx
0x14001c0aa  push    rsi
0x14001c0ab  push    rdi
0x14001c0ac  push    r12
0x14001c0ae  push    r13
0x14001c0b0  push    r14
0x14001c0b2  push    r15
0x14001c0b4  sub     rsp, 1D0h
0x14001c0bb  mov     rax, cs:__security_cookie
0x14001c0c2  xor     rax, rsp
0x14001c0c5  mov     [rsp+208h+var_48], rax
0x14001c0cd  mov     ebx, r9d
0x14001c0d0  mov     rax, r8
0x14001c0d3  mov     [rsp+208h+var_198], rax
0x14001c0d8  mov     rdi, rdx
0x14001c0db  mov     [rsp+208h+var_1A0], rdx
0x14001c0e0  mov     [rsp+208h+var_190], rcx
0x14001c0e5  mov     [rsp+208h+var_168], rcx
0x14001c0ed  mov     [rsp+208h+var_160], rdx
0x14001c0f5  mov     [rsp+208h+var_158], rax
0x14001c0fd  mov     [rsp+208h+var_180], ebx
0x14001c104  mov     rax, [rsp+208h+arg_20]
0x14001c10c  mov     [rsp+208h+var_170], rax
0x14001c114  mov     rax, [rsp+208h+arg_30]
0x14001c11c  mov     [rsp+208h+var_140], rax
0x14001c124  xor     r12d, r12d
0x14001c127  mov     [rsp+208h+var_1B8], r12d
0x14001c12c  xorps   xmm0, xmm0
0x14001c12f  movups  [rsp+208h+var_120], xmm0
0x14001c137  mov     [rsp+208h+var_148], r12
0x14001c13f  mov     r15d, r12d
0x14001c142  mov     [rsp+208h+var_150], r12
0x14001c14a  mov     [rsp+208h+Entry], r12
0x14001c152  mov     r13d, r12d
0x14001c155  call    cs:__imp_KeGetCurrentNodeNumber
0x14001c15c  nop     dword ptr [rax+rax+00h]
0x14001c161  movzx   edx, al
0x14001c164  mov     rax, cs:VidDeviceExtension
0x14001c16b  mov     rcx, [rax+108h]
0x14001c172  mov     r9, [rcx+rdx*8]
0x14001c176  mov     [rsp+208h+var_1A8], r9
0x14001c17b  mov     [rsp+208h+var_128], r9
0x14001c183  mov     r10, [rsp+208h+var_190]
0x14001c188  mov     rsi, [r10+8]
0x14001c18c  mov     [rsp+208h+var_1B0], rsi
0x14001c191  mov     [rsp+208h+var_130], rsi
0x14001c199  mov     eax, [rsi+27F0h]
0x14001c19f  test    al, 1
0x14001c1a1  jnz     loc_14001C2F4
0x14001c1a7  mov     r8d, 0C000000Dh
0x14001c1ad  mov     edi, r8d
0x14001c1b0  mov     eax, cs:dword_140065110
0x14001c1b6  cmp     eax, 2
0x14001c1b9  jbe     loc_14001C45B
0x14001c1bf  mov     edx, 100h
0x14001c1c4  lea     rcx, dword_140065110
0x14001c1cb  call    _tlgKeywordOn
0x14001c1d0  test    al, al
0x14001c1d2  jz      loc_14001C45B
0x14001c1d8  lea     rdx, aVsmmpreadencry; "VsmmpReadEncryptMbpRange"
0x14001c1df  lea     rcx, [rsp+208h+var_E8]
0x14001c1e7  call    _tlgCreate1Sz_char
0x14001c1ec  lea     rdx, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x14001c1f3  lea     rcx, [rsp+208h+var_D8]
0x14001c1fb  call    _tlgCreate1Sz_char
0x14001c200  mov     [rsp+208h+var_1B8], 3D9h
0x14001c208  lea     rax, [rsp+208h+var_1B8]
0x14001c20d  mov     [rsp+208h+var_C8], rax
0x14001c215  mov     [rsp+208h+var_C0], 4
0x14001c221  mov     [rsp+208h+var_1B4], r8d
0x14001c226  lea     rcx, [rsp+208h+var_1B4]
0x14001c22b  mov     [rsp+208h+var_B8], rcx
0x14001c233  mov     [rsp+208h+var_B0], 4
0x14001c23f  mov     rdx, [r10+8]
0x14001c243  lea     rax, [rdx+290h]
0x14001c24a  mov     [rsp+208h+var_A8], rax
0x14001c252  mov     [rsp+208h+var_A0], 10h
0x14001c25e  movzx   ecx, word ptr [rdx+78h]
0x14001c262  mov     rax, [rdx+80h]
0x14001c269  lea     r8, [rsp+208h+var_80]
0x14001c271  mov     [rsp+208h+var_98], r8
0x14001c279  mov     [rsp+208h+var_90], 2
0x14001c285  mov     [rsp+208h+var_88], rax
0x14001c28d  mov     [rsp+208h+var_80], ecx
0x14001c294  mov     [rsp+208h+var_7C], r12d
0x14001c29c  mov     rax, [rdx+288h]
0x14001c2a3  mov     [rsp+208h+var_1A0], rax
0x14001c2a8  lea     rax, [rsp+208h+var_1A0]
0x14001c2ad  mov     [rsp+208h+var_78], rax
0x14001c2b5  mov     [rsp+208h+var_70], 8
0x14001c2c1  lea     rax, [rsp+208h+var_108]
0x14001c2c9  mov     [rsp+208h+var_1E0], rax
0x14001c2ce  mov     dword ptr [rsp+208h+var_1E8], 0Ah
0x14001c2d6  xor     r9d, r9d
0x14001c2d9  xor     r8d, r8d
0x14001c2dc  lea     rdx, byte_1400570BF
0x14001c2e3  lea     rcx, dword_140065110
0x14001c2ea  call    _tlgWriteTransfer_EtwWriteTransfer
0x14001c2ef  jmp     loc_14001C456
0x14001c2f4  mov     esi, ebx
0x14001c2f6  shr     esi, 2
0x14001c2f9  and     esi, 3
0x14001c2fc  jz      loc_14001C4E1
0x14001c302  mov     r14d, 4
0x14001c308  test    r14b, al
0x14001c30b  jnz     loc_14001C4E1
0x14001c311  mov     r8d, 0C000000Dh
0x14001c317  mov     edi, r8d
0x14001c31a  mov     eax, cs:dword_140065110
0x14001c320  cmp     eax, 2
0x14001c323  jbe     loc_14001D02F
0x14001c329  mov     edx, 100h
0x14001c32e  lea     rcx, dword_140065110
0x14001c335  call    _tlgKeywordOn
0x14001c33a  test    al, al
0x14001c33c  jz      loc_14001D02F
0x14001c342  lea     rdx, aVsmmpreadencry; "VsmmpReadEncryptMbpRange"
0x14001c349  lea     rcx, [rsp+208h+var_E8]
0x14001c351  call    _tlgCreate1Sz_char
0x14001c356  lea     rdx, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x14001c35d  lea     rcx, [rsp+208h+var_D8]
0x14001c365  call    _tlgCreate1Sz_char
0x14001c36a  mov     [rsp+208h+var_1B4], 3E1h
0x14001c372  lea     rax, [rsp+208h+var_1B4]
0x14001c377  mov     [rsp+208h+var_C8], rax
0x14001c37f  mov     [rsp+208h+var_C0], r14
0x14001c387  mov     [rsp+208h+var_1B8], r8d
0x14001c38c  lea     rax, [rsp+208h+var_1B8]
0x14001c391  mov     [rsp+208h+var_B8], rax
0x14001c399  mov     [rsp+208h+var_B0], r14
0x14001c3a1  mov     rdx, [r10+8]
0x14001c3a5  lea     rax, [rdx+290h]
0x14001c3ac  mov     [rsp+208h+var_A8], rax
0x14001c3b4  mov     [rsp+208h+var_A0], 10h
0x14001c3c0  movzx   ecx, word ptr [rdx+78h]
0x14001c3c4  mov     rax, [rdx+80h]
0x14001c3cb  lea     r8, [rsp+208h+var_80]
0x14001c3d3  mov     [rsp+208h+var_98], r8
0x14001c3db  mov     [rsp+208h+var_90], 2
0x14001c3e7  mov     [rsp+208h+var_88], rax
0x14001c3ef  mov     [rsp+208h+var_80], ecx
0x14001c3f6  mov     [rsp+208h+var_7C], r12d
0x14001c3fe  mov     rax, [rdx+288h]
0x14001c405  lea     rdx, byte_14005712D
0x14001c40c  mov     [rsp+208h+var_1A0], rax
0x14001c411  lea     rax, [rsp+208h+var_1A0]
0x14001c416  mov     [rsp+208h+var_78], rax
0x14001c41e  lea     rax, [rsp+208h+var_108]
0x14001c426  mov     [rsp+208h+var_1E0], rax
0x14001c42b  mov     dword ptr [rsp+208h+var_1E8], 0Ah
0x14001c433  xor     r9d, r9d
0x14001c436  xor     r8d, r8d
0x14001c439  mov     [rsp+208h+var_70], 8
0x14001c445  lea     rcx, dword_140065110
0x14001c44c  call    _tlgWriteTransfer_EtwWriteTransfer
0x14001c451  mov     rsi, [rsp+208h+var_1B0]
0x14001c456  mov     r9, [rsp+208h+var_1A8]
0x14001c45b  mov     rdx, [rsp+208h+Entry]; Entry
0x14001c463  test    rdx, rdx
0x14001c466  jz      short loc_14001C48E
0x14001c468  shr     ebx, 2
0x14001c46b  and     ebx, 3
0x14001c46e  dec     ebx
0x14001c470  lea     rcx, [rbx+rbx*2]
0x14001c474  shl     rcx, 5
0x14001c478  add     r9, 0E0h
0x14001c47f  add     rcx, r9; Lookaside
0x14001c482  call    cs:__imp_ExFreeToLookasideListEx
0x14001c489  nop     dword ptr [rax+rax+00h]
0x14001c48e  mov     rdx, [rsp+208h+var_150]
0x14001c496  test    rdx, rdx
0x14001c499  jz      short loc_14001C4A7
0x14001c49b  lea     rcx, [rsi+26B0h]
0x14001c4a2  call    VidManagedBufferListElementRelease
0x14001c4a7  test    r13, r13
0x14001c4aa  jz      short loc_14001C4BB
0x14001c4ac  lea     rcx, [rsi+2750h]
0x14001c4b3  mov     rdx, r13
0x14001c4b6  call    VidManagedBufferListElementRelease
0x14001c4bb  mov     eax, edi
0x14001c4bd  mov     rcx, [rsp+208h+var_48]
0x14001c4c5  xor     rcx, rsp; StackCookie
0x14001c4c8  call    __security_check_cookie
0x14001c4cd  add     rsp, 1D0h
0x14001c4d4  pop     r15
0x14001c4d6  pop     r14
0x14001c4d8  pop     r13
0x14001c4da  pop     r12
0x14001c4dc  pop     rdi
0x14001c4dd  pop     rsi
0x14001c4de  pop     rbx
0x14001c4df  retn
0x14001c4e1  mov     eax, 0FFFFFFFFh
0x14001c4e6  cmp     [rsp+208h+arg_28], rax
0x14001c4ee  jbe     loc_14001C5FC
0x14001c4f4  mov     r8d, 0C000000Dh
0x14001c4fa  mov     edi, r8d
0x14001c4fd  mov     eax, cs:dword_140065110
0x14001c503  cmp     eax, 2
0x14001c506  jbe     loc_14001D02F
0x14001c50c  mov     edx, 100h
0x14001c511  lea     rcx, dword_140065110
0x14001c518  call    _tlgKeywordOn
0x14001c51d  test    al, al
0x14001c51f  jz      loc_14001D02F
0x14001c525  lea     rdx, aVsmmpreadencry; "VsmmpReadEncryptMbpRange"
0x14001c52c  lea     rcx, [rsp+208h+var_E8]
0x14001c534  call    _tlgCreate1Sz_char
0x14001c539  lea     rdx, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x14001c540  lea     rcx, [rsp+208h+var_D8]
0x14001c548  call    _tlgCreate1Sz_char
0x14001c54d  mov     [rsp+208h+var_1B4], 3EBh
0x14001c555  lea     rax, [rsp+208h+var_1B4]
0x14001c55a  mov     [rsp+208h+var_C8], rax
0x14001c562  mov     [rsp+208h+var_C0], 4
0x14001c56e  mov     [rsp+208h+var_1B8], r8d
0x14001c573  lea     rax, [rsp+208h+var_1B8]
0x14001c578  mov     [rsp+208h+var_B8], rax
0x14001c580  mov     [rsp+208h+var_B0], 4
0x14001c58c  mov     rdx, [r10+8]
0x14001c590  lea     rax, [rdx+290h]
0x14001c597  mov     [rsp+208h+var_A8], rax
0x14001c59f  mov     [rsp+208h+var_A0], 10h
0x14001c5ab  movzx   ecx, word ptr [rdx+78h]
0x14001c5af  mov     rax, [rdx+80h]
0x14001c5b6  lea     r8, [rsp+208h+var_80]
0x14001c5be  mov     [rsp+208h+var_98], r8
0x14001c5c6  mov     [rsp+208h+var_90], 2
0x14001c5d2  mov     [rsp+208h+var_88], rax
0x14001c5da  mov     [rsp+208h+var_80], ecx
0x14001c5e1  mov     [rsp+208h+var_7C], r12d
0x14001c5e9  mov     rax, [rdx+288h]
0x14001c5f0  lea     rdx, byte_14005719B
0x14001c5f7  jmp     loc_14001C40C
0x14001c5fc  xorps   xmm0, xmm0
0x14001c5ff  movups  [rsp+208h+var_120], xmm0
0x14001c607  mov     [rsp+208h+var_1D8], r12
0x14001c60c  lea     rax, [rsp+208h+var_120]
0x14001c614  mov     [rsp+208h+var_1E0], rax
0x14001c619  mov     dword ptr [rsp+208h+var_1E8], r12d
0x14001c61e  mov     r9d, 1
0x14001c624  mov     r8, rdi
0x14001c627  mov     rdx, r10
0x14001c62a  mov     rcx, [rsp+208h+var_1B0]
0x14001c62f  call    VsmmGpaRangeLookupGpaByMbp
0x14001c634  mov     edi, eax
0x14001c636  test    eax, eax
0x14001c638  jns     loc_14001C78B
0x14001c63e  mov     eax, cs:dword_140065110
0x14001c644  cmp     eax, 2
0x14001c647  jbe     loc_14001C451
0x14001c64d  mov     edx, 100h
0x14001c652  lea     rcx, dword_140065110
0x14001c659  call    _tlgKeywordOn
0x14001c65e  test    al, al
0x14001c660  jz      loc_14001C451
0x14001c666  lea     rdx, aVsmmpreadencry; "VsmmpReadEncryptMbpRange"
0x14001c66d  lea     rcx, [rsp+208h+var_E8]
0x14001c675  call    _tlgCreate1Sz_char
0x14001c67a  lea     rdx, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x14001c681  lea     rcx, [rsp+208h+var_D8]
0x14001c689  call    _tlgCreate1Sz_char
0x14001c68e  mov     [rsp+208h+var_1B4], 402h
0x14001c696  lea     rax, [rsp+208h+var_1B4]
0x14001c69b  mov     [rsp+208h+var_C8], rax
0x14001c6a3  mov     [rsp+208h+var_C0], 4
0x14001c6af  mov     [rsp+208h+var_1B8], edi
0x14001c6b3  lea     rax, [rsp+208h+var_1B8]
0x14001c6b8  mov     [rsp+208h+var_B8], rax
0x14001c6c0  mov     [rsp+208h+var_B0], 4
0x14001c6cc  mov     rcx, [rsp+208h+var_190]
0x14001c6d1  mov     rdx, [rcx+8]
0x14001c6d5  lea     rax, [rdx+290h]
0x14001c6dc  mov     [rsp+208h+var_A8], rax
0x14001c6e4  mov     [rsp+208h+var_A0], 10h
0x14001c6f0  movzx   ecx, word ptr [rdx+78h]
0x14001c6f4  mov     rax, [rdx+80h]
0x14001c6fb  lea     r8, [rsp+208h+var_80]
0x14001c703  mov     [rsp+208h+var_98], r8
0x14001c70b  mov     [rsp+208h+var_90], 2
0x14001c717  mov     [rsp+208h+var_88], rax
0x14001c71f  mov     [rsp+208h+var_80], ecx
0x14001c726  mov     [rsp+208h+var_7C], r12d
0x14001c72e  mov     rax, [rdx+288h]
0x14001c735  mov     [rsp+208h+var_198], rax
0x14001c73a  lea     rax, [rsp+208h+var_198]
0x14001c73f  mov     [rsp+208h+var_78], rax
0x14001c747  mov     rdx, [rsp+208h+var_1A0]
0x14001c74c  mov     [rsp+208h+var_1A0], rdx
0x14001c751  lea     rax, [rsp+208h+var_1A0]
0x14001c756  mov     [rsp+208h+var_68], rax
0x14001c75e  mov     [rsp+208h+var_60], 8
0x14001c76a  lea     rax, [rsp+208h+var_108]
0x14001c772  mov     [rsp+208h+var_1E0], rax
0x14001c777  mov     dword ptr [rsp+208h+var_1E8], 0Bh
0x14001c77f  lea     rdx, byte_140057209
0x14001c786  jmp     loc_14001C433
0x14001c78b  mov     r14, [rsp+208h+var_198]
0x14001c790  shl     r14, 0Ch
0x14001c794  mov     rdi, [rsp+208h+var_1B0]
  ... truncated ...
```
