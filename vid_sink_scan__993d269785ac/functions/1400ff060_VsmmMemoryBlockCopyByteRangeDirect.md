# VsmmMemoryBlockCopyByteRangeDirect

- ea: `0x1400ff060`
- end: `0x1400ff8a6`
- name: `VsmmMemoryBlockCopyByteRangeDirect`
- size: `2118`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x14001995c`

## callees

- `0x1400029c0`
- `0x1400068b0`
- `0x140006bf8`
- `0x14000a4e0`
- `0x14000fd30`
- `0x140021650`
- `0x140023008`
- `0x1400b9fc8`
- `0x1400ff060`

## import_xrefs

- `ntoskrnl!KeInvalidateRangeAllCaches` at `0x1400ff6ba`
- `ntoskrnl!KeInvalidateRangeAllCaches` at `0x1400ff6ba`

## string_xrefs

- `0x1400ff0eb`: `VsmmMemoryBlockCopyByteRangeDirect`
- `0x1400ff262`: `VsmmMemoryBlockCopyByteRangeDirect`
- `0x1400ff3c6`: `VsmmMemoryBlockCopyByteRangeDirect`
- `0x1400ff526`: `VsmmMemoryBlockCopyByteRangeDirect`
- `0x1400ff735`: `VsmmMemoryBlockCopyByteRangeDirect`

## pseudocode

```c
__int64 __fastcall VsmmMemoryBlockCopyByteRangeDirect(__int64 *a1, __int64 a2)
{
  char *v3; // rsi
  __int64 v4; // rcx
  int v5; // edi
  __int64 result; // rax
  __int64 v7; // r8
  __int64 v8; // rax
  int v9; // edx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r8
  __int64 v13; // rax
  int v14; // edx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // rax
  int v18; // edx
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // rax
  int v22; // edx
  __int64 v23; // rcx
  char v24; // r9
  void *v25; // r8
  char v26; // dl
  void *v27; // rcx
  unsigned __int64 i; // rdi
  ULONG v29; // r15d
  int v30; // [rsp+34h] [rbp-304h] BYREF
  int v31; // [rsp+38h] [rbp-300h] BYREF
  int v32; // [rsp+3Ch] [rbp-2FCh] BYREF
  int v33; // [rsp+40h] [rbp-2F8h] BYREF
  int v34; // [rsp+44h] [rbp-2F4h] BYREF
  int v35; // [rsp+48h] [rbp-2F0h] BYREF
  int v36; // [rsp+4Ch] [rbp-2ECh] BYREF
  int v37; // [rsp+50h] [rbp-2E8h] BYREF
  _QWORD v38[2]; // [rsp+58h] [rbp-2E0h] BYREF
  __int64 v39; // [rsp+68h] [rbp-2D0h] BYREF
  __int64 v40; // [rsp+70h] [rbp-2C8h] BYREF
  __int64 v41; // [rsp+78h] [rbp-2C0h] BYREF
  char v42[24]; // [rsp+80h] [rbp-2B8h] BYREF
  char v43[16]; // [rsp+A0h] [rbp-298h] BYREF
  char v44[16]; // [rsp+B0h] [rbp-288h] BYREF
  int *v45; // [rsp+C0h] [rbp-278h]
  __int64 v46; // [rsp+C8h] [rbp-270h]
  int *v47; // [rsp+D0h] [rbp-268h]
  __int64 v48; // [rsp+D8h] [rbp-260h]
  __int64 v49; // [rsp+E0h] [rbp-258h]
  __int64 v50; // [rsp+E8h] [rbp-250h]
  _DWORD *v51; // [rsp+F0h] [rbp-248h]
  __int64 v52; // [rsp+F8h] [rbp-240h]
  __int64 v53; // [rsp+100h] [rbp-238h]
  _DWORD v54[2]; // [rsp+108h] [rbp-230h] BYREF
  _QWORD *v55; // [rsp+110h] [rbp-228h]
  __int64 v56; // [rsp+118h] [rbp-220h]
  char v57[32]; // [rsp+120h] [rbp-218h] BYREF
  char v58[16]; // [rsp+140h] [rbp-1F8h] BYREF
  char v59[16]; // [rsp+150h] [rbp-1E8h] BYREF
  int *v60; // [rsp+160h] [rbp-1D8h]
  __int64 v61; // [rsp+168h] [rbp-1D0h]
  int *v62; // [rsp+170h] [rbp-1C8h]
  __int64 v63; // [rsp+178h] [rbp-1C0h]
  __int64 v64; // [rsp+180h] [rbp-1B8h]
  __int64 v65; // [rsp+188h] [rbp-1B0h]
  _DWORD *v66; // [rsp+190h] [rbp-1A8h]
  __int64 v67; // [rsp+198h] [rbp-1A0h]
  __int64 v68; // [rsp+1A0h] [rbp-198h]
  _DWORD v69[2]; // [rsp+1A8h] [rbp-190h] BYREF
  __int64 *v70; // [rsp+1B0h] [rbp-188h]
  __int64 v71; // [rsp+1B8h] [rbp-180h]
  char v72[32]; // [rsp+1C0h] [rbp-178h] BYREF
  char v73[16]; // [rsp+1E0h] [rbp-158h] BYREF
  char v74[16]; // [rsp+1F0h] [rbp-148h] BYREF
  int *v75; // [rsp+200h] [rbp-138h]
  __int64 v76; // [rsp+208h] [rbp-130h]
  int *v77; // [rsp+210h] [rbp-128h]
  __int64 v78; // [rsp+218h] [rbp-120h]
  __int64 v79; // [rsp+220h] [rbp-118h]
  __int64 v80; // [rsp+228h] [rbp-110h]
  _DWORD *v81; // [rsp+230h] [rbp-108h]
  __int64 v82; // [rsp+238h] [rbp-100h]
  __int64 v83; // [rsp+240h] [rbp-F8h]
  _DWORD v84[2]; // [rsp+248h] [rbp-F0h] BYREF
  __int64 *v85; // [rsp+250h] [rbp-E8h]
  __int64 v86; // [rsp+258h] [rbp-E0h]
  char v87[32]; // [rsp+260h] [rbp-D8h] BYREF
  char v88[16]; // [rsp+280h] [rbp-B8h] BYREF
  char v89[16]; // [rsp+290h] [rbp-A8h] BYREF
  int *v90; // [rsp+2A0h] [rbp-98h]
  __int64 v91; // [rsp+2A8h] [rbp-90h]
  int *v92; // [rsp+2B0h] [rbp-88h]
  __int64 v93; // [rsp+2B8h] [rbp-80h]
  __int64 v94; // [rsp+2C0h] [rbp-78h]
  __int64 v95; // [rsp+2C8h] [rbp-70h]
  _DWORD *v96; // [rsp+2D0h] [rbp-68h]
  __int64 v97; // [rsp+2D8h] [rbp-60h]
  __int64 v98; // [rsp+2E0h] [rbp-58h]
  _DWORD v99[2]; // [rsp+2E8h] [rbp-50h] BYREF
  __int64 *v100; // [rsp+2F0h] [rbp-48h]
  __int64 v101; // [rsp+2F8h] [rbp-40h]

  v38[1] = a1;
  v30 = 0;
  v3 = (char *)(a1[3] + a2);
  v4 = a1[2];
  if ( !v4 )
  {
    if ( (*((_DWORD *)a1 + 11) & 1) != 0 )
    {
      v24 = *((_BYTE *)a1 + 41);
      v25 = (void *)a1[1];
      v26 = (*(_DWORD *)(*a1 + 20) & 8) != 0;
      v27 = v3;
    }
    else
    {
      v24 = (*(_DWORD *)(*a1 + 20) & 8) != 0;
      v25 = v3;
      v26 = *((_BYTE *)a1 + 41);
      v27 = (void *)a1[1];
    }
    VsmmpCopyFromModeToMode(v27, v26, v25, v24, a1[4]);
    goto LABEL_27;
  }
  if ( (unsigned __int64)a1[4] > 0xFFFFFFFF )
  {
    v5 = -1073741637;
    result = (unsigned int)dword_140064110;
    if ( (unsigned int)dword_140064110 > 2 )
    {
      result = tlgKeywordOn(&dword_140064110, 256);
      if ( (_BYTE)result )
      {
        tlgCreate1Sz_char(v58, "VsmmMemoryBlockCopyByteRangeDirect");
        tlgCreate1Sz_char(v59, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemoryblock.c");
        v30 = 6683;
        v60 = &v30;
        v61 = 4;
        v33 = -1073741637;
        v62 = &v33;
        v63 = 4;
        v7 = *a1;
        v64 = *(_QWORD *)(*a1 + 8) + 656LL;
        v65 = 16;
        v8 = *(_QWORD *)(v7 + 8);
        v9 = *(unsigned __int16 *)(v8 + 120);
        v10 = *(_QWORD *)(v8 + 128);
        v66 = v69;
        v67 = 2;
        v68 = v10;
        v69[0] = v9;
        v69[1] = 0;
        v39 = *(_QWORD *)(*(_QWORD *)(v7 + 8) + 648LL);
        v70 = &v39;
        v71 = 8;
        result = tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, byte_140059309, 0, 0, 10, v57);
      }
    }
    goto LABEL_37;
  }
  v11 = *((unsigned int *)a1 + 8);
  if ( (*((_DWORD *)a1 + 11) & 1) != 0 )
  {
    result = VmCompressUnpackEx(v4, v3, v11, &v30);
    v5 = result;
    if ( (int)result < 0 )
    {
      if ( (unsigned int)dword_140064110 > 2 )
      {
        result = tlgKeywordOn(&dword_140064110, 256);
        if ( (_BYTE)result )
        {
          tlgCreate1Sz_char(v73, "VsmmMemoryBlockCopyByteRangeDirect");
          tlgCreate1Sz_char(v74, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemoryblock.c");
          v34 = 6704;
          v75 = &v34;
          v76 = 4;
          v35 = v5;
          v77 = &v35;
          v78 = 4;
          v12 = *a1;
          v79 = *(_QWORD *)(*a1 + 8) + 656LL;
          v80 = 16;
          v13 = *(_QWORD *)(v12 + 8);
          v14 = *(unsigned __int16 *)(v13 + 120);
          v15 = *(_QWORD *)(v13 + 128);
          v81 = v84;
          v82 = 2;
          v83 = v15;
          v84[0] = v14;
          v84[1] = 0;
          v40 = *(_QWORD *)(*(_QWORD *)(v12 + 8) + 648LL);
          v85 = &v40;
          v86 = 8;
          result = tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, &byte_140059377, 0, 0, 10, v72);
        }
      }
      goto LABEL_37;
    }
    if ( v30 != a1[4] )
    {
      v5 = -1073741811;
      result = (unsigned int)dword_140064110;
      if ( (unsigned int)dword_140064110 > 2 )
      {
        result = tlgKeywordOn(&dword_140064110, 256);
        if ( (_BYTE)result )
        {
          tlgCreate1Sz_char(v88, "VsmmMemoryBlockCopyByteRangeDirect");
          tlgCreate1Sz_char(v89, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemoryblock.c");
          v36 = 6719;
          v90 = &v36;
          v91 = 4;
          v37 = -1073741811;
          v92 = &v37;
          v93 = 4;
          v16 = *a1;
          v94 = *(_QWORD *)(*a1 + 8) + 656LL;
          v95 = 16;
          v17 = *(_QWORD *)(v16 + 8);
          v18 = *(unsigned __int16 *)(v17 + 120);
          v19 = *(_QWORD *)(v17 + 128);
          v96 = v99;
          v97 = 2;
          v98 = v19;
          v99[0] = v18;
          v99[1] = 0;
          v41 = *(_QWORD *)(*(_QWORD *)(v16 + 8) + 648LL);
          v100 = &v41;
          v101 = 8;
          result = tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, byte_1400593E5, 0, 0, 10, v87);
        }
      }
      goto LABEL_37;
    }
LABEL_27:
    result = *((unsigned int *)a1 + 11);
    if ( (result & 1) != 0 )
    {
      if ( *((_BYTE *)a1 + 40) )
      {
        for ( i = a1[4]; i; i -= v29 )
        {
          v29 = i;
          if ( i >= 0xFFFFFFFF )
            v29 = -1;
          KeInvalidateRangeAllCaches(v3, v29);
          result = v29;
          v3 += v29;
        }
      }
      else if ( (*(_DWORD *)(*a1 + 20) & 0x2000) != 0 )
      {
        result = VsmmDaxFileFlushVaRange(*(_QWORD *)(*a1 + 768), v3, a1[4], 0);
        v5 = result;
        if ( (int)result < 0 )
          goto LABEL_37;
      }
    }
    v5 = 0;
    goto LABEL_37;
  }
  v5 = VmCompressPackEx(v4, v3, v11);
  if ( v5 >= 0 )
    goto LABEL_27;
  result = (unsigned int)dword_140064110;
  if ( (unsigned int)dword_140064110 > 2 )
  {
    result = tlgKeywordOn(&dword_140064110, 256);
    if ( (_BYTE)result )
    {
      tlgCreate1Sz_char(v43, "VsmmMemoryBlockCopyByteRangeDirect");
      tlgCreate1Sz_char(v44, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemoryblock.c");
      v31 = 6735;
      v45 = &v31;
      v46 = 4;
      v32 = v5;
      v47 = &v32;
      v48 = 4;
      v20 = *a1;
      v49 = *(_QWORD *)(*a1 + 8) + 656LL;
      v50 = 16;
      v21 = *(_QWORD *)(v20 + 8);
      v22 = *(unsigned __int16 *)(v21 + 120);
      v23 = *(_QWORD *)(v21 + 128);
      v51 = v54;
      v52 = 2;
      v53 = v23;
      v54[0] = v22;
      v54[1] = 0;
      v38[0] = *(_QWORD *)(*(_QWORD *)(v20 + 8) + 648LL);
      v55 = v38;
      v56 = 8;
      result = tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, byte_140059453, 0, 0, 10, v42);
    }
  }
LABEL_37:
  *((_DWORD *)a1 + 12) = v5;
  return result;
}

```

## disassembly

```asm
0x1400ff060  mov     [rsp+arg_10], rbx
0x1400ff065  push    rsi
0x1400ff066  push    rdi
0x1400ff067  push    r12
0x1400ff069  push    r14
0x1400ff06b  push    r15
0x1400ff06d  sub     rsp, 310h
0x1400ff074  mov     rax, cs:__security_cookie
0x1400ff07b  xor     rax, rsp
0x1400ff07e  mov     [rsp+338h+var_38], rax
0x1400ff086  mov     rsi, rdx
0x1400ff089  mov     rbx, rcx
0x1400ff08c  mov     [rsp+338h+var_2D8], rcx
0x1400ff091  xor     r12d, r12d
0x1400ff094  mov     [rsp+338h+var_304], r12d
0x1400ff099  add     rsi, [rcx+18h]
0x1400ff09d  mov     rcx, [rcx+10h]
0x1400ff0a1  test    rcx, rcx
0x1400ff0a4  jz      loc_1400FF64B
0x1400ff0aa  mov     r14d, 0FFFFFFFFh
0x1400ff0b0  cmp     [rbx+20h], r14
0x1400ff0b4  jbe     loc_1400FF210
0x1400ff0ba  mov     edi, 0C00000BBh
0x1400ff0bf  mov     [rsp+338h+var_308], edi
0x1400ff0c3  mov     eax, cs:dword_140064110
0x1400ff0c9  cmp     eax, 2
0x1400ff0cc  jbe     loc_1400FF20B
0x1400ff0d2  mov     edx, 100h
0x1400ff0d7  lea     rcx, dword_140064110
0x1400ff0de  call    _tlgKeywordOn
0x1400ff0e3  test    al, al
0x1400ff0e5  jz      loc_1400FF20B
0x1400ff0eb  lea     rdx, aVsmmmemorybloc_22; "VsmmMemoryBlockCopyByteRangeDirect"
0x1400ff0f2  lea     rcx, [rsp+338h+var_1F8]
0x1400ff0fa  call    _tlgCreate1Sz_char
0x1400ff0ff  lea     rdx, aOnecoreVmVidSy_39; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemory"...
0x1400ff106  lea     rcx, [rsp+338h+var_1E8]
0x1400ff10e  call    _tlgCreate1Sz_char
0x1400ff113  mov     [rsp+338h+var_304], 1A1Bh
0x1400ff11b  lea     rax, [rsp+338h+var_304]
0x1400ff120  mov     [rsp+338h+var_1D8], rax
0x1400ff128  mov     [rsp+338h+var_1D0], 4
0x1400ff134  mov     [rsp+338h+var_2F8], edi
0x1400ff138  lea     rcx, [rsp+338h+var_2F8]
0x1400ff13d  mov     [rsp+338h+var_1C8], rcx
0x1400ff145  mov     [rsp+338h+var_1C0], 4
0x1400ff151  mov     r8, [rbx]
0x1400ff154  mov     rax, [r8+8]
0x1400ff158  add     rax, 290h
0x1400ff15e  mov     [rsp+338h+var_1B8], rax
0x1400ff166  mov     [rsp+338h+var_1B0], 10h
0x1400ff172  mov     rax, [r8+8]
0x1400ff176  movzx   edx, word ptr [rax+78h]
0x1400ff17a  mov     rcx, [rax+80h]
0x1400ff181  lea     rax, [rsp+338h+var_190]
0x1400ff189  mov     [rsp+338h+var_1A8], rax
0x1400ff191  mov     [rsp+338h+var_1A0], 2
0x1400ff19d  mov     [rsp+338h+var_198], rcx
0x1400ff1a5  mov     [rsp+338h+var_190], edx
0x1400ff1ac  mov     [rsp+338h+var_18C], r12d
0x1400ff1b4  mov     rax, [r8+8]
0x1400ff1b8  mov     rdx, [rax+288h]
0x1400ff1bf  mov     [rsp+338h+var_2D0], rdx
0x1400ff1c4  lea     rax, [rsp+338h+var_2D0]
0x1400ff1c9  mov     [rsp+338h+var_188], rax
0x1400ff1d1  mov     [rsp+338h+var_180], 8
0x1400ff1dd  lea     rax, [rsp+338h+var_218]
0x1400ff1e5  mov     [rsp+338h+var_310], rax
0x1400ff1ea  mov     dword ptr [rsp+338h+var_318], 0Ah
0x1400ff1f2  xor     r9d, r9d
0x1400ff1f5  xor     r8d, r8d
0x1400ff1f8  lea     rdx, byte_140059309
0x1400ff1ff  lea     rcx, dword_140064110
0x1400ff206  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400ff20b  jmp     loc_1400FF87A
0x1400ff210  mov     r8d, [rbx+20h]
0x1400ff214  mov     eax, [rbx+2Ch]
0x1400ff217  mov     rdx, rsi
0x1400ff21a  test    al, 1
0x1400ff21c  jz      loc_1400FF4EB
0x1400ff222  lea     r9, [rsp+338h+var_304]
0x1400ff227  call    VmCompressUnpackEx
0x1400ff22c  mov     edi, eax
0x1400ff22e  mov     [rsp+338h+var_308], eax
0x1400ff232  test    eax, eax
0x1400ff234  jns     loc_1400FF387
0x1400ff23a  mov     ecx, cs:dword_140064110
0x1400ff240  cmp     ecx, 2
0x1400ff243  jbe     loc_1400FF382
0x1400ff249  mov     edx, 100h
0x1400ff24e  lea     rcx, dword_140064110
0x1400ff255  call    _tlgKeywordOn
0x1400ff25a  test    al, al
0x1400ff25c  jz      loc_1400FF382
0x1400ff262  lea     rdx, aVsmmmemorybloc_22; "VsmmMemoryBlockCopyByteRangeDirect"
0x1400ff269  lea     rcx, [rsp+338h+var_158]
0x1400ff271  call    _tlgCreate1Sz_char
0x1400ff276  lea     rdx, aOnecoreVmVidSy_39; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemory"...
0x1400ff27d  lea     rcx, [rsp+338h+var_148]
0x1400ff285  call    _tlgCreate1Sz_char
0x1400ff28a  mov     [rsp+338h+var_2F4], 1A30h
0x1400ff292  lea     rax, [rsp+338h+var_2F4]
0x1400ff297  mov     [rsp+338h+var_138], rax
0x1400ff29f  mov     [rsp+338h+var_130], 4
0x1400ff2ab  mov     [rsp+338h+var_2F0], edi
0x1400ff2af  lea     rcx, [rsp+338h+var_2F0]
0x1400ff2b4  mov     [rsp+338h+var_128], rcx
0x1400ff2bc  mov     [rsp+338h+var_120], 4
0x1400ff2c8  mov     r8, [rbx]
0x1400ff2cb  mov     rax, [r8+8]
0x1400ff2cf  add     rax, 290h
0x1400ff2d5  mov     [rsp+338h+var_118], rax
0x1400ff2dd  mov     [rsp+338h+var_110], 10h
0x1400ff2e9  mov     rax, [r8+8]
0x1400ff2ed  movzx   edx, word ptr [rax+78h]
0x1400ff2f1  mov     rcx, [rax+80h]
0x1400ff2f8  lea     rax, [rsp+338h+var_F0]
0x1400ff300  mov     [rsp+338h+var_108], rax
0x1400ff308  mov     [rsp+338h+var_100], 2
0x1400ff314  mov     [rsp+338h+var_F8], rcx
0x1400ff31c  mov     [rsp+338h+var_F0], edx
0x1400ff323  mov     [rsp+338h+var_EC], r12d
0x1400ff32b  mov     rax, [r8+8]
0x1400ff32f  mov     rcx, [rax+288h]
0x1400ff336  mov     [rsp+338h+var_2C8], rcx
0x1400ff33b  lea     rax, [rsp+338h+var_2C8]
0x1400ff340  mov     [rsp+338h+var_E8], rax
0x1400ff348  mov     [rsp+338h+var_E0], 8
0x1400ff354  lea     rax, [rsp+338h+var_178]
0x1400ff35c  mov     [rsp+338h+var_310], rax
0x1400ff361  mov     dword ptr [rsp+338h+var_318], 0Ah
0x1400ff369  xor     r9d, r9d
0x1400ff36c  xor     r8d, r8d
0x1400ff36f  lea     rdx, byte_140059377
0x1400ff376  lea     rcx, dword_140064110
0x1400ff37d  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400ff382  jmp     loc_1400FF87A
0x1400ff387  mov     eax, [rsp+338h+var_304]
0x1400ff38b  cmp     rax, [rbx+20h]
0x1400ff38f  jz      loc_1400FF693
0x1400ff395  mov     edi, 0C000000Dh
0x1400ff39a  mov     [rsp+338h+var_308], edi
0x1400ff39e  mov     eax, cs:dword_140064110
0x1400ff3a4  cmp     eax, 2
0x1400ff3a7  jbe     loc_1400FF4E6
0x1400ff3ad  mov     edx, 100h
0x1400ff3b2  lea     rcx, dword_140064110
0x1400ff3b9  call    _tlgKeywordOn
0x1400ff3be  test    al, al
0x1400ff3c0  jz      loc_1400FF4E6
0x1400ff3c6  lea     rdx, aVsmmmemorybloc_22; "VsmmMemoryBlockCopyByteRangeDirect"
0x1400ff3cd  lea     rcx, [rsp+338h+var_B8]
0x1400ff3d5  call    _tlgCreate1Sz_char
0x1400ff3da  lea     rdx, aOnecoreVmVidSy_39; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemory"...
0x1400ff3e1  lea     rcx, [rsp+338h+var_A8]
0x1400ff3e9  call    _tlgCreate1Sz_char
0x1400ff3ee  mov     [rsp+338h+var_2EC], 1A3Fh
0x1400ff3f6  lea     rax, [rsp+338h+var_2EC]
0x1400ff3fb  mov     [rsp+338h+var_98], rax
0x1400ff403  mov     [rsp+338h+var_90], 4
0x1400ff40f  mov     [rsp+338h+var_2E8], edi
0x1400ff413  lea     rcx, [rsp+338h+var_2E8]
0x1400ff418  mov     [rsp+338h+var_88], rcx
0x1400ff420  mov     [rsp+338h+var_80], 4
0x1400ff42c  mov     r8, [rbx]
0x1400ff42f  mov     rax, [r8+8]
0x1400ff433  add     rax, 290h
0x1400ff439  mov     [rsp+338h+var_78], rax
0x1400ff441  mov     [rsp+338h+var_70], 10h
0x1400ff44d  mov     rax, [r8+8]
0x1400ff451  movzx   edx, word ptr [rax+78h]
0x1400ff455  mov     rcx, [rax+80h]
0x1400ff45c  lea     rax, [rsp+338h+var_50]
0x1400ff464  mov     [rsp+338h+var_68], rax
0x1400ff46c  mov     [rsp+338h+var_60], 2
0x1400ff478  mov     [rsp+338h+var_58], rcx
0x1400ff480  mov     [rsp+338h+var_50], edx
0x1400ff487  mov     [rsp+338h+var_4C], r12d
0x1400ff48f  mov     rax, [r8+8]
0x1400ff493  mov     rcx, [rax+288h]
0x1400ff49a  mov     [rsp+338h+var_2C0], rcx
0x1400ff49f  lea     rax, [rsp+338h+var_2C0]
0x1400ff4a4  mov     [rsp+338h+var_48], rax
0x1400ff4ac  mov     [rsp+338h+var_40], 8
0x1400ff4b8  lea     rax, [rsp+338h+var_D8]
0x1400ff4c0  mov     [rsp+338h+var_310], rax
0x1400ff4c5  mov     dword ptr [rsp+338h+var_318], 0Ah
0x1400ff4cd  xor     r9d, r9d
0x1400ff4d0  xor     r8d, r8d
0x1400ff4d3  lea     rdx, byte_1400593E5
0x1400ff4da  lea     rcx, dword_140064110
0x1400ff4e1  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400ff4e6  jmp     loc_1400FF87A
0x1400ff4eb  call    VmCompressPackEx
0x1400ff4f0  mov     edi, eax
0x1400ff4f2  mov     [rsp+338h+var_308], eax
0x1400ff4f6  test    eax, eax
0x1400ff4f8  jns     loc_1400FF693
0x1400ff4fe  mov     eax, cs:dword_140064110
0x1400ff504  cmp     eax, 2
0x1400ff507  jbe     loc_1400FF646
0x1400ff50d  mov     edx, 100h
0x1400ff512  lea     rcx, dword_140064110
0x1400ff519  call    _tlgKeywordOn
0x1400ff51e  test    al, al
0x1400ff520  jz      loc_1400FF646
0x1400ff526  lea     rdx, aVsmmmemorybloc_22; "VsmmMemoryBlockCopyByteRangeDirect"
0x1400ff52d  lea     rcx, [rsp+338h+var_298]
0x1400ff535  call    _tlgCreate1Sz_char
0x1400ff53a  lea     rdx, aOnecoreVmVidSy_39; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemory"...
0x1400ff541  lea     rcx, [rsp+338h+var_288]
0x1400ff549  call    _tlgCreate1Sz_char
0x1400ff54e  mov     [rsp+338h+var_300], 1A4Fh
0x1400ff556  lea     rax, [rsp+338h+var_300]
0x1400ff55b  mov     [rsp+338h+var_278], rax
0x1400ff563  mov     [rsp+338h+var_270], 4
0x1400ff56f  mov     [rsp+338h+var_2FC], edi
0x1400ff573  lea     rcx, [rsp+338h+var_2FC]
0x1400ff578  mov     [rsp+338h+var_268], rcx
0x1400ff580  mov     [rsp+338h+var_260], 4
0x1400ff58c  mov     r8, [rbx]
0x1400ff58f  mov     rax, [r8+8]
0x1400ff593  add     rax, 290h
0x1400ff599  mov     [rsp+338h+var_258], rax
0x1400ff5a1  mov     [rsp+338h+var_250], 10h
0x1400ff5ad  mov     rax, [r8+8]
0x1400ff5b1  movzx   edx, word ptr [rax+78h]
0x1400ff5b5  mov     rcx, [rax+80h]
0x1400ff5bc  lea     rax, [rsp+338h+var_230]
0x1400ff5c4  mov     [rsp+338h+var_248], rax
0x1400ff5cc  mov     [rsp+338h+var_240], 2
0x1400ff5d8  mov     [rsp+338h+var_238], rcx
0x1400ff5e0  mov     [rsp+338h+var_230], edx
0x1400ff5e7  mov     [rsp+338h+var_22C], r12d
0x1400ff5ef  mov     rax, [r8+8]
0x1400ff5f3  mov     rcx, [rax+288h]
0x1400ff5fa  mov     [rsp+338h+var_2E0], rcx
0x1400ff5ff  lea     rax, [rsp+338h+var_2E0]
0x1400ff604  mov     [rsp+338h+var_228], rax
0x1400ff60c  mov     [rsp+338h+var_220], 8
0x1400ff618  lea     rax, [rsp+338h+var_2B8]
0x1400ff620  mov     [rsp+338h+var_310], rax
0x1400ff625  mov     dword ptr [rsp+338h+var_318], 0Ah
0x1400ff62d  xor     r9d, r9d
0x1400ff630  xor     r8d, r8d
0x1400ff633  lea     rdx, byte_140059453
0x1400ff63a  lea     rcx, dword_140064110
0x1400ff641  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400ff646  jmp     loc_1400FF87A
0x1400ff64b  mov     rax, [rbx]
0x1400ff64e  mov     ecx, [rax+14h]
0x1400ff651  shr     ecx, 3
0x1400ff654  and     cl, 1
0x1400ff657  mov     rdx, [rbx+20h]
0x1400ff65b  mov     r10b, [rbx+29h]
0x1400ff65f  mov     r11, [rbx+8]
0x1400ff663  mov     eax, [rbx+2Ch]
0x1400ff666  mov     [rsp+338h+var_318], rdx
0x1400ff66b  test    al, 1
0x1400ff66d  jz      short loc_1400FF67C
0x1400ff66f  mov     r9b, r10b
0x1400ff672  mov     r8, r11
0x1400ff675  mov     dl, cl
0x1400ff677  mov     rcx, rsi
0x1400ff67a  jmp     short loc_1400FF688
0x1400ff67c  mov     r9b, cl
0x1400ff67f  mov     r8, rsi
0x1400ff682  mov     dl, r10b
0x1400ff685  mov     rcx, r11
0x1400ff688  call    VsmmpCopyFromModeToMode
0x1400ff68d  mov     r14d, 0FFFFFFFFh
0x1400ff693  mov     eax, [rbx+2Ch]
0x1400ff696  test    al, 1
0x1400ff698  jz      short loc_1400FF6FF
0x1400ff69a  cmp     [rbx+28h], r12b
0x1400ff69e  jz      short loc_1400FF6D3
0x1400ff6a0  mov     rdi, [rbx+20h]
0x1400ff6a4  test    rdi, rdi
0x1400ff6a7  jz      short loc_1400FF6FF
0x1400ff6a9  cmp     rdi, r14
0x1400ff6ac  mov     r15d, edi
0x1400ff6af  jb      short loc_1400FF6B4
0x1400ff6b1  mov     r15d, r14d
0x1400ff6b4  mov     edx, r15d; Length
0x1400ff6b7  mov     rcx, rsi; BaseAddress
0x1400ff6ba  call    cs:__imp_KeInvalidateRangeAllCaches
0x1400ff6c1  nop     dword ptr [rax+rax+00h]
0x1400ff6c6  mov     eax, r15d
0x1400ff6c9  add     rsi, rax
0x1400ff6cc  sub     rdi, rax
0x1400ff6cf  jnz     short loc_1400FF6A9
0x1400ff6d1  jmp     short loc_1400FF6FF
0x1400ff6d3  mov     rcx, [rbx]
0x1400ff6d6  test    dword ptr [rcx+14h], 2000h
0x1400ff6dd  jz      short loc_1400FF6FF
0x1400ff6df  mov     r9d, r12d
0x1400ff6e2  mov     r8, [rbx+20h]
0x1400ff6e6  mov     rdx, rsi
0x1400ff6e9  mov     rcx, [rcx+300h]
0x1400ff6f0  call    VsmmDaxFileFlushVaRange
  ... truncated ...
```
