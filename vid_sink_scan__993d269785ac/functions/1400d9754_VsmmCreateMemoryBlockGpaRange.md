# VsmmCreateMemoryBlockGpaRange

- ea: `0x1400d9754`
- end: `0x1400daa8f`
- name: `VsmmCreateMemoryBlockGpaRange`
- size: `4923`
- prototype: `__int64 __usercall@<rax>(PVOID P@<rcx>, __int64, __int64, __int64, int, __int64)`
- caller_count: `2`
- callee_count: `29`
- tags: ``

## callers

- `0x140035698`
- `0x14008aaf0`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x14000a4e0`
- `0x140021650`
- `0x14002e080`
- `0x14002f524`
- `0x1400303c0`
- `0x140034554`
- `0x140034914`
- `0x140038630`
- `0x14009abb8`
- `0x14009aefc`
- `0x14009ea60`
- `0x1400aa41c`
- `0x1400acf1c`
- `0x1400b0f00`
- `0x1400d1728`
- `0x1400d9754`
- `0x1400ee9e0`
- `0x1400ef710`
- `0x1400efcc0`
- `0x1400f2e2c`
- `0x1400f380c`
- `0x1400f42c8`
- `0x1400f57e8`
- `0x1400f6994`
- `0x1400f8bd8`
- `0x1400fb920`
- `0x1400fbdbc`

## string_xrefs

- `0x1400d9819`: `VsmmCreateMemoryBlockGpaRange`
- `0x1400d9856`: `VsmmCreateMemoryBlockGpaRange`
- `0x1400d9886`: `VsmmCreateMemoryBlockGpaRange`
- `0x1400d98c0`: `VsmmCreateMemoryBlockGpaRange`
- `0x1400d98ef`: `VsmmCreateMemoryBlockGpaRange`
- `0x1400d9920`: `VsmmCreateMemoryBlockGpaRange`
- `0x1400d998f`: `VsmmCreateMemoryBlockGpaRange`
- `0x1400d9acd`: `VsmmCreateMemoryBlockGpaRange`
- `0x1400d9b4b`: `VsmmCreateMemoryBlockGpaRange`
- `0x1400d9bf0`: `VsmmCreateMemoryBlockGpaRange`
- `0x1400d9cc6`: `VsmmCreateMemoryBlockGpaRange`
- `0x1400d9d6b`: `VsmmCreateMemoryBlockGpaRange`
- `0x1400d9de5`: `VsmmCreateMemoryBlockGpaRange`
- `0x1400d9ed1`: `VsmmCreateMemoryBlockGpaRange`
- `0x1400da060`: `VsmmCreateMemoryBlockGpaRange`
- `0x1400da0b7`: `VsmmCreateMemoryBlockGpaRange`
- `0x1400da183`: `VsmmCreateMemoryBlockGpaRange`
- `0x1400da2b9`: `VsmmCreateMemoryBlockGpaRange`
- `0x1400da30c`: `VsmmCreateMemoryBlockGpaRange`
- `0x1400da3a9`: `VsmmCreateMemoryBlockGpaRange`
- `0x1400da426`: `VsmmCreateMemoryBlockGpaRange`
- `0x1400da57f`: `VsmmCreateMemoryBlockGpaRange`
- `0x1400da6db`: `VsmmCreateMemoryBlockGpaRange`
- `0x1400da75f`: `VsmmCreateMemoryBlockGpaRange`
- `0x1400da7af`: `VsmmCreateMemoryBlockGpaRange`
- `0x1400da82d`: `VsmmCreateMemoryBlockGpaRange`
- `0x1400da8d5`: `VsmmCreateMemoryBlockGpaRange`

## pseudocode

```c
__int64 __fastcall VsmmCreateMemoryBlockGpaRange(
        _DWORD *P,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        _QWORD *a7,
        unsigned int a8,
        _QWORD *a9)
{
  __int64 v10; // rsi
  __int64 v11; // r13
  __int64 v12; // r15
  __int64 v13; // rdi
  int Entry; // ebx
  int v15; // r15d
  __int64 v16; // r9
  __int64 v17; // r10
  __int16 *v18; // rdx
  __int64 *v19; // rax
  __int64 v20; // r12
  __int64 v21; // rdx
  __int64 v22; // rcx
  int v23; // r8d
  __int64 v24; // r8
  int v25; // ecx
  int v26; // r8d
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rcx
  int v30; // r11d
  _QWORD *v31; // rcx
  __int64 v32; // r9
  __int64 v33; // rax
  __int64 v34; // rax
  int v35; // edx
  __int64 v36; // rcx
  int v37; // r11d
  _QWORD *v38; // rcx
  __int64 v39; // r9
  unsigned __int64 v40; // rax
  unsigned __int64 v41; // r9
  char *v42; // rdx
  int v43; // r11d
  __int64 v44; // r9
  __int64 v45; // rdx
  unsigned __int64 v46; // rbx
  unsigned __int64 v47; // rdx
  unsigned __int64 v48; // r12
  __int64 v49; // rcx
  __int64 v50; // rcx
  unsigned __int64 v51; // rdx
  int v52; // r15d
  __int64 v53; // rdx
  __int64 v54; // rbx
  int v55; // eax
  __int64 v56; // r8
  __int64 v58; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v59; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v60; // [rsp+50h] [rbp-B0h] BYREF
  char v61; // [rsp+58h] [rbp-A8h]
  _QWORD *v62; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v63; // [rsp+68h] [rbp-98h] BYREF
  __int64 v64; // [rsp+70h] [rbp-90h] BYREF
  __int64 v65; // [rsp+78h] [rbp-88h] BYREF
  __int64 v66; // [rsp+80h] [rbp-80h] BYREF
  __int64 v67; // [rsp+88h] [rbp-78h] BYREF
  __int64 v68; // [rsp+90h] [rbp-70h] BYREF
  _OWORD v69[2]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v70; // [rsp+B8h] [rbp-48h]
  _BYTE v71[32]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v72[16]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v73[16]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 *v74; // [rsp+100h] [rbp+0h]
  __int64 v75; // [rsp+108h] [rbp+8h]
  __int64 *v76; // [rsp+110h] [rbp+10h]
  __int64 v77; // [rsp+118h] [rbp+18h]
  char *v78; // [rsp+120h] [rbp+20h]
  __int64 v79; // [rsp+128h] [rbp+28h]
  int *v80; // [rsp+130h] [rbp+30h]
  __int64 v81; // [rsp+138h] [rbp+38h]
  __int64 v82; // [rsp+140h] [rbp+40h]
  int v83; // [rsp+148h] [rbp+48h] BYREF
  int v84; // [rsp+14Ch] [rbp+4Ch]
  __int64 *v85; // [rsp+150h] [rbp+50h]
  __int64 v86; // [rsp+158h] [rbp+58h]
  __int64 *v87; // [rsp+160h] [rbp+60h]
  __int64 v88; // [rsp+168h] [rbp+68h]
  __int64 *v89; // [rsp+170h] [rbp+70h]
  __int64 v90; // [rsp+178h] [rbp+78h]
  __int64 *v91; // [rsp+180h] [rbp+80h]
  __int64 v92; // [rsp+188h] [rbp+88h]
  __int64 *v93; // [rsp+190h] [rbp+90h]
  __int64 v94; // [rsp+198h] [rbp+98h]
  __int64 *v95; // [rsp+1A0h] [rbp+A0h]
  __int64 v96; // [rsp+1A8h] [rbp+A8h]
  __int64 *v97; // [rsp+1B0h] [rbp+B0h]
  __int64 v98; // [rsp+1B8h] [rbp+B8h]
  __int64 *v99; // [rsp+1C0h] [rbp+C0h]
  __int64 v100; // [rsp+1C8h] [rbp+C8h]

  v65 = a4;
  v70 = 0;
  v10 = 0;
  v58 = a3;
  v11 = 0;
  v63 = a2;
  v62 = a9;
  v12 = a3;
  v59 = 0;
  v60 = 0;
  v61 = 0;
  v69[0] = 0;
  *a9 = -1;
  v69[1] = 0;
  VidObjectLockAcquireExclusive(P + 934);
  v13 = a6;
  v64 = (unsigned __int8)a6 & 0x80;
  if ( ((a6 & 0x80) != 0) != (a7 != 0) )
  {
    Entry = -1073741811;
    VidTraceErrorStatusInternal0("VsmmCreateMemoryBlockGpaRange", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 1155);
LABEL_26:
    v20 = (__int64)a7;
    goto LABEL_27;
  }
  if ( (a6 & 0x80) != 0 && !*((_BYTE *)P + 8657) )
  {
    Entry = VsmmPhuCheckObjectRestore(P, a7);
    if ( Entry < 0 )
    {
      VidTraceErrorStatusInternal0("VsmmCreateMemoryBlockGpaRange", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 1170);
      goto LABEL_26;
    }
    if ( P[2159] != 2 )
    {
      Entry = -1073741811;
      VidTraceErrorStatusInternal0("VsmmCreateMemoryBlockGpaRange", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 1180);
      goto LABEL_26;
    }
  }
  Entry = VsmmGpaRangeValidatePageRange(P, v63, v12);
  if ( Entry < 0 )
  {
    VidTraceErrorStatusInternal0("VsmmCreateMemoryBlockGpaRange", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 1191);
    goto LABEL_26;
  }
  if ( (a6 & 0xFFFFFFFFFFFFFC00uLL) != 0 )
  {
    Entry = -1073741811;
    VidTraceErrorStatusInternal0("VsmmCreateMemoryBlockGpaRange", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 1198);
    goto LABEL_26;
  }
  if ( (a6 & 4) != 0 )
  {
    Entry = -1073741811;
    VidTraceErrorStatusInternal0("VsmmCreateMemoryBlockGpaRange", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 1208);
    goto LABEL_26;
  }
  if ( (a6 & 0x261) != 0 || (v15 = 0, a8 == 1) )
    v15 = 1;
  if ( (a6 & 0x100) != 0 )
  {
    if ( a8 != 1 )
    {
      Entry = -1073741811;
      if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
        goto LABEL_25;
      tlgCreate1Sz_char(v72, "VsmmCreateMemoryBlockGpaRange");
      tlgCreate1Sz_char(v73, "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c");
      LODWORD(v60) = 1237;
      v74 = &v60;
      v18 = (__int16 *)&dword_1400584C4;
      v19 = &v59;
      LODWORD(v59) = -1073741811;
      goto LABEL_23;
    }
    if ( (P[2194] & 4) == 0 )
    {
      Entry = -1073741811;
      if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
        goto LABEL_25;
      tlgCreate1Sz_char(v72, "VsmmCreateMemoryBlockGpaRange");
      tlgCreate1Sz_char(v73, "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c");
      LODWORD(v59) = 1244;
      v74 = &v59;
      v18 = &word_140058266;
      v19 = &v60;
      LODWORD(v60) = -1073741811;
      goto LABEL_23;
    }
    if ( (a6 & 0x80) != 0 )
    {
      Entry = -1073741637;
      if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
        goto LABEL_25;
      tlgCreate1Sz_char(v72, "VsmmCreateMemoryBlockGpaRange");
      tlgCreate1Sz_char(v73, "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c");
      LODWORD(v59) = 1258;
      v74 = &v59;
      v18 = (__int16 *)&dword_1400582D4;
      v19 = &v60;
      LODWORD(v60) = v23;
LABEL_23:
      v76 = v19;
      v78 = (char *)(P + 164);
      v80 = &v83;
      v82 = *((_QWORD *)P + 16);
      v83 = *((unsigned __int16 *)P + 60);
      v62 = (_QWORD *)*((_QWORD *)P + 81);
      v75 = v17;
      v77 = v17;
      v79 = 16;
      v81 = 2;
      v84 = v16;
      v86 = 8;
LABEL_24:
      v85 = (__int64 *)&v62;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, v18, 0, v16, 10, v71);
LABEL_25:
      v12 = v58;
      goto LABEL_26;
    }
  }
  else if ( (a6 & 0x80) != 0 )
  {
    if ( *((_BYTE *)P + 8657) )
    {
      v20 = (__int64)a7;
      Entry = VsmmGpaRangeLookupByPersistId(P, a7, a8, v62);
      if ( Entry < 0 && (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
      {
        tlgCreate1Sz_char(v72, "VsmmCreateMemoryBlockGpaRange");
        tlgCreate1Sz_char(v73, "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c");
        LODWORD(v59) = 1281;
        v74 = &v59;
        v75 = 4;
        v76 = (__int64 *)&v62;
        v62 = a7;
        v77 = 8;
        tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, word_140058342, 0, 0, 6, v71);
      }
      v12 = v58;
      goto LABEL_27;
    }
    v15 |= 2u;
  }
  if ( (unsigned int)VsmmGpaRangeListOverlapCheck((_DWORD)P, v63, v58, v15, 0) )
  {
    Entry = -1070137272;
    if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
    {
      tlgCreate1Sz_char(v72, "VsmmCreateMemoryBlockGpaRange");
      tlgCreate1Sz_char(v73, "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c");
      LODWORD(v59) = 1300;
      v74 = &v59;
      v75 = 4;
      v76 = &v60;
      LODWORD(v60) = v15;
      v77 = 4;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, word_140058382, 0, 0, 6, v71);
    }
    goto LABEL_25;
  }
  Entry = VsmmMemoryBlockLookupByHandle((_DWORD)P, v65, a8, 1, (__int64)&v59);
  if ( Entry < 0 )
  {
    VidTraceErrorInternal0("VsmmCreateMemoryBlockGpaRange", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 1318);
    v10 = v59;
    goto LABEL_25;
  }
  v10 = v59;
  v25 = *(_DWORD *)(v59 + 20);
  if ( (v25 & 8) != 0 )
  {
    Entry = -1070137326;
    goto LABEL_25;
  }
  if ( (a6 & 0x200) != 0 )
  {
    if ( (P[4] & 0x10) != 0 )
    {
      Entry = -1073741637;
      if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
        goto LABEL_25;
      tlgCreate1Sz_char(v72, "VsmmCreateMemoryBlockGpaRange");
      tlgCreate1Sz_char(v73, "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c");
      LODWORD(v59) = 1350;
      v74 = &v59;
      v76 = &v60;
      v75 = 4;
      LODWORD(v60) = v26;
      v77 = 4;
      v27 = *(_QWORD *)(v10 + 8) + 656LL;
      v79 = 16;
      v78 = (char *)v27;
      v28 = *(_QWORD *)(v10 + 8);
      v29 = *(_QWORD *)(v28 + 128);
      v83 = *(unsigned __int16 *)(v28 + 120);
      v18 = word_14005809A;
      v80 = &v83;
      v81 = 2;
      v82 = v29;
      v84 = v30;
      v31 = *(_QWORD **)(*(_QWORD *)(v10 + 8) + 648LL);
      v86 = v32;
      v16 = 0;
      v62 = v31;
      goto LABEL_24;
    }
    if ( (a6 & 0xFFFFFFFFFFFFFC7FuLL) != 0 )
    {
      Entry = -1073741811;
      if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
      {
        tlgCreate1Sz_char(v72, "VsmmCreateMemoryBlockGpaRange");
        tlgCreate1Sz_char(v73, "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c");
        LODWORD(v59) = 1368;
        v74 = &v59;
        v76 = &v60;
        v75 = 4;
        LODWORD(v60) = -1073741811;
        v77 = 4;
        v33 = *(_QWORD *)(v10 + 8) + 656LL;
        v79 = 16;
        v78 = (char *)v33;
        v34 = *(_QWORD *)(v10 + 8);
        v35 = *(unsigned __int16 *)(v34 + 120);
        v36 = *(_QWORD *)(v34 + 128);
        v80 = &v83;
        v83 = v35;
        v81 = 2;
        v82 = v36;
        v84 = v37;
        v38 = *(_QWORD **)(*(_QWORD *)(v10 + 8) + 648LL);
        v85 = (__int64 *)&v62;
        v87 = &v64;
        v86 = v39;
        v88 = v39;
        v62 = v38;
        v64 = a6;
        tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, qword_140058108, 0, 0, 11, v71);
      }
      goto LABEL_25;
    }
    v40 = 0;
  }
  else
  {
    v40 = a6 & 0xFFFFFFFFFFFFFC7FuLL;
  }
  LOBYTE(v24) = 32;
  if ( a8 )
  {
    v12 = v58;
    if ( a8 != 1 )
      goto LABEL_76;
    v41 = a5;
    if ( a5 || v58 != *(_QWORD *)(v59 + 40) || v40 )
      goto LABEL_76;
  }
  else
  {
    if ( ((a6 & 1) != 0 || (a6 & 0x20) != 0) && (a6 & 2) != 0 || (a6 & 8) != 0 && ((v25 & 1) == 0 || (a6 & 0x80) != 0) )
    {
      Entry = -1073741811;
      goto LABEL_25;
    }
    v12 = v58;
    if ( (a6 & 0xFFFFFFFFFFFFFF2FuLL) != 0 && (a6 & 0x40) != 0 )
    {
LABEL_76:
      Entry = -1073741811;
      goto LABEL_26;
    }
    v41 = a5;
  }
  if ( *(_QWORD *)(v59 + 232) == -1 )
  {
    Entry = -1070137322;
    VidTraceErrorInternal0("VsmmCreateMemoryBlockGpaRange", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 1452);
    goto LABEL_26;
  }
  if ( *(_DWORD *)(v59 + 224) && (P[4] & 2) == 0 )
  {
    Entry = -1070137326;
    if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
      goto LABEL_26;
    tlgCreate1Sz_char(v72, "VsmmCreateMemoryBlockGpaRange");
    tlgCreate1Sz_char(v73, "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c");
    LODWORD(v59) = 1463;
    v42 = byte_14005817D;
    goto LABEL_90;
  }
  if ( *(_DWORD *)(v59 + 244) == 1 && (v41 || v12 != *(_QWORD *)(v59 + 40)) )
  {
    Entry = -1073741811;
    if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
    {
      tlgCreate1Sz_char(v72, "VsmmCreateMemoryBlockGpaRange");
      tlgCreate1Sz_char(v73, "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c");
      LODWORD(v59) = 1484;
      v74 = &v59;
      v75 = 4;
      v76 = &v60;
      v78 = (char *)(P + 164);
      v80 = &v83;
      v82 = *((_QWORD *)P + 16);
      v83 = *((unsigned __int16 *)P + 60);
      v62 = (_QWORD *)*((_QWORD *)P + 81);
      v85 = (__int64 *)&v62;
      v87 = &v64;
      v89 = &v58;
      LODWORD(v60) = -1073741811;
      v77 = 4;
      v79 = 16;
      v81 = 2;
      v84 = v43;
      v86 = 8;
      v64 = v44;
      v88 = 8;
      v58 = v12;
      v90 = 8;
      v66 = *(_QWORD *)(v10 + 40);
      v91 = &v66;
      v92 = 8;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, word_1400581D2, 0, 0, 13, v71);
    }
    goto LABEL_26;
  }
  if ( (a6 & 1) != 0 )
  {
    if ( *(_QWORD *)&P[2 * *(unsigned __int8 *)(v59 + 16) + 2246] )
    {
      Entry = -1073741811;
      VidTraceErrorInternal0("VsmmCreateMemoryBlockGpaRange", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 1498);
      goto LABEL_26;
    }
    if ( (*(_DWORD *)(v59 + 20) & 1) == 0 )
      goto LABEL_76;
    if ( *(_DWORD *)(v59 + 224) )
    {
      Entry = -1073741811;
      if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
        goto LABEL_26;
      tlgCreate1Sz_char(v72, "VsmmCreateMemoryBlockGpaRange");
      tlgCreate1Sz_char(v73, "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c");
      LODWORD(v59) = 1523;
      v42 = byte_140057F2B;
      goto LABEL_90;
    }
    if ( v41 )
      goto LABEL_76;
    v45 = *(_QWORD *)(v59 + 40);
    if ( v12 != v45 )
      goto LABEL_76;
    v46 = v63;
    v47 = v45 - 1;
    v48 = *(_QWORD *)(v59 + 48) + v63 - 1;
    goto LABEL_133;
  }
  if ( (*(_DWORD *)(v59 + 20) & 1) != 0 && !*(_DWORD *)(v59 + 224) )
  {
    Entry = -1073741811;
    if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
      goto LABEL_26;
    tlgCreate1Sz_char(v72, "VsmmCreateMemoryBlockGpaRange");
    tlgCreate1Sz_char(v73, "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c");
    LODWORD(v59) = 1552;
    v42 = (char *)qword_140057F80;
LABEL_90:
    v75 = 4;
    v74 = &v59;
    LODWORD(v60) = *(_DWORD *)(v10 + 224);
    v76 = &v60;
    v77 = 4;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, v42, 0, 0, 6, v71);
    goto LABEL_26;
  }
  v46 = v63;
  v47 = *(_QWORD *)(v59 + 48) - 1LL;
  v48 = v12 + v63 - 1;
  if ( (a6 & 0x20) != 0 )
  {
    if ( (*(_DWORD *)(v59 + 20) & 0x20) == 0 )
      goto LABEL_76;
    if ( !*(_QWORD *)(v59 + 640) && P[2158] == 2 )
    {
      Entry = -1073741811;
      VidTraceErrorInternal0("VsmmCreateMemoryBlockGpaRange", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 1580);
      goto LABEL_26;
    }
    v13 = a6 | 0x2010;
  }
  else
  {
    v24 = *(unsigned int *)(v59 + 20);
    if ( (a6 & 0x40) != 0 )
    {
      if ( (v24 & 0x40) == 0 )
        goto LABEL_76;
      v13 = a6 | 0x2000;
    }
    else if ( (v24 & 0x40) != 0 )
    {
      goto LABEL_76;
    }
    if ( (v24 & 0x20) != 0 )
      goto LABEL_76;
    v49 = v13 | 0x2010;
    if ( (v13 & 0x200) == 0 )
      v49 = v13;
    v13 = v49;
    if ( a8 == 1 )
    {
      if ( (v49 & 0x200) == 0 )
      {
        v13 = v49 | 0x2000;
        if ( (P[8] & 0x1E0LL) == 0 )
          v13 = v49 | 0x12000;
      }
    }
    else if ( (P[4] & 0x40) != 0 || (v24 & 1) != 0 )
    {
LABEL_133:
      v13 |= 0x10uLL;
    }
  }
  v50 = v13 | 0x2000;
  if ( (P[4] & 1) != 0 )
    v50 = v13;
  v13 = v50;
  if ( v41 > v47 || v12 - 1 > v47 || (v51 = v47 - v12 + 1, v51 < v41) || v48 < v46 )
  {
    Entry = -1070137325;
    goto LABEL_26;
  }
  if ( (v50 & 0x48) != 0 )
  {
    v13 = v50 & 0xFFFFFFFFFFFFFFF7uLL;
    v52 = VsmmVsmAnyDefaultVtlProtectionsRequired(P, v51, v24);
  }
  else
  {
    v52 = 0;
  }
  v53 = *(unsigned __int8 *)(v10 + 16);
  if ( (_BYTE)v53 != 0xFF && *(_QWORD *)&P[4 * v53 + 544] )
    VidNumaSetGroupAffinity(P, v53, v69);
  Entry = VsmmGpaRangeAlloc((volatile signed __int64 *)P, 0, v13, v46, v58, (PVOID *)&v60);
  if ( Entry < 0 )
  {
    VidTraceErrorInternal0("VsmmCreateMemoryBlockGpaRange", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 1743);
    v11 = v60;
    goto LABEL_25;
  }
  v11 = v60;
  VsmmGpaRangeInitializeMbBacked(v60, v10, a5);
  v54 = v63;
  *(_QWORD *)(v11 + 264) = v48;
  if ( (v13 & 1) != 0 )
    *(_QWORD *)(v10 + 872) = v54 & 0x3FFFF;
  _InterlockedIncrement64((volatile signed __int64 *)(*((_QWORD *)P + 191) + 784LL));
  _InterlockedAdd64((volatile signed __int64 *)(*((_QWORD *)P + 191) + ((v13 & 2) != 0 ? 800LL : 792LL)), v58);
  if ( v64 )
  {
    Entry = VsmmPhuStoreGpaRangeRestore(v11, (_DWORD)a7, v54, v58, a5, v13);
    if ( Entry < 0 )
      goto LABEL_25;
  }
  else
  {
    VsmmHvMemPreDepositForGpaRange(v11);
    if ( (v13 & 0x20) != 0 )
      *(_DWORD *)(v10 + 20) |= 0x800u;
    if ( v52 || (v55 = 8, (v13 & 0x100) != 0) )
      v55 = 9;
    Entry = VsmmAdjustGpaSpaceForMemoryBlockRange((_DWORD)P, v54, v10, a5, v48 - v54 + 1, *(_DWORD *)(v11 + 292), v55);
    if ( Entry < 0 )
      goto LABEL_25;
    *(_DWORD *)(v11 + 292) |= 0x400u;
    if ( *(_DWORD *)(v10 + 244) == 1 )
      *(_DWORD *)(v10 + 248) = 1;
  }
  Entry = VsmmGpaRangeListInsert((__int64)P, v11);
  if ( Entry < 0 )
  {
    VidTraceErrorInternal0("VsmmCreateMemoryBlockGpaRange", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 1866);
    goto LABEL_25;
  }
  v61 = 1;
  if ( v64 )
    goto LABEL_171;
  if ( v52 )
  {
    Entry = VsmmVsmApplyDefaultVtlProtectionToGpaRange(
              (__int64)P,
              1,
              v11,
              *(_QWORD *)(v11 + 256),
              *(_QWORD *)(v11 + 264) - *(_QWORD *)(v11 + 256) + 1LL);
    if ( Entry < 0 )
    {
      VidTraceErrorStatusInternal0("VsmmCreateMemoryBlockGpaRange", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 1898);
      goto LABEL_25;
    }
LABEL_170:
    Entry = VsmmAdjustGpaSpaceForMemoryBlockRange((_DWORD)P, v63, v10, a5, v48 - v63 + 1, *(_DWORD *)(v11 + 292), 0);
    if ( Entry < 0 )
      goto LABEL_25;
    goto LABEL_171;
  }
  if ( (v13 & 0x100) != 0 )
  {
    Entry = VsmmVsmModifyGpaRangeVtlProtection(
              (__int64)P,
              0,
              2,
              0,
              v11,
              *(_QWORD *)(v11 + 256),
              *(_QWORD *)(v11 + 264) - *(_QWORD *)(v11 + 256) + 1LL,
              0);
    if ( Entry < 0 )
    {
      VidTraceErrorStatusInternal0("VsmmCreateMemoryBlockGpaRange", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 1917);
      goto LABEL_25;
    }
    goto LABEL_170;
  }
LABEL_171:
  Entry = VidHandleTableAllocateEntry(P + 816, v11, v11 + 248);
  if ( Entry < 0 )
  {
    VidTraceErrorInternal0("VsmmCreateMemoryBlockGpaRange", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 1953);
    goto LABEL_25;
  }
  v12 = v58;
  v20 = (__int64)a7;
  *v62 = *(_QWORD *)(v11 + 248);
  if ( *(_QWORD *)(v10 + 40) != *(_QWORD *)(v10 + 48) )
    *(_QWORD *)&P[2 * *(unsigned __int8 *)(v10 + 16) + 2246] = *(_QWORD *)(v11 + 264) + 1LL;
LABEL_27:
  VidObjectLockRelease(P + 934);
  if ( Entry < 0 )
  {
    if ( v11 )
    {
      if ( v61 )
      {
        LOBYTE(v21) = 1;
        VidOpCtrlBlock(v11 + 8, v21);
      }
      VsmmGpaRangeRelease(v22, v11, 0);
    }
    else if ( v10 )
    {
      VidOpCtrlFinish(v10 + 128);
    }
  }
  VidNumaRevertGroupAffinity(v69);
  if ( Entry < 0 && (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
  {
    tlgCreate1Sz_char(v72, "VsmmCreateMemoryBlockGpaRange");
    tlgCreate1Sz_char(v73, "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c");
    LODWORD(v59) = 2057;
    v74 = &v59;
    v75 = 4;
    v76 = &v60;
    LODWORD(v60) = Entry;
    v78 = (char *)(P + 164);
    v77 = 4;
    v80 = &v83;
    v82 = *((_QWORD *)P + 16);
    v83 = *((unsigned __int16 *)P + 60);
    v66 = *((_QWORD *)P + 81);
    v85 = &v66;
    v62 = (_QWORD *)v63;
    v87 = (__int64 *)&v62;
    v89 = &v64;
    v91 = &v65;
    v63 = a5;
    v93 = &v63;
    v95 = &v67;
    v97 = &v68;
    LODWORD(v58) = a8;
    v99 = &v58;
    v79 = 16;
    v81 = 2;
    v84 = v56;
    v86 = 8;
    v88 = 8;
    v64 = v12;
    v90 = 8;
    v92 = 8;
    v94 = 8;
    v67 = v13;
    v96 = 8;
    v68 = v20;
    v98 = 8;
    v100 = 4;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, byte_140057FD5, v56, 0, 17, v71);
  }
  return (unsigned int)Entry;
}

```

## disassembly

```asm
0x1400d9754  push    rbp
0x1400d9756  push    rbx
0x1400d9757  push    rsi
0x1400d9758  push    rdi
0x1400d9759  push    r12
0x1400d975b  push    r13
0x1400d975d  push    r14
0x1400d975f  push    r15
0x1400d9761  lea     rbp, [rsp-0E8h]
0x1400d9769  sub     rsp, 1E8h
0x1400d9770  mov     rax, cs:__security_cookie
0x1400d9777  xor     rax, rsp
0x1400d977a  mov     [rbp+120h+var_50], rax
0x1400d9781  mov     rax, [rbp+120h+arg_40]
0x1400d9788  mov     r14, rcx
0x1400d978b  xor     ecx, ecx
0x1400d978d  mov     [rsp+220h+var_1A8], r9
0x1400d9792  xorps   xmm0, xmm0
0x1400d9795  mov     [rbp+120h+var_168], rcx
0x1400d9799  xor     esi, esi
0x1400d979b  mov     [rsp+220h+var_1E0], r8
0x1400d97a0  xor     r13d, r13d
0x1400d97a3  mov     [rsp+220h+var_1B8], rdx
0x1400d97a8  lea     rcx, [r14+0E98h]
0x1400d97af  mov     [rsp+220h+var_1C0], rax
0x1400d97b4  mov     r15, r8
0x1400d97b7  mov     [rsp+220h+var_1D8], rsi
0x1400d97bc  mov     [rsp+220h+var_1D0], r13
0x1400d97c1  mov     [rsp+220h+var_1C8], sil
0x1400d97c6  movups  [rbp+120h+var_188], xmm0
0x1400d97ca  mov     qword ptr [rax], 0FFFFFFFFFFFFFFFFh
0x1400d97d1  movups  [rbp+120h+var_178], xmm0
0x1400d97d5  call    VidObjectLockAcquireExclusive
0x1400d97da  mov     rdi, [rbp+120h+arg_28]
0x1400d97e1  mov     rdx, [rbp+120h+arg_30]
0x1400d97e8  mov     r12, rdi
0x1400d97eb  and     r12d, 80h
0x1400d97f2  mov     [rsp+220h+var_1B0], r12
0x1400d97f7  setnz   cl
0x1400d97fa  test    rdx, rdx
0x1400d97fd  setnz   al
0x1400d9800  cmp     cl, al
0x1400d9802  jz      short loc_1400D982A
0x1400d9804  mov     ebx, 0C000000Dh
0x1400d9809  mov     r9d, ebx
0x1400d980c  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400d9813  mov     r8d, 483h
0x1400d9819  lea     rcx, aVsmmcreatememo; "VsmmCreateMemoryBlockGpaRange"
0x1400d9820  call    VidTraceErrorStatusInternal0
0x1400d9825  jmp     loc_1400D9A58
0x1400d982a  test    r12, r12
0x1400d982d  jz      short loc_1400D9897
0x1400d982f  cmp     [r14+21D1h], sil
0x1400d9836  jnz     short loc_1400D9897
0x1400d9838  mov     rcx, r14
0x1400d983b  call    VsmmPhuCheckObjectRestore
0x1400d9840  mov     ebx, eax
0x1400d9842  test    eax, eax
0x1400d9844  jns     short loc_1400D9867
0x1400d9846  mov     r9d, eax
0x1400d9849  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400d9850  mov     r8d, 492h
0x1400d9856  lea     rcx, aVsmmcreatememo; "VsmmCreateMemoryBlockGpaRange"
0x1400d985d  call    VidTraceErrorStatusInternal0
0x1400d9862  jmp     loc_1400D9A58
0x1400d9867  cmp     dword ptr [r14+21BCh], 2
0x1400d986f  jz      short loc_1400D9897
0x1400d9871  mov     ebx, 0C000000Dh
0x1400d9876  mov     r9d, ebx
0x1400d9879  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400d9880  mov     r8d, 49Ch
0x1400d9886  lea     rcx, aVsmmcreatememo; "VsmmCreateMemoryBlockGpaRange"
0x1400d988d  call    VidTraceErrorStatusInternal0
0x1400d9892  jmp     loc_1400D9A58
0x1400d9897  mov     rdx, [rsp+220h+var_1B8]
0x1400d989c  mov     r8, r15
0x1400d989f  mov     rcx, r14
0x1400d98a2  call    VsmmGpaRangeValidatePageRange
0x1400d98a7  xor     r9d, r9d
0x1400d98aa  mov     ebx, eax
0x1400d98ac  test    eax, eax
0x1400d98ae  jns     short loc_1400D98D1
0x1400d98b0  mov     r9d, eax
0x1400d98b3  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400d98ba  mov     r8d, 4A7h
0x1400d98c0  lea     rcx, aVsmmcreatememo; "VsmmCreateMemoryBlockGpaRange"
0x1400d98c7  call    VidTraceErrorStatusInternal0
0x1400d98cc  jmp     loc_1400D9A58
0x1400d98d1  test    rdi, 0FFFFFFFFFFFFFC00h
0x1400d98d8  jz      short loc_1400D9900
0x1400d98da  mov     ebx, 0C000000Dh
0x1400d98df  mov     r9d, ebx
0x1400d98e2  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400d98e9  mov     r8d, 4AEh
0x1400d98ef  lea     rcx, aVsmmcreatememo; "VsmmCreateMemoryBlockGpaRange"
0x1400d98f6  call    VidTraceErrorStatusInternal0
0x1400d98fb  jmp     loc_1400D9A58
0x1400d9900  mov     r10d, 4
0x1400d9906  test    r10b, dil
0x1400d9909  jz      short loc_1400D9931
0x1400d990b  mov     ebx, 0C000000Dh
0x1400d9910  mov     r9d, ebx
0x1400d9913  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400d991a  mov     r8d, 4B8h
0x1400d9920  lea     rcx, aVsmmcreatememo; "VsmmCreateMemoryBlockGpaRange"
0x1400d9927  call    VidTraceErrorStatusInternal0
0x1400d992c  jmp     loc_1400D9A58
0x1400d9931  mov     ebx, [rbp+120h+arg_38]
0x1400d9937  test    rdi, 261h
0x1400d993e  jnz     short loc_1400D9948
0x1400d9940  mov     r15d, r9d
0x1400d9943  cmp     ebx, 1
0x1400d9946  jnz     short loc_1400D994E
0x1400d9948  mov     r15d, 1
0x1400d994e  mov     ecx, 100h
0x1400d9953  test    rcx, rdi
0x1400d9956  jz      loc_1400D9B92
0x1400d995c  cmp     ebx, 1
0x1400d995f  jz      loc_1400D9A9E
0x1400d9965  mov     eax, cs:dword_140064110
0x1400d996b  mov     ebx, 0C000000Dh
0x1400d9970  cmp     eax, 2
0x1400d9973  jbe     loc_1400D9A53
0x1400d9979  mov     edx, ecx
0x1400d997b  lea     rcx, dword_140064110
0x1400d9982  call    _tlgKeywordOn
0x1400d9987  test    al, al
0x1400d9989  jz      loc_1400D9A53
0x1400d998f  lea     rdx, aVsmmcreatememo; "VsmmCreateMemoryBlockGpaRange"
0x1400d9996  lea     rcx, [rbp+120h+var_140]
0x1400d999a  call    _tlgCreate1Sz_char
0x1400d999f  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400d99a6  lea     rcx, [rbp+120h+var_130]
0x1400d99aa  call    _tlgCreate1Sz_char
0x1400d99af  lea     rax, [rsp+220h+var_1D0]
0x1400d99b4  mov     dword ptr [rsp+220h+var_1D0], 4D5h
0x1400d99bc  mov     [rbp+120h+var_120], rax
0x1400d99c0  lea     rdx, dword_1400584C4
0x1400d99c7  lea     rax, [rsp+220h+var_1D8]
0x1400d99cc  mov     dword ptr [rsp+220h+var_1D8], ebx
0x1400d99d0  mov     [rbp+120h+var_110], rax
0x1400d99d4  lea     rax, [r14+290h]
0x1400d99db  mov     [rbp+120h+var_100], rax
0x1400d99df  lea     rax, [rbp+120h+var_D8]
0x1400d99e3  mov     [rbp+120h+var_F0], rax
0x1400d99e7  mov     rax, [r14+80h]
0x1400d99ee  mov     [rbp+120h+var_E0], rax
0x1400d99f2  movzx   eax, word ptr [r14+78h]
0x1400d99f7  mov     [rbp+120h+var_D8], eax
0x1400d99fa  mov     rax, [r14+288h]
0x1400d9a01  mov     [rsp+220h+var_1C0], rax
0x1400d9a06  mov     [rbp+120h+var_118], r10
0x1400d9a0a  mov     [rbp+120h+var_108], r10
0x1400d9a0e  mov     [rbp+120h+var_F8], 10h
0x1400d9a16  mov     [rbp+120h+var_E8], 2
0x1400d9a1e  mov     [rbp+120h+var_D4], r9d
0x1400d9a22  mov     [rbp+120h+var_C8], 8
0x1400d9a2a  lea     rax, [rsp+220h+var_1C0]
0x1400d9a2f  mov     [rbp+120h+var_D0], rax
0x1400d9a33  lea     rax, [rbp+120h+var_160]
0x1400d9a37  mov     [rsp+220h+var_1F8], rax
0x1400d9a3c  mov     dword ptr [rsp+220h+var_200], 0Ah
0x1400d9a44  xor     r8d, r8d
0x1400d9a47  lea     rcx, dword_140064110
0x1400d9a4e  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400d9a53  mov     r15, [rsp+220h+var_1E0]
0x1400d9a58  mov     r12, [rbp+120h+arg_30]
0x1400d9a5f  lea     rcx, [r14+0E98h]
0x1400d9a66  call    VidObjectLockRelease
0x1400d9a6b  test    ebx, ebx
0x1400d9a6d  jns     loc_1400DA899
0x1400d9a73  test    r13, r13
0x1400d9a76  jz      loc_1400DA888
0x1400d9a7c  cmp     [rsp+220h+var_1C8], 0
0x1400d9a81  jz      short loc_1400D9A8E
0x1400d9a83  lea     rcx, [r13+8]
0x1400d9a87  mov     dl, 1
0x1400d9a89  call    VidOpCtrlBlock
0x1400d9a8e  xor     r8d, r8d
0x1400d9a91  mov     rdx, r13
0x1400d9a94  call    VsmmGpaRangeRelease
0x1400d9a99  jmp     loc_1400DA899
0x1400d9a9e  mov     eax, [r14+2248h]
0x1400d9aa5  test    r10b, al
0x1400d9aa8  jnz     short loc_1400D9B13
0x1400d9aaa  mov     eax, cs:dword_140064110
0x1400d9ab0  mov     ebx, 0C000000Dh
0x1400d9ab5  cmp     eax, 2
0x1400d9ab8  jbe     short loc_1400D9A53
0x1400d9aba  mov     rdx, rcx
0x1400d9abd  lea     rcx, dword_140064110
0x1400d9ac4  call    _tlgKeywordOn
0x1400d9ac9  test    al, al
0x1400d9acb  jz      short loc_1400D9A53
0x1400d9acd  lea     rdx, aVsmmcreatememo; "VsmmCreateMemoryBlockGpaRange"
0x1400d9ad4  lea     rcx, [rbp+120h+var_140]
0x1400d9ad8  call    _tlgCreate1Sz_char
0x1400d9add  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400d9ae4  lea     rcx, [rbp+120h+var_130]
0x1400d9ae8  call    _tlgCreate1Sz_char
0x1400d9aed  lea     rax, [rsp+220h+var_1D8]
0x1400d9af2  mov     dword ptr [rsp+220h+var_1D8], 4DCh
0x1400d9afa  mov     [rbp+120h+var_120], rax
0x1400d9afe  lea     rdx, word_140058266
0x1400d9b05  lea     rax, [rsp+220h+var_1D0]
0x1400d9b0a  mov     dword ptr [rsp+220h+var_1D0], ebx
0x1400d9b0e  jmp     loc_1400D99D0
0x1400d9b13  test    r12, r12
0x1400d9b16  jz      loc_1400D9C77
0x1400d9b1c  mov     eax, cs:dword_140064110
0x1400d9b22  mov     r8d, 0C00000BBh
0x1400d9b28  mov     ebx, r8d
0x1400d9b2b  cmp     eax, 2
0x1400d9b2e  jbe     loc_1400D9A53
0x1400d9b34  mov     rdx, rcx
0x1400d9b37  lea     rcx, dword_140064110
0x1400d9b3e  call    _tlgKeywordOn
0x1400d9b43  test    al, al
0x1400d9b45  jz      loc_1400D9A53
0x1400d9b4b  lea     rdx, aVsmmcreatememo; "VsmmCreateMemoryBlockGpaRange"
0x1400d9b52  lea     rcx, [rbp+120h+var_140]
0x1400d9b56  call    _tlgCreate1Sz_char
0x1400d9b5b  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400d9b62  lea     rcx, [rbp+120h+var_130]
0x1400d9b66  call    _tlgCreate1Sz_char
0x1400d9b6b  lea     rax, [rsp+220h+var_1D8]
0x1400d9b70  mov     dword ptr [rsp+220h+var_1D8], 4EAh
0x1400d9b78  mov     [rbp+120h+var_120], rax
0x1400d9b7c  lea     rdx, dword_1400582D4
0x1400d9b83  lea     rax, [rsp+220h+var_1D0]
0x1400d9b88  mov     dword ptr [rsp+220h+var_1D0], r8d
0x1400d9b8d  jmp     loc_1400D99D0
0x1400d9b92  test    r12, r12
0x1400d9b95  jz      loc_1400D9C77
0x1400d9b9b  cmp     [r14+21D1h], r9b
0x1400d9ba2  jz      loc_1400D9C73
0x1400d9ba8  mov     r12, [rbp+120h+arg_30]
0x1400d9baf  mov     r8d, ebx
0x1400d9bb2  mov     r9, [rsp+220h+var_1C0]
0x1400d9bb7  mov     rdx, r12
0x1400d9bba  mov     rcx, r14
0x1400d9bbd  call    VsmmGpaRangeLookupByPersistId
0x1400d9bc2  mov     ebx, eax
0x1400d9bc4  test    eax, eax
0x1400d9bc6  jns     loc_1400D9C69
0x1400d9bcc  mov     eax, cs:dword_140064110
0x1400d9bd2  cmp     eax, 2
0x1400d9bd5  jbe     loc_1400D9C69
0x1400d9bdb  mov     edx, 100h
0x1400d9be0  lea     rcx, dword_140064110
0x1400d9be7  call    _tlgKeywordOn
0x1400d9bec  test    al, al
0x1400d9bee  jz      short loc_1400D9C69
0x1400d9bf0  lea     rdx, aVsmmcreatememo; "VsmmCreateMemoryBlockGpaRange"
0x1400d9bf7  lea     rcx, [rbp+120h+var_140]
0x1400d9bfb  call    _tlgCreate1Sz_char
0x1400d9c00  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400d9c07  lea     rcx, [rbp+120h+var_130]
0x1400d9c0b  call    _tlgCreate1Sz_char
0x1400d9c10  lea     rax, [rsp+220h+var_1D8]
0x1400d9c15  mov     dword ptr [rsp+220h+var_1D8], 501h
0x1400d9c1d  mov     [rbp+120h+var_120], rax
0x1400d9c21  lea     rdx, word_140058342
0x1400d9c28  lea     rax, [rsp+220h+var_1C0]
0x1400d9c2d  mov     [rbp+120h+var_118], 4
0x1400d9c35  mov     [rbp+120h+var_110], rax
0x1400d9c39  lea     rcx, dword_140064110
0x1400d9c40  lea     rax, [rbp+120h+var_160]
0x1400d9c44  mov     [rsp+220h+var_1C0], r12
0x1400d9c49  mov     [rsp+220h+var_1F8], rax
0x1400d9c4e  xor     r9d, r9d
0x1400d9c51  xor     r8d, r8d
0x1400d9c54  mov     dword ptr [rsp+220h+var_200], 6
0x1400d9c5c  mov     [rbp+120h+var_108], 8
0x1400d9c64  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400d9c69  mov     r15, [rsp+220h+var_1E0]
0x1400d9c6e  jmp     loc_1400D9A5F
0x1400d9c73  or      r15d, 2
0x1400d9c77  mov     r8, [rsp+220h+var_1E0]
0x1400d9c7c  mov     rcx, r14
0x1400d9c7f  mov     rdx, [rsp+220h+var_1B8]
0x1400d9c84  mov     [rsp+220h+var_200], r9
0x1400d9c89  mov     r9d, r15d
0x1400d9c8c  call    VsmmGpaRangeListOverlapCheck
0x1400d9c91  test    eax, eax
0x1400d9c93  jz      loc_1400D9D35
0x1400d9c99  mov     eax, cs:dword_140064110
0x1400d9c9f  mov     ebx, 0C0370048h
0x1400d9ca4  cmp     eax, 2
0x1400d9ca7  jbe     loc_1400D9A53
0x1400d9cad  mov     edx, 100h
0x1400d9cb2  lea     rcx, dword_140064110
0x1400d9cb9  call    _tlgKeywordOn
0x1400d9cbe  test    al, al
0x1400d9cc0  jz      loc_1400D9A53
0x1400d9cc6  lea     rdx, aVsmmcreatememo; "VsmmCreateMemoryBlockGpaRange"
0x1400d9ccd  lea     rcx, [rbp+120h+var_140]
0x1400d9cd1  call    _tlgCreate1Sz_char
0x1400d9cd6  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400d9cdd  lea     rcx, [rbp+120h+var_130]
  ... truncated ...
```
