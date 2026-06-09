# VsmmpReadEncryptMbpRange

- ea: `0x1400199c4`
- end: `0x14001a955`
- name: `VsmmpReadEncryptMbpRange`
- size: `3985`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int, __int64, unsigned __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400295e0`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x14000a4e0`
- `0x14000bc64`
- `0x1400199c4`
- `0x140021240`
- `0x140021444`
- `0x140021474`
- `0x140021650`
- `0x140021800`
- `0x140021d40`
- `0x1400280d0`
- `0x1400a984c`
- `0x1400edc70`
- `0x1400f8bc8`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x140019d9e`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140019d9e`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14001a337`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14001a337`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140019a71`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140019a71`

## string_xrefs

- `0x140019af4`: `VsmmpReadEncryptMbpRange`
- `0x140019c5e`: `VsmmpReadEncryptMbpRange`
- `0x140019e41`: `VsmmpReadEncryptMbpRange`
- `0x140019f82`: `VsmmpReadEncryptMbpRange`
- `0x14001a109`: `VsmmpReadEncryptMbpRange`
- `0x14001a241`: `VsmmpReadEncryptMbpRange`
- `0x14001a385`: `VsmmpReadEncryptMbpRange`
- `0x14001a5d8`: `VsmmpReadEncryptMbpRange`
- `0x14001a791`: `VsmmpReadEncryptMbpRange`

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
  char *v9; // r15
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
  char *v39; // rax
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
  char *v75; // [rsp+B8h] [rbp-150h]
  char *v76; // [rsp+C0h] [rbp-148h] BYREF
  _QWORD *v77; // [rsp+C8h] [rbp-140h]
  char *v78; // [rsp+D0h] [rbp-138h]
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
          if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
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
          v28 = &byte_140056B67;
          goto LABEL_11;
        }
        v38 = v69 << 12;
        v39 = (char *)VidManagedBufferListElementRequest(v66 + 10064, v69 << 12);
        v10 = v39;
        v78 = v39;
        if ( !v39 )
        {
          v14 = 3221225626LL;
          v15 = -1073741670;
          if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
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
          v28 = byte_1400568D3;
          goto LABEL_10;
        }
        if ( v21 )
        {
          v9 = (char *)VidManagedBufferListElementRequest(v66 + 9904, v38);
          v75 = v9;
          if ( !v9 )
          {
            v14 = 3221225626LL;
            v15 = -1073741670;
            if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
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
            v28 = byte_140056941;
            goto LABEL_10;
          }
          Entry = ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(96LL * (v21 - 1) + v67 + 224));
          if ( !Entry )
          {
            v14 = 3221225626LL;
            v15 = -1073741670;
            if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
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
            v28 = &byte_1400569AF;
            goto LABEL_10;
          }
          v39 = v9;
        }
        v15 = VsmmpReadMemoryBlockByteRange(v70, v68 << 12, v69 << 12, a4 & 0xFFFFFFF3, v39, v38, 0, 0, &v76);
        if ( v15 >= 0 )
        {
          v53 = (_DWORD)v69 << 12;
          if ( v21 )
          {
            DataAlignment = VsmmCryptGetDataAlignment();
            v54 = VsmmCompressionFormatToVmCompress(v21, (unsigned int)(2 * (((_DWORD)v69 << 11) - DataAlignment)));
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
          if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
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
            tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, &byte_1400567CF, 0, 0, 12, v82);
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
      if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
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
        v28 = byte_140056AF9;
        goto LABEL_10;
      }
    }
    else
    {
      v14 = 3221225485LL;
      v15 = -1073741811;
      if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
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
        v28 = byte_140056A8B;
LABEL_10:
        v68 = v27;
        v96 = &v68;
        v63 = 10;
LABEL_11:
        v97 = 8;
        tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, v28, 0, 0, v63, v82);
        goto LABEL_12;
      }
    }
    v12 = v66;
    goto LABEL_14;
  }
  v14 = 3221225485LL;
  v15 = -1073741811;
  if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
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
    tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, byte_140056A1D, 0, 0, 10, v82);
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
0x1400199c4  push    rbx
0x1400199c6  push    rsi
0x1400199c7  push    rdi
0x1400199c8  push    r12
0x1400199ca  push    r13
0x1400199cc  push    r14
0x1400199ce  push    r15
0x1400199d0  sub     rsp, 1D0h
0x1400199d7  mov     rax, cs:__security_cookie
0x1400199de  xor     rax, rsp
0x1400199e1  mov     [rsp+208h+var_48], rax
0x1400199e9  mov     ebx, r9d
0x1400199ec  mov     rax, r8
0x1400199ef  mov     [rsp+208h+var_198], rax
0x1400199f4  mov     rdi, rdx
0x1400199f7  mov     [rsp+208h+var_1A0], rdx
0x1400199fc  mov     [rsp+208h+var_190], rcx
0x140019a01  mov     [rsp+208h+var_168], rcx
0x140019a09  mov     [rsp+208h+var_160], rdx
0x140019a11  mov     [rsp+208h+var_158], rax
0x140019a19  mov     [rsp+208h+var_180], ebx
0x140019a20  mov     rax, [rsp+208h+arg_20]
0x140019a28  mov     [rsp+208h+var_170], rax
0x140019a30  mov     rax, [rsp+208h+arg_30]
0x140019a38  mov     [rsp+208h+var_140], rax
0x140019a40  xor     r12d, r12d
0x140019a43  mov     [rsp+208h+var_1B8], r12d
0x140019a48  xorps   xmm0, xmm0
0x140019a4b  movups  [rsp+208h+var_120], xmm0
0x140019a53  mov     [rsp+208h+var_148], r12
0x140019a5b  mov     r15d, r12d
0x140019a5e  mov     [rsp+208h+var_150], r12
0x140019a66  mov     [rsp+208h+Entry], r12
0x140019a6e  mov     r13d, r12d
0x140019a71  call    cs:__imp_KeGetCurrentNodeNumber
0x140019a78  nop     dword ptr [rax+rax+00h]
0x140019a7d  movzx   edx, al
0x140019a80  mov     rax, cs:VidDeviceExtension
0x140019a87  mov     rcx, [rax+108h]
0x140019a8e  mov     r9, [rcx+rdx*8]
0x140019a92  mov     [rsp+208h+var_1A8], r9
0x140019a97  mov     [rsp+208h+var_128], r9
0x140019a9f  mov     r10, [rsp+208h+var_190]
0x140019aa4  mov     rsi, [r10+8]
0x140019aa8  mov     [rsp+208h+var_1B0], rsi
0x140019aad  mov     [rsp+208h+var_130], rsi
0x140019ab5  mov     eax, [rsi+27F0h]
0x140019abb  test    al, 1
0x140019abd  jnz     loc_140019C10
0x140019ac3  mov     r8d, 0C000000Dh
0x140019ac9  mov     edi, r8d
0x140019acc  mov     eax, cs:dword_140064110
0x140019ad2  cmp     eax, 2
0x140019ad5  jbe     loc_140019D77
0x140019adb  mov     edx, 100h
0x140019ae0  lea     rcx, dword_140064110
0x140019ae7  call    _tlgKeywordOn
0x140019aec  test    al, al
0x140019aee  jz      loc_140019D77
0x140019af4  lea     rdx, aVsmmpreadencry; "VsmmpReadEncryptMbpRange"
0x140019afb  lea     rcx, [rsp+208h+var_E8]
0x140019b03  call    _tlgCreate1Sz_char
0x140019b08  lea     rdx, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x140019b0f  lea     rcx, [rsp+208h+var_D8]
0x140019b17  call    _tlgCreate1Sz_char
0x140019b1c  mov     [rsp+208h+var_1B8], 3D9h
0x140019b24  lea     rax, [rsp+208h+var_1B8]
0x140019b29  mov     [rsp+208h+var_C8], rax
0x140019b31  mov     [rsp+208h+var_C0], 4
0x140019b3d  mov     [rsp+208h+var_1B4], r8d
0x140019b42  lea     rcx, [rsp+208h+var_1B4]
0x140019b47  mov     [rsp+208h+var_B8], rcx
0x140019b4f  mov     [rsp+208h+var_B0], 4
0x140019b5b  mov     rdx, [r10+8]
0x140019b5f  lea     rax, [rdx+290h]
0x140019b66  mov     [rsp+208h+var_A8], rax
0x140019b6e  mov     [rsp+208h+var_A0], 10h
0x140019b7a  movzx   ecx, word ptr [rdx+78h]
0x140019b7e  mov     rax, [rdx+80h]
0x140019b85  lea     r8, [rsp+208h+var_80]
0x140019b8d  mov     [rsp+208h+var_98], r8
0x140019b95  mov     [rsp+208h+var_90], 2
0x140019ba1  mov     [rsp+208h+var_88], rax
0x140019ba9  mov     [rsp+208h+var_80], ecx
0x140019bb0  mov     [rsp+208h+var_7C], r12d
0x140019bb8  mov     rax, [rdx+288h]
0x140019bbf  mov     [rsp+208h+var_1A0], rax
0x140019bc4  lea     rax, [rsp+208h+var_1A0]
0x140019bc9  mov     [rsp+208h+var_78], rax
0x140019bd1  mov     [rsp+208h+var_70], 8
0x140019bdd  lea     rax, [rsp+208h+var_108]
0x140019be5  mov     [rsp+208h+var_1E0], rax
0x140019bea  mov     dword ptr [rsp+208h+var_1E8], 0Ah
0x140019bf2  xor     r9d, r9d
0x140019bf5  xor     r8d, r8d
0x140019bf8  lea     rdx, byte_140056A1D
0x140019bff  lea     rcx, dword_140064110
0x140019c06  call    _tlgWriteTransfer_EtwWriteTransfer
0x140019c0b  jmp     loc_140019D72
0x140019c10  mov     esi, ebx
0x140019c12  shr     esi, 2
0x140019c15  and     esi, 3
0x140019c18  jz      loc_140019DFD
0x140019c1e  mov     r14d, 4
0x140019c24  test    r14b, al
0x140019c27  jnz     loc_140019DFD
0x140019c2d  mov     r8d, 0C000000Dh
0x140019c33  mov     edi, r8d
0x140019c36  mov     eax, cs:dword_140064110
0x140019c3c  cmp     eax, 2
0x140019c3f  jbe     loc_14001A94B
0x140019c45  mov     edx, 100h
0x140019c4a  lea     rcx, dword_140064110
0x140019c51  call    _tlgKeywordOn
0x140019c56  test    al, al
0x140019c58  jz      loc_14001A94B
0x140019c5e  lea     rdx, aVsmmpreadencry; "VsmmpReadEncryptMbpRange"
0x140019c65  lea     rcx, [rsp+208h+var_E8]
0x140019c6d  call    _tlgCreate1Sz_char
0x140019c72  lea     rdx, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x140019c79  lea     rcx, [rsp+208h+var_D8]
0x140019c81  call    _tlgCreate1Sz_char
0x140019c86  mov     [rsp+208h+var_1B4], 3E1h
0x140019c8e  lea     rax, [rsp+208h+var_1B4]
0x140019c93  mov     [rsp+208h+var_C8], rax
0x140019c9b  mov     [rsp+208h+var_C0], r14
0x140019ca3  mov     [rsp+208h+var_1B8], r8d
0x140019ca8  lea     rax, [rsp+208h+var_1B8]
0x140019cad  mov     [rsp+208h+var_B8], rax
0x140019cb5  mov     [rsp+208h+var_B0], r14
0x140019cbd  mov     rdx, [r10+8]
0x140019cc1  lea     rax, [rdx+290h]
0x140019cc8  mov     [rsp+208h+var_A8], rax
0x140019cd0  mov     [rsp+208h+var_A0], 10h
0x140019cdc  movzx   ecx, word ptr [rdx+78h]
0x140019ce0  mov     rax, [rdx+80h]
0x140019ce7  lea     r8, [rsp+208h+var_80]
0x140019cef  mov     [rsp+208h+var_98], r8
0x140019cf7  mov     [rsp+208h+var_90], 2
0x140019d03  mov     [rsp+208h+var_88], rax
0x140019d0b  mov     [rsp+208h+var_80], ecx
0x140019d12  mov     [rsp+208h+var_7C], r12d
0x140019d1a  mov     rax, [rdx+288h]
0x140019d21  lea     rdx, byte_140056A8B
0x140019d28  mov     [rsp+208h+var_1A0], rax
0x140019d2d  lea     rax, [rsp+208h+var_1A0]
0x140019d32  mov     [rsp+208h+var_78], rax
0x140019d3a  lea     rax, [rsp+208h+var_108]
0x140019d42  mov     [rsp+208h+var_1E0], rax
0x140019d47  mov     dword ptr [rsp+208h+var_1E8], 0Ah
0x140019d4f  xor     r9d, r9d
0x140019d52  xor     r8d, r8d
0x140019d55  mov     [rsp+208h+var_70], 8
0x140019d61  lea     rcx, dword_140064110
0x140019d68  call    _tlgWriteTransfer_EtwWriteTransfer
0x140019d6d  mov     rsi, [rsp+208h+var_1B0]
0x140019d72  mov     r9, [rsp+208h+var_1A8]
0x140019d77  mov     rdx, [rsp+208h+Entry]; Entry
0x140019d7f  test    rdx, rdx
0x140019d82  jz      short loc_140019DAA
0x140019d84  shr     ebx, 2
0x140019d87  and     ebx, 3
0x140019d8a  dec     ebx
0x140019d8c  lea     rcx, [rbx+rbx*2]
0x140019d90  shl     rcx, 5
0x140019d94  add     r9, 0E0h
0x140019d9b  add     rcx, r9; Lookaside
0x140019d9e  call    cs:__imp_ExFreeToLookasideListEx
0x140019da5  nop     dword ptr [rax+rax+00h]
0x140019daa  mov     rdx, [rsp+208h+var_150]
0x140019db2  test    rdx, rdx
0x140019db5  jz      short loc_140019DC3
0x140019db7  lea     rcx, [rsi+26B0h]
0x140019dbe  call    VidManagedBufferListElementRelease
0x140019dc3  test    r13, r13
0x140019dc6  jz      short loc_140019DD7
0x140019dc8  lea     rcx, [rsi+2750h]
0x140019dcf  mov     rdx, r13
0x140019dd2  call    VidManagedBufferListElementRelease
0x140019dd7  mov     eax, edi
0x140019dd9  mov     rcx, [rsp+208h+var_48]
0x140019de1  xor     rcx, rsp; StackCookie
0x140019de4  call    __security_check_cookie
0x140019de9  add     rsp, 1D0h
0x140019df0  pop     r15
0x140019df2  pop     r14
0x140019df4  pop     r13
0x140019df6  pop     r12
0x140019df8  pop     rdi
0x140019df9  pop     rsi
0x140019dfa  pop     rbx
0x140019dfb  retn
0x140019dfd  mov     eax, 0FFFFFFFFh
0x140019e02  cmp     [rsp+208h+arg_28], rax
0x140019e0a  jbe     loc_140019F18
0x140019e10  mov     r8d, 0C000000Dh
0x140019e16  mov     edi, r8d
0x140019e19  mov     eax, cs:dword_140064110
0x140019e1f  cmp     eax, 2
0x140019e22  jbe     loc_14001A94B
0x140019e28  mov     edx, 100h
0x140019e2d  lea     rcx, dword_140064110
0x140019e34  call    _tlgKeywordOn
0x140019e39  test    al, al
0x140019e3b  jz      loc_14001A94B
0x140019e41  lea     rdx, aVsmmpreadencry; "VsmmpReadEncryptMbpRange"
0x140019e48  lea     rcx, [rsp+208h+var_E8]
0x140019e50  call    _tlgCreate1Sz_char
0x140019e55  lea     rdx, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x140019e5c  lea     rcx, [rsp+208h+var_D8]
0x140019e64  call    _tlgCreate1Sz_char
0x140019e69  mov     [rsp+208h+var_1B4], 3EBh
0x140019e71  lea     rax, [rsp+208h+var_1B4]
0x140019e76  mov     [rsp+208h+var_C8], rax
0x140019e7e  mov     [rsp+208h+var_C0], 4
0x140019e8a  mov     [rsp+208h+var_1B8], r8d
0x140019e8f  lea     rax, [rsp+208h+var_1B8]
0x140019e94  mov     [rsp+208h+var_B8], rax
0x140019e9c  mov     [rsp+208h+var_B0], 4
0x140019ea8  mov     rdx, [r10+8]
0x140019eac  lea     rax, [rdx+290h]
0x140019eb3  mov     [rsp+208h+var_A8], rax
0x140019ebb  mov     [rsp+208h+var_A0], 10h
0x140019ec7  movzx   ecx, word ptr [rdx+78h]
0x140019ecb  mov     rax, [rdx+80h]
0x140019ed2  lea     r8, [rsp+208h+var_80]
0x140019eda  mov     [rsp+208h+var_98], r8
0x140019ee2  mov     [rsp+208h+var_90], 2
0x140019eee  mov     [rsp+208h+var_88], rax
0x140019ef6  mov     [rsp+208h+var_80], ecx
0x140019efd  mov     [rsp+208h+var_7C], r12d
0x140019f05  mov     rax, [rdx+288h]
0x140019f0c  lea     rdx, byte_140056AF9
0x140019f13  jmp     loc_140019D28
0x140019f18  xorps   xmm0, xmm0
0x140019f1b  movups  [rsp+208h+var_120], xmm0
0x140019f23  mov     [rsp+208h+var_1D8], r12
0x140019f28  lea     rax, [rsp+208h+var_120]
0x140019f30  mov     [rsp+208h+var_1E0], rax
0x140019f35  mov     dword ptr [rsp+208h+var_1E8], r12d
0x140019f3a  mov     r9d, 1
0x140019f40  mov     r8, rdi
0x140019f43  mov     rdx, r10
0x140019f46  mov     rcx, [rsp+208h+var_1B0]
0x140019f4b  call    VsmmGpaRangeLookupGpaByMbp
0x140019f50  mov     edi, eax
0x140019f52  test    eax, eax
0x140019f54  jns     loc_14001A0A7
0x140019f5a  mov     eax, cs:dword_140064110
0x140019f60  cmp     eax, 2
0x140019f63  jbe     loc_140019D6D
0x140019f69  mov     edx, 100h
0x140019f6e  lea     rcx, dword_140064110
0x140019f75  call    _tlgKeywordOn
0x140019f7a  test    al, al
0x140019f7c  jz      loc_140019D6D
0x140019f82  lea     rdx, aVsmmpreadencry; "VsmmpReadEncryptMbpRange"
0x140019f89  lea     rcx, [rsp+208h+var_E8]
0x140019f91  call    _tlgCreate1Sz_char
0x140019f96  lea     rdx, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x140019f9d  lea     rcx, [rsp+208h+var_D8]
0x140019fa5  call    _tlgCreate1Sz_char
0x140019faa  mov     [rsp+208h+var_1B4], 402h
0x140019fb2  lea     rax, [rsp+208h+var_1B4]
0x140019fb7  mov     [rsp+208h+var_C8], rax
0x140019fbf  mov     [rsp+208h+var_C0], 4
0x140019fcb  mov     [rsp+208h+var_1B8], edi
0x140019fcf  lea     rax, [rsp+208h+var_1B8]
0x140019fd4  mov     [rsp+208h+var_B8], rax
0x140019fdc  mov     [rsp+208h+var_B0], 4
0x140019fe8  mov     rcx, [rsp+208h+var_190]
0x140019fed  mov     rdx, [rcx+8]
0x140019ff1  lea     rax, [rdx+290h]
0x140019ff8  mov     [rsp+208h+var_A8], rax
0x14001a000  mov     [rsp+208h+var_A0], 10h
0x14001a00c  movzx   ecx, word ptr [rdx+78h]
0x14001a010  mov     rax, [rdx+80h]
0x14001a017  lea     r8, [rsp+208h+var_80]
0x14001a01f  mov     [rsp+208h+var_98], r8
0x14001a027  mov     [rsp+208h+var_90], 2
0x14001a033  mov     [rsp+208h+var_88], rax
0x14001a03b  mov     [rsp+208h+var_80], ecx
0x14001a042  mov     [rsp+208h+var_7C], r12d
0x14001a04a  mov     rax, [rdx+288h]
0x14001a051  mov     [rsp+208h+var_198], rax
0x14001a056  lea     rax, [rsp+208h+var_198]
0x14001a05b  mov     [rsp+208h+var_78], rax
0x14001a063  mov     rdx, [rsp+208h+var_1A0]
0x14001a068  mov     [rsp+208h+var_1A0], rdx
0x14001a06d  lea     rax, [rsp+208h+var_1A0]
0x14001a072  mov     [rsp+208h+var_68], rax
0x14001a07a  mov     [rsp+208h+var_60], 8
0x14001a086  lea     rax, [rsp+208h+var_108]
0x14001a08e  mov     [rsp+208h+var_1E0], rax
0x14001a093  mov     dword ptr [rsp+208h+var_1E8], 0Bh
0x14001a09b  lea     rdx, byte_140056B67
0x14001a0a2  jmp     loc_140019D4F
0x14001a0a7  mov     r14, [rsp+208h+var_198]
0x14001a0ac  shl     r14, 0Ch
0x14001a0b0  mov     rdi, [rsp+208h+var_1B0]
  ... truncated ...
```
