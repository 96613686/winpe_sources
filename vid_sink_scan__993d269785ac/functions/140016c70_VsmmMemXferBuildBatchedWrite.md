# VsmmMemXferBuildBatchedWrite

- ea: `0x140016c70`
- end: `0x140017ac6`
- name: `VsmmMemXferBuildBatchedWrite`
- size: `3670`
- prototype: `__int64 __fastcall(__int64, unsigned __int64, __int64, unsigned __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x1400f819c`

## callees

- `0x1400029c0`
- `0x140003298`
- `0x140005b14`
- `0x140006bf8`
- `0x14000a4e0`
- `0x140016c70`
- `0x140021650`
- `0x140027098`
- `0x1400280d0`
- `0x140030760`
- `0x1400f9cbc`
- `0x1400faa8c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400177c8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400177c8`
- `ntoskrnl!ExAllocatePool2` at `0x140016eb9`
- `ntoskrnl!ExAllocatePool2` at `0x140016eb9`
- `ntoskrnl!IoFreeMdl` at `0x14001777d`
- `ntoskrnl!IoFreeMdl` at `0x14001777d`
- `ntoskrnl!IoAllocateMdl` at `0x140016d97`
- `ntoskrnl!IoAllocateMdl` at `0x140016d97`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140016db5`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140016db5`

## string_xrefs

- `0x140016ff4`: `VsmmMemXferBuildBatchedWrite`
- `0x1400170ef`: `VsmmMemXferBuildBatchedWrite`
- `0x140017150`: `VsmmMemXferBuildBatchedWrite`
- `0x14001725d`: `VsmmMemXferBuildBatchedWrite`
- `0x14001734d`: `VsmmMemXferBuildBatchedWrite`
- `0x14001743c`: `VsmmMemXferBuildBatchedWrite`
- `0x1400175c6`: `VsmmMemXferBuildBatchedWrite`
- `0x14001780a`: `VsmmMemXferBuildBatchedWrite`
- `0x1400178f8`: `VsmmMemXferBuildBatchedWrite`

## pseudocode

```c
__int64 __fastcall VsmmMemXferBuildBatchedWrite(
        __int64 a1,
        unsigned __int64 a2,
        __int64 a3,
        unsigned __int64 a4,
        _QWORD *a5)
{
  unsigned int v6; // ecx
  __int64 v7; // r9
  unsigned __int64 v8; // rsi
  unsigned __int64 v9; // rdi
  unsigned __int64 v10; // rdx
  unsigned __int64 v11; // r13
  int v12; // esi
  __int64 v13; // rcx
  struct _MDL *Mdl; // rax
  unsigned __int64 Pool2; // rdi
  __int64 v16; // rdx
  unsigned __int64 v17; // r8
  unsigned __int64 v18; // rax
  int v19; // eax
  int v20; // edx
  char v21; // r8
  int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // rax
  int v26; // edx
  int v27; // ecx
  int v28; // eax
  char v29; // r8
  __int64 v30; // r10
  __int64 v31; // r9
  __int64 v32; // rax
  __int64 v33; // r13
  __int64 v34; // r9
  __int64 v35; // r10
  __int64 v36; // r11
  unsigned __int64 v37; // r13
  char *v38; // rdx
  int v39; // r10d
  __int64 v40; // r8
  char *v41; // rdx
  char v42; // al
  unsigned __int64 v43; // r13
  char v44; // cl
  unsigned int v45; // r8d
  __int64 v46; // r9
  int v47; // r10d
  __int64 v48; // r8
  __int64 v49; // r8
  unsigned __int64 v50; // rcx
  unsigned int v51; // r8d
  int v52; // r10d
  __int64 v53; // r8
  int v54; // r10d
  int Irp; // [rsp+20h] [rbp-E0h]
  unsigned int v57; // [rsp+50h] [rbp-B0h] BYREF
  int v58; // [rsp+54h] [rbp-ACh] BYREF
  char v59; // [rsp+58h] [rbp-A8h]
  __int64 v60; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v61; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int64 v62; // [rsp+70h] [rbp-90h] BYREF
  __int64 v63; // [rsp+78h] [rbp-88h] BYREF
  __int64 v64; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 v65; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int64 v66; // [rsp+90h] [rbp-70h] BYREF
  __int64 v67; // [rsp+98h] [rbp-68h] BYREF
  __int128 v68; // [rsp+A0h] [rbp-60h]
  __int64 v69; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v70; // [rsp+B8h] [rbp-48h]
  __int128 v71; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v72[32]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v73[16]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v74[16]; // [rsp+110h] [rbp+10h] BYREF
  int *v75; // [rsp+120h] [rbp+20h]
  __int64 v76; // [rsp+128h] [rbp+28h]
  unsigned int *v77; // [rsp+130h] [rbp+30h]
  __int64 v78; // [rsp+138h] [rbp+38h]
  __int64 v79; // [rsp+140h] [rbp+40h]
  __int64 v80; // [rsp+148h] [rbp+48h]
  int *v81; // [rsp+150h] [rbp+50h]
  __int64 v82; // [rsp+158h] [rbp+58h]
  __int64 v83; // [rsp+160h] [rbp+60h]
  int v84; // [rsp+168h] [rbp+68h] BYREF
  int v85; // [rsp+16Ch] [rbp+6Ch]
  __int64 *v86; // [rsp+170h] [rbp+70h]
  __int64 v87; // [rsp+178h] [rbp+78h]
  __int64 *v88; // [rsp+180h] [rbp+80h]
  __int64 v89; // [rsp+188h] [rbp+88h]
  unsigned __int64 *v90; // [rsp+190h] [rbp+90h]
  __int64 v91; // [rsp+198h] [rbp+98h]
  unsigned __int64 *v92; // [rsp+1A0h] [rbp+A0h]
  __int64 v93; // [rsp+1A8h] [rbp+A8h]
  __int64 *v94; // [rsp+1B0h] [rbp+B0h]
  __int64 v95; // [rsp+1B8h] [rbp+B8h]
  __int64 *v96; // [rsp+1C0h] [rbp+C0h]
  __int64 v97; // [rsp+1C8h] [rbp+C8h]
  __int64 *v98; // [rsp+1D0h] [rbp+D0h]
  __int64 v99; // [rsp+1D8h] [rbp+D8h]

  v69 = a1;
  v66 = a4;
  v60 = a3;
  v62 = a2;
  v6 = 0;
  v58 = 0;
  v7 = a3;
  v71 = 0;
  v68 = 0;
  v70 = 0;
  if ( !v66 )
  {
LABEL_67:
    v12 = 0;
    goto LABEL_68;
  }
  while ( 1 )
  {
    v64 = *(_QWORD *)(a2 + 8LL * v6);
    v68 = *(_OWORD *)(v7 + 16LL * v6);
    if ( *(_DWORD *)(v64 + 288) )
    {
      v12 = -1073741811;
      if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
        goto LABEL_68;
      tlgCreate1Sz_char(v73, "VsmmMemXferBuildBatchedWrite");
      tlgCreate1Sz_char(v74, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfer.c");
      v58 = 1804;
      v75 = &v58;
      v76 = 4;
      v79 = a1 + 656;
      v38 = byte_14004CF8B;
      v57 = -1073741811;
      v81 = &v84;
      v83 = *(_QWORD *)(a1 + 128);
      v84 = *(unsigned __int16 *)(a1 + 120);
      v67 = *(_QWORD *)(a1 + 648);
      v86 = &v67;
      v60 = v68;
      v88 = &v60;
      v62 = *((_QWORD *)&v68 + 1);
      v90 = &v62;
      v66 = *(_QWORD *)(v53 + 248);
      v92 = &v66;
      v65 = *(_QWORD *)(v53 + 256);
      v94 = (__int64 *)&v65;
      v63 = *(_QWORD *)(v53 + 264);
      v96 = &v63;
      v64 = *(int *)(v53 + 292);
      v98 = &v64;
      Irp = 16;
      v77 = &v57;
      v78 = 4;
      v80 = 16;
      v82 = 2;
      v85 = v54;
      v87 = 8;
      v91 = 8;
      v93 = 8;
      v95 = 8;
      v97 = 8;
      v99 = 8;
      goto LABEL_65;
    }
    v8 = *((_QWORD *)&v68 + 1);
    v9 = a5[8];
    v10 = a5[6];
    v11 = *((_QWORD *)&v68 + 1) << 12;
    v65 = v9;
    v61 = *((_QWORD *)&v68 + 1);
    v57 = DWORD2(v68) << 12;
    if ( v9 < v10 )
      goto LABEL_6;
    v12 = VsmmMemXferpBatchedWriteAlloc(a5, 2 * v10);
    if ( v12 < 0 )
    {
      if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
        goto LABEL_68;
      tlgCreate1Sz_char(v73, "VsmmMemXferBuildBatchedWrite");
      tlgCreate1Sz_char(v74, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfer.c");
      v58 = 1838;
      v75 = &v58;
      v76 = 4;
      v79 = a1 + 656;
      v38 = &byte_14004D0A7;
      v57 = v12;
      v81 = &v84;
      v83 = *(_QWORD *)(a1 + 128);
      v84 = *(unsigned __int16 *)(a1 + 120);
      v60 = *(_QWORD *)(a1 + 648);
      v86 = &v60;
      v88 = (__int64 *)&v62;
      Irp = 11;
      v77 = &v57;
      v78 = 4;
      v80 = 16;
      v82 = 2;
      v85 = v39;
      v87 = 8;
      v62 = v9;
LABEL_65:
      v89 = 8;
      goto LABEL_66;
    }
    v8 = v61;
LABEL_6:
    if ( (*(_BYTE *)(a1 + 40) & 2) != 0 )
      break;
    v24 = a5[11];
    v25 = (unsigned int)(8 * v8 + 48);
    if ( (unsigned __int64)(v25 + v24) > a5[10] )
    {
      Pool2 = ExAllocatePool2(64, (unsigned int)(8 * v8 + 48), 1833788502);
      if ( !Pool2 )
      {
        v12 = -1073741670;
        if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
          goto LABEL_68;
        tlgCreate1Sz_char(v73, "VsmmMemXferBuildBatchedWrite");
        tlgCreate1Sz_char(v74, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfer.c");
        v58 = 1962;
        v75 = &v58;
        v76 = 4;
        v79 = a1 + 656;
        v38 = &byte_14004CEAF;
        v57 = v51;
        v81 = &v84;
        v83 = *(_QWORD *)(a1 + 128);
        v84 = *(unsigned __int16 *)(a1 + 120);
        v67 = *(_QWORD *)(a1 + 648);
        v86 = &v67;
        Irp = 10;
        v77 = &v57;
        v78 = 4;
        v80 = 16;
        v82 = 2;
        v85 = v52;
        v87 = 8;
LABEL_66:
        tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, v38, 0, 0, Irp, v72);
        goto LABEL_68;
      }
    }
    else
    {
      Pool2 = v24 + a5[9];
      a5[11] = v25 + v24;
    }
    *(_QWORD *)(Pool2 + 12) = 0;
    *(_QWORD *)(Pool2 + 20) = 0;
    *(_DWORD *)(Pool2 + 28) = 0;
    v26 = v68;
    v27 = v64;
    *(_QWORD *)Pool2 = 0;
    *(_WORD *)(Pool2 + 8) = 8 * ((v11 >> 12) + 6);
    *(_QWORD *)(Pool2 + 32) = 0;
    *(_DWORD *)(Pool2 + 44) = 0;
    *(_DWORD *)(Pool2 + 40) = v11;
    *(_WORD *)(Pool2 + 10) = 2;
    v28 = VsmmLockGpaRange(v27, v26, v8, 0, Pool2);
    v29 = 0;
    v12 = v28;
    if ( v28 < 0 )
    {
      if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
      {
        tlgCreate1Sz_char(v73, "VsmmMemXferBuildBatchedWrite");
        tlgCreate1Sz_char(v74, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfer.c");
        v43 = v61;
        v75 = &v58;
        v77 = &v57;
        v79 = a1 + 656;
        v58 = 1986;
        v81 = &v84;
        v83 = *(_QWORD *)(a1 + 128);
        v84 = *(unsigned __int16 *)(a1 + 120);
        v60 = *(_QWORD *)(a1 + 648);
        v86 = &v60;
        v62 = v68;
        v88 = (__int64 *)&v62;
        v90 = &v66;
        v65 = *(_QWORD *)(v64 + 248);
        v92 = &v65;
        v63 = *(_QWORD *)(v64 + 256);
        v94 = &v63;
        v61 = *(_QWORD *)(v64 + 264);
        v96 = (__int64 *)&v61;
        v67 = *(int *)(v64 + 292);
        v98 = &v67;
        v76 = 4;
        v57 = v12;
        v78 = 4;
        v80 = 16;
        v82 = 2;
        v85 = v49;
        v87 = 8;
        v89 = 8;
        v66 = v43;
        v91 = 8;
        v93 = 8;
        v95 = 8;
        v97 = 8;
        v99 = 8;
        tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, byte_14004CD25, v49, 0, 16, v72);
        v29 = 0;
      }
      else
      {
        LODWORD(v43) = v61;
      }
      v44 = v29;
      goto LABEL_51;
    }
    v59 = 1;
LABEL_19:
    v30 = a5[7];
    v31 = 5 * v65;
    *(_DWORD *)(v30 + 8 * v31 + 24) = 1;
    *(_DWORD *)(v30 + 8 * v31 + 28) = *(_DWORD *)(Pool2 + 40);
    v32 = v68;
    *(_QWORD *)(v30 + 8 * v31 + 32) = Pool2;
    *(_DWORD *)(v30 + 8 * v31 + 52) = v11;
    v33 = v64;
    *(_QWORD *)(v30 + 8 * v31 + 40) = v32 << 12;
    if ( !(unsigned __int8)VidOpCtrlStart(v33 + 8, v23, 0) )
    {
      v12 = -1070137310;
      if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
      {
        tlgCreate1Sz_char(v73, "VsmmMemXferBuildBatchedWrite");
        tlgCreate1Sz_char(v74, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfer.c");
        v58 = 2013;
        v75 = &v58;
        v77 = &v57;
        v79 = a1 + 656;
        v76 = 4;
        v81 = &v84;
        v83 = *(_QWORD *)(a1 + 128);
        v84 = *(unsigned __int16 *)(a1 + 120);
        v60 = *(_QWORD *)(a1 + 648);
        v86 = &v60;
        v62 = *(_QWORD *)(v33 + 248);
        v88 = (__int64 *)&v62;
        v66 = *(_QWORD *)(v33 + 256);
        v90 = &v66;
        v65 = *(_QWORD *)(v33 + 264);
        v92 = &v65;
        v63 = *(int *)(v33 + 292);
        v94 = &v63;
        v57 = -1070137310;
        v78 = 4;
        v80 = 16;
        v82 = 2;
        v85 = v48;
        v87 = 8;
        v89 = 8;
        v91 = 8;
        v93 = 8;
        v95 = 8;
        tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, &byte_14004CC87, v48, 0, 14, v72);
      }
      v44 = v59;
      LODWORD(v43) = v61;
LABEL_51:
      if ( !Pool2 )
        goto LABEL_68;
      goto LABEL_52;
    }
    *(_QWORD *)(a5[12] + 8 * v36) = v33;
    if ( v36 )
      *(_DWORD *)(v35 + 8 * v34 - 24) = 40;
    v37 = v61;
    v6 = v58 + 1;
    ++a5[8];
    a5[3] += v37;
    v58 = v6;
    if ( v6 >= v66 )
      goto LABEL_67;
    a2 = v62;
    v7 = v60;
  }
  v13 = a5[15];
  if ( v13 + (unsigned __int64)(unsigned int)v11 > a5[14] )
  {
    v12 = -1073741789;
    if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
      goto LABEL_68;
    tlgCreate1Sz_char(v73, "VsmmMemXferBuildBatchedWrite");
    tlgCreate1Sz_char(v74, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfer.c");
    v58 = 1853;
    v75 = &v58;
    v76 = 4;
    v79 = a1 + 656;
    v38 = byte_14004D039;
    v57 = -1073741789;
    v81 = &v84;
    v83 = *(_QWORD *)(a1 + 128);
    v84 = *(unsigned __int16 *)(a1 + 120);
    v60 = *(_QWORD *)(a1 + 648);
    v86 = &v60;
    Irp = 10;
    v77 = &v57;
    v78 = 4;
    v80 = 16;
    v82 = 2;
    v85 = v47;
    v87 = 8;
    goto LABEL_66;
  }
  v63 = v13 + a5[13];
  Mdl = IoAllocateMdl((PVOID)v63, v11, 0, 0, 0);
  Pool2 = (unsigned __int64)Mdl;
  if ( !Mdl )
  {
    v12 = -1073741670;
    if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
    {
      tlgCreate1Sz_char(v73, "VsmmMemXferBuildBatchedWrite");
      tlgCreate1Sz_char(v74, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfer.c");
      v58 = 1871;
      v75 = &v58;
      v76 = 4;
      v79 = a1 + 656;
      v57 = v45;
      v81 = &v84;
      v83 = *(_QWORD *)(a1 + 128);
      v84 = *(unsigned __int16 *)(a1 + 120);
      v60 = *(_QWORD *)(a1 + 648);
      v86 = &v60;
      v77 = &v57;
      v78 = 4;
      v80 = 16;
      v82 = 2;
      v85 = v46;
      v87 = 8;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, byte_14004CE41, 0, v46, 10, v72);
    }
    goto LABEL_68;
  }
  MmBuildMdlForNonPagedPool(Mdl);
  v16 = *(_QWORD *)(v64 + 384);
  v17 = v68 + *(_QWORD *)(v64 + 392) - *(_QWORD *)(v64 + 256);
  v18 = *(_QWORD *)(v16 + 48);
  if ( v17 < v18 && v8 <= v18 - v17 )
  {
    v19 = VsmmMemoryBlockCopyByteRange((unsigned int)&v69, v16, (_DWORD)v17 << 12, v11, v63, 0, 0, 0, 0, 0);
    v21 = 0;
    v12 = v19;
    if ( v19 < 0 )
    {
      if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
      {
        tlgCreate1Sz_char(v73, "VsmmMemXferBuildBatchedWrite");
        tlgCreate1Sz_char(v74, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfer.c");
        v58 = 1913;
        v41 = byte_14004CF1D;
        goto LABEL_33;
      }
      goto LABEL_35;
    }
    *(_QWORD *)&v71 = v68;
    v22 = VsmmCryptPack(a1, v20, (unsigned int)&v71, v63, (__int64)&v57, v63, v11);
    v21 = 0;
    v12 = v22;
    if ( v22 < 0 )
      goto LABEL_35;
    LODWORD(v11) = v57;
    a5[15] += v57;
    v59 = 0;
    goto LABEL_19;
  }
  v12 = -1073741808;
  if ( (unsigned int)dword_140064110 <= 2 )
    goto LABEL_34;
  v42 = tlgKeywordOn(&dword_140064110, 256);
  v21 = 0;
  if ( v42 )
  {
    tlgCreate1Sz_char(v73, "VsmmMemXferBuildBatchedWrite");
    tlgCreate1Sz_char(v74, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfer.c");
    v58 = 1892;
    v41 = byte_14004CDD3;
LABEL_33:
    v87 = 8;
    v75 = &v58;
    v77 = &v57;
    v79 = a1 + 656;
    v85 = v40;
    v81 = &v84;
    v83 = *(_QWORD *)(a1 + 128);
    v84 = *(unsigned __int16 *)(a1 + 120);
    v60 = *(_QWORD *)(a1 + 648);
    v86 = &v60;
    v82 = 2;
    v80 = 16;
    v78 = 4;
    v57 = v12;
    v76 = 4;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, v41, v40, 0, 10, v72);
LABEL_34:
    v21 = 0;
  }
LABEL_35:
  LODWORD(v43) = v61;
  v44 = v21;
LABEL_52:
  if ( (*(_BYTE *)(a1 + 40) & 2) != 0 )
  {
    IoFreeMdl((PMDL)Pool2);
  }
  else
  {
    if ( v44 )
      VsmmUnlockGpaRange(v64, v68, v43, 0, Pool2);
    v50 = a5[9];
    if ( Pool2 < v50 || Pool2 >= a5[10] + v50 )
      ExFreePoolWithTag((PVOID)Pool2, 0x6D4D6456u);
  }
LABEL_68:
  VsmmMemoryBlockMbpRangeVaDestroy(&v69);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140016c70  mov     [rsp-8+arg_18], rbx
0x140016c75  push    rbp
0x140016c76  push    rsi
0x140016c77  push    rdi
0x140016c78  push    r12
0x140016c7a  push    r13
0x140016c7c  push    r14
0x140016c7e  push    r15
0x140016c80  lea     rbp, [rsp-0F0h]
0x140016c88  sub     rsp, 1F0h
0x140016c8f  mov     rax, cs:__security_cookie
0x140016c96  xor     rax, rsp
0x140016c99  mov     [rbp+120h+var_40], rax
0x140016ca0  mov     r14, [rbp+120h+arg_20]
0x140016ca7  xor     r10d, r10d
0x140016caa  mov     rax, r9
0x140016cad  mov     [rbp+120h+var_170], rcx
0x140016cb1  mov     [rbp+120h+var_190], rax
0x140016cb5  xorps   xmm0, xmm0
0x140016cb8  mov     [rsp+220h+var_1C0], r8
0x140016cbd  mov     r15, rcx
0x140016cc0  mov     [rsp+220h+var_1B0], rdx
0x140016cc5  mov     ecx, r10d
0x140016cc8  mov     [rsp+220h+var_1CC], ecx
0x140016ccc  xorps   xmm1, xmm1
0x140016ccf  mov     r9, r8
0x140016cd2  mov     ebx, r10d
0x140016cd5  movups  [rbp+120h+var_158], xmm0
0x140016cd9  movups  [rbp+120h+var_180], xmm1
0x140016cdd  movdqu  [rbp+120h+var_168], xmm0
0x140016ce2  test    rax, rax
0x140016ce5  jz      loc_140017A8D
0x140016ceb  mov     eax, ecx
0x140016ced  mov     r11d, 2
0x140016cf3  mov     r8, [rdx+rax*8]
0x140016cf7  add     rax, rax
0x140016cfa  mov     [rbp+120h+var_1A0], r8
0x140016cfe  movups  xmm0, xmmword ptr [r9+rax*8]
0x140016d03  movdqu  [rbp+120h+var_180], xmm0
0x140016d08  cmp     [r8+120h], r10d
0x140016d0f  jnz     loc_1400178CB
0x140016d15  mov     rsi, qword ptr [rbp+120h+var_180+8]
0x140016d19  mov     rdi, [r14+40h]
0x140016d1d  mov     r13, rsi
0x140016d20  mov     rdx, [r14+30h]
0x140016d24  shl     r13, 0Ch
0x140016d28  mov     [rbp+120h+var_198], rdi
0x140016d2c  mov     [rsp+220h+var_1B8], rsi
0x140016d31  mov     [rsp+220h+var_1D0], r13d
0x140016d36  cmp     rdi, rdx
0x140016d39  jb      short loc_140016D5C
0x140016d3b  add     rdx, rdx
0x140016d3e  mov     rcx, r14
0x140016d41  call    VsmmMemXferpBatchedWriteAlloc
0x140016d46  xor     r10d, r10d
0x140016d49  mov     esi, eax
0x140016d4b  test    eax, eax
0x140016d4d  js      loc_140016FCC
0x140016d53  mov     rsi, [rsp+220h+var_1B8]
0x140016d58  lea     r11d, [r10+2]
0x140016d5c  test    [r15+28h], r11b
0x140016d60  jz      loc_140016E86
0x140016d66  mov     rcx, [r14+78h]
0x140016d6a  mov     eax, r13d
0x140016d6d  add     rax, rcx
0x140016d70  cmp     rax, [r14+70h]
0x140016d74  ja      loc_140017320
0x140016d7a  mov     rax, [r14+68h]
0x140016d7e  xor     r9d, r9d; ChargeQuota
0x140016d81  add     rax, rcx
0x140016d84  mov     [rsp+220h+Irp], r10; Irp
0x140016d89  mov     rcx, rax; VirtualAddress
0x140016d8c  mov     [rsp+220h+var_1A8], rax
0x140016d91  xor     r8d, r8d; SecondaryBuffer
0x140016d94  mov     edx, r13d; Length
0x140016d97  call    cs:__imp_IoAllocateMdl
0x140016d9e  nop     dword ptr [rax+rax+00h]
0x140016da3  xor     r9d, r9d
0x140016da6  mov     rdi, rax
0x140016da9  test    rax, rax
0x140016dac  jz      loc_14001722C
0x140016db2  mov     rcx, rax; MemoryDescriptorList
0x140016db5  call    cs:__imp_MmBuildMdlForNonPagedPool
0x140016dbc  nop     dword ptr [rax+rax+00h]
0x140016dc1  mov     rax, [rbp+120h+var_1A0]
0x140016dc5  mov     r8, [rax+188h]
0x140016dcc  sub     r8, [rax+100h]
0x140016dd3  mov     rdx, [rax+180h]
0x140016dda  add     r8, qword ptr [rbp+120h+var_180]
0x140016dde  mov     rax, [rdx+30h]
0x140016de2  cmp     r8, rax
0x140016de5  jnb     loc_140017120
0x140016deb  sub     rax, r8
0x140016dee  cmp     rsi, rax
0x140016df1  ja      loc_140017120
0x140016df7  mov     rax, [rsp+220h+var_1A8]
0x140016dfc  xor     ecx, ecx
0x140016dfe  mov     [rsp+220h+var_1D8], rcx
0x140016e03  mov     r9, r13
0x140016e06  mov     [rsp+220h+var_1E0], cl
0x140016e0a  mov     [rsp+220h+var_1E8], cl
0x140016e0e  mov     [rsp+220h+var_1F0], ecx
0x140016e12  mov     [rsp+220h+var_1F8], rcx
0x140016e17  lea     rcx, [rbp+120h+var_170]
0x140016e1b  shl     r8, 0Ch
0x140016e1f  mov     [rsp+220h+Irp], rax
0x140016e24  call    VsmmMemoryBlockCopyByteRange
0x140016e29  xor     r8d, r8d
0x140016e2c  mov     esi, eax
0x140016e2e  test    eax, eax
0x140016e30  js      loc_1400170C7
0x140016e36  mov     rax, qword ptr [rbp+120h+var_180]
0x140016e3a  lea     rcx, [rsp+220h+var_1D0]
0x140016e3f  mov     qword ptr [rbp+120h+var_158], rax
0x140016e43  lea     r8, [rbp+120h+var_158]
0x140016e47  mov     rax, [rsp+220h+var_1A8]
0x140016e4c  mov     [rsp+220h+var_1F0], r13d
0x140016e51  mov     r9, rax
0x140016e54  mov     [rsp+220h+var_1F8], rax
0x140016e59  mov     [rsp+220h+Irp], rcx
0x140016e5e  mov     rcx, r15
0x140016e61  call    VsmmCryptPack
0x140016e66  xor     r8d, r8d
0x140016e69  mov     esi, eax
0x140016e6b  test    eax, eax
0x140016e6d  js      loc_14001721F
0x140016e73  mov     r13d, [rsp+220h+var_1D0]
0x140016e78  add     [r14+78h], r13
0x140016e7c  mov     [rsp+220h+var_1C8], r8b
0x140016e81  jmp     loc_140016F35
0x140016e86  mov     rcx, [r14+58h]
0x140016e8a  lea     eax, ds:30h[rsi*8]
0x140016e91  mov     r9d, eax
0x140016e94  lea     rdx, [rax+rcx]
0x140016e98  cmp     rdx, [r14+50h]
0x140016e9c  ja      short loc_140016EAB
0x140016e9e  mov     rdi, [r14+48h]
0x140016ea2  add     rdi, rcx
0x140016ea5  mov     [r14+58h], rdx
0x140016ea9  jmp     short loc_140016ED8
0x140016eab  mov     r8d, 6D4D6456h
0x140016eb1  mov     rdx, r9
0x140016eb4  mov     ecx, 40h ; '@'
0x140016eb9  call    cs:__imp_ExAllocatePool2
0x140016ec0  nop     dword ptr [rax+rax+00h]
0x140016ec5  xor     r10d, r10d
0x140016ec8  mov     rdi, rax
0x140016ecb  test    rax, rax
0x140016ece  jz      loc_1400177D9
0x140016ed4  lea     r11d, [r10+2]
0x140016ed8  mov     [rdi+0Ch], r10
0x140016edc  mov     rax, r13
0x140016edf  mov     [rdi+14h], r10
0x140016ee3  mov     r9d, ebx
0x140016ee6  mov     [rdi+1Ch], r10d
0x140016eea  mov     r8, rsi
0x140016eed  mov     rdx, qword ptr [rbp+120h+var_180]
0x140016ef1  mov     rcx, [rbp+120h+var_1A0]
0x140016ef5  shr     rax, 0Ch
0x140016ef9  add     ax, 6
0x140016efd  mov     [rdi], r10
0x140016f00  shl     ax, 3
0x140016f04  mov     [rdi+8], ax
0x140016f08  mov     [rdi+20h], r10
0x140016f0c  mov     [rdi+2Ch], r10d
0x140016f10  mov     [rdi+28h], r13d
0x140016f14  mov     [rdi+0Ah], r11w
0x140016f19  mov     [rsp+220h+Irp], rdi
0x140016f1e  call    VsmmLockGpaRange
0x140016f23  xor     r8d, r8d
0x140016f26  mov     esi, eax
0x140016f28  test    eax, eax
0x140016f2a  js      loc_14001759E
0x140016f30  mov     [rsp+220h+var_1C8], 1
0x140016f35  mov     r10, [r14+38h]
0x140016f39  mov     r11, [rbp+120h+var_198]
0x140016f3d  lea     r9, [r11+r11*4]
0x140016f41  mov     dword ptr [r10+r9*8+18h], 1
0x140016f4a  mov     eax, [rdi+28h]
0x140016f4d  mov     [r10+r9*8+1Ch], eax
0x140016f52  mov     rax, qword ptr [rbp+120h+var_180]
0x140016f56  mov     [r10+r9*8+20h], rdi
0x140016f5b  mov     [r10+r9*8+34h], r13d
0x140016f60  mov     r13, [rbp+120h+var_1A0]
0x140016f64  shl     rax, 0Ch
0x140016f68  mov     [r10+r9*8+28h], rax
0x140016f6d  lea     rcx, [r13+8]
0x140016f71  call    VidOpCtrlStart
0x140016f76  xor     r8d, r8d
0x140016f79  test    al, al
0x140016f7b  jz      loc_14001740F
0x140016f81  mov     rax, [r14+60h]
0x140016f85  mov     [rax+r11*8], r13
0x140016f89  test    r11, r11
0x140016f8c  jz      short loc_140016F97
0x140016f8e  mov     dword ptr [r10+r9*8-18h], 28h ; '('
0x140016f97  mov     ecx, [rsp+220h+var_1CC]
0x140016f9b  xor     r10d, r10d
0x140016f9e  mov     r13, [rsp+220h+var_1B8]
0x140016fa3  inc     ecx
0x140016fa5  inc     qword ptr [r14+40h]
0x140016fa9  add     [r14+18h], r13
0x140016fad  mov     eax, ecx
0x140016faf  mov     [rsp+220h+var_1CC], ecx
0x140016fb3  cmp     rax, [rbp+120h+var_190]
0x140016fb7  jnb     loc_140017A8D
0x140016fbd  mov     rdx, [rsp+220h+var_1B0]
0x140016fc2  mov     r9, [rsp+220h+var_1C0]
0x140016fc7  jmp     loc_140016CEB
0x140016fcc  mov     eax, cs:dword_140064110
0x140016fd2  cmp     eax, 2
0x140016fd5  jbe     loc_140017A90
0x140016fdb  mov     edx, 100h
0x140016fe0  lea     rcx, dword_140064110
0x140016fe7  call    _tlgKeywordOn
0x140016fec  test    al, al
0x140016fee  jz      loc_140017A90
0x140016ff4  lea     rdx, aVsmmmemxferbui; "VsmmMemXferBuildBatchedWrite"
0x140016ffb  lea     rcx, [rbp+120h+var_120]
0x140016fff  call    _tlgCreate1Sz_char
0x140017004  lea     rdx, aOnecoreVmVidSy_56; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfe"...
0x14001700b  lea     rcx, [rbp+120h+var_110]
0x14001700f  call    _tlgCreate1Sz_char
0x140017014  lea     rax, [rsp+220h+var_1CC]
0x140017019  mov     [rsp+220h+var_1CC], 72Eh
0x140017021  mov     [rbp+120h+var_100], rax
0x140017025  lea     rcx, [rsp+220h+var_1D0]
0x14001702a  lea     rax, [r15+290h]
0x140017031  mov     [rbp+120h+var_F8], 4
0x140017039  mov     [rbp+120h+var_E0], rax
0x14001703d  lea     rdx, byte_14004D0A7
0x140017044  lea     rax, [rbp+120h+var_B8]
0x140017048  mov     [rsp+220h+var_1D0], esi
0x14001704c  mov     [rbp+120h+var_D0], rax
0x140017050  mov     rax, [r15+80h]
0x140017057  mov     [rbp+120h+var_C0], rax
0x14001705b  movzx   eax, word ptr [r15+78h]
0x140017060  mov     [rbp+120h+var_B8], eax
0x140017063  mov     rax, [r15+288h]
0x14001706a  mov     [rsp+220h+var_1C0], rax
0x14001706f  lea     rax, [rsp+220h+var_1C0]
0x140017074  mov     [rbp+120h+var_B0], rax
0x140017078  lea     rax, [rsp+220h+var_1B0]
0x14001707d  mov     [rbp+120h+var_A0], rax
0x140017084  lea     rax, [rbp+120h+var_140]
0x140017088  mov     [rsp+220h+var_1F8], rax
0x14001708d  mov     dword ptr [rsp+220h+Irp], 0Bh
0x140017095  mov     [rbp+120h+var_F0], rcx
0x140017099  mov     [rbp+120h+var_E8], 4
0x1400170a1  mov     [rbp+120h+var_D8], 10h
0x1400170a9  mov     [rbp+120h+var_C8], 2
0x1400170b1  mov     [rbp+120h+var_B4], r10d
0x1400170b5  mov     [rbp+120h+var_A8], 8
0x1400170bd  mov     [rsp+220h+var_1B0], rdi
0x1400170c2  jmp     loc_140017A6E
0x1400170c7  mov     eax, cs:dword_140064110
0x1400170cd  cmp     eax, 2
0x1400170d0  jbe     loc_14001721F
0x1400170d6  mov     edx, 100h
0x1400170db  lea     rcx, dword_140064110
0x1400170e2  call    _tlgKeywordOn
0x1400170e7  test    al, al
0x1400170e9  jz      loc_14001721F
0x1400170ef  lea     rdx, aVsmmmemxferbui; "VsmmMemXferBuildBatchedWrite"
0x1400170f6  lea     rcx, [rbp+120h+var_120]
0x1400170fa  call    _tlgCreate1Sz_char
0x1400170ff  lea     rdx, aOnecoreVmVidSy_56; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfe"...
0x140017106  lea     rcx, [rbp+120h+var_110]
0x14001710a  call    _tlgCreate1Sz_char
0x14001710f  mov     [rsp+220h+var_1CC], 779h
0x140017117  lea     rdx, byte_14004CF1D
0x14001711e  jmp     short loc_14001717F
0x140017120  mov     eax, cs:dword_140064110
0x140017126  mov     esi, 0C0000010h
0x14001712b  cmp     eax, 2
0x14001712e  jbe     loc_14001721C
0x140017134  mov     edx, 100h
0x140017139  lea     rcx, dword_140064110
0x140017140  call    _tlgKeywordOn
0x140017145  xor     r8d, r8d
0x140017148  test    al, al
0x14001714a  jz      loc_14001721F
0x140017150  lea     rdx, aVsmmmemxferbui; "VsmmMemXferBuildBatchedWrite"
0x140017157  lea     rcx, [rbp+120h+var_120]
0x14001715b  call    _tlgCreate1Sz_char
0x140017160  lea     rdx, aOnecoreVmVidSy_56; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfe"...
0x140017167  lea     rcx, [rbp+120h+var_110]
0x14001716b  call    _tlgCreate1Sz_char
0x140017170  mov     [rsp+220h+var_1CC], 764h
0x140017178  lea     rdx, byte_14004CDD3
0x14001717f  lea     rax, [rsp+220h+var_1CC]
0x140017184  mov     [rbp+120h+var_A8], 8
0x14001718c  mov     [rbp+120h+var_100], rax
0x140017190  lea     rcx, [rsp+220h+var_1D0]
0x140017195  lea     rax, [r15+290h]
0x14001719c  mov     [rbp+120h+var_F0], rcx
0x1400171a0  mov     [rbp+120h+var_E0], rax
0x1400171a4  lea     rcx, dword_140064110
0x1400171ab  lea     rax, [rbp+120h+var_B8]
0x1400171af  mov     [rbp+120h+var_B4], r8d
  ... truncated ...
```
