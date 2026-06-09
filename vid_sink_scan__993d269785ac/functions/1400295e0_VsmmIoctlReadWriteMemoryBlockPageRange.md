# VsmmIoctlReadWriteMemoryBlockPageRange

- ea: `0x1400295e0`
- end: `0x14002a070`
- name: `VsmmIoctlReadWriteMemoryBlockPageRange`
- size: `2704`
- prototype: `__int64 __fastcall(__int64, SIZE_T, __int64, unsigned __int64, volatile void *Address, SIZE_T Length, volatile void *, SIZE_T, unsigned int, _QWORD *, char)`
- caller_count: `1`
- callee_count: `18`
- tags: ``

## callers

- `0x140031fa4`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x14000a4e0`
- `0x14000bc64`
- `0x14000d75c`
- `0x1400199c4`
- `0x14001aa60`
- `0x140021650`
- `0x1400295e0`
- `0x1400303c0`
- `0x140038630`
- `0x1400758a4`
- `0x1400cb774`
- `0x1400d496c`
- `0x1400e2408`
- `0x1400e8c7c`
- `0x1400ea5a4`
- `0x1400f42c8`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x14002990a`
- `ntoskrnl!ProbeForWrite` at `0x1400299f7`
- `ntoskrnl!ProbeForWrite` at `0x14002990a`
- `ntoskrnl!ProbeForWrite` at `0x1400299f7`
- `ntoskrnl!ProbeForRead` at `0x1400298fc`
- `ntoskrnl!ProbeForRead` at `0x140029956`
- `ntoskrnl!ProbeForRead` at `0x1400298fc`
- `ntoskrnl!ProbeForRead` at `0x140029956`

## string_xrefs

- `0x140029708`: `VsmmIoctlReadWriteMemoryBlockPageRange`
- `0x1400298da`: `VsmmIoctlReadWriteMemoryBlockPageRange`
- `0x140029976`: `VsmmIoctlReadWriteMemoryBlockPageRange`
- `0x140029a1c`: `VsmmIoctlReadWriteMemoryBlockPageRange`
- `0x140029cd5`: `VsmmIoctlReadWriteMemoryBlockPageRange`
- `0x140029d75`: `VsmmIoctlReadWriteMemoryBlockPageRange`
- `0x140029ddc`: `VsmmIoctlReadWriteMemoryBlockPageRange`

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
  if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
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
    tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, &dword_1400555E4, 0, 0, 11, v46);
  }
LABEL_75:
  if ( v13 )
    VidOpCtrlFinish(v13 + 128);
  if ( !(unsigned __int8)VsmmReadWriteFailureExpected(v35, v16, (unsigned int)v14)
    && v14 < 0
    && (unsigned int)dword_140064110 > 2
    && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
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
    tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, word_140055662, 0, 0, 19, v46);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1400295e0  push    rbx
0x1400295e2  push    rsi
0x1400295e3  push    rdi
0x1400295e4  push    r12
0x1400295e6  push    r13
0x1400295e8  push    r14
0x1400295ea  push    r15
0x1400295ec  sub     rsp, 200h
0x1400295f3  mov     rax, cs:__security_cookie
0x1400295fa  xor     rax, rsp
0x1400295fd  mov     [rsp+238h+var_48], rax
0x140029605  mov     r14, r9
0x140029608  mov     rax, r8
0x14002960b  mov     qword ptr [rsp+238h+var_1D0], rax
0x140029610  mov     [rsp+238h+var_1B0], rdx
0x140029618  mov     [rsp+238h+var_1D8], rcx
0x14002961d  mov     [rsp+238h+var_1A0], rcx
0x140029625  mov     [rsp+238h+var_198], rdx
0x14002962d  mov     [rsp+238h+var_190], rax
0x140029635  mov     [rsp+238h+var_188], r9
0x14002963d  mov     r12, [rsp+238h+Address]
0x140029645  mov     [rsp+238h+var_1E8], r12
0x14002964a  mov     [rsp+238h+var_1A8], r12
0x140029652  mov     r9, [rsp+238h+arg_30]
0x14002965a  mov     [rsp+238h+var_1B8], r9
0x140029662  mov     rax, [rsp+238h+arg_48]
0x14002966a  mov     [rsp+238h+var_1C0], rax
0x14002966f  xor     esi, esi
0x140029671  mov     r15d, esi
0x140029674  mov     qword ptr [rsp+238h+var_1C8], rsi
0x140029679  test    r12, r12
0x14002967c  jnz     short loc_1400296A1
0x14002967e  cmp     [rsp+238h+Length], rsi
0x140029686  jz      short loc_1400296A1
0x140029688  mov     edi, 0C000000Dh
0x14002968d  mov     r13b, [rsp+238h+arg_50]
0x140029695  mov     ebx, [rsp+238h+arg_40]
0x14002969c  jmp     loc_140029D81
0x1400296a1  test    r9, r9
0x1400296a4  jnz     short loc_1400296B0
0x1400296a6  cmp     [rsp+238h+arg_38], rsi
0x1400296ae  jnz     short loc_140029688
0x1400296b0  test    r12, r12
0x1400296b3  jnz     short loc_1400296BA
0x1400296b5  test    r9, r9
0x1400296b8  jz      short loc_140029688
0x1400296ba  mov     r13b, [rsp+238h+arg_50]
0x1400296c2  mov     r8b, r13b
0x1400296c5  mov     ebx, [rsp+238h+arg_40]
0x1400296cc  mov     edx, ebx
0x1400296ce  call    VsmmpValidateMbpRwFlags
0x1400296d3  test    al, al
0x1400296d5  jnz     loc_140029846
0x1400296db  mov     edi, 0C000000Dh
0x1400296e0  mov     eax, cs:dword_140064110
0x1400296e6  cmp     eax, 2
0x1400296e9  jbe     loc_140029D81
0x1400296ef  mov     edx, 100h
0x1400296f4  lea     rcx, dword_140064110
0x1400296fb  call    _tlgKeywordOn
0x140029700  test    al, al
0x140029702  jz      loc_140029D81
0x140029708  lea     rdx, aVsmmioctlreadw; "VsmmIoctlReadWriteMemoryBlockPageRange"
0x14002970f  lea     rcx, [rsp+238h+var_158]
0x140029717  call    _tlgCreate1Sz_char
0x14002971c  lea     rdx, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x140029723  lea     rcx, [rsp+238h+var_148]
0x14002972b  call    _tlgCreate1Sz_char
0x140029730  mov     [rsp+238h+var_1C8], 0E11h
0x140029738  lea     rax, [rsp+238h+var_1C8]
0x14002973d  mov     [rsp+238h+var_138], rax
0x140029745  mov     [rsp+238h+var_130], 4
0x140029751  mov     dword ptr [rsp+238h+var_1C0], edi
0x140029755  lea     rax, [rsp+238h+var_1C0]
0x14002975a  mov     [rsp+238h+var_128], rax
0x140029762  mov     [rsp+238h+var_120], 4
0x14002976e  mov     rcx, [rsp+238h+var_1D8]
0x140029773  lea     rax, [rcx+290h]
0x14002977a  mov     [rsp+238h+var_118], rax
0x140029782  mov     [rsp+238h+var_110], 10h
0x14002978e  lea     rax, [rsp+238h+var_F0]
0x140029796  mov     [rsp+238h+var_108], rax
0x14002979e  mov     [rsp+238h+var_100], 2
0x1400297aa  mov     rax, [rcx+80h]
0x1400297b1  mov     [rsp+238h+var_F8], rax
0x1400297b9  movzx   eax, word ptr [rcx+78h]
0x1400297bd  mov     [rsp+238h+var_F0], eax
0x1400297c4  mov     [rsp+238h+var_EC], esi
0x1400297cb  mov     rax, [rcx+288h]
0x1400297d2  mov     [rsp+238h+var_1A8], rax
0x1400297da  lea     rax, [rsp+238h+var_1A8]
0x1400297e2  mov     [rsp+238h+var_E8], rax
0x1400297ea  mov     [rsp+238h+var_E0], 8
0x1400297f6  mov     dword ptr [rsp+238h+var_1E8], ebx
0x1400297fa  lea     rax, [rsp+238h+var_1E8]
0x1400297ff  mov     [rsp+238h+var_D8], rax
0x140029807  mov     [rsp+238h+var_D0], 4
0x140029813  lea     rax, [rsp+238h+var_178]
0x14002981b  mov     [rsp+238h+Size], rax
0x140029820  mov     [rsp+238h+var_218], 0Bh
0x140029828  xor     r9d, r9d
0x14002982b  xor     r8d, r8d
0x14002982e  lea     rdx, dword_1400555E4
0x140029835  lea     rcx, dword_140064110
0x14002983c  call    _tlgWriteTransfer_EtwWriteTransfer
0x140029841  jmp     loc_140029D81
0x140029846  lea     rax, [rsp+238h+var_1C8]
0x14002984b  mov     qword ptr [rsp+238h+var_218], rax
0x140029850  xor     r9d, r9d
0x140029853  xor     r8d, r8d
0x140029856  mov     rdx, [rsp+238h+var_1B0]
0x14002985e  mov     rcx, [rsp+238h+var_1D8]
0x140029863  call    VsmmMemoryBlockLookupByHandle
0x140029868  mov     edi, eax
0x14002986a  mov     r15, qword ptr [rsp+238h+var_1C8]
0x14002986f  test    eax, eax
0x140029871  js      loc_140029D81
0x140029877  mov     rax, [r15+30h]
0x14002987b  lea     rcx, [rax-1]
0x14002987f  mov     rdi, qword ptr [rsp+238h+var_1D0]
0x140029884  cmp     rdi, rcx
0x140029887  ja      loc_140029D63
0x14002988d  cmp     r14, rax
0x140029890  ja      loc_140029D63
0x140029896  lea     rax, [rdi-1]
0x14002989a  add     rax, r14
0x14002989d  cmp     rax, rcx
0x1400298a0  ja      loc_140029D63
0x1400298a6  test    r12, r12
0x1400298a9  jz      loc_1400299D7
0x1400298af  mov     rcx, [rsp+238h+Length]
0x1400298b7  test    bl, 0Ch
0x1400298ba  jnz     short loc_1400298EB
0x1400298bc  mov     rax, r14
0x1400298bf  shl     rax, 0Ch
0x1400298c3  cmp     rcx, rax
0x1400298c6  jnb     short loc_1400298EB
0x1400298c8  mov     edi, 0C0000023h
0x1400298cd  mov     r8d, 0E42h
0x1400298d3  lea     rdx, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x1400298da  lea     rcx, aVsmmioctlreadw; "VsmmIoctlReadWriteMemoryBlockPageRange"
0x1400298e1  call    VidTraceErrorInternal0
0x1400298e6  jmp     loc_140029D81
0x1400298eb  mov     r8d, 1; Alignment
0x1400298f1  mov     rdx, rcx; Length
0x1400298f4  mov     rcx, r12; Address
0x1400298f7  test    r13b, r13b
0x1400298fa  jz      short loc_14002990A
0x1400298fc  call    cs:__imp_ProbeForRead
0x140029903  nop     dword ptr [rax+rax+00h]
0x140029908  jmp     short loc_140029917
0x14002990a  call    cs:__imp_ProbeForWrite
0x140029911  nop     dword ptr [rax+rax+00h]
0x140029916  nop
0x140029917  mov     r12d, ebx
0x14002991a  shr     r12d, 12h
0x14002991e  and     r12d, 3
0x140029922  mov     r9, [rsp+238h+var_1B8]
0x14002992a  test    r9, r9
0x14002992d  jz      loc_140029A7D
0x140029933  test    r12d, r12d
0x140029936  jz      loc_1400299E8
0x14002993c  mov     r8d, 1; Alignment
0x140029942  mov     rdx, [rsp+238h+arg_38]; Length
0x14002994a  mov     rcx, r9; Address
0x14002994d  test    r13b, r13b
0x140029950  jz      loc_1400299F7
0x140029956  call    cs:__imp_ProbeForRead
0x14002995d  nop     dword ptr [rax+rax+00h]
0x140029962  jmp     loc_140029A03
0x140029967  mov     edi, eax
0x140029969  mov     r8d, 0E62h
0x14002996f  lea     rdx, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x140029976  lea     rcx, aVsmmioctlreadw; "VsmmIoctlReadWriteMemoryBlockPageRange"
0x14002997d  call    VidTraceErrorInternal0
0x140029982  xor     esi, esi
0x140029984  mov     r13b, [rsp+238h+arg_50]
0x14002998c  mov     ebx, [rsp+238h+arg_40]
0x140029993  mov     r15, qword ptr [rsp+238h+var_1C8]
0x140029998  mov     rax, [rsp+238h+var_1A0]
0x1400299a0  mov     [rsp+238h+var_1D8], rax
0x1400299a5  mov     rcx, [rsp+238h+var_198]
0x1400299ad  mov     [rsp+238h+var_1B0], rcx
0x1400299b5  mov     rax, [rsp+238h+var_190]
0x1400299bd  mov     qword ptr [rsp+238h+var_1D0], rax
0x1400299c2  mov     r14, [rsp+238h+var_188]
0x1400299ca  mov     r12, [rsp+238h+var_1A8]
0x1400299d2  jmp     loc_140029D81
0x1400299d7  mov     r12d, ebx
0x1400299da  shr     r12d, 12h
0x1400299de  test    r12b, 3
0x1400299e2  jnz     loc_14002991E
0x1400299e8  mov     edi, 0C000000Dh
0x1400299ed  mov     r12, [rsp+238h+var_1E8]
0x1400299f2  jmp     loc_140029D81
0x1400299f7  call    cs:__imp_ProbeForWrite
0x1400299fe  nop     dword ptr [rax+rax+00h]
0x140029a03  mov     r9, [rsp+238h+var_1B8]
0x140029a0b  jmp     short loc_140029A7D
0x140029a0d  mov     edi, eax
0x140029a0f  mov     r8d, 0E89h
0x140029a15  lea     rdx, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x140029a1c  lea     rcx, aVsmmioctlreadw; "VsmmIoctlReadWriteMemoryBlockPageRange"
0x140029a23  call    VidTraceErrorInternal0
0x140029a28  xor     esi, esi
0x140029a2a  mov     r13b, [rsp+238h+arg_50]
0x140029a32  mov     ebx, [rsp+238h+arg_40]
0x140029a39  mov     r15, qword ptr [rsp+238h+var_1C8]
0x140029a3e  mov     rax, [rsp+238h+var_1A0]
0x140029a46  mov     [rsp+238h+var_1D8], rax
0x140029a4b  mov     rax, [rsp+238h+var_198]
0x140029a53  mov     [rsp+238h+var_1B0], rax
0x140029a5b  mov     rax, [rsp+238h+var_190]
0x140029a63  mov     qword ptr [rsp+238h+var_1D0], rax
0x140029a68  mov     r14, [rsp+238h+var_188]
0x140029a70  mov     r12, [rsp+238h+var_1A8]
0x140029a78  jmp     loc_140029D81
0x140029a7d  test    r12d, r12d
0x140029a80  jz      short loc_140029AFE
0x140029a82  cmp     dword ptr [r15+0F4h], 1
0x140029a8a  jnz     loc_1400299E8
0x140029a90  mov     rcx, [rsp+238h+var_1D8]
0x140029a95  cmp     r12d, 2
0x140029a99  jz      short loc_140029B0D
0x140029a9b  mov     eax, [rcx+20h]
0x140029a9e  and     eax, 1E0h
0x140029aa3  cmp     rax, 20h ; ' '
0x140029aa7  jz      short loc_140029AB9
0x140029aa9  mov     r8, r14
0x140029aac  mov     rdx, rdi
0x140029aaf  mov     rcx, r15
0x140029ab2  call    VsmmModifyMbpRangeHostVisibility
0x140029ab7  jmp     short loc_140029AEF
0x140029ab9  test    r13b, r13b
0x140029abc  jnz     short loc_140029B03
0x140029abe  mov     [rsp+238h+var_1F8], sil; char
0x140029ac3  mov     [rsp+238h+var_200], ebx; int
0x140029ac7  mov     rax, [rsp+238h+arg_38]
0x140029acf  mov     qword ptr [rsp+238h+var_208], rax; ULONG
0x140029ad4  mov     [rsp+238h+Size], r9; __int64
0x140029ad9  mov     qword ptr [rsp+238h+var_218], rsi; Length
0x140029ade  xor     r9d, r9d; int
0x140029ae1  mov     r8, r14; int
0x140029ae4  mov     rdx, rdi; int
0x140029ae7  mov     rcx, r15; int
0x140029aea  call    VsmmSvcImportExportMbpRange
0x140029aef  test    eax, eax
0x140029af1  mov     edi, eax
0x140029af3  js      loc_1400299ED
0x140029af9  mov     rdi, qword ptr [rsp+238h+var_1D0]
0x140029afe  mov     rcx, [rsp+238h+var_1D8]
0x140029b03  cmp     r12d, 2
0x140029b07  jnz     loc_140029BAE
0x140029b0d  mov     eax, [rcx+20h]
0x140029b10  and     eax, 1E0h
0x140029b15  cmp     rax, 20h ; ' '
0x140029b19  jnz     short loc_140029B60
0x140029b1b  mov     [rsp+238h+var_1F8], r13b; char
0x140029b20  mov     [rsp+238h+var_200], ebx; int
0x140029b24  mov     rax, [rsp+238h+arg_38]
0x140029b2c  mov     qword ptr [rsp+238h+var_208], rax; ULONG
0x140029b31  mov     rax, [rsp+238h+var_1B8]
0x140029b39  mov     [rsp+238h+Size], rax; __int64
0x140029b3e  mov     rax, [rsp+238h+Length]
0x140029b46  mov     qword ptr [rsp+238h+var_218], rax; Length
0x140029b4b  mov     r9, [rsp+238h+var_1E8]; int
0x140029b50  mov     r8, r14; int
0x140029b53  mov     rdx, rdi; int
0x140029b56  mov     rcx, r15; int
0x140029b59  call    VsmmSvcImportExportMbpRange
0x140029b5e  jmp     short loc_140029BA0
0x140029b60  test    r13b, r13b
0x140029b63  jnz     loc_1400299E8
0x140029b69  test    bl, 0Ch
0x140029b6c  jnz     loc_1400299E8
0x140029b72  cmp     [rsp+238h+arg_38], rsi
0x140029b7a  jnz     loc_1400299E8
0x140029b80  mov     rax, [rsp+238h+Length]
0x140029b88  mov     qword ptr [rsp+238h+var_218], rax
0x140029b8d  mov     r9, [rsp+238h+var_1E8]
0x140029b92  mov     r8, r14
0x140029b95  mov     rdx, rdi
0x140029b98  mov     rcx, r15
0x140029b9b  call    VsmmHwIsoDebugReadMbpRange
0x140029ba0  mov     edi, eax
0x140029ba2  mov     r12, [rsp+238h+var_1E8]
0x140029ba7  test    eax, eax
0x140029ba9  jmp     loc_140029C4D
0x140029bae  test    bl, 3
0x140029bb1  jnz     short loc_140029C0A
0x140029bb3  mov     rax, [r15+8]
0x140029bb7  test    byte ptr [rax+28h], 2
0x140029bbb  jz      short loc_140029C0A
0x140029bbd  mov     rax, [rsp+238h+Length]
0x140029bc5  mov     r12, [rsp+238h+var_1E8]
0x140029bca  mov     r9d, ebx; int
0x140029bcd  mov     r8, r14; int
0x140029bd0  mov     rdx, rdi; int
0x140029bd3  test    r13b, r13b
0x140029bd6  jz      short loc_140029BEC
  ... truncated ...
```
