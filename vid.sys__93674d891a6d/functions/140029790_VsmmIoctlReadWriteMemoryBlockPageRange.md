# VsmmIoctlReadWriteMemoryBlockPageRange

- ea: `0x140029790`
- end: `0x14002a220`
- name: `VsmmIoctlReadWriteMemoryBlockPageRange`
- size: `2704`
- prototype: `__int64 __fastcall(__int64, SIZE_T, __int64, unsigned __int64, volatile void *Address, SIZE_T Length, volatile void *, SIZE_T, unsigned int, _QWORD *, char)`
- caller_count: `1`
- callee_count: `18`
- tags: ``

## callers

- `0x1400321a4`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x14000a010`
- `0x14000ba38`
- `0x14000d4d8`
- `0x14001c0a8`
- `0x14001d140`
- `0x140021c60`
- `0x140029790`
- `0x1400305c0`
- `0x1400386a0`
- `0x140076780`
- `0x1400cdee4`
- `0x1400d7310`
- `0x1400e5074`
- `0x1400eb8bc`
- `0x1400ed28c`
- `0x1400f6da8`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x140029aba`
- `ntoskrnl!ProbeForWrite` at `0x140029ba7`
- `ntoskrnl!ProbeForWrite` at `0x140029aba`
- `ntoskrnl!ProbeForWrite` at `0x140029ba7`
- `ntoskrnl!ProbeForRead` at `0x140029aac`
- `ntoskrnl!ProbeForRead` at `0x140029b06`
- `ntoskrnl!ProbeForRead` at `0x140029aac`
- `ntoskrnl!ProbeForRead` at `0x140029b06`

## string_xrefs

- `0x1400298b8`: `VsmmIoctlReadWriteMemoryBlockPageRange`
- `0x140029a8a`: `VsmmIoctlReadWriteMemoryBlockPageRange`
- `0x140029b26`: `VsmmIoctlReadWriteMemoryBlockPageRange`
- `0x140029bcc`: `VsmmIoctlReadWriteMemoryBlockPageRange`
- `0x140029e85`: `VsmmIoctlReadWriteMemoryBlockPageRange`
- `0x140029f25`: `VsmmIoctlReadWriteMemoryBlockPageRange`
- `0x140029f8c`: `VsmmIoctlReadWriteMemoryBlockPageRange`

## pseudocode

```c
__int64 __fastcall VsmmIoctlReadWriteMemoryBlockPageRange(
        __int64 a1,
        SIZE_T a2,
        __int64 a3,
        unsigned __int64 a4,
        volatile void *Address,
        SIZE_T Length,
        volatile void *a7,
        SIZE_T a8,
        unsigned int a9,
        _QWORD *a10,
        char a11)
{
  __int64 v12; // r12
  __int64 v13; // r15
  int v14; // edi
  char v15; // r13
  unsigned int v16; // ebx
  unsigned __int64 v17; // rax
  int v18; // edi
  unsigned int v19; // r12d
  int v20; // r12d
  volatile void *v21; // r9
  int v22; // eax
  int MbpRange; // eax
  int v24; // r9d
  bool v25; // sf
  int v26; // eax
  int MemoryBlockByteRange; // eax
  int v28; // r8d
  int v29; // edx
  __int64 v30; // rcx
  __int64 v31; // r9
  __int64 v33; // [rsp+50h] [rbp-1E8h] BYREF
  char v34; // [rsp+58h] [rbp-1E0h] BYREF
  __int64 v35; // [rsp+60h] [rbp-1D8h]
  int v36[2]; // [rsp+68h] [rbp-1D0h] BYREF
  int v37[2]; // [rsp+70h] [rbp-1C8h] BYREF
  _QWORD *v38; // [rsp+78h] [rbp-1C0h] BYREF
  volatile void *v39; // [rsp+80h] [rbp-1B8h] BYREF
  SIZE_T v40; // [rsp+88h] [rbp-1B0h] BYREF
  volatile void *v41; // [rsp+90h] [rbp-1A8h] BYREF
  __int64 v42; // [rsp+98h] [rbp-1A0h] BYREF
  unsigned __int64 v43; // [rsp+A0h] [rbp-198h] BYREF
  __int64 v44; // [rsp+A8h] [rbp-190h] BYREF
  unsigned __int64 v45; // [rsp+B0h] [rbp-188h] BYREF
  _BYTE v46[32]; // [rsp+C0h] [rbp-178h] BYREF
  _BYTE v47[16]; // [rsp+E0h] [rbp-158h] BYREF
  _BYTE v48[16]; // [rsp+F0h] [rbp-148h] BYREF
  void *v49; // [rsp+100h] [rbp-138h]
  __int64 v50; // [rsp+108h] [rbp-130h]
  _QWORD **v51; // [rsp+110h] [rbp-128h]
  __int64 v52; // [rsp+118h] [rbp-120h]
  __int64 v53; // [rsp+120h] [rbp-118h]
  __int64 v54; // [rsp+128h] [rbp-110h]
  int *v55; // [rsp+130h] [rbp-108h]
  __int64 v56; // [rsp+138h] [rbp-100h]
  __int64 v57; // [rsp+140h] [rbp-F8h]
  int v58; // [rsp+148h] [rbp-F0h] BYREF
  int v59; // [rsp+14Ch] [rbp-ECh]
  volatile void **v60; // [rsp+150h] [rbp-E8h]
  __int64 v61; // [rsp+158h] [rbp-E0h]
  __int64 *v62; // [rsp+160h] [rbp-D8h]
  __int64 v63; // [rsp+168h] [rbp-D0h]
  __int64 *v64; // [rsp+170h] [rbp-C8h]
  __int64 v65; // [rsp+178h] [rbp-C0h]
  unsigned __int64 *v66; // [rsp+180h] [rbp-B8h]
  __int64 v67; // [rsp+188h] [rbp-B0h]
  __int64 *v68; // [rsp+190h] [rbp-A8h]
  __int64 v69; // [rsp+198h] [rbp-A0h]
  SIZE_T *v70; // [rsp+1A0h] [rbp-98h]
  __int64 v71; // [rsp+1A8h] [rbp-90h]
  volatile void **v72; // [rsp+1B0h] [rbp-88h]
  __int64 v73; // [rsp+1B8h] [rbp-80h]
  int *v74; // [rsp+1C0h] [rbp-78h]
  __int64 v75; // [rsp+1C8h] [rbp-70h]
  int *v76; // [rsp+1D0h] [rbp-68h]
  __int64 v77; // [rsp+1D8h] [rbp-60h]
  char *v78; // [rsp+1E0h] [rbp-58h]
  __int64 v79; // [rsp+1E8h] [rbp-50h]

  *(_QWORD *)v36 = a3;
  v40 = a2;
  v35 = a1;
  v42 = a1;
  v43 = a2;
  v44 = a3;
  v45 = a4;
  v12 = (__int64)Address;
  v33 = (__int64)Address;
  v41 = Address;
  v39 = a7;
  v38 = a10;
  v13 = 0;
  *(_QWORD *)v37 = 0;
  if ( !Address && Length || !a7 && a8 || !Address && !a7 )
  {
    v14 = -1073741811;
    v15 = a11;
    v16 = a9;
    goto LABEL_75;
  }
  v15 = a11;
  LOBYTE(a3) = a11;
  v16 = a9;
  if ( (unsigned __int8)VsmmpValidateMbpRwFlags(a1, a9, a3) )
  {
    v14 = VsmmMemoryBlockLookupByHandle(v35, v40, 0, 0, (__int64)v37);
    v13 = *(_QWORD *)v37;
    if ( v14 < 0 )
      goto LABEL_75;
    v17 = *(_QWORD *)(*(_QWORD *)v37 + 48LL);
    v18 = v36[0];
    if ( *(_QWORD *)v36 > v17 - 1 || a4 > v17 || a4 + *(_QWORD *)v36 - 1LL > v17 - 1 )
    {
      v14 = -1073741811;
      VidTraceErrorInternal0(
        "VsmmIoctlReadWriteMemoryBlockPageRange",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c",
        3634);
      goto LABEL_75;
    }
    if ( Address )
    {
      if ( (a9 & 0xC) == 0 && Length < a4 << 12 )
      {
        v14 = -1073741789;
        VidTraceErrorInternal0(
          "VsmmIoctlReadWriteMemoryBlockPageRange",
          "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c",
          3650);
        goto LABEL_75;
      }
      if ( a11 )
        ProbeForRead(Address, Length, 1u);
      else
        ProbeForWrite(Address, Length, 1u);
      v19 = a9 >> 18;
    }
    else
    {
      v19 = a9 >> 18;
      if ( ((a9 >> 18) & 3) == 0 )
        goto LABEL_29;
    }
    v20 = v19 & 3;
    v21 = v39;
    if ( v39 )
    {
      if ( !v20 )
        goto LABEL_29;
      if ( a11 )
        ProbeForRead(v39, a8, 1u);
      else
        ProbeForWrite(v39, a8, 1u);
      v21 = v39;
    }
    if ( !v20 )
      goto LABEL_50;
    if ( *(_DWORD *)(v13 + 244) == 1 )
    {
      if ( v20 != 2 )
      {
        if ( (*(_DWORD *)(v35 + 32) & 0x1E0) == 0x20 )
        {
          if ( a11 )
            goto LABEL_50;
          v22 = VsmmSvcImportExportMbpRange(v13, v36[0], a4, 0, 0, (__int64)v21, a8, a9, 0);
        }
        else
        {
          v22 = VsmmModifyMbpRangeHostVisibility(v13, *(_QWORD *)v36, a4);
        }
        v14 = v22;
        if ( v22 < 0 )
          goto LABEL_30;
        v18 = v36[0];
LABEL_50:
        if ( (a9 & 3) != 0 || (*(_BYTE *)(*(_QWORD *)(v13 + 8) + 40LL) & 2) == 0 )
        {
          v28 = (_DWORD)a4 << 12;
          v12 = v33;
          v29 = v18 << 12;
          if ( a11 )
          {
            v26 = VsmmpWriteMemoryBlockByteRange(v13, v29, v28, a9, v33, Length, 1, 0);
            goto LABEL_57;
          }
          MemoryBlockByteRange = VsmmpReadMemoryBlockByteRange(v13, v29, v28, a9, v33, Length, 1, 0, (__int64)v38);
        }
        else
        {
          v12 = v33;
          if ( a11 )
          {
            v26 = VsmmpWriteDecryptMbpRange(v13, v18, a4, a9, v33, Length);
LABEL_57:
            v14 = v26;
            v25 = v26 < 0;
LABEL_58:
            if ( !v25 )
              *v38 = a4 << 12;
            goto LABEL_62;
          }
          MemoryBlockByteRange = VsmmpReadEncryptMbpRange(v13, v18, a4, a9, v33, Length, (__int64)v38);
        }
        v14 = MemoryBlockByteRange;
LABEL_62:
        if ( v14 >= 0 )
        {
          if ( !a11 || (a9 & 0x40000) == 0 )
            goto LABEL_71;
          if ( (a9 & 0x100000) == 0 )
          {
            v14 = VsmmHostAccessReleaseMbpRange(v13, v36[0], a4, v24, 0, 0);
            if ( v14 < 0 )
            {
              VidTraceErrorInternal0(
                "VsmmIoctlReadWriteMemoryBlockPageRange",
                "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c",
                3936);
              goto LABEL_75;
            }
          }
          if ( (*(_DWORD *)(v35 + 32) & 0x1E0) == 0x20 )
            v14 = VsmmSvcImportExportMbpRange(v13, v36[0], a4, 0, 0, (__int64)v39, a8, a9, a11);
          if ( v14 >= 0 )
          {
LABEL_71:
            v30 = *(_QWORD *)(v35 + 1528);
            if ( a11 )
              _InterlockedAdd64((volatile signed __int64 *)(v30 + 856), a4);
            else
              _InterlockedAdd64((volatile signed __int64 *)(v30 + 848), a4);
            goto LABEL_75;
          }
        }
LABEL_30:
        v12 = v33;
        goto LABEL_75;
      }
      if ( (*(_DWORD *)(v35 + 32) & 0x1E0) == 0x20 )
      {
        MbpRange = VsmmSvcImportExportMbpRange(v13, v36[0], a4, v33, Length, (__int64)v39, a8, a9, a11);
LABEL_49:
        v14 = MbpRange;
        v12 = v33;
        v25 = MbpRange < 0;
        goto LABEL_58;
      }
      if ( !a11 && (a9 & 0xC) == 0 && !a8 )
      {
        MbpRange = VsmmHwIsoDebugReadMbpRange(v13, *(_QWORD *)v36, a4, v33, Length);
        goto LABEL_49;
      }
    }
LABEL_29:
    v14 = -1073741811;
    goto LABEL_30;
  }
  v14 = -1073741811;
  if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
  {
    tlgCreate1Sz_char(v47, "VsmmIoctlReadWriteMemoryBlockPageRange");
    tlgCreate1Sz_char(v48, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
    v37[0] = 3601;
    v49 = v37;
    v50 = 4;
    LODWORD(v38) = -1073741811;
    v51 = &v38;
    v52 = 4;
    v53 = v35 + 656;
    v54 = 16;
    v55 = &v58;
    v56 = 2;
    v57 = *(_QWORD *)(v35 + 128);
    v58 = *(unsigned __int16 *)(v35 + 120);
    v59 = 0;
    v41 = *(volatile void **)(v35 + 648);
    v60 = &v41;
    v61 = 8;
    LODWORD(v33) = a9;
    v62 = &v33;
    v63 = 4;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, byte_140055D81, 0, 0, 11, v46);
  }
LABEL_75:
  if ( v13 )
    VidOpCtrlFinish(v13 + 128, a2, a3);
  if ( !(unsigned __int8)VsmmReadWriteFailureExpected(v35, v16, (unsigned int)v14)
    && v14 < 0
    && (unsigned int)dword_140065110 > 2
    && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
  {
    tlgCreate1Sz_char(v47, "VsmmIoctlReadWriteMemoryBlockPageRange");
    tlgCreate1Sz_char(v48, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
    LODWORD(v33) = 4004;
    v49 = &v33;
    v50 = 4;
    LODWORD(v38) = v14;
    v51 = &v38;
    v52 = 4;
    v53 = v31 + 656;
    v54 = 16;
    v55 = &v58;
    v56 = 2;
    v57 = *(_QWORD *)(v31 + 128);
    v58 = *(unsigned __int16 *)(v31 + 120);
    v59 = 0;
    v41 = *(volatile void **)(v31 + 648);
    v60 = &v41;
    v61 = 8;
    v45 = v40;
    v62 = (__int64 *)&v45;
    v63 = 8;
    v44 = *(_QWORD *)v36;
    v64 = &v44;
    v65 = 8;
    v43 = a4;
    v66 = &v43;
    v67 = 8;
    v42 = v12;
    v68 = &v42;
    v69 = 8;
    v40 = Length;
    v70 = &v40;
    v71 = 8;
    v72 = &v39;
    v73 = 8;
    *(_QWORD *)v36 = a8;
    v74 = v36;
    v75 = 8;
    v37[0] = v16;
    v76 = v37;
    v77 = 4;
    v34 = v15;
    v78 = &v34;
    v79 = 1;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &word_140055C86, 0, 0, 19, v46);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x140029790  push    rbx
0x140029792  push    rsi
0x140029793  push    rdi
0x140029794  push    r12
0x140029796  push    r13
0x140029798  push    r14
0x14002979a  push    r15
0x14002979c  sub     rsp, 200h
0x1400297a3  mov     rax, cs:__security_cookie
0x1400297aa  xor     rax, rsp
0x1400297ad  mov     [rsp+238h+var_48], rax
0x1400297b5  mov     r14, r9
0x1400297b8  mov     rax, r8
0x1400297bb  mov     qword ptr [rsp+238h+var_1D0], rax
0x1400297c0  mov     [rsp+238h+var_1B0], rdx
0x1400297c8  mov     [rsp+238h+var_1D8], rcx
0x1400297cd  mov     [rsp+238h+var_1A0], rcx
0x1400297d5  mov     [rsp+238h+var_198], rdx
0x1400297dd  mov     [rsp+238h+var_190], rax
0x1400297e5  mov     [rsp+238h+var_188], r9
0x1400297ed  mov     r12, [rsp+238h+Address]
0x1400297f5  mov     [rsp+238h+var_1E8], r12
0x1400297fa  mov     [rsp+238h+var_1A8], r12
0x140029802  mov     r9, [rsp+238h+arg_30]
0x14002980a  mov     [rsp+238h+var_1B8], r9
0x140029812  mov     rax, [rsp+238h+arg_48]
0x14002981a  mov     [rsp+238h+var_1C0], rax
0x14002981f  xor     esi, esi
0x140029821  mov     r15d, esi
0x140029824  mov     qword ptr [rsp+238h+var_1C8], rsi
0x140029829  test    r12, r12
0x14002982c  jnz     short loc_140029851
0x14002982e  cmp     [rsp+238h+Length], rsi
0x140029836  jz      short loc_140029851
0x140029838  mov     edi, 0C000000Dh
0x14002983d  mov     r13b, [rsp+238h+arg_50]
0x140029845  mov     ebx, [rsp+238h+arg_40]
0x14002984c  jmp     loc_140029F31
0x140029851  test    r9, r9
0x140029854  jnz     short loc_140029860
0x140029856  cmp     [rsp+238h+arg_38], rsi
0x14002985e  jnz     short loc_140029838
0x140029860  test    r12, r12
0x140029863  jnz     short loc_14002986A
0x140029865  test    r9, r9
0x140029868  jz      short loc_140029838
0x14002986a  mov     r13b, [rsp+238h+arg_50]
0x140029872  mov     r8b, r13b
0x140029875  mov     ebx, [rsp+238h+arg_40]
0x14002987c  mov     edx, ebx
0x14002987e  call    VsmmpValidateMbpRwFlags
0x140029883  test    al, al
0x140029885  jnz     loc_1400299F6
0x14002988b  mov     edi, 0C000000Dh
0x140029890  mov     eax, cs:dword_140065110
0x140029896  cmp     eax, 2
0x140029899  jbe     loc_140029F31
0x14002989f  mov     edx, 100h
0x1400298a4  lea     rcx, dword_140065110
0x1400298ab  call    _tlgKeywordOn
0x1400298b0  test    al, al
0x1400298b2  jz      loc_140029F31
0x1400298b8  lea     rdx, aVsmmioctlreadw; "VsmmIoctlReadWriteMemoryBlockPageRange"
0x1400298bf  lea     rcx, [rsp+238h+var_158]
0x1400298c7  call    _tlgCreate1Sz_char
0x1400298cc  lea     rdx, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x1400298d3  lea     rcx, [rsp+238h+var_148]
0x1400298db  call    _tlgCreate1Sz_char
0x1400298e0  mov     [rsp+238h+var_1C8], 0E11h
0x1400298e8  lea     rax, [rsp+238h+var_1C8]
0x1400298ed  mov     [rsp+238h+var_138], rax
0x1400298f5  mov     [rsp+238h+var_130], 4
0x140029901  mov     dword ptr [rsp+238h+var_1C0], edi
0x140029905  lea     rax, [rsp+238h+var_1C0]
0x14002990a  mov     [rsp+238h+var_128], rax
0x140029912  mov     [rsp+238h+var_120], 4
0x14002991e  mov     rcx, [rsp+238h+var_1D8]
0x140029923  lea     rax, [rcx+290h]
0x14002992a  mov     [rsp+238h+var_118], rax
0x140029932  mov     [rsp+238h+var_110], 10h
0x14002993e  lea     rax, [rsp+238h+var_F0]
0x140029946  mov     [rsp+238h+var_108], rax
0x14002994e  mov     [rsp+238h+var_100], 2
0x14002995a  mov     rax, [rcx+80h]
0x140029961  mov     [rsp+238h+var_F8], rax
0x140029969  movzx   eax, word ptr [rcx+78h]
0x14002996d  mov     [rsp+238h+var_F0], eax
0x140029974  mov     [rsp+238h+var_EC], esi
0x14002997b  mov     rax, [rcx+288h]
0x140029982  mov     [rsp+238h+var_1A8], rax
0x14002998a  lea     rax, [rsp+238h+var_1A8]
0x140029992  mov     [rsp+238h+var_E8], rax
0x14002999a  mov     [rsp+238h+var_E0], 8
0x1400299a6  mov     dword ptr [rsp+238h+var_1E8], ebx
0x1400299aa  lea     rax, [rsp+238h+var_1E8]
0x1400299af  mov     [rsp+238h+var_D8], rax
0x1400299b7  mov     [rsp+238h+var_D0], 4
0x1400299c3  lea     rax, [rsp+238h+var_178]
0x1400299cb  mov     [rsp+238h+Size], rax
0x1400299d0  mov     [rsp+238h+var_218], 0Bh
0x1400299d8  xor     r9d, r9d
0x1400299db  xor     r8d, r8d
0x1400299de  lea     rdx, byte_140055D81
0x1400299e5  lea     rcx, dword_140065110
0x1400299ec  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400299f1  jmp     loc_140029F31
0x1400299f6  lea     rax, [rsp+238h+var_1C8]
0x1400299fb  mov     qword ptr [rsp+238h+var_218], rax
0x140029a00  xor     r9d, r9d
0x140029a03  xor     r8d, r8d
0x140029a06  mov     rdx, [rsp+238h+var_1B0]
0x140029a0e  mov     rcx, [rsp+238h+var_1D8]
0x140029a13  call    VsmmMemoryBlockLookupByHandle
0x140029a18  mov     edi, eax
0x140029a1a  mov     r15, qword ptr [rsp+238h+var_1C8]
0x140029a1f  test    eax, eax
0x140029a21  js      loc_140029F31
0x140029a27  mov     rax, [r15+30h]
0x140029a2b  lea     rcx, [rax-1]
0x140029a2f  mov     rdi, qword ptr [rsp+238h+var_1D0]
0x140029a34  cmp     rdi, rcx
0x140029a37  ja      loc_140029F13
0x140029a3d  cmp     r14, rax
0x140029a40  ja      loc_140029F13
0x140029a46  lea     rax, [rdi-1]
0x140029a4a  add     rax, r14
0x140029a4d  cmp     rax, rcx
0x140029a50  ja      loc_140029F13
0x140029a56  test    r12, r12
0x140029a59  jz      loc_140029B87
0x140029a5f  mov     rcx, [rsp+238h+Length]
0x140029a67  test    bl, 0Ch
0x140029a6a  jnz     short loc_140029A9B
0x140029a6c  mov     rax, r14
0x140029a6f  shl     rax, 0Ch
0x140029a73  cmp     rcx, rax
0x140029a76  jnb     short loc_140029A9B
0x140029a78  mov     edi, 0C0000023h
0x140029a7d  mov     r8d, 0E42h
0x140029a83  lea     rdx, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x140029a8a  lea     rcx, aVsmmioctlreadw; "VsmmIoctlReadWriteMemoryBlockPageRange"
0x140029a91  call    VidTraceErrorInternal0
0x140029a96  jmp     loc_140029F31
0x140029a9b  mov     r8d, 1; Alignment
0x140029aa1  mov     rdx, rcx; Length
0x140029aa4  mov     rcx, r12; Address
0x140029aa7  test    r13b, r13b
0x140029aaa  jz      short loc_140029ABA
0x140029aac  call    cs:__imp_ProbeForRead
0x140029ab3  nop     dword ptr [rax+rax+00h]
0x140029ab8  jmp     short loc_140029AC7
0x140029aba  call    cs:__imp_ProbeForWrite
0x140029ac1  nop     dword ptr [rax+rax+00h]
0x140029ac6  nop
0x140029ac7  mov     r12d, ebx
0x140029aca  shr     r12d, 12h
0x140029ace  and     r12d, 3
0x140029ad2  mov     r9, [rsp+238h+var_1B8]
0x140029ada  test    r9, r9
0x140029add  jz      loc_140029C2D
0x140029ae3  test    r12d, r12d
0x140029ae6  jz      loc_140029B98
0x140029aec  mov     r8d, 1; Alignment
0x140029af2  mov     rdx, [rsp+238h+arg_38]; Length
0x140029afa  mov     rcx, r9; Address
0x140029afd  test    r13b, r13b
0x140029b00  jz      loc_140029BA7
0x140029b06  call    cs:__imp_ProbeForRead
0x140029b0d  nop     dword ptr [rax+rax+00h]
0x140029b12  jmp     loc_140029BB3
0x140029b17  mov     edi, eax
0x140029b19  mov     r8d, 0E62h
0x140029b1f  lea     rdx, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x140029b26  lea     rcx, aVsmmioctlreadw; "VsmmIoctlReadWriteMemoryBlockPageRange"
0x140029b2d  call    VidTraceErrorInternal0
0x140029b32  xor     esi, esi
0x140029b34  mov     r13b, [rsp+238h+arg_50]
0x140029b3c  mov     ebx, [rsp+238h+arg_40]
0x140029b43  mov     r15, qword ptr [rsp+238h+var_1C8]
0x140029b48  mov     rax, [rsp+238h+var_1A0]
0x140029b50  mov     [rsp+238h+var_1D8], rax
0x140029b55  mov     rcx, [rsp+238h+var_198]
0x140029b5d  mov     [rsp+238h+var_1B0], rcx
0x140029b65  mov     rax, [rsp+238h+var_190]
0x140029b6d  mov     qword ptr [rsp+238h+var_1D0], rax
0x140029b72  mov     r14, [rsp+238h+var_188]
0x140029b7a  mov     r12, [rsp+238h+var_1A8]
0x140029b82  jmp     loc_140029F31
0x140029b87  mov     r12d, ebx
0x140029b8a  shr     r12d, 12h
0x140029b8e  test    r12b, 3
0x140029b92  jnz     loc_140029ACE
0x140029b98  mov     edi, 0C000000Dh
0x140029b9d  mov     r12, [rsp+238h+var_1E8]
0x140029ba2  jmp     loc_140029F31
0x140029ba7  call    cs:__imp_ProbeForWrite
0x140029bae  nop     dword ptr [rax+rax+00h]
0x140029bb3  mov     r9, [rsp+238h+var_1B8]
0x140029bbb  jmp     short loc_140029C2D
0x140029bbd  mov     edi, eax
0x140029bbf  mov     r8d, 0E89h
0x140029bc5  lea     rdx, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x140029bcc  lea     rcx, aVsmmioctlreadw; "VsmmIoctlReadWriteMemoryBlockPageRange"
0x140029bd3  call    VidTraceErrorInternal0
0x140029bd8  xor     esi, esi
0x140029bda  mov     r13b, [rsp+238h+arg_50]
0x140029be2  mov     ebx, [rsp+238h+arg_40]
0x140029be9  mov     r15, qword ptr [rsp+238h+var_1C8]
0x140029bee  mov     rax, [rsp+238h+var_1A0]
0x140029bf6  mov     [rsp+238h+var_1D8], rax
0x140029bfb  mov     rax, [rsp+238h+var_198]
0x140029c03  mov     [rsp+238h+var_1B0], rax
0x140029c0b  mov     rax, [rsp+238h+var_190]
0x140029c13  mov     qword ptr [rsp+238h+var_1D0], rax
0x140029c18  mov     r14, [rsp+238h+var_188]
0x140029c20  mov     r12, [rsp+238h+var_1A8]
0x140029c28  jmp     loc_140029F31
0x140029c2d  test    r12d, r12d
0x140029c30  jz      short loc_140029CAE
0x140029c32  cmp     dword ptr [r15+0F4h], 1
0x140029c3a  jnz     loc_140029B98
0x140029c40  mov     rcx, [rsp+238h+var_1D8]
0x140029c45  cmp     r12d, 2
0x140029c49  jz      short loc_140029CBD
0x140029c4b  mov     eax, [rcx+20h]
0x140029c4e  and     eax, 1E0h
0x140029c53  cmp     rax, 20h ; ' '
0x140029c57  jz      short loc_140029C69
0x140029c59  mov     r8, r14
0x140029c5c  mov     rdx, rdi
0x140029c5f  mov     rcx, r15
0x140029c62  call    VsmmModifyMbpRangeHostVisibility
0x140029c67  jmp     short loc_140029C9F
0x140029c69  test    r13b, r13b
0x140029c6c  jnz     short loc_140029CB3
0x140029c6e  mov     [rsp+238h+var_1F8], sil; char
0x140029c73  mov     [rsp+238h+var_200], ebx; int
0x140029c77  mov     rax, [rsp+238h+arg_38]
0x140029c7f  mov     qword ptr [rsp+238h+var_208], rax; ULONG
0x140029c84  mov     [rsp+238h+Size], r9; __int64
0x140029c89  mov     qword ptr [rsp+238h+var_218], rsi; Length
0x140029c8e  xor     r9d, r9d; int
0x140029c91  mov     r8, r14; int
0x140029c94  mov     rdx, rdi; int
0x140029c97  mov     rcx, r15; int
0x140029c9a  call    VsmmSvcImportExportMbpRange
0x140029c9f  test    eax, eax
0x140029ca1  mov     edi, eax
0x140029ca3  js      loc_140029B9D
0x140029ca9  mov     rdi, qword ptr [rsp+238h+var_1D0]
0x140029cae  mov     rcx, [rsp+238h+var_1D8]
0x140029cb3  cmp     r12d, 2
0x140029cb7  jnz     loc_140029D5E
0x140029cbd  mov     eax, [rcx+20h]
0x140029cc0  and     eax, 1E0h
0x140029cc5  cmp     rax, 20h ; ' '
0x140029cc9  jnz     short loc_140029D10
0x140029ccb  mov     [rsp+238h+var_1F8], r13b; char
0x140029cd0  mov     [rsp+238h+var_200], ebx; int
0x140029cd4  mov     rax, [rsp+238h+arg_38]
0x140029cdc  mov     qword ptr [rsp+238h+var_208], rax; ULONG
0x140029ce1  mov     rax, [rsp+238h+var_1B8]
0x140029ce9  mov     [rsp+238h+Size], rax; __int64
0x140029cee  mov     rax, [rsp+238h+Length]
0x140029cf6  mov     qword ptr [rsp+238h+var_218], rax; Length
0x140029cfb  mov     r9, [rsp+238h+var_1E8]; int
0x140029d00  mov     r8, r14; int
0x140029d03  mov     rdx, rdi; int
0x140029d06  mov     rcx, r15; int
0x140029d09  call    VsmmSvcImportExportMbpRange
0x140029d0e  jmp     short loc_140029D50
0x140029d10  test    r13b, r13b
0x140029d13  jnz     loc_140029B98
0x140029d19  test    bl, 0Ch
0x140029d1c  jnz     loc_140029B98
0x140029d22  cmp     [rsp+238h+arg_38], rsi
0x140029d2a  jnz     loc_140029B98
0x140029d30  mov     rax, [rsp+238h+Length]
0x140029d38  mov     qword ptr [rsp+238h+var_218], rax
0x140029d3d  mov     r9, [rsp+238h+var_1E8]
0x140029d42  mov     r8, r14
0x140029d45  mov     rdx, rdi
0x140029d48  mov     rcx, r15
0x140029d4b  call    VsmmHwIsoDebugReadMbpRange
0x140029d50  mov     edi, eax
0x140029d52  mov     r12, [rsp+238h+var_1E8]
0x140029d57  test    eax, eax
0x140029d59  jmp     loc_140029DFD
0x140029d5e  test    bl, 3
0x140029d61  jnz     short loc_140029DBA
0x140029d63  mov     rax, [r15+8]
0x140029d67  test    byte ptr [rax+28h], 2
0x140029d6b  jz      short loc_140029DBA
0x140029d6d  mov     rax, [rsp+238h+Length]
0x140029d75  mov     r12, [rsp+238h+var_1E8]
0x140029d7a  mov     r9d, ebx; int
0x140029d7d  mov     r8, r14; int
0x140029d80  mov     rdx, rdi; int
0x140029d83  test    r13b, r13b
0x140029d86  jz      short loc_140029D9C
  ... truncated ...
```
