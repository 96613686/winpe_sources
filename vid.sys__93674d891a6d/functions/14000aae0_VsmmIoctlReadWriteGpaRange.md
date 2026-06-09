# VsmmIoctlReadWriteGpaRange

- ea: `0x14000aae0`
- end: `0x14000ba32`
- name: `VsmmIoctlReadWriteGpaRange`
- size: `3922`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned __int64, char *, unsigned int, char *Address, SIZE_T Length, char, _QWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1400321a4`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x14000a010`
- `0x14000aae0`
- `0x14000ba38`
- `0x14000d4d8`
- `0x140021c60`
- `0x1400254ec`
- `0x140030a00`
- `0x140076780`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x14000acfb`
- `ntoskrnl!ProbeForWrite` at `0x14000acfb`
- `ntoskrnl!ProbeForRead` at `0x14000aced`
- `ntoskrnl!ProbeForRead` at `0x14000aced`

## string_xrefs

- `0x14000abce`: `VsmmIoctlReadWriteGpaRange`
- `0x14000af3b`: `VsmmIoctlReadWriteGpaRange`
- `0x14000b116`: `VsmmIoctlReadWriteGpaRange`
- `0x14000b30b`: `VsmmIoctlReadWriteGpaRange`
- `0x14000b500`: `VsmmIoctlReadWriteGpaRange`
- `0x14000b63a`: `VsmmIoctlReadWriteGpaRange`
- `0x14000b769`: `VsmmIoctlReadWriteGpaRange`
- `0x14000b8c5`: `VsmmIoctlReadWriteGpaRange`

## pseudocode

```c
__int64 __fastcall VsmmIoctlReadWriteGpaRange(
        unsigned __int64 a1,
        unsigned __int64 a2,
        char *a3,
        unsigned int a4,
        char *Address,
        SIZE_T Length,
        char a7,
        _QWORD *a8)
{
  char *v9; // r13
  _QWORD *v12; // r12
  int v13; // edx
  int MemoryBlockByteRange; // esi
  __int64 v15; // r8
  __int16 *v16; // rdx
  char *v17; // r13
  __int64 v18; // rax
  int v19; // eax
  unsigned __int64 v20; // r13
  unsigned __int64 v21; // rdx
  unsigned int v22; // r9d
  __int64 v23; // rcx
  unsigned __int64 v24; // rsi
  unsigned __int64 v25; // rax
  int v27; // [rsp+20h] [rbp-1D8h]
  int i; // [rsp+50h] [rbp-1A8h] BYREF
  int v29; // [rsp+54h] [rbp-1A4h] BYREF
  unsigned __int64 v30; // [rsp+58h] [rbp-1A0h] BYREF
  _QWORD *v31; // [rsp+60h] [rbp-198h] BYREF
  char *v32; // [rsp+68h] [rbp-190h] BYREF
  __int64 v33; // [rsp+70h] [rbp-188h] BYREF
  unsigned __int64 v34; // [rsp+78h] [rbp-180h] BYREF
  unsigned __int64 v35; // [rsp+80h] [rbp-178h] BYREF
  unsigned __int64 v36; // [rsp+88h] [rbp-170h] BYREF
  __int64 v37; // [rsp+90h] [rbp-168h] BYREF
  int v38; // [rsp+98h] [rbp-160h] BYREF
  unsigned __int64 v39; // [rsp+A0h] [rbp-158h] BYREF
  __int64 v40; // [rsp+A8h] [rbp-150h] BYREF
  _BYTE v41[24]; // [rsp+B0h] [rbp-148h] BYREF
  _BYTE v42[16]; // [rsp+D0h] [rbp-128h] BYREF
  _BYTE v43[16]; // [rsp+E0h] [rbp-118h] BYREF
  int *v44; // [rsp+F0h] [rbp-108h]
  __int64 v45; // [rsp+F8h] [rbp-100h]
  int *p_i; // [rsp+100h] [rbp-F8h]
  __int64 v47; // [rsp+108h] [rbp-F0h]
  unsigned __int64 v48; // [rsp+110h] [rbp-E8h]
  __int64 v49; // [rsp+118h] [rbp-E0h]
  int *v50; // [rsp+120h] [rbp-D8h]
  __int64 v51; // [rsp+128h] [rbp-D0h]
  __int64 v52; // [rsp+130h] [rbp-C8h]
  int v53; // [rsp+138h] [rbp-C0h] BYREF
  int v54; // [rsp+13Ch] [rbp-BCh]
  unsigned __int64 *v55; // [rsp+140h] [rbp-B8h]
  __int64 v56; // [rsp+148h] [rbp-B0h]
  unsigned __int64 *v57; // [rsp+150h] [rbp-A8h]
  __int64 v58; // [rsp+158h] [rbp-A0h]
  volatile void **v59; // [rsp+160h] [rbp-98h]
  __int64 v60; // [rsp+168h] [rbp-90h]
  volatile void **v61; // [rsp+170h] [rbp-88h]
  __int64 v62; // [rsp+178h] [rbp-80h]
  volatile void **v63; // [rsp+180h] [rbp-78h]
  __int64 v64; // [rsp+188h] [rbp-70h]
  volatile void **v65; // [rsp+190h] [rbp-68h]
  __int64 v66; // [rsp+198h] [rbp-60h]
  unsigned __int64 *v67; // [rsp+1A0h] [rbp-58h]
  __int64 v68; // [rsp+1A8h] [rbp-50h]

  v9 = a3;
  v34 = (unsigned __int64)a3;
  v35 = a1;
  v32 = Address;
  v12 = a8;
  v31 = a8;
  v39 = 0;
  v38 = 0;
  v40 = 0;
  *a8 = 0;
  v37 = 0;
  LOBYTE(a3) = a7;
  if ( !(unsigned __int8)VsmmpValidateMbpRwFlags(a1, a4, a3) || (v13 & 0xC0000) != 0 )
  {
    MemoryBlockByteRange = -1073741811;
    if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      goto LABEL_52;
    tlgCreate1Sz_char(v42, "VsmmIoctlReadWriteGpaRange");
    tlgCreate1Sz_char(v43, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
    v29 = 4262;
    v44 = &v29;
    p_i = &i;
    v48 = a1 + 656;
    v50 = &v53;
    v52 = *(_QWORD *)(a1 + 128);
    v53 = *(unsigned __int16 *)(a1 + 120);
    v31 = *(_QWORD **)(a1 + 648);
    v55 = (unsigned __int64 *)&v31;
    LODWORD(v30) = a4;
    v57 = &v30;
    v58 = 4;
    v27 = 11;
    v16 = word_140055A92;
    goto LABEL_49;
  }
  v29 = v13 & 0xC;
  if ( (v13 & 0xC) == 0 && Length < (unsigned __int64)v9 )
  {
    MemoryBlockByteRange = -1073741789;
    if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      goto LABEL_52;
    tlgCreate1Sz_char(v42, "VsmmIoctlReadWriteGpaRange");
    tlgCreate1Sz_char(v43, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
    i = 4282;
    v44 = &i;
    v29 = -1073741789;
    p_i = &v29;
    v48 = a1 + 656;
    v50 = &v53;
    v52 = *(_QWORD *)(a1 + 128);
    v53 = *(unsigned __int16 *)(a1 + 120);
    v36 = *(_QWORD *)(a1 + 648);
    v55 = &v36;
    v33 = v15;
    v57 = (unsigned __int64 *)&v33;
    v58 = 8;
    v32 = v9;
    v59 = (volatile void **)&v32;
    v60 = 8;
    v27 = 12;
    v16 = (__int16 *)qword_140055B10;
    goto LABEL_50;
  }
  if ( a7 )
    ProbeForRead(Address, Length, 1u);
  else
    ProbeForWrite(Address, Length, 1u);
  v17 = &v9[a2];
  v36 = (unsigned __int64)v17;
  if ( (unsigned __int64)v17 < a2 )
  {
    MemoryBlockByteRange = -1073741675;
    if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      goto LABEL_52;
    tlgCreate1Sz_char(v42, "VsmmIoctlReadWriteGpaRange");
    tlgCreate1Sz_char(v43, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
    v29 = 4319;
    v44 = &v29;
    p_i = &i;
    v48 = a1 + 656;
    v50 = &v53;
    v52 = *(_QWORD *)(a1 + 128);
    v53 = *(unsigned __int16 *)(a1 + 120);
    v31 = *(_QWORD **)(a1 + 648);
    v55 = (unsigned __int64 *)&v31;
    v35 = a2;
    v57 = &v35;
    v58 = 8;
    v59 = (volatile void **)&v34;
    v60 = 8;
    v27 = 12;
    v16 = (__int16 *)byte_140055C03;
LABEL_49:
    i = MemoryBlockByteRange;
LABEL_50:
    v56 = 8;
LABEL_51:
    v47 = 4;
    v45 = 4;
    v49 = 16;
    v51 = 2;
    v54 = 0;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, v16, 0, 0, v27, v41);
    goto LABEL_52;
  }
  v30 = Length;
  v18 = 0;
  v33 = 0;
  if ( (unsigned __int64)v17 <= a2 )
  {
LABEL_41:
    MemoryBlockByteRange = 0;
    if ( !a7 )
      *v12 = v18;
  }
  else
  {
    v19 = a4 & 3;
    for ( i = v19; ; v19 = i )
    {
      v38 = v19;
      MemoryBlockByteRange = VsmmGpaRangeLookupByGpn(a1, 0, a2 >> 12, 8, (__int64)&v38, (__int64)&v40, (__int64)&v37);
      if ( MemoryBlockByteRange < 0 )
        break;
      v20 = (unsigned __int64)&v17[-a2];
      if ( v20 >= ((*(_QWORD *)(v37 + 272) + 1LL) << 12) - a2 )
        v20 = ((*(_QWORD *)(v37 + 272) + 1LL) << 12) - a2;
      v34 = a2 + v20;
      if ( a2 + v20 != v36 && v29 )
      {
        MemoryBlockByteRange = -1073741637;
        if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
        {
          tlgCreate1Sz_char(v42, "VsmmIoctlReadWriteGpaRange");
          tlgCreate1Sz_char(v43, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
          v29 = 4385;
          v44 = &v29;
          v45 = 4;
          i = -1073741637;
          p_i = &i;
          v47 = 4;
          v48 = a1 + 656;
          v49 = 16;
          v50 = &v53;
          v51 = 2;
          v52 = *(_QWORD *)(a1 + 128);
          v53 = *(unsigned __int16 *)(a1 + 120);
          v54 = 0;
          v34 = *(_QWORD *)(a1 + 648);
          v55 = &v34;
          v56 = 8;
          v36 = a2;
          v57 = &v36;
          v58 = 8;
          v33 = *(_QWORD *)(v37 + 248);
          v59 = (volatile void **)&v33;
          v60 = 8;
          v32 = *(char **)(v37 + 256);
          v61 = (volatile void **)&v32;
          v62 = 8;
          v30 = *(_QWORD *)(v37 + 264);
          v63 = (volatile void **)&v30;
          v64 = 8;
          v35 = *(int *)(v37 + 292);
          v65 = (volatile void **)&v35;
          v66 = 8;
          tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &dword_140055874, 0, 0, 15, v41);
        }
        goto LABEL_52;
      }
      v21 = (a2 & 0xFFF) + ((v40 + *(_QWORD *)(v37 + 392) - *(_QWORD *)(v37 + 256)) << 12);
      v22 = v38 & 3 | a4 & 0xFFFFFFFC;
      v23 = *(_QWORD *)(v37 + 384);
      if ( a7 )
      {
        MemoryBlockByteRange = VsmmpWriteMemoryBlockByteRange(v23, v21, v20, v22, (__int64)v32, v30, 1, v37);
        if ( MemoryBlockByteRange < 0 )
        {
          if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
          {
            tlgCreate1Sz_char(v42, "VsmmIoctlReadWriteGpaRange");
            tlgCreate1Sz_char(v43, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
            v29 = 4420;
            v44 = &v29;
            v45 = 4;
            i = MemoryBlockByteRange;
            p_i = &i;
            v47 = 4;
            v48 = a1 + 656;
            v49 = 16;
            v50 = &v53;
            v51 = 2;
            v52 = *(_QWORD *)(a1 + 128);
            v53 = *(unsigned __int16 *)(a1 + 120);
            v54 = 0;
            v35 = *(_QWORD *)(a1 + 648);
            v55 = &v35;
            v56 = 8;
            v34 = a2;
            v57 = &v34;
            v58 = 8;
            v36 = v20;
            v59 = (volatile void **)&v36;
            v60 = 8;
            v33 = *(_QWORD *)(v37 + 248);
            v61 = (volatile void **)&v33;
            v62 = 8;
            v32 = *(char **)(v37 + 256);
            v63 = (volatile void **)&v32;
            v64 = 8;
            v30 = *(_QWORD *)(v37 + 264);
            v65 = (volatile void **)&v30;
            v66 = 8;
            v31 = (_QWORD *)*(int *)(v37 + 292);
            v67 = (unsigned __int64 *)&v31;
            v68 = 8;
            tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &word_14005591E, 0, 0, 16, v41);
          }
          goto LABEL_52;
        }
        v24 = v30;
        v25 = v30;
        if ( v20 < v30 )
          v25 = v20;
        v39 = v25;
      }
      else
      {
        MemoryBlockByteRange = VsmmpReadMemoryBlockByteRange(
                                 v23,
                                 v21,
                                 v20,
                                 v22,
                                 (__int64)v32,
                                 v30,
                                 1,
                                 v37,
                                 (__int64)&v39);
        if ( MemoryBlockByteRange < 0 )
        {
          if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
          {
            tlgCreate1Sz_char(v42, "VsmmIoctlReadWriteGpaRange");
            tlgCreate1Sz_char(v43, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
            v29 = 4459;
            v44 = &v29;
            v45 = 4;
            i = MemoryBlockByteRange;
            p_i = &i;
            v47 = 4;
            v48 = a1 + 656;
            v49 = 16;
            v50 = &v53;
            v51 = 2;
            v52 = *(_QWORD *)(a1 + 128);
            v53 = *(unsigned __int16 *)(a1 + 120);
            v54 = 0;
            v31 = *(_QWORD **)(a1 + 648);
            v55 = (unsigned __int64 *)&v31;
            v56 = 8;
            v35 = a2;
            v57 = &v35;
            v58 = 8;
            v34 = v20;
            v59 = (volatile void **)&v34;
            v60 = 8;
            v36 = *(_QWORD *)(v37 + 248);
            v61 = (volatile void **)&v36;
            v62 = 8;
            v33 = *(_QWORD *)(v37 + 256);
            v63 = (volatile void **)&v33;
            v64 = 8;
            v32 = *(char **)(v37 + 264);
            v65 = (volatile void **)&v32;
            v66 = 8;
            v30 = *(int *)(v37 + 292);
            v67 = &v30;
            v68 = 8;
            tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, qword_1400559D8, 0, 0, 16, v41);
          }
          goto LABEL_52;
        }
        v33 += v39;
        v24 = v30;
      }
      VidRefCounterDec(v37 + 8, 0);
      v37 = 0;
      v30 = v24 - v39;
      v32 += v39;
      a2 = v34;
      v17 = (char *)v36;
      if ( v34 >= v36 )
      {
        v18 = v33;
        v12 = v31;
        goto LABEL_41;
      }
    }
    if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
    {
      tlgCreate1Sz_char(v42, "VsmmIoctlReadWriteGpaRange");
      tlgCreate1Sz_char(v43, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
      v29 = 4353;
      v44 = &v29;
      i = MemoryBlockByteRange;
      p_i = &i;
      v48 = a1 + 656;
      v50 = &v53;
      v52 = *(_QWORD *)(a1 + 128);
      v53 = *(unsigned __int16 *)(a1 + 120);
      v31 = *(_QWORD **)(a1 + 648);
      v55 = (unsigned __int64 *)&v31;
      v56 = 8;
      v35 = a2;
      v57 = &v35;
      v58 = 8;
      v27 = 11;
      v16 = word_1400557FA;
      goto LABEL_51;
    }
  }
LABEL_52:
  if ( v37 )
    VidRefCounterDec(v37 + 8, 0);
  return (unsigned int)MemoryBlockByteRange;
}

```

## disassembly

```asm
0x14000aae0  push    rbx
0x14000aae2  push    rsi
0x14000aae3  push    rdi
0x14000aae4  push    r12
0x14000aae6  push    r13
0x14000aae8  push    r14
0x14000aaea  push    r15
0x14000aaec  sub     rsp, 1C0h
0x14000aaf3  mov     rax, cs:__security_cookie
0x14000aafa  xor     rax, rsp
0x14000aafd  mov     [rsp+1F8h+var_48], rax
0x14000ab05  mov     ebx, r9d
0x14000ab08  mov     r13, r8
0x14000ab0b  mov     [rsp+1F8h+var_180], r8
0x14000ab10  mov     r15, rdx
0x14000ab13  mov     r14, rcx
0x14000ab16  mov     [rsp+1F8h+var_178], rcx
0x14000ab1e  mov     rsi, [rsp+1F8h+Address]
0x14000ab26  mov     [rsp+1F8h+var_190], rsi
0x14000ab2b  mov     r12, [rsp+1F8h+arg_38]
0x14000ab33  mov     [rsp+1F8h+var_198], r12
0x14000ab38  xor     edi, edi
0x14000ab3a  mov     [rsp+1F8h+var_158], rdi
0x14000ab42  mov     [rsp+1F8h+var_160], edi
0x14000ab49  mov     [rsp+1F8h+var_150], rdi
0x14000ab51  mov     [r12], rdi
0x14000ab55  mov     [rsp+1F8h+var_168], rdi
0x14000ab5d  mov     r8b, [rsp+1F8h+arg_30]
0x14000ab65  mov     edx, r9d
0x14000ab68  call    VsmmpValidateMbpRwFlags
0x14000ab6d  test    al, al
0x14000ab6f  jz      loc_14000B898
0x14000ab75  test    edx, 0C0000h
0x14000ab7b  jnz     loc_14000B898
0x14000ab81  mov     eax, edx
0x14000ab83  and     eax, 0Ch
0x14000ab86  mov     [rsp+1F8h+var_1A4], eax
0x14000ab8a  jnz     loc_14000ACD2
0x14000ab90  mov     r8, [rsp+1F8h+Length]
0x14000ab98  cmp     r8, r13
0x14000ab9b  jnb     loc_14000ACD2
0x14000aba1  mov     esi, 0C0000023h
0x14000aba6  mov     eax, cs:dword_140065110
0x14000abac  cmp     eax, 2
0x14000abaf  jbe     loc_14000B9F4
0x14000abb5  mov     edx, 100h
0x14000abba  lea     rcx, dword_140065110
0x14000abc1  call    _tlgKeywordOn
0x14000abc6  test    al, al
0x14000abc8  jz      loc_14000B9F4
0x14000abce  lea     rdx, aVsmmioctlreadw_1; "VsmmIoctlReadWriteGpaRange"
0x14000abd5  lea     rcx, [rsp+1F8h+var_128]
0x14000abdd  call    _tlgCreate1Sz_char
0x14000abe2  lea     rdx, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x14000abe9  lea     rcx, [rsp+1F8h+var_118]
0x14000abf1  call    _tlgCreate1Sz_char
0x14000abf6  mov     [rsp+1F8h+var_1A8], 10BAh
0x14000abfe  lea     rax, [rsp+1F8h+var_1A8]
0x14000ac03  mov     [rsp+1F8h+var_108], rax
0x14000ac0b  mov     [rsp+1F8h+var_1A4], esi
0x14000ac0f  lea     rax, [rsp+1F8h+var_1A4]
0x14000ac14  mov     [rsp+1F8h+var_F8], rax
0x14000ac1c  lea     rax, [r14+290h]
0x14000ac23  mov     [rsp+1F8h+var_E8], rax
0x14000ac2b  lea     rax, [rsp+1F8h+var_C0]
0x14000ac33  mov     [rsp+1F8h+var_D8], rax
0x14000ac3b  mov     rax, [r14+80h]
0x14000ac42  mov     [rsp+1F8h+var_C8], rax
0x14000ac4a  movzx   eax, word ptr [r14+78h]
0x14000ac4f  mov     [rsp+1F8h+var_C0], eax
0x14000ac56  mov     rax, [r14+288h]
0x14000ac5d  mov     [rsp+1F8h+var_170], rax
0x14000ac65  lea     rax, [rsp+1F8h+var_170]
0x14000ac6d  mov     [rsp+1F8h+var_B8], rax
0x14000ac75  mov     [rsp+1F8h+var_188], r8
0x14000ac7a  lea     rax, [rsp+1F8h+var_188]
0x14000ac7f  mov     [rsp+1F8h+var_A8], rax
0x14000ac87  mov     [rsp+1F8h+var_A0], 8
0x14000ac93  mov     [rsp+1F8h+var_190], r13
0x14000ac98  lea     rax, [rsp+1F8h+var_190]
0x14000ac9d  mov     [rsp+1F8h+var_98], rax
0x14000aca5  mov     [rsp+1F8h+var_90], 8
0x14000acb1  lea     rax, [rsp+1F8h+var_148]
0x14000acb9  mov     [rsp+1F8h+var_1D0], rax
0x14000acbe  mov     dword ptr [rsp+1F8h+var_1D8], 0Ch
0x14000acc6  lea     rdx, qword_140055B10
0x14000accd  jmp     loc_14000B99F
0x14000acd2  mov     r8d, 1; Alignment
0x14000acd8  mov     rdx, [rsp+1F8h+Length]; Length
0x14000ace0  mov     rcx, rsi; Address
0x14000ace3  cmp     [rsp+1F8h+arg_30], dil
0x14000aceb  jz      short loc_14000ACFB
0x14000aced  call    cs:__imp_ProbeForRead
0x14000acf4  nop     dword ptr [rax+rax+00h]
0x14000acf9  jmp     short loc_14000AD08
0x14000acfb  call    cs:__imp_ProbeForWrite
0x14000ad02  nop     dword ptr [rax+rax+00h]
0x14000ad07  nop
0x14000ad08  add     r13, r15
0x14000ad0b  mov     [rsp+1F8h+var_170], r13
0x14000ad13  cmp     r13, r15
0x14000ad16  jb      loc_14000B60D
0x14000ad1c  mov     rax, [rsp+1F8h+Length]
0x14000ad24  mov     [rsp+1F8h+var_1A0], rax
0x14000ad29  mov     rax, rdi
0x14000ad2c  mov     [rsp+1F8h+var_188], rax
0x14000ad31  jbe     loc_14000B5F4
0x14000ad37  mov     eax, ebx
0x14000ad39  and     eax, 3
0x14000ad3c  mov     [rsp+1F8h+var_1A8], eax
0x14000ad40  mov     r12d, 8
0x14000ad46  mov     [rsp+1F8h+var_160], eax
0x14000ad4d  mov     r8, r15
0x14000ad50  shr     r8, 0Ch
0x14000ad54  lea     rax, [rsp+1F8h+var_168]
0x14000ad5c  mov     [rsp+1F8h+var_1C8], rax
0x14000ad61  lea     rax, [rsp+1F8h+var_150]
0x14000ad69  mov     [rsp+1F8h+var_1D0], rax
0x14000ad6e  lea     rax, [rsp+1F8h+var_160]
0x14000ad76  mov     [rsp+1F8h+var_1D8], rax
0x14000ad7b  mov     r9d, r12d
0x14000ad7e  xor     edx, edx
0x14000ad80  mov     rcx, r14
0x14000ad83  call    VsmmGpaRangeLookupByGpn
0x14000ad88  mov     esi, eax
0x14000ad8a  test    eax, eax
0x14000ad8c  js      loc_14000B4D8
0x14000ad92  mov     r10, [rsp+1F8h+var_168]
0x14000ad9a  mov     rax, [r10+110h]
0x14000ada1  inc     rax
0x14000ada4  shl     rax, 0Ch
0x14000ada8  sub     rax, r15
0x14000adab  sub     r13, r15
0x14000adae  cmp     r13, rax
0x14000adb1  cmovnb  r13, rax
0x14000adb5  lea     rax, [r15+r13]
0x14000adb9  mov     [rsp+1F8h+var_180], rax
0x14000adbe  cmp     rax, [rsp+1F8h+var_170]
0x14000adc6  jz      short loc_14000ADD2
0x14000adc8  cmp     [rsp+1F8h+var_1A4], edi
0x14000adcc  jnz     loc_14000AF0E
0x14000add2  mov     rdx, [r10+188h]
0x14000add9  sub     rdx, [r10+100h]
0x14000ade0  add     rdx, [rsp+1F8h+var_150]
0x14000ade8  shl     rdx, 0Ch
0x14000adec  mov     eax, r15d
0x14000adef  and     eax, 0FFFh
0x14000adf4  add     rdx, rax
0x14000adf7  mov     r9d, ebx
0x14000adfa  and     r9d, 0FFFFFFFCh
0x14000adfe  mov     eax, [rsp+1F8h+var_160]
0x14000ae05  and     eax, 3
0x14000ae08  or      r9d, eax
0x14000ae0b  mov     r8, r13
0x14000ae0e  mov     rcx, [r10+180h]
0x14000ae15  cmp     [rsp+1F8h+arg_30], dil
0x14000ae1d  jz      short loc_14000AE65
0x14000ae1f  mov     [rsp+1F8h+var_1C0], r10
0x14000ae24  mov     byte ptr [rsp+1F8h+var_1C8], 1
0x14000ae29  mov     rax, [rsp+1F8h+var_1A0]
0x14000ae2e  mov     [rsp+1F8h+var_1D0], rax
0x14000ae33  mov     rax, [rsp+1F8h+var_190]
0x14000ae38  mov     [rsp+1F8h+var_1D8], rax
0x14000ae3d  call    VsmmpWriteMemoryBlockByteRange
0x14000ae42  mov     esi, eax
0x14000ae44  test    eax, eax
0x14000ae46  js      loc_14000B0EE
0x14000ae4c  mov     rsi, [rsp+1F8h+var_1A0]
0x14000ae51  mov     rax, rsi
0x14000ae54  cmp     r13, rsi
0x14000ae57  cmovb   rax, r13
0x14000ae5b  mov     [rsp+1F8h+var_158], rax
0x14000ae63  jmp     short loc_14000AEB6
0x14000ae65  lea     rax, [rsp+1F8h+var_158]
0x14000ae6d  mov     [rsp+1F8h+var_1B8], rax
0x14000ae72  mov     [rsp+1F8h+var_1C0], r10
0x14000ae77  mov     byte ptr [rsp+1F8h+var_1C8], 1
0x14000ae7c  mov     rax, [rsp+1F8h+var_1A0]
0x14000ae81  mov     [rsp+1F8h+var_1D0], rax
0x14000ae86  mov     rax, [rsp+1F8h+var_190]
0x14000ae8b  mov     [rsp+1F8h+var_1D8], rax
0x14000ae90  call    VsmmpReadMemoryBlockByteRange
0x14000ae95  mov     esi, eax
0x14000ae97  test    eax, eax
0x14000ae99  js      loc_14000B2E3
0x14000ae9f  mov     rax, [rsp+1F8h+var_188]
0x14000aea4  add     rax, [rsp+1F8h+var_158]
0x14000aeac  mov     [rsp+1F8h+var_188], rax
0x14000aeb1  mov     rsi, [rsp+1F8h+var_1A0]
0x14000aeb6  mov     rcx, [rsp+1F8h+var_168]
0x14000aebe  add     rcx, r12
0x14000aec1  xor     edx, edx
0x14000aec3  call    VidRefCounterDec
0x14000aec8  mov     [rsp+1F8h+var_168], rdi
0x14000aed0  sub     rsi, [rsp+1F8h+var_158]
0x14000aed8  mov     [rsp+1F8h+var_1A0], rsi
0x14000aedd  mov     rax, [rsp+1F8h+var_190]
0x14000aee2  add     rax, [rsp+1F8h+var_158]
0x14000aeea  mov     [rsp+1F8h+var_190], rax
0x14000aeef  mov     r15, [rsp+1F8h+var_180]
0x14000aef4  mov     r13, [rsp+1F8h+var_170]
0x14000aefc  cmp     r15, r13
0x14000aeff  jnb     loc_14000B5EA
0x14000af05  mov     eax, [rsp+1F8h+var_1A8]
0x14000af09  jmp     loc_14000AD46
0x14000af0e  mov     esi, 0C00000BBh
0x14000af13  mov     eax, cs:dword_140065110
0x14000af19  cmp     eax, 2
0x14000af1c  jbe     loc_14000B9F4
0x14000af22  mov     edx, 100h
0x14000af27  lea     rcx, dword_140065110
0x14000af2e  call    _tlgKeywordOn
0x14000af33  test    al, al
0x14000af35  jz      loc_14000B9F4
0x14000af3b  lea     rdx, aVsmmioctlreadw_1; "VsmmIoctlReadWriteGpaRange"
0x14000af42  lea     rcx, [rsp+1F8h+var_128]
0x14000af4a  call    _tlgCreate1Sz_char
0x14000af4f  lea     rdx, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x14000af56  lea     rcx, [rsp+1F8h+var_118]
0x14000af5e  call    _tlgCreate1Sz_char
0x14000af63  mov     [rsp+1F8h+var_1A4], 1121h
0x14000af6b  lea     rax, [rsp+1F8h+var_1A4]
0x14000af70  mov     [rsp+1F8h+var_108], rax
0x14000af78  mov     [rsp+1F8h+var_100], 4
0x14000af84  mov     [rsp+1F8h+var_1A8], esi
0x14000af88  lea     rax, [rsp+1F8h+var_1A8]
0x14000af8d  mov     [rsp+1F8h+var_F8], rax
0x14000af95  mov     [rsp+1F8h+var_F0], 4
0x14000afa1  lea     rax, [r14+290h]
0x14000afa8  mov     [rsp+1F8h+var_E8], rax
0x14000afb0  mov     [rsp+1F8h+var_E0], 10h
0x14000afbc  lea     rax, [rsp+1F8h+var_C0]
0x14000afc4  mov     [rsp+1F8h+var_D8], rax
0x14000afcc  mov     [rsp+1F8h+var_D0], 2
0x14000afd8  mov     rax, [r14+80h]
0x14000afdf  mov     [rsp+1F8h+var_C8], rax
0x14000afe7  movzx   eax, word ptr [r14+78h]
0x14000afec  mov     [rsp+1F8h+var_C0], eax
0x14000aff3  mov     [rsp+1F8h+var_BC], edi
0x14000affa  mov     rax, [r14+288h]
0x14000b001  mov     [rsp+1F8h+var_180], rax
0x14000b006  lea     rax, [rsp+1F8h+var_180]
0x14000b00b  mov     [rsp+1F8h+var_B8], rax
0x14000b013  mov     [rsp+1F8h+var_B0], r12
0x14000b01b  mov     [rsp+1F8h+var_170], r15
0x14000b023  lea     rax, [rsp+1F8h+var_170]
0x14000b02b  mov     [rsp+1F8h+var_A8], rax
0x14000b033  mov     [rsp+1F8h+var_A0], r12
0x14000b03b  mov     rcx, [rsp+1F8h+var_168]
0x14000b043  mov     rax, [rcx+0F8h]
0x14000b04a  mov     [rsp+1F8h+var_188], rax
0x14000b04f  lea     rax, [rsp+1F8h+var_188]
0x14000b054  mov     [rsp+1F8h+var_98], rax
0x14000b05c  mov     [rsp+1F8h+var_90], r12
0x14000b064  mov     rax, [rcx+100h]
0x14000b06b  mov     [rsp+1F8h+var_190], rax
0x14000b070  lea     rax, [rsp+1F8h+var_190]
0x14000b075  mov     [rsp+1F8h+var_88], rax
0x14000b07d  mov     [rsp+1F8h+var_80], r12
0x14000b085  mov     rax, [rcx+108h]
0x14000b08c  mov     [rsp+1F8h+var_1A0], rax
0x14000b091  lea     rax, [rsp+1F8h+var_1A0]
0x14000b096  mov     [rsp+1F8h+var_78], rax
0x14000b09e  mov     [rsp+1F8h+var_70], r12
0x14000b0a6  movsxd  rax, dword ptr [rcx+124h]
0x14000b0ad  mov     [rsp+1F8h+var_178], rax
0x14000b0b5  lea     rax, [rsp+1F8h+var_178]
0x14000b0bd  mov     [rsp+1F8h+var_68], rax
0x14000b0c5  mov     [rsp+1F8h+var_60], r12
0x14000b0cd  lea     rax, [rsp+1F8h+var_148]
0x14000b0d5  mov     [rsp+1F8h+var_1D0], rax
0x14000b0da  mov     dword ptr [rsp+1F8h+var_1D8], 0Fh
0x14000b0e2  lea     rdx, dword_140055874
0x14000b0e9  jmp     loc_14000B9E2
0x14000b0ee  mov     eax, cs:dword_140065110
0x14000b0f4  cmp     eax, 2
0x14000b0f7  jbe     loc_14000B9F4
0x14000b0fd  mov     edx, 100h
0x14000b102  lea     rcx, dword_140065110
0x14000b109  call    _tlgKeywordOn
0x14000b10e  test    al, al
0x14000b110  jz      loc_14000B9F4
0x14000b116  lea     rdx, aVsmmioctlreadw_1; "VsmmIoctlReadWriteGpaRange"
0x14000b11d  lea     rcx, [rsp+1F8h+var_128]
0x14000b125  call    _tlgCreate1Sz_char
0x14000b12a  lea     rdx, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x14000b131  lea     rcx, [rsp+1F8h+var_118]
0x14000b139  call    _tlgCreate1Sz_char
0x14000b13e  mov     [rsp+1F8h+var_1A4], 1144h
0x14000b146  lea     rax, [rsp+1F8h+var_1A4]
0x14000b14b  mov     [rsp+1F8h+var_108], rax
0x14000b153  mov     [rsp+1F8h+var_100], 4
0x14000b15f  mov     [rsp+1F8h+var_1A8], esi
0x14000b163  lea     rax, [rsp+1F8h+var_1A8]
0x14000b168  mov     [rsp+1F8h+var_F8], rax
0x14000b170  mov     [rsp+1F8h+var_F0], 4
0x14000b17c  lea     rax, [r14+290h]
0x14000b183  mov     [rsp+1F8h+var_E8], rax
0x14000b18b  mov     [rsp+1F8h+var_E0], 10h
0x14000b197  lea     rax, [rsp+1F8h+var_C0]
  ... truncated ...
```
