# VsmmIoctlReadWriteGpaRange

- ea: `0x14000ad0c`
- end: `0x14000bc5e`
- name: `VsmmIoctlReadWriteGpaRange`
- size: `3922`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned __int64, char *, unsigned int, char *Address, SIZE_T Length, char, _QWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140031fa4`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x14000a4e0`
- `0x14000ad0c`
- `0x14000bc64`
- `0x14000d75c`
- `0x140021650`
- `0x14002534c`
- `0x140030800`
- `0x1400758a4`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x14000af27`
- `ntoskrnl!ProbeForWrite` at `0x14000af27`
- `ntoskrnl!ProbeForRead` at `0x14000af19`
- `ntoskrnl!ProbeForRead` at `0x14000af19`

## string_xrefs

- `0x14000adfa`: `VsmmIoctlReadWriteGpaRange`
- `0x14000b167`: `VsmmIoctlReadWriteGpaRange`
- `0x14000b342`: `VsmmIoctlReadWriteGpaRange`
- `0x14000b537`: `VsmmIoctlReadWriteGpaRange`
- `0x14000b72c`: `VsmmIoctlReadWriteGpaRange`
- `0x14000b866`: `VsmmIoctlReadWriteGpaRange`
- `0x14000b995`: `VsmmIoctlReadWriteGpaRange`
- `0x14000baf1`: `VsmmIoctlReadWriteGpaRange`

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
  char *v16; // rdx
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
    if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
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
    v16 = byte_140055473;
    goto LABEL_49;
  }
  v29 = v13 & 0xC;
  if ( (v13 & 0xC) == 0 && Length < (unsigned __int64)v9 )
  {
    MemoryBlockByteRange = -1073741789;
    if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
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
    v16 = byte_1400554F1;
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
    if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
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
    v16 = (char *)word_140055212;
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
    tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, v16, 0, 0, v27, v41);
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
        if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
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
          tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, &byte_14005530F, 0, 0, 15, v41);
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
          if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
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
            tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, byte_1400553B9, 0, 0, 16, v41);
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
          if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
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
            tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, qword_140055158, 0, 0, 16, v41);
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
    if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
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
      v16 = byte_140055295;
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
0x14000ad0c  push    rbx
0x14000ad0e  push    rsi
0x14000ad0f  push    rdi
0x14000ad10  push    r12
0x14000ad12  push    r13
0x14000ad14  push    r14
0x14000ad16  push    r15
0x14000ad18  sub     rsp, 1C0h
0x14000ad1f  mov     rax, cs:__security_cookie
0x14000ad26  xor     rax, rsp
0x14000ad29  mov     [rsp+1F8h+var_48], rax
0x14000ad31  mov     ebx, r9d
0x14000ad34  mov     r13, r8
0x14000ad37  mov     [rsp+1F8h+var_180], r8
0x14000ad3c  mov     r15, rdx
0x14000ad3f  mov     r14, rcx
0x14000ad42  mov     [rsp+1F8h+var_178], rcx
0x14000ad4a  mov     rsi, [rsp+1F8h+Address]
0x14000ad52  mov     [rsp+1F8h+var_190], rsi
0x14000ad57  mov     r12, [rsp+1F8h+arg_38]
0x14000ad5f  mov     [rsp+1F8h+var_198], r12
0x14000ad64  xor     edi, edi
0x14000ad66  mov     [rsp+1F8h+var_158], rdi
0x14000ad6e  mov     [rsp+1F8h+var_160], edi
0x14000ad75  mov     [rsp+1F8h+var_150], rdi
0x14000ad7d  mov     [r12], rdi
0x14000ad81  mov     [rsp+1F8h+var_168], rdi
0x14000ad89  mov     r8b, [rsp+1F8h+arg_30]
0x14000ad91  mov     edx, r9d
0x14000ad94  call    VsmmpValidateMbpRwFlags
0x14000ad99  test    al, al
0x14000ad9b  jz      loc_14000BAC4
0x14000ada1  test    edx, 0C0000h
0x14000ada7  jnz     loc_14000BAC4
0x14000adad  mov     eax, edx
0x14000adaf  and     eax, 0Ch
0x14000adb2  mov     [rsp+1F8h+var_1A4], eax
0x14000adb6  jnz     loc_14000AEFE
0x14000adbc  mov     r8, [rsp+1F8h+Length]
0x14000adc4  cmp     r8, r13
0x14000adc7  jnb     loc_14000AEFE
0x14000adcd  mov     esi, 0C0000023h
0x14000add2  mov     eax, cs:dword_140064110
0x14000add8  cmp     eax, 2
0x14000addb  jbe     loc_14000BC20
0x14000ade1  mov     edx, 100h
0x14000ade6  lea     rcx, dword_140064110
0x14000aded  call    _tlgKeywordOn
0x14000adf2  test    al, al
0x14000adf4  jz      loc_14000BC20
0x14000adfa  lea     rdx, aVsmmioctlreadw_1; "VsmmIoctlReadWriteGpaRange"
0x14000ae01  lea     rcx, [rsp+1F8h+var_128]
0x14000ae09  call    _tlgCreate1Sz_char
0x14000ae0e  lea     rdx, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x14000ae15  lea     rcx, [rsp+1F8h+var_118]
0x14000ae1d  call    _tlgCreate1Sz_char
0x14000ae22  mov     [rsp+1F8h+var_1A8], 10BAh
0x14000ae2a  lea     rax, [rsp+1F8h+var_1A8]
0x14000ae2f  mov     [rsp+1F8h+var_108], rax
0x14000ae37  mov     [rsp+1F8h+var_1A4], esi
0x14000ae3b  lea     rax, [rsp+1F8h+var_1A4]
0x14000ae40  mov     [rsp+1F8h+var_F8], rax
0x14000ae48  lea     rax, [r14+290h]
0x14000ae4f  mov     [rsp+1F8h+var_E8], rax
0x14000ae57  lea     rax, [rsp+1F8h+var_C0]
0x14000ae5f  mov     [rsp+1F8h+var_D8], rax
0x14000ae67  mov     rax, [r14+80h]
0x14000ae6e  mov     [rsp+1F8h+var_C8], rax
0x14000ae76  movzx   eax, word ptr [r14+78h]
0x14000ae7b  mov     [rsp+1F8h+var_C0], eax
0x14000ae82  mov     rax, [r14+288h]
0x14000ae89  mov     [rsp+1F8h+var_170], rax
0x14000ae91  lea     rax, [rsp+1F8h+var_170]
0x14000ae99  mov     [rsp+1F8h+var_B8], rax
0x14000aea1  mov     [rsp+1F8h+var_188], r8
0x14000aea6  lea     rax, [rsp+1F8h+var_188]
0x14000aeab  mov     [rsp+1F8h+var_A8], rax
0x14000aeb3  mov     [rsp+1F8h+var_A0], 8
0x14000aebf  mov     [rsp+1F8h+var_190], r13
0x14000aec4  lea     rax, [rsp+1F8h+var_190]
0x14000aec9  mov     [rsp+1F8h+var_98], rax
0x14000aed1  mov     [rsp+1F8h+var_90], 8
0x14000aedd  lea     rax, [rsp+1F8h+var_148]
0x14000aee5  mov     [rsp+1F8h+var_1D0], rax
0x14000aeea  mov     dword ptr [rsp+1F8h+var_1D8], 0Ch
0x14000aef2  lea     rdx, byte_1400554F1
0x14000aef9  jmp     loc_14000BBCB
0x14000aefe  mov     r8d, 1; Alignment
0x14000af04  mov     rdx, [rsp+1F8h+Length]; Length
0x14000af0c  mov     rcx, rsi; Address
0x14000af0f  cmp     [rsp+1F8h+arg_30], dil
0x14000af17  jz      short loc_14000AF27
0x14000af19  call    cs:__imp_ProbeForRead
0x14000af20  nop     dword ptr [rax+rax+00h]
0x14000af25  jmp     short loc_14000AF34
0x14000af27  call    cs:__imp_ProbeForWrite
0x14000af2e  nop     dword ptr [rax+rax+00h]
0x14000af33  nop
0x14000af34  add     r13, r15
0x14000af37  mov     [rsp+1F8h+var_170], r13
0x14000af3f  cmp     r13, r15
0x14000af42  jb      loc_14000B839
0x14000af48  mov     rax, [rsp+1F8h+Length]
0x14000af50  mov     [rsp+1F8h+var_1A0], rax
0x14000af55  mov     rax, rdi
0x14000af58  mov     [rsp+1F8h+var_188], rax
0x14000af5d  jbe     loc_14000B820
0x14000af63  mov     eax, ebx
0x14000af65  and     eax, 3
0x14000af68  mov     [rsp+1F8h+var_1A8], eax
0x14000af6c  mov     r12d, 8
0x14000af72  mov     [rsp+1F8h+var_160], eax
0x14000af79  mov     r8, r15
0x14000af7c  shr     r8, 0Ch
0x14000af80  lea     rax, [rsp+1F8h+var_168]
0x14000af88  mov     [rsp+1F8h+var_1C8], rax
0x14000af8d  lea     rax, [rsp+1F8h+var_150]
0x14000af95  mov     [rsp+1F8h+var_1D0], rax
0x14000af9a  lea     rax, [rsp+1F8h+var_160]
0x14000afa2  mov     [rsp+1F8h+var_1D8], rax
0x14000afa7  mov     r9d, r12d
0x14000afaa  xor     edx, edx
0x14000afac  mov     rcx, r14
0x14000afaf  call    VsmmGpaRangeLookupByGpn
0x14000afb4  mov     esi, eax
0x14000afb6  test    eax, eax
0x14000afb8  js      loc_14000B704
0x14000afbe  mov     r10, [rsp+1F8h+var_168]
0x14000afc6  mov     rax, [r10+110h]
0x14000afcd  inc     rax
0x14000afd0  shl     rax, 0Ch
0x14000afd4  sub     rax, r15
0x14000afd7  sub     r13, r15
0x14000afda  cmp     r13, rax
0x14000afdd  cmovnb  r13, rax
0x14000afe1  lea     rax, [r15+r13]
0x14000afe5  mov     [rsp+1F8h+var_180], rax
0x14000afea  cmp     rax, [rsp+1F8h+var_170]
0x14000aff2  jz      short loc_14000AFFE
0x14000aff4  cmp     [rsp+1F8h+var_1A4], edi
0x14000aff8  jnz     loc_14000B13A
0x14000affe  mov     rdx, [r10+188h]
0x14000b005  sub     rdx, [r10+100h]
0x14000b00c  add     rdx, [rsp+1F8h+var_150]
0x14000b014  shl     rdx, 0Ch
0x14000b018  mov     eax, r15d
0x14000b01b  and     eax, 0FFFh
0x14000b020  add     rdx, rax
0x14000b023  mov     r9d, ebx
0x14000b026  and     r9d, 0FFFFFFFCh
0x14000b02a  mov     eax, [rsp+1F8h+var_160]
0x14000b031  and     eax, 3
0x14000b034  or      r9d, eax
0x14000b037  mov     r8, r13
0x14000b03a  mov     rcx, [r10+180h]
0x14000b041  cmp     [rsp+1F8h+arg_30], dil
0x14000b049  jz      short loc_14000B091
0x14000b04b  mov     [rsp+1F8h+var_1C0], r10
0x14000b050  mov     byte ptr [rsp+1F8h+var_1C8], 1
0x14000b055  mov     rax, [rsp+1F8h+var_1A0]
0x14000b05a  mov     [rsp+1F8h+var_1D0], rax
0x14000b05f  mov     rax, [rsp+1F8h+var_190]
0x14000b064  mov     [rsp+1F8h+var_1D8], rax
0x14000b069  call    VsmmpWriteMemoryBlockByteRange
0x14000b06e  mov     esi, eax
0x14000b070  test    eax, eax
0x14000b072  js      loc_14000B31A
0x14000b078  mov     rsi, [rsp+1F8h+var_1A0]
0x14000b07d  mov     rax, rsi
0x14000b080  cmp     r13, rsi
0x14000b083  cmovb   rax, r13
0x14000b087  mov     [rsp+1F8h+var_158], rax
0x14000b08f  jmp     short loc_14000B0E2
0x14000b091  lea     rax, [rsp+1F8h+var_158]
0x14000b099  mov     [rsp+1F8h+var_1B8], rax
0x14000b09e  mov     [rsp+1F8h+var_1C0], r10
0x14000b0a3  mov     byte ptr [rsp+1F8h+var_1C8], 1
0x14000b0a8  mov     rax, [rsp+1F8h+var_1A0]
0x14000b0ad  mov     [rsp+1F8h+var_1D0], rax
0x14000b0b2  mov     rax, [rsp+1F8h+var_190]
0x14000b0b7  mov     [rsp+1F8h+var_1D8], rax
0x14000b0bc  call    VsmmpReadMemoryBlockByteRange
0x14000b0c1  mov     esi, eax
0x14000b0c3  test    eax, eax
0x14000b0c5  js      loc_14000B50F
0x14000b0cb  mov     rax, [rsp+1F8h+var_188]
0x14000b0d0  add     rax, [rsp+1F8h+var_158]
0x14000b0d8  mov     [rsp+1F8h+var_188], rax
0x14000b0dd  mov     rsi, [rsp+1F8h+var_1A0]
0x14000b0e2  mov     rcx, [rsp+1F8h+var_168]
0x14000b0ea  add     rcx, r12
0x14000b0ed  xor     edx, edx
0x14000b0ef  call    VidRefCounterDec
0x14000b0f4  mov     [rsp+1F8h+var_168], rdi
0x14000b0fc  sub     rsi, [rsp+1F8h+var_158]
0x14000b104  mov     [rsp+1F8h+var_1A0], rsi
0x14000b109  mov     rax, [rsp+1F8h+var_190]
0x14000b10e  add     rax, [rsp+1F8h+var_158]
0x14000b116  mov     [rsp+1F8h+var_190], rax
0x14000b11b  mov     r15, [rsp+1F8h+var_180]
0x14000b120  mov     r13, [rsp+1F8h+var_170]
0x14000b128  cmp     r15, r13
0x14000b12b  jnb     loc_14000B816
0x14000b131  mov     eax, [rsp+1F8h+var_1A8]
0x14000b135  jmp     loc_14000AF72
0x14000b13a  mov     esi, 0C00000BBh
0x14000b13f  mov     eax, cs:dword_140064110
0x14000b145  cmp     eax, 2
0x14000b148  jbe     loc_14000BC20
0x14000b14e  mov     edx, 100h
0x14000b153  lea     rcx, dword_140064110
0x14000b15a  call    _tlgKeywordOn
0x14000b15f  test    al, al
0x14000b161  jz      loc_14000BC20
0x14000b167  lea     rdx, aVsmmioctlreadw_1; "VsmmIoctlReadWriteGpaRange"
0x14000b16e  lea     rcx, [rsp+1F8h+var_128]
0x14000b176  call    _tlgCreate1Sz_char
0x14000b17b  lea     rdx, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x14000b182  lea     rcx, [rsp+1F8h+var_118]
0x14000b18a  call    _tlgCreate1Sz_char
0x14000b18f  mov     [rsp+1F8h+var_1A4], 1121h
0x14000b197  lea     rax, [rsp+1F8h+var_1A4]
0x14000b19c  mov     [rsp+1F8h+var_108], rax
0x14000b1a4  mov     [rsp+1F8h+var_100], 4
0x14000b1b0  mov     [rsp+1F8h+var_1A8], esi
0x14000b1b4  lea     rax, [rsp+1F8h+var_1A8]
0x14000b1b9  mov     [rsp+1F8h+var_F8], rax
0x14000b1c1  mov     [rsp+1F8h+var_F0], 4
0x14000b1cd  lea     rax, [r14+290h]
0x14000b1d4  mov     [rsp+1F8h+var_E8], rax
0x14000b1dc  mov     [rsp+1F8h+var_E0], 10h
0x14000b1e8  lea     rax, [rsp+1F8h+var_C0]
0x14000b1f0  mov     [rsp+1F8h+var_D8], rax
0x14000b1f8  mov     [rsp+1F8h+var_D0], 2
0x14000b204  mov     rax, [r14+80h]
0x14000b20b  mov     [rsp+1F8h+var_C8], rax
0x14000b213  movzx   eax, word ptr [r14+78h]
0x14000b218  mov     [rsp+1F8h+var_C0], eax
0x14000b21f  mov     [rsp+1F8h+var_BC], edi
0x14000b226  mov     rax, [r14+288h]
0x14000b22d  mov     [rsp+1F8h+var_180], rax
0x14000b232  lea     rax, [rsp+1F8h+var_180]
0x14000b237  mov     [rsp+1F8h+var_B8], rax
0x14000b23f  mov     [rsp+1F8h+var_B0], r12
0x14000b247  mov     [rsp+1F8h+var_170], r15
0x14000b24f  lea     rax, [rsp+1F8h+var_170]
0x14000b257  mov     [rsp+1F8h+var_A8], rax
0x14000b25f  mov     [rsp+1F8h+var_A0], r12
0x14000b267  mov     rcx, [rsp+1F8h+var_168]
0x14000b26f  mov     rax, [rcx+0F8h]
0x14000b276  mov     [rsp+1F8h+var_188], rax
0x14000b27b  lea     rax, [rsp+1F8h+var_188]
0x14000b280  mov     [rsp+1F8h+var_98], rax
0x14000b288  mov     [rsp+1F8h+var_90], r12
0x14000b290  mov     rax, [rcx+100h]
0x14000b297  mov     [rsp+1F8h+var_190], rax
0x14000b29c  lea     rax, [rsp+1F8h+var_190]
0x14000b2a1  mov     [rsp+1F8h+var_88], rax
0x14000b2a9  mov     [rsp+1F8h+var_80], r12
0x14000b2b1  mov     rax, [rcx+108h]
0x14000b2b8  mov     [rsp+1F8h+var_1A0], rax
0x14000b2bd  lea     rax, [rsp+1F8h+var_1A0]
0x14000b2c2  mov     [rsp+1F8h+var_78], rax
0x14000b2ca  mov     [rsp+1F8h+var_70], r12
0x14000b2d2  movsxd  rax, dword ptr [rcx+124h]
0x14000b2d9  mov     [rsp+1F8h+var_178], rax
0x14000b2e1  lea     rax, [rsp+1F8h+var_178]
0x14000b2e9  mov     [rsp+1F8h+var_68], rax
0x14000b2f1  mov     [rsp+1F8h+var_60], r12
0x14000b2f9  lea     rax, [rsp+1F8h+var_148]
0x14000b301  mov     [rsp+1F8h+var_1D0], rax
0x14000b306  mov     dword ptr [rsp+1F8h+var_1D8], 0Fh
0x14000b30e  lea     rdx, byte_14005530F
0x14000b315  jmp     loc_14000BC0E
0x14000b31a  mov     eax, cs:dword_140064110
0x14000b320  cmp     eax, 2
0x14000b323  jbe     loc_14000BC20
0x14000b329  mov     edx, 100h
0x14000b32e  lea     rcx, dword_140064110
0x14000b335  call    _tlgKeywordOn
0x14000b33a  test    al, al
0x14000b33c  jz      loc_14000BC20
0x14000b342  lea     rdx, aVsmmioctlreadw_1; "VsmmIoctlReadWriteGpaRange"
0x14000b349  lea     rcx, [rsp+1F8h+var_128]
0x14000b351  call    _tlgCreate1Sz_char
0x14000b356  lea     rdx, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x14000b35d  lea     rcx, [rsp+1F8h+var_118]
0x14000b365  call    _tlgCreate1Sz_char
0x14000b36a  mov     [rsp+1F8h+var_1A4], 1144h
0x14000b372  lea     rax, [rsp+1F8h+var_1A4]
0x14000b377  mov     [rsp+1F8h+var_108], rax
0x14000b37f  mov     [rsp+1F8h+var_100], 4
0x14000b38b  mov     [rsp+1F8h+var_1A8], esi
0x14000b38f  lea     rax, [rsp+1F8h+var_1A8]
0x14000b394  mov     [rsp+1F8h+var_F8], rax
0x14000b39c  mov     [rsp+1F8h+var_F0], 4
0x14000b3a8  lea     rax, [r14+290h]
0x14000b3af  mov     [rsp+1F8h+var_E8], rax
0x14000b3b7  mov     [rsp+1F8h+var_E0], 10h
0x14000b3c3  lea     rax, [rsp+1F8h+var_C0]
  ... truncated ...
```
