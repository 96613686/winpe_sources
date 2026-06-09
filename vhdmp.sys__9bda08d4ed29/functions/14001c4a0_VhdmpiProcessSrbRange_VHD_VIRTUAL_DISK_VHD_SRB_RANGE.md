# VhdmpiProcessSrbRange(_VHD_VIRTUAL_DISK *,_VHD_SRB_RANGE *)

- ea: `0x14001c4a0`
- end: `0x14001dcce`
- name: `?VhdmpiProcessSrbRange@@YAJPEAU_VHD_VIRTUAL_DISK@@PEAU_VHD_SRB_RANGE@@@Z`
- size: `6190`
- prototype: `int(struct _VHD_VIRTUAL_DISK *, struct _VHD_SRB_RANGE *)`
- caller_count: `2`
- callee_count: `41`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140016e00`
- `0x14001c300`

## callees

- `0x140012960`
- `0x140014c30`
- `0x140016f44`
- `0x14001730c`
- `0x140017404`
- `0x14001b108`
- `0x14001bf54`
- `0x14001c4a0`
- `0x14001e8f0`
- `0x14001f350`
- `0x1400205a4`
- `0x1400207d0`
- `0x1400210f0`
- `0x14002112c`
- `0x1400212ac`
- `0x140021e98`
- `0x1400226e8`
- `0x1400237b0`
- `0x140023980`
- `0x1400239b0`
- `0x1400252a4`
- `0x140027358`
- `0x14002738c`
- `0x14002b4ec`
- `0x140033860`
- `0x140036284`
- `0x14003b9f4`
- `0x14003bac4`
- `0x14003c0f4`
- `0x14003c154`
- `0x14003ce6c`
- `0x14003cf38`
- `0x14003cf90`
- `0x14003d444`
- `0x14003d5dc`
- `0x14003d9f8`
- `0x14003db70`
- `0x14003e0cc`
- `0x14003e364`
- `0x1400ccbcc`
- `0x1400e606c`

## import_xrefs

- `ntoskrnl!MmProbeAndLockPages` at `0x14001ceeb`
- `ntoskrnl!MmProbeAndLockPages` at `0x14001ceeb`
- `ntoskrnl!MmUnlockPages` at `0x14001cf56`
- `ntoskrnl!MmUnlockPages` at `0x14001cf56`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14001d48e`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14001d48e`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14001d88d`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14001d88d`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14001c8be`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14001c8be`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001d8b8`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001d8b8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001d05f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001d551`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001d05f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001d551`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001d0a7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001d5a0`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001d0a7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001d5a0`

## pseudocode

```c
__int64 __fastcall VhdmpiProcessSrbRange(struct _VHD_VIRTUAL_DISK *a1, struct _VHD_SRB_RANGE *a2)
{
  __int64 v4; // r13
  struct _VHD_SRB_EXTENSION *v5; // r11
  int v6; // ecx
  unsigned int v7; // eax
  char v8; // r15
  int v9; // edx
  unsigned int v10; // edx
  __int64 v11; // r14
  struct _SECTOR_BITMAP *v12; // r10
  unsigned int v13; // r12d
  signed int LbaStatus; // ebx
  __int64 v15; // r8
  int v16; // r9d
  __int64 v17; // r11
  int v18; // eax
  unsigned __int64 v19; // rcx
  unsigned __int64 v20; // r9
  __int64 v21; // r9
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r9
  _DWORD *v25; // rax
  __int64 v26; // r9
  unsigned int v27; // r9d
  unsigned int v28; // r10d
  __int64 v29; // r9
  struct _SLIST_ENTRY *v30; // rdx
  _DWORD *v31; // rdx
  unsigned int v32; // edx
  int v33; // r8d
  int v34; // r9d
  int v35; // r10d
  __int64 v36; // r8
  unsigned int v37; // ecx
  int v38; // r9d
  unsigned int v39; // edx
  int v40; // eax
  __int64 v41; // r8
  int v42; // r8d
  struct _SECTOR_BITMAP *v43; // r10
  unsigned __int8 v44; // al
  unsigned int v45; // edx
  const void *v46; // r10
  int v47; // eax
  unsigned int v48; // ecx
  unsigned int v49; // eax
  struct _SECTOR_BITMAP *v50; // r11
  char v51; // al
  struct _VHD_SRB_RANGE *v52; // rcx
  __int64 v53; // rdx
  __int64 v54; // r8
  unsigned __int64 v55; // r10
  unsigned __int64 v56; // rbx
  unsigned __int64 v57; // rcx
  unsigned __int64 v58; // r9
  unsigned __int64 v59; // r8
  unsigned __int64 v60; // rax
  struct _MDL *Mdl; // rax
  struct _VHD1_IRP_CONTEXT *v62; // rax
  KIRQL v63; // al
  __int64 v64; // r10
  __int64 v65; // rdx
  _QWORD *v66; // r9
  char *v67; // r8
  struct _SECTOR_BITMAP *v68; // rbx
  unsigned __int8 *v69; // rax
  struct _MDL *v70; // rdx
  __int64 v71; // rbx
  KIRQL v72; // r8
  __int64 v73; // r9
  __int64 v74; // rcx
  _QWORD *v75; // rdx
  char *v76; // rax
  struct _VHD1_IRP_CONTEXT *v77; // r8
  struct _VHD1_IRP_CONTEXT *v78; // r8
  unsigned int v79; // edx
  int v80; // r10d
  int v81; // eax
  int v82; // eax
  struct _SECTOR_BITMAP *v83; // r10
  unsigned int v84; // r11d
  unsigned int EndOfZeroesRun; // r12d
  unsigned int EndOfOnesRun; // r12d
  unsigned int v87; // edx
  _QWORD *v88; // rbx
  int v89; // ecx
  struct _VHD1_IRP_CONTEXT *v90; // rax
  int v91; // eax
  __int64 v92; // rdx
  __int64 v93; // r10
  char v94; // cl
  _DWORD *IoSegmentForBufferOffset; // rax
  int *v96; // r9
  unsigned int v97; // edx
  int v98; // ecx
  unsigned int v99; // r14d
  int *v100; // rcx
  unsigned int v101; // eax
  int v102; // edx
  unsigned int v103; // edi
  int v104; // r9d
  __int64 *v105; // rdx
  signed __int32 v107[8]; // [rsp+0h] [rbp-238h] BYREF
  char *v108; // [rsp+20h] [rbp-218h]
  char v109[8]; // [rsp+28h] [rbp-210h]
  __int64 v110; // [rsp+38h] [rbp-200h]
  unsigned int v111; // [rsp+50h] [rbp-1E8h]
  struct _SECTOR_BITMAP *v112; // [rsp+58h] [rbp-1E0h]
  char v113; // [rsp+60h] [rbp-1D8h]
  int v114; // [rsp+64h] [rbp-1D4h]
  char v115; // [rsp+68h] [rbp-1D0h]
  char v116; // [rsp+69h] [rbp-1CFh]
  unsigned int v117[2]; // [rsp+70h] [rbp-1C8h]
  char v118[4]; // [rsp+78h] [rbp-1C0h]
  unsigned int v119; // [rsp+7Ch] [rbp-1BCh]
  unsigned int v120; // [rsp+80h] [rbp-1B8h]
  unsigned int v121; // [rsp+84h] [rbp-1B4h]
  unsigned int v122; // [rsp+88h] [rbp-1B0h]
  unsigned int v123; // [rsp+8Ch] [rbp-1ACh]
  unsigned int v124; // [rsp+90h] [rbp-1A8h]
  struct _VHD1_IRP_CONTEXT *v125; // [rsp+98h] [rbp-1A0h]
  unsigned int v126; // [rsp+A0h] [rbp-198h]
  unsigned int v127; // [rsp+A4h] [rbp-194h] BYREF
  struct _VHD_SRB_EXTENSION *v128; // [rsp+A8h] [rbp-190h]
  unsigned __int64 v129; // [rsp+B0h] [rbp-188h]
  __int64 v130; // [rsp+B8h] [rbp-180h]
  unsigned int v131; // [rsp+C0h] [rbp-178h]
  unsigned int v132; // [rsp+C4h] [rbp-174h]
  ULONG CurrentProcessorNumber; // [rsp+C8h] [rbp-170h]
  struct _SECTOR_BITMAP *v134; // [rsp+D0h] [rbp-168h] BYREF
  struct _VHD1_IRP_CONTEXT *v135; // [rsp+D8h] [rbp-160h] BYREF
  unsigned __int64 v136; // [rsp+E0h] [rbp-158h]
  int *v137; // [rsp+E8h] [rbp-150h]
  unsigned __int64 v138; // [rsp+F0h] [rbp-148h]
  __int64 v139; // [rsp+F8h] [rbp-140h]
  unsigned __int64 v140; // [rsp+100h] [rbp-138h]
  struct _VHD1_IRP_CONTEXT *v141; // [rsp+108h] [rbp-130h] BYREF
  unsigned __int64 v142; // [rsp+110h] [rbp-128h]
  __int64 v143; // [rsp+118h] [rbp-120h]
  PMDL MemoryDescriptorList; // [rsp+120h] [rbp-118h]
  int v145; // [rsp+128h] [rbp-110h]
  unsigned int v146; // [rsp+12Ch] [rbp-10Ch]
  struct _VHD1_IRP_CONTEXT *v147[2]; // [rsp+130h] [rbp-108h] BYREF
  unsigned __int64 v148; // [rsp+140h] [rbp-F8h]
  struct _VHD1_BACKING_STORE *v149; // [rsp+148h] [rbp-F0h]
  unsigned int v150; // [rsp+150h] [rbp-E8h]
  _BYTE *v151; // [rsp+158h] [rbp-E0h]
  unsigned __int64 v152; // [rsp+160h] [rbp-D8h]
  __int64 v153; // [rsp+168h] [rbp-D0h]
  struct _VHD_SRB_EXTENSION *v154; // [rsp+170h] [rbp-C8h]
  _DWORD *v155; // [rsp+178h] [rbp-C0h]
  struct _VHD_SRB_RANGE *v156; // [rsp+180h] [rbp-B8h]
  union _SLIST_HEADER *v157; // [rsp+188h] [rbp-B0h]
  __int64 v158; // [rsp+190h] [rbp-A8h]
  __int64 v159; // [rsp+198h] [rbp-A0h]
  unsigned __int64 v160; // [rsp+1A0h] [rbp-98h]
  __int64 v161; // [rsp+1A8h] [rbp-90h]
  unsigned __int64 v162; // [rsp+1B0h] [rbp-88h]
  __int64 v163; // [rsp+1B8h] [rbp-80h]
  struct _VHD_SRB_RANGE *v164; // [rsp+1C0h] [rbp-78h]
  _QWORD *v165; // [rsp+1D0h] [rbp-68h]
  struct _SECTOR_BITMAP **v166; // [rsp+1D8h] [rbp-60h]
  struct _VHD1_IRP_CONTEXT **v167; // [rsp+1E0h] [rbp-58h]
  unsigned int *v168; // [rsp+1E8h] [rbp-50h]
  unsigned int *v169; // [rsp+1F0h] [rbp-48h]
  unsigned int *v170; // [rsp+1F8h] [rbp-40h]
  struct _VHD_SRB_RANGE *v172; // [rsp+248h] [rbp+10h] BYREF
  char v173; // [rsp+250h] [rbp+18h]
  char v174; // [rsp+258h] [rbp+20h]

  v172 = a2;
  v141 = 0;
  v147[0] = 0;
  v115 = 0;
  v4 = *(_QWORD *)a2;
  v147[1] = (struct _VHD1_IRP_CONTEXT *)v4;
  v5 = *(struct _VHD_SRB_EXTENSION **)v4;
  v128 = v5;
  v154 = v5;
  if ( (unsigned int)dword_1400876D0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
  {
    TraceEvents(
      "VhdmpiProcessSrbRange",
      0x3577u,
      5u,
      8u,
      "VhdmpiProcessSrbRange: Enter... SrbRange=0x%p ByteOffset=0x%I64X Length=0x%x Operation=%d",
      a2,
      *((_QWORD *)a2 + 6),
      *((_DWORD *)a2 + 14),
      *((_DWORD *)v5 + 15));
    v5 = v128;
  }
  v6 = *(_DWORD *)(*(_QWORD *)v5 + 2144LL);
  v7 = *((_DWORD *)v5 + 15);
  v8 = 1;
  if ( (v6 & 1) != 0 && v7 <= 7 && (v9 = 146, _bittest(&v9, v7)) || (v6 & 4) != 0 && v7 == 8 )
  {
    VhdmpiMapAndWriteSrbToTraceFile((__int64 *)v5, 2, *((_DWORD *)a2 + 15));
    v5 = v128;
  }
  v10 = *((_DWORD *)v5 + 15);
  v111 = v10;
  v132 = v10;
  v11 = *((_QWORD *)a2 + 1);
  v149 = (struct _VHD1_BACKING_STORE *)v11;
  v166 = (struct _SECTOR_BITMAP **)((char *)a2 + 32);
  v12 = (struct _SECTOR_BITMAP *)*((_QWORD *)a2 + 4);
  v112 = v12;
  v134 = v12;
  v170 = (unsigned int *)((char *)a2 + 64);
  v13 = *((_DWORD *)a2 + 16);
  v122 = v13;
  v167 = (struct _VHD1_IRP_CONTEXT **)((char *)a2 + 40);
  v125 = (struct _VHD1_IRP_CONTEXT *)*((_QWORD *)a2 + 5);
  v135 = v125;
  v168 = (unsigned int *)((char *)a2 + 68);
  v119 = *((_DWORD *)a2 + 17);
  v124 = v119;
  v169 = (unsigned int *)((char *)a2 + 72);
  v120 = *((_DWORD *)a2 + 18);
  v123 = v120;
  if ( v10 == 8 && *(_DWORD *)(v11 + 1988) != 2 )
  {
    *((_DWORD *)a2 + 15) = *((_DWORD *)a2 + 14);
    LbaStatus = -1073741637;
    VhdmpiVhd1AccumulateStatusSrbPart(v4, 0, 3221225659LL, 0);
    goto LABEL_207;
  }
  if ( v10 == 9 )
  {
    LODWORD(v172) = 0;
    v16 = *((_DWORD *)v5 + 16) >> 9;
    LOBYTE(v16) = (*((_DWORD *)v5 + 16) & 0x200) != 0;
    LbaStatus = VhdmpiProcessGetLbaStatus(
                  v11,
                  *(_QWORD *)(v4 + 88),
                  *(_DWORD *)(*((_QWORD *)v5 + 3) + 16LL),
                  v16,
                  *(_QWORD *)(*((_QWORD *)v5 + 3) + 24LL),
                  (__int64)&v172);
    if ( LbaStatus >= 0 )
      *(_DWORD *)(*((_QWORD *)v128 + 3) + 16LL) = (_DWORD)v172;
    *((_DWORD *)a2 + 15) = *((_DWORD *)a2 + 14);
    goto LABEL_207;
  }
  if ( v10 != 11 )
  {
    v156 = a2;
    v164 = a2;
    v157 = (union _SLIST_HEADER *)a1;
    v139 = v4;
    LODWORD(v15) = -1;
    *(_QWORD *)v117 = 0xFFFFFFFFLL;
    v173 = 0;
    v165 = (_QWORD *)((char *)a2 + 8);
    while ( 1 )
    {
      v174 = 0;
      v116 = 0;
      v137 = (int *)((char *)a2 + 60);
      v138 = *((unsigned int *)a2 + 15);
      v19 = *((_QWORD *)a2 + 6);
      v20 = -1;
      if ( v19 + v138 >= v19 )
        v20 = v19 + v138;
      v136 = v20;
      v140 = v20;
      LbaStatus = v19 + v138 < v19 ? 0xC0000095 : 0;
      if ( v19 + v138 < v19 )
      {
        v21 = 0;
        v22 = 0;
        goto LABEL_27;
      }
      v25 = (_DWORD *)(v11 + 1988);
      v155 = (_DWORD *)(v11 + 1988);
      if ( *(_DWORD *)(v11 + 1988) == 2 )
      {
        *(_DWORD *)v118 = 0;
        v121 = 0;
        v129 = v20;
        v174 = 1;
        v26 = v11;
        goto LABEL_142;
      }
      LOBYTE(v25) = 0;
      v114 = (int)v25;
      v113 = 0;
      v27 = *(_DWORD *)(v11 + 2472);
      v148 = v136 % v27;
      v28 = v148;
      *(_QWORD *)v117 = v136 / v27;
      v131 = v117[0];
      CurrentProcessorNumber = v148;
      v29 = v27 - (unsigned int)v148;
      v143 = v29;
      if ( v13 > (unsigned int)v29 )
      {
        if ( (*((_DWORD *)v5 + 16) & 0x100) != 0 )
        {
          v31 = (_DWORD *)((char *)v156 + 56);
        }
        else
        {
          v142 = (unsigned __int64)a2 + 56;
          VhdmpiCreateSrbRange(
            (struct VHD_SRB_PART *)v4,
            v136 + (unsigned int)v29,
            *((_DWORD *)a2 + 14) - v138 - v29,
            (struct _VHD1_BACKING_STORE *)v11,
            v13 - v29);
          VhdmpiVhd1IncrementSrbPartRefCount((struct VHD_SRB_PART *)v4);
          if ( !*(_BYTE *)(v4 + 111) )
            *(_BYTE *)(v4 + 111) = 2;
          ExpInterlockedPushEntrySList(v157 + 72, v30 + 1);
          LODWORD(v29) = v143;
          v31 = (_DWORD *)v142;
          v28 = v148;
        }
        v13 = v29;
        v122 = v29;
        *v31 = v29 + *v137;
      }
      *(_DWORD *)v118 = v28 >> 9;
      v150 = v28 >> 9;
      v121 = (v28 + v13) >> 9;
      v146 = v121;
      if ( (unsigned int)dword_1400876D0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
        TraceEvents(
          "VhdmpiProcessSrbRange",
          0x3660u,
          v32 - 3,
          v32,
          "VhdmpiProcessSrbRange: BlockRelativeByteOffset=0x%x FileLength=0x%x StartBlockRelativeSector=0x%x EndBlockRelativeSector=0x%x",
          v35,
          v13,
          v33,
          v34);
      v36 = *(_QWORD *)(v11 + 3816);
      v130 = v36;
      v37 = v111;
      v38 = 146;
      v39 = v117[0];
      if ( v111 > 7
        || !_bittest(&v38, v111)
        || *((_BYTE *)a2 + 80)
        || (v138 = v117[0], *(_DWORD *)(v36 + 4LL * v117[0]) != -1) )
      {
        LOBYTE(v42) = v114;
        goto LABEL_58;
      }
      if ( VhdmpiVhd1IsAnyPortionOfSrbRangeDefinedByAnyParent((struct _VHD1_BACKING_STORE *)v11, a2) )
        break;
      v40 = VhdmpiSrbPartCheckZero((struct VHD_SRB_PART *)v4);
      LbaStatus = v40;
      if ( v40 < 0 )
      {
        v41 = (unsigned int)v40;
        goto LABEL_48;
      }
      v15 = 279;
      if ( v115 )
        LbaStatus = 279;
      if ( LbaStatus != 279 )
        break;
      v174 = 1;
      LbaStatus = 0;
      if ( (*((_DWORD *)v128 + 16) & 0x100) != 0 )
        VhdmpiSrbPartRangeReported((struct VHD_SRB_PART *)v4, 0, v13);
LABEL_182:
      if ( *((_BYTE *)a2 + 83) )
      {
        VhdmpiSectorBitmapDecPrerequisiteIoCount(v112, 259, 0);
        *((_BYTE *)a2 + 83) = 0;
      }
      if ( v112 )
      {
        VhdmpiSectorBitmapRelease(v112);
        v112 = 0;
        v134 = 0;
      }
      if ( v125 )
      {
        VhdmpiReleaseSectorBitmapWriteIrpContext(v125);
        v125 = 0;
        v135 = 0;
      }
      *((_WORD *)a2 + 40) = 0;
      v93 = v139;
      v94 = v174;
      if ( *(int *)(v139 + 176) < 0 )
        v94 = 1;
      v5 = v128;
      if ( v94 )
        goto LABEL_194;
      if ( v11 == *((_QWORD *)v128 + 17) )
      {
        IoSegmentForBufferOffset = (_DWORD *)VhdmpiGetIoSegmentForBufferOffset(
                                               *((_QWORD *)v128 + 16),
                                               v136 - *((_QWORD *)v128 + 4),
                                               v15,
                                               v24);
        *IoSegmentForBufferOffset = 4;
        IoSegmentForBufferOffset[1] = v13;
        v94 = 1;
      }
      if ( v94 )
      {
LABEL_194:
        if ( (*((_DWORD *)v5 + 16) & 0x100) != 0 )
        {
          *v137 = *((_DWORD *)a2 + 14);
          goto LABEL_207;
        }
        v96 = v137;
        LODWORD(v15) = *v137;
        v97 = *v137 + v13;
        v98 = -1;
        if ( v97 >= *v137 )
          v98 = *v137 + v13;
        v99 = v97 < (unsigned int)v15 ? 0xC0000095 : 0;
        *v137 = v98;
        if ( v97 < (unsigned int)v15 )
        {
          VhdmpiVhd1AccumulateStatusSrbPart(v4, 0, v99, 0);
          if ( LbaStatus >= 0 )
            LbaStatus = v99;
          v5 = v128;
          v96 = v137;
          v93 = v139;
        }
        v100 = (int *)((char *)a2 + 56);
        v101 = *((_DWORD *)a2 + 14);
        v102 = *v96;
        if ( *v96 >= v101 )
          goto LABEL_207;
        v11 = *((_QWORD *)v5 + 1);
        v13 = v101 - v102;
        v122 = v101 - v102;
      }
      else
      {
        v11 = *(_QWORD *)(v11 + 1144);
        v100 = (int *)((char *)v156 + 56);
        v96 = v137;
      }
      v149 = (struct _VHD1_BACKING_STORE *)v11;
      *v165 = v11;
      LODWORD(v15) = v117[0];
      if ( *(int *)(v93 + 176) < 0 )
      {
        *v96 = *v100;
        goto LABEL_207;
      }
      v12 = v112;
      v10 = v111;
    }
    v42 = (unsigned __int8)v114;
    if ( *(_DWORD *)(v130 + 4 * v138) == -1 )
      v42 = 1;
    v114 = v42;
    v113 = v42;
    v37 = v111;
    v39 = v117[0];
    v38 = 146;
LABEL_58:
    if ( v37 - 1 <= 1 || v37 - 4 <= 3 )
    {
      v43 = v112;
      if ( !v112 )
      {
        if ( v37 > 7 || (v44 = 1, !_bittest(&v38, v37)) )
          v44 = 0;
        LbaStatus = VhdmpiSectorBitmapGet(v128, a2, (struct _VHD1_BACKING_STORE *)v11, v39, v44, v42, &v134);
        if ( LbaStatus == 259 )
        {
          *((_DWORD *)a2 + 19) = 1;
          v112 = v134;
          goto LABEL_66;
        }
        v43 = v134;
        v112 = v134;
        v37 = v111;
      }
      if ( *((_DWORD *)v43 + 50) == 259 )
      {
        if ( v37 == 2 || v37 - 5 <= 1 )
        {
          if ( (int)VhdmpiSectorBitmapAttachSrbRangeToReadCompletion(v43, a2) >= 0 )
          {
            LbaStatus = 0;
            goto LABEL_67;
          }
LABEL_74:
          v43 = v112;
        }
        else if ( !*((_BYTE *)a2 + 81) )
        {
          v119 = *(_DWORD *)v118;
          v124 = *(_DWORD *)v118;
          v120 = v121;
          v123 = v121;
          *((_BYTE *)a2 + 83) = 1;
          VhdmpiSectorBitmapIncPrerequisiteIoCount(v43);
          *((_BYTE *)a2 + 81) = 1;
          goto LABEL_74;
        }
      }
      _InterlockedOr(v107, 0);
      v23 = *((unsigned int *)v43 + 50);
      if ( (int)v23 < 0 )
      {
        LbaStatus = *((_DWORD *)v43 + 50);
        v21 = 1;
        v22 = *(_QWORD *)v43;
        goto LABEL_28;
      }
      _InterlockedOr(v107, 0);
      if ( (unsigned int)dword_1400876D0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
        TraceEvents(
          "VhdmpiProcessSrbRange",
          0x37B7u,
          v45 - 3,
          v45,
          "VhdmpiProcessSrbRange: SectorBitmap=0x%p Block=0x%x IsNewBlock=%d",
          v46,
          v117[0],
          (unsigned __int8)v114);
      v37 = v111;
    }
    v143 = v130;
    if ( v37 <= 7 )
    {
      v47 = 146;
      if ( _bittest(&v47, v37) )
      {
        if ( !*((_BYTE *)a2 + 81) )
        {
          if ( VhdmpiVhd1IsAnyPortionOfVirtualBlockDefinedByAnyParent((struct _VHD1_BACKING_STORE *)v11, v117[0]) )
          {
            v48 = *(_DWORD *)v118;
            v49 = v121;
          }
          else
          {
            v48 = 0;
            v49 = *(_DWORD *)(v11 + 2472) >> 9;
          }
          v123 = v49;
          v120 = v49;
          v124 = v48;
          v119 = v48;
          if ( VhdmpiSectorBitmapIsWriteNeeded(v112, v48, v49) )
          {
            VhdmpiSectorBitmapIncPrerequisiteIoCount(v50);
            v51 = 1;
          }
          else
          {
            v51 = 0;
          }
          v52 = v164;
          *((_BYTE *)v164 + 83) = v51;
          *((_BYTE *)v52 + 82) = v51;
          *((_BYTE *)a2 + 81) = 1;
        }
      }
    }
    v151 = (char *)a2 + 80;
    if ( !*((_BYTE *)a2 + 80) )
    {
      v126 = 0;
      v127 = 0;
      if ( (_BYTE)v114 )
      {
        LbaStatus = VhdmpiAllocatePhysicalSectors(
                      (struct _VHD1_BACKING_STORE *)v11,
                      *(_DWORD *)(v11 + 1924) + *(_DWORD *)(v11 + 2472),
                      &v127);
        v126 = v127 - 1 + (*(_DWORD *)(v11 + 1924) >> 9);
        v127 = v126;
        if ( LbaStatus < 0 )
        {
          v21 = 1;
          v22 = v11;
LABEL_27:
          v23 = (unsigned int)LbaStatus;
LABEL_28:
          VhdmpiVhd1AccumulateStatusSrbPart(v4, v22, v23, v21);
          goto LABEL_182;
        }
        if ( LbaStatus == 259 )
        {
          *((_DWORD *)a2 + 19) = 6;
          goto LABEL_66;
        }
        if ( (_BYTE)v114 )
          goto LABEL_101;
      }
      if ( VhdmpiBatWriteIsNeeded((struct _VHD1_BACKING_STORE *)v11, v117[0]) )
      {
LABEL_101:
        v53 = *(unsigned int *)(v11 + 1924);
        v54 = ~(v53 - 1);
        v55 = *(_QWORD *)(v11 + 2456);
        v56 = v117[0];
        v142 = v117[0];
        v163 = v117[0];
        v161 = 4LL * v117[0];
        v159 = v161;
        v158 = v161;
        v57 = v54 & (v55 + v161);
        v58 = v54 & (v53 + v55 + v161 + 3);
        v59 = v55 + 4LL * *(unsigned int *)(v11 + 3824);
        v60 = v55;
        if ( v57 >= v55 )
          v60 = v57;
        v152 = v60;
        v162 = v60;
        v129 = v60 + v130 - v55;
        v138 = v129;
        if ( v58 <= v59 )
          LODWORD(v59) = v58;
        v153 = (unsigned int)(v59 - v60);
        v145 = v59 - v60;
        v160 = v60 + v130 - v55;
        Mdl = (struct _MDL *)VhdmpiVhd1AllocateMdl(a2, v11, v160, (unsigned int)v153, 1);
        MemoryDescriptorList = Mdl;
        if ( !Mdl )
        {
          if ( v129 == *(_QWORD *)(v11 + 8720) )
            VhdmpiReleaseReserveResource(a2, (struct _VHD1_BACKING_STORE *)v11, 0, 1u);
          if ( (_BYTE)v114 )
          {
            _InterlockedOr8((volatile signed __int8 *)(*(_QWORD *)(v11 + 4352) + (v56 >> 3)), 0x80u >> (v117[0] & 7));
            *(_DWORD *)(v158 + v130) = _byteswap_ulong(v126);
          }
LABEL_110:
          LbaStatus = 259;
          goto LABEL_111;
        }
        MmProbeAndLockPages(Mdl, 0, IoWriteAccess);
        LODWORD(v108) = 129;
        LbaStatus = VhdmpiVhd1AllocateAndInitializeIrp(
                      v11,
                      a2,
                      v152,
                      (unsigned int)v153,
                      v108,
                      VhdmpiBatWriteIoCompletion,
                      MemoryDescriptorList,
                      &v141);
        if ( LbaStatus == 259 )
        {
          MmUnlockPages(MemoryDescriptorList);
          if ( (_BYTE)v114 )
          {
            _InterlockedOr8((volatile signed __int8 *)(*(_QWORD *)(v11 + 4352) + (v142 >> 3)), 0x80u >> (v117[0] & 7));
            *(_DWORD *)(v159 + v130) = _byteswap_ulong(v126);
          }
          VhdmpiVhd1FreeMdl(a2, v11, MemoryDescriptorList, 1);
          if ( v129 == *(_QWORD *)(v11 + 8720) )
            VhdmpiReleaseReserveResource(a2, (struct _VHD1_BACKING_STORE *)v11, 3u, 1u);
LABEL_111:
          *((_DWORD *)a2 + 19) = 10;
          goto LABEL_66;
        }
        if ( v129 == *(_QWORD *)(v11 + 8720) )
        {
          v62 = v141;
          *((_QWORD *)v141 + 39) = v160;
          *((_BYTE *)v62 + 305) = 1;
        }
        *((_DWORD *)v141 + 46) = v117[0];
        if ( (_BYTE)v114 )
          *(_DWORD *)(v161 + v130) = _byteswap_ulong(v126);
        v63 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v139 + 120));
        v64 = v139;
        v65 = v139 + 144;
        v66 = *(_QWORD **)(v139 + 152);
        if ( *v66 != v139 + 144 )
LABEL_133:
          __fastfail(3u);
        v67 = (char *)v141 + 112;
        *((_QWORD *)v141 + 14) = v65;
        *((_QWORD *)v67 + 1) = v66;
        *v66 = v67;
        *(_QWORD *)(v65 + 8) = v67;
        KeReleaseSpinLock((PKSPIN_LOCK)(v64 + 120), v63);
        VhdmpiVhd1IncrementSrbPartRefCount((struct VHD_SRB_PART *)v4);
        VhdmpiBatWriteQueue((struct _VHD1_BACKING_STORE *)v11, v141, v147);
        if ( v147[0] )
        {
          VhdmpiBatWriteIssueIrp(v147[0]);
          v147[0] = 0;
        }
      }
      *v151 = 1;
    }
    if ( *((_BYTE *)a2 + 83) && !v125 )
    {
      v68 = v112;
      v69 = VhdmpiAddRefSectorBitmapIoBuffer(a2, (struct _VHD1_BACKING_STORE *)v11, v112);
      if ( !v69 )
        goto LABEL_110;
      v70 = (struct _MDL *)VhdmpiVhd1AllocateMdl(a2, v11, v69, *(unsigned int *)(v11 + 1924), 4);
      v140 = (unsigned __int64)v70;
      if ( !v70 )
      {
        VhdmpiReleaseSectorBitmapIoBuffer(a2, (struct _VHD1_BACKING_STORE *)v11, v68);
        goto LABEL_110;
      }
      v71 = ((_byteswap_ulong(*(_DWORD *)(v130 + 4LL * v117[0])) + 1LL) << 9) - *(unsigned int *)(v11 + 1924);
      MmBuildMdlForNonPagedPool(v70);
      LODWORD(v108) = 130;
      LbaStatus = VhdmpiVhd1AllocateAndInitializeIrp(
                    v11,
                    a2,
                    v71,
                    *(unsigned int *)(v11 + 1924),
                    v108,
                    VhdmpiSectorBitmapWriteIoCompletion,
                    v140,
                    &v135);
      if ( LbaStatus == 259 )
      {
        VhdmpiVhd1FreeMdl(a2, v11, v140, 4);
        VhdmpiReleaseSectorBitmapIoBuffer(a2, (struct _VHD1_BACKING_STORE *)v11, v112);
        *((_DWORD *)a2 + 19) = 10;
        v125 = v135;
LABEL_66:
        *((_BYTE *)a2 + 84) = 1;
LABEL_67:
        v8 = v173;
        goto LABEL_207;
      }
      v125 = v135;
      *((_DWORD *)v135 + 70) = 2;
      v72 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v139 + 120));
      v73 = v139;
      v74 = v139 + 128;
      v75 = *(_QWORD **)(v139 + 136);
      if ( *v75 != v139 + 128 )
        goto LABEL_133;
      v76 = (char *)v125 + 112;
      *((_QWORD *)v125 + 14) = v74;
      *((_QWORD *)v76 + 1) = v75;
      *v75 = v76;
      *(_QWORD *)(v74 + 8) = v76;
      KeReleaseSpinLock((PKSPIN_LOCK)(v73 + 120), v72);
      v77 = v125;
      *((_DWORD *)v125 + 74) = v119;
      *((_DWORD *)v77 + 75) = v120;
      *((_BYTE *)v77 + 304) = *((_BYTE *)a2 + 82);
      VhdmpiVhd1IncrementSrbPartRefCount((struct VHD_SRB_PART *)v4);
      VhdmpiSectorBitmapQueueWrite(v78, v112);
    }
    v26 = v11;
    v10 = v111;
    LODWORD(v15) = v117[0];
    if ( v111 == 3 )
    {
      v129 = 0;
    }
    else
    {
      v129 = (unsigned int)v148 + ((_byteswap_ulong(*(_DWORD *)(v130 + 4LL * v117[0])) + 1LL) << 9);
      if ( (unsigned int)dword_1400876D0 > 5 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
        {
          TraceEvents(
            "VhdmpiProcessSrbRange",
            0x3A34u,
            v79 - 3,
            v79,
            "VhdmpiProcessSrbRange: Block=0x%x Sector=0x%x",
            v15,
            v80);
          LODWORD(v15) = v117[0];
          v26 = v11;
        }
        v10 = v111;
      }
    }
    v25 = v155;
    v12 = v112;
LABEL_142:
    if ( *v25 != 2 )
    {
      if ( v10 == 2 || v10 - 5 <= 1 )
      {
        if ( v12 == (struct _SECTOR_BITMAP *)&g_TheOneSectorBitmap
          && *(_DWORD *)(*(_QWORD *)(v26 + 3816) + 4LL * (unsigned int)v15) == -1 )
        {
          v82 = VhdmpiSrbPartReportZero((struct VHD_SRB_PART *)v4, (int)v136 - *(_DWORD *)(v4 + 88), v13);
          LbaStatus = v82;
          if ( v82 >= 0 )
          {
            v174 = 1;
            goto LABEL_182;
          }
          v41 = (unsigned int)v82;
LABEL_48:
          VhdmpiVhd1AccumulateStatusSrbPart(v4, 0, v41, 0);
LABEL_181:
          LbaStatus = 0;
          goto LABEL_182;
        }
        if ( (unsigned int)dword_1400876D0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
        {
          TraceEvents(
            "VhdmpiProcessSrbRange",
            0x3A7Eu,
            5u,
            8u,
            "VhdmpiProcessSrbRange: StartBlockSector=0x%x EndBlockSector=0x%x",
            *(_DWORD *)v118,
            v121);
          v12 = v112;
        }
        EndOfZeroesRun = VhdmpiSectorBitmapFindEndOfZeroesRun(v12, *(unsigned int *)v118, v121);
        if ( (unsigned int)dword_1400876D0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
        {
          TraceEvents(
            "VhdmpiProcessSrbRange",
            0x3A8Fu,
            5u,
            8u,
            "VhdmpiProcessSrbRange: EndOfZeroesRun=0x%x",
            EndOfZeroesRun);
          v83 = v112;
          v84 = v121;
        }
        if ( EndOfZeroesRun != *(_DWORD *)v118 )
        {
          v13 = (EndOfZeroesRun - *(_DWORD *)v118) << 9;
          v122 = v13;
          goto LABEL_182;
        }
        EndOfOnesRun = VhdmpiSectorBitmapFindEndOfOnesRun(v83, *(unsigned int *)v118, v84);
        if ( (unsigned int)dword_1400876D0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
          TraceEvents(
            "VhdmpiProcessSrbRange",
            0x3AB8u,
            v87 - 3,
            v87,
            "VhdmpiProcessSrbRange: EndOfOnesRun=0x%x",
            EndOfOnesRun);
        v13 = (EndOfOnesRun - *(_DWORD *)v118) << 9;
        v122 = v13;
        goto LABEL_165;
      }
      if ( v10 <= 7 )
      {
        v81 = 154;
        if ( _bittest(&v81, v10) )
LABEL_165:
          v174 = 1;
      }
    }
    CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
    v88 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)((char *)VhdPerProcData
                                                                   + 192 * CurrentProcessorNumber
                                                                   + 64));
    if ( !v88 )
    {
      if ( !VhdmpiAcquireReserveResource(a2, (struct _VHD1_BACKING_STORE *)v11, 7u) )
        goto LABEL_110;
      v88 = *(_QWORD **)(v11 + 8776);
    }
    *v88 = a2;
    v88[1] = v11;
    *((_BYTE *)v88 + 28) = 0;
    v88[2] = 0;
    *((_DWORD *)v88 + 6) = CurrentProcessorNumber;
    VhdmpiVhd1IncrementSrbPartRefCount((struct VHD_SRB_PART *)v4);
    if ( v111 <= 7 )
    {
      v89 = 146;
      if ( _bittest(&v89, v111) )
      {
        if ( !*((_BYTE *)a2 + 83) )
        {
LABEL_176:
          if ( v111 == 8 )
          {
            v91 = VhdmpiVhd1HandleFileTrimSubIo((struct _VHD1_MAIN_IO_CONTEXT *)v88, v129, v13);
          }
          else
          {
            v92 = (unsigned int)(v136 - *(_DWORD *)(v4 + 88));
            LOBYTE(v110) = v13 >= *((_DWORD *)a2 + 14) - *v137;
            v91 = VhdmpiSrbPartReportPresent(v4, v92, v13, v11, v129, VhdmpiMainIoCompletion, v88, v110);
          }
          if ( v91 != 259 )
            VhdmpiMainIoCompletion((struct VHD_SRB_PART *)v4, v88, v91, 0);
          goto LABEL_181;
        }
        if ( VhdmpiVhd1IsAnyPortionOfSrbRangeDefinedByAnyParent((struct _VHD1_BACKING_STORE *)v11, a2) )
        {
          VhdmpiSectorBitmapIncPrerequisiteIoCount(v112);
          v90 = v125;
          _InterlockedAdd((volatile signed __int32 *)v125 + 70, 1u);
          *((_BYTE *)v88 + 28) = 1;
          v88[2] = v90;
        }
      }
    }
    if ( *((_BYTE *)a2 + 83) )
    {
      VhdmpiSectorBitmapDecPrerequisiteIoCount(v112, 259, 0);
      *((_BYTE *)a2 + 83) = 0;
    }
    goto LABEL_176;
  }
  VhdmpiVhd1IncrementSrbPartRefCount((struct VHD_SRB_PART *)v4);
  *((_DWORD *)a2 + 15) = *((_DWORD *)a2 + 14);
  v18 = VhdmpiProcessScsiPassthrough(v11, v17, VhdmpiVhd1ScsiPassthroughComplete, v4);
  LbaStatus = 0;
  if ( v18 < 0 )
    LbaStatus = v18;
LABEL_207:
  v103 = v111;
  *v166 = v112;
  *v167 = v125;
  *v168 = v119;
  *v169 = v120;
  *v170 = v13;
  if ( v8 )
    VhdmpiVhd1DecrementSrbPartRefCount((struct VHD_SRB_PART *)v4);
  if ( (unsigned int)dword_1400876D0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
    TraceEvents(
      "VhdmpiProcessSrbRange",
      0x3C36u,
      5u,
      8u,
      "VhdmpiProcessSrbRange: SrbPart=0x%p leaving (0x%08x)",
      (const void *)v4,
      LbaStatus);
  if ( LbaStatus < 0 && !_interlockedbittestandset((volatile signed __int32 *)a1 + 86, 0) )
  {
    if ( v103 == 8 && LbaStatus == -1073741637 )
    {
      if ( (Microsoft_Windows_VHDMPEnableBits & 8) != 0 )
      {
        *(_DWORD *)v109 = -1073741637;
        v104 = 8;
        v105 = VhdIoErrorNonCritical;
LABEL_220:
        McTemplateK0qzq_EtwWriteTransfer(
          (_DWORD)a1,
          (_DWORD)v105,
          v15,
          v104,
          *(_QWORD *)(*((_QWORD *)a1 + 18) + 120LL),
          v109[0]);
      }
    }
    else if ( (Microsoft_Windows_VHDMPEnableBits & 4) != 0 )
    {
      *(_DWORD *)v109 = LbaStatus;
      v104 = v103;
      v105 = VhdIoErrorCritical;
      goto LABEL_220;
    }
  }
  return (unsigned int)LbaStatus;
}

```

## disassembly

```asm
0x14001c4a0  mov     rax, rsp
0x14001c4a3  mov     [rax+10h], rdx
0x14001c4a7  mov     [rax+8], rcx
0x14001c4ab  push    rbx
0x14001c4ac  push    rsi
0x14001c4ad  push    rdi
0x14001c4ae  push    r12
0x14001c4b0  push    r13
0x14001c4b2  push    r14
0x14001c4b4  push    r15
0x14001c4b6  sub     rsp, 200h
0x14001c4bd  mov     rdi, rdx
0x14001c4c0  mov     rbx, rcx
0x14001c4c3  xor     esi, esi
0x14001c4c5  mov     [rax-130h], rsi
0x14001c4cc  mov     [rax-108h], rsi
0x14001c4d3  mov     [rsp+238h+var_1D0], sil
0x14001c4d8  mov     r13, [rdx]
0x14001c4db  mov     [rsp+238h+var_100], r13
0x14001c4e3  mov     r11, [r13+0]
0x14001c4e7  mov     [rsp+238h+var_190], r11
0x14001c4ef  mov     [rsp+238h+var_C8], r11
0x14001c4f7  mov     eax, cs:dword_1400876D0
0x14001c4fd  cmp     eax, 5
0x14001c500  jbe     short loc_14001C55F
0x14001c502  lea     edx, [rsi+8]
0x14001c505  lea     rcx, dword_1400876D0
0x14001c50c  call    _tlgKeywordOn
0x14001c511  test    al, al
0x14001c513  jz      short loc_14001C55F
0x14001c515  mov     edx, 3577h; int
0x14001c51a  mov     eax, [r11+3Ch]
0x14001c51e  mov     [rsp+238h+var_1F8], eax
0x14001c522  mov     eax, [rdi+38h]
0x14001c525  mov     dword ptr [rsp+238h+var_200], eax
0x14001c529  mov     rax, [rdi+30h]
0x14001c52d  mov     [rsp+238h+var_208], rax
0x14001c532  mov     qword ptr [rsp+238h+var_210], rdi; char
0x14001c537  lea     rax, aVhdmpiprocesss_1; "VhdmpiProcessSrbRange: Enter... SrbRang"...
0x14001c53e  mov     [rsp+238h+var_218], rax; char *
0x14001c543  lea     r9d, [rsi+8]; int
0x14001c547  lea     r8d, [rsi+5]; int
0x14001c54b  lea     rcx, aVhdmpiprocesss_3; "VhdmpiProcessSrbRange"
0x14001c552  call    TraceEvents
0x14001c557  mov     r11, [rsp+238h+var_190]
0x14001c55f  mov     rax, [r11]
0x14001c562  mov     ecx, [rax+860h]
0x14001c568  mov     eax, [r11+3Ch]
0x14001c56c  mov     r15d, 1
0x14001c572  test    r15b, cl
0x14001c575  jz      short loc_14001C586
0x14001c577  cmp     eax, 7
0x14001c57a  ja      short loc_14001C586
0x14001c57c  mov     edx, 92h
0x14001c581  bt      edx, eax
0x14001c584  jb      short loc_14001C590
0x14001c586  test    cl, 4
0x14001c589  jz      short loc_14001C5A9
0x14001c58b  cmp     eax, 8
0x14001c58e  jnz     short loc_14001C5A9
0x14001c590  mov     r8d, [rdi+3Ch]
0x14001c594  mov     edx, 2
0x14001c599  mov     rcx, r11
0x14001c59c  call    VhdmpiMapAndWriteSrbToTraceFile
0x14001c5a1  mov     r11, [rsp+238h+var_190]
0x14001c5a9  mov     edx, [r11+3Ch]
0x14001c5ad  mov     [rsp+238h+var_1E8], edx
0x14001c5b1  mov     [rsp+238h+var_174], edx
0x14001c5b8  lea     rcx, [rdi+8]
0x14001c5bc  mov     r14, [rcx]
0x14001c5bf  mov     [rsp+238h+var_F0], r14
0x14001c5c7  lea     rax, [rdi+20h]
0x14001c5cb  mov     [rsp+238h+var_60], rax
0x14001c5d3  mov     r10, [rax]
0x14001c5d6  mov     [rsp+238h+var_1E0], r10
0x14001c5db  mov     [rsp+238h+var_168], r10
0x14001c5e3  lea     rax, [rdi+40h]
0x14001c5e7  mov     [rsp+238h+var_40], rax
0x14001c5ef  mov     r12d, [rax]
0x14001c5f2  mov     [rsp+238h+var_1B0], r12d
0x14001c5fa  lea     rax, [rdi+28h]
0x14001c5fe  mov     [rsp+238h+var_58], rax
0x14001c606  mov     rax, [rax]
0x14001c609  mov     [rsp+238h+var_1A0], rax
0x14001c611  mov     [rsp+238h+var_160], rax
0x14001c619  lea     rax, [rdi+44h]
0x14001c61d  mov     [rsp+238h+var_50], rax
0x14001c625  mov     eax, [rax]
0x14001c627  mov     [rsp+238h+var_1BC], eax
0x14001c62b  mov     [rsp+238h+var_1A8], eax
0x14001c632  lea     rax, [rdi+48h]
0x14001c636  mov     [rsp+238h+var_48], rax
0x14001c63e  mov     eax, [rax]
0x14001c640  mov     [rsp+238h+var_1B8], eax
0x14001c647  mov     [rsp+238h+var_1AC], eax
0x14001c64e  cmp     edx, 8
0x14001c651  jnz     short loc_14001C67D
0x14001c653  cmp     dword ptr [r14+7C4h], 2
0x14001c65b  jz      short loc_14001C67D
0x14001c65d  mov     eax, [rdi+38h]
0x14001c660  mov     [rdi+3Ch], eax
0x14001c663  mov     ebx, 0C00000BBh
0x14001c668  xor     r9d, r9d
0x14001c66b  xor     edx, edx
0x14001c66d  mov     r8d, ebx
0x14001c670  mov     rcx, r13
0x14001c673  call    ?VhdmpiVhd1AccumulateStatusSrbPart@@YAXPEAUVHD_SRB_PART@@PEAU_VHD1_BACKING_STORE@@JW4_VHDMP_IO_STATUS_SEVERITY@@@Z; VhdmpiVhd1AccumulateStatusSrbPart(VHD_SRB_PART *,_VHD1_BACKING_STORE *,long,_VHDMP_IO_STATUS_SEVERITY)
0x14001c678  jmp     loc_14001DB9A
0x14001c67d  cmp     edx, 9
0x14001c680  jnz     short loc_14001C6E5
0x14001c682  mov     dword ptr [rsp+238h+arg_8], esi
0x14001c689  mov     r8, [r11+18h]
0x14001c68d  mov     r9d, [r11+40h]
0x14001c691  shr     r9d, 9
0x14001c695  and     r9b, r15b
0x14001c698  lea     rax, [rsp+238h+arg_8]
0x14001c6a0  mov     qword ptr [rsp+238h+var_210], rax
0x14001c6a5  mov     rax, [r8+18h]
0x14001c6a9  mov     [rsp+238h+var_218], rax
0x14001c6ae  mov     r8d, [r8+10h]
0x14001c6b2  mov     rdx, [r13+58h]
0x14001c6b6  mov     rcx, r14
0x14001c6b9  call    VhdmpiProcessGetLbaStatus
0x14001c6be  mov     ebx, eax
0x14001c6c0  test    eax, eax
0x14001c6c2  js      short loc_14001C6DA
0x14001c6c4  mov     r10, [rsp+238h+var_190]
0x14001c6cc  mov     rdx, [r10+18h]
0x14001c6d0  mov     ecx, dword ptr [rsp+238h+arg_8]
0x14001c6d7  mov     [rdx+10h], ecx
0x14001c6da  mov     ecx, [rdi+38h]
0x14001c6dd  mov     [rdi+3Ch], ecx
0x14001c6e0  jmp     loc_14001DB9A
0x14001c6e5  cmp     edx, 0Bh
0x14001c6e8  jnz     short loc_14001C71B
0x14001c6ea  mov     rcx, r13; struct VHD_SRB_PART *
0x14001c6ed  call    ?VhdmpiVhd1IncrementSrbPartRefCount@@YAXPEAUVHD_SRB_PART@@@Z; VhdmpiVhd1IncrementSrbPartRefCount(VHD_SRB_PART *)
0x14001c6f2  mov     r8d, [rdi+38h]
0x14001c6f6  mov     [rdi+3Ch], r8d
0x14001c6fa  mov     r9, r13
0x14001c6fd  lea     r8, ?VhdmpiVhd1ScsiPassthroughComplete@@YAXJPEAX@Z; VhdmpiVhd1ScsiPassthroughComplete(long,void *)
0x14001c704  mov     rdx, r11
0x14001c707  mov     rcx, r14
0x14001c70a  call    VhdmpiProcessScsiPassthrough
0x14001c70f  mov     ebx, esi
0x14001c711  test    eax, eax
0x14001c713  cmovs   ebx, eax
0x14001c716  jmp     loc_14001DB9A
0x14001c71b  mov     [rsp+238h+var_B8], rdi
0x14001c723  mov     [rsp+238h+var_78], rdi
0x14001c72b  mov     [rsp+238h+var_B0], rbx
0x14001c733  mov     [rsp+238h+var_140], r13
0x14001c73b  or      r8d, 0FFFFFFFFh
0x14001c73f  mov     qword ptr [rsp+238h+var_1C8], r8
0x14001c744  mov     [rsp+238h+arg_10], sil
0x14001c74c  mov     [rsp+238h+var_68], rcx
0x14001c754  jmp     short loc_14001C75F
0x14001c756  mov     r10, [rsp+238h+var_1E0]
0x14001c75b  mov     edx, [rsp+238h+var_1E8]
0x14001c75f  mov     al, sil
0x14001c762  mov     [rsp+238h+arg_18], al
0x14001c769  mov     [rsp+238h+var_1CF], al
0x14001c76d  lea     rax, [rdi+3Ch]
0x14001c771  mov     [rsp+238h+var_150], rax
0x14001c779  mov     eax, [rax]
0x14001c77b  mov     [rsp+238h+var_148], rax
0x14001c783  mov     rcx, [rdi+30h]
0x14001c787  add     rax, rcx
0x14001c78a  or      r9, 0FFFFFFFFFFFFFFFFh
0x14001c78e  cmp     rax, rcx
0x14001c791  cmovnb  r9, rax
0x14001c795  mov     [rsp+238h+var_158], r9
0x14001c79d  mov     [rsp+238h+var_138], r9
0x14001c7a5  sbb     ebx, ebx
0x14001c7a7  and     ebx, 0C0000095h
0x14001c7ad  cmp     rax, rcx
0x14001c7b0  jnb     short loc_14001C7C7
0x14001c7b2  xor     r9d, r9d
0x14001c7b5  xor     edx, edx
0x14001c7b7  mov     r8d, ebx
0x14001c7ba  mov     rcx, r13
0x14001c7bd  call    ?VhdmpiVhd1AccumulateStatusSrbPart@@YAXPEAUVHD_SRB_PART@@PEAU_VHD1_BACKING_STORE@@JW4_VHDMP_IO_STATUS_SEVERITY@@@Z; VhdmpiVhd1AccumulateStatusSrbPart(VHD_SRB_PART *,_VHD1_BACKING_STORE *,long,_VHDMP_IO_STATUS_SEVERITY)
0x14001c7c2  jmp     loc_14001D9F2
0x14001c7c7  lea     rax, [r14+7C4h]
0x14001c7ce  mov     [rsp+238h+var_C0], rax
0x14001c7d6  cmp     dword ptr [rax], 2
0x14001c7d9  jnz     short loc_14001C7FE
0x14001c7db  mov     dword ptr [rsp+238h+var_1C0], esi
0x14001c7df  mov     [rsp+238h+var_1B4], esi
0x14001c7e6  mov     [rsp+238h+var_188], r9
0x14001c7ee  mov     [rsp+238h+arg_18], r15b
0x14001c7f6  mov     r9, r14
0x14001c7f9  jmp     loc_14001D6A3
0x14001c7fe  mov     al, sil
0x14001c801  mov     [rsp+238h+var_1D4], eax
0x14001c805  mov     [rsp+238h+var_1D8], al
0x14001c809  mov     r9d, [r14+9A8h]
0x14001c810  xor     edx, edx
0x14001c812  mov     rax, [rsp+238h+var_158]
0x14001c81a  div     r9
0x14001c81d  mov     r10, rdx
0x14001c820  mov     [rsp+238h+var_F8], rdx
0x14001c828  mov     qword ptr [rsp+238h+var_1C8], rax
0x14001c82d  mov     [rsp+238h+var_178], eax
0x14001c834  mov     [rsp+238h+var_170], edx
0x14001c83b  sub     r9d, edx
0x14001c83e  mov     [rsp+238h+var_120], r9
0x14001c846  cmp     r12d, r9d
0x14001c849  jbe     loc_14001C90A
0x14001c84f  test    dword ptr [r11+40h], 100h
0x14001c857  jnz     loc_14001C8E4
0x14001c85d  lea     rax, [rdi+38h]
0x14001c861  mov     [rsp+238h+var_128], rax
0x14001c869  sub     r12d, r9d
0x14001c86c  mov     r8d, [rax]
0x14001c86f  sub     r8d, dword ptr [rsp+238h+var_148]
0x14001c877  sub     r8d, r9d; unsigned int
0x14001c87a  mov     edx, r9d
0x14001c87d  add     rdx, [rsp+238h+var_158]; unsigned __int64
0x14001c885  mov     dword ptr [rsp+238h+var_218], r12d; unsigned int
0x14001c88a  mov     r9, r14; struct _VHD1_BACKING_STORE *
0x14001c88d  mov     rcx, r13; struct VHD_SRB_PART *
0x14001c890  call    ?VhdmpiCreateSrbRange@@YAPEAU_VHD_SRB_RANGE@@PEAUVHD_SRB_PART@@_KKPEAU_VHD1_BACKING_STORE@@K@Z; VhdmpiCreateSrbRange(VHD_SRB_PART *,unsigned __int64,ulong,_VHD1_BACKING_STORE *,ulong)
0x14001c895  mov     rdx, rax
0x14001c898  mov     rcx, r13; struct VHD_SRB_PART *
0x14001c89b  call    ?VhdmpiVhd1IncrementSrbPartRefCount@@YAXPEAUVHD_SRB_PART@@@Z; VhdmpiVhd1IncrementSrbPartRefCount(VHD_SRB_PART *)
0x14001c8a0  cmp     [r13+6Fh], sil
0x14001c8a4  jnz     short loc_14001C8AB
0x14001c8a6  mov     byte ptr [r13+6Fh], 2
0x14001c8ab  add     rdx, 10h; ListEntry
0x14001c8af  mov     rcx, [rsp+238h+var_B0]
0x14001c8b7  add     rcx, 480h; ListHead
0x14001c8be  call    cs:__imp_ExpInterlockedPushEntrySList
0x14001c8c5  nop     dword ptr [rax+rax+00h]
0x14001c8ca  mov     r9, [rsp+238h+var_120]
0x14001c8d2  mov     rdx, [rsp+238h+var_128]
0x14001c8da  mov     r10, [rsp+238h+var_F8]
0x14001c8e2  jmp     short loc_14001C8F0
0x14001c8e4  mov     rdx, [rsp+238h+var_B8]
0x14001c8ec  add     rdx, 38h ; '8'
0x14001c8f0  mov     r12d, r9d
0x14001c8f3  mov     [rsp+238h+var_1B0], r9d
0x14001c8fb  mov     rax, [rsp+238h+var_150]
0x14001c903  mov     ecx, [rax]
0x14001c905  add     ecx, r9d
0x14001c908  mov     [rdx], ecx
0x14001c90a  mov     r8d, r10d
0x14001c90d  shr     r8d, 9
0x14001c911  mov     dword ptr [rsp+238h+var_1C0], r8d
0x14001c916  mov     [rsp+238h+var_E8], r8d
0x14001c91e  lea     r9d, [r10+r12]
0x14001c922  shr     r9d, 9
0x14001c926  mov     [rsp+238h+var_1B4], r9d
0x14001c92e  mov     [rsp+238h+var_10C], r9d
0x14001c936  mov     eax, cs:dword_1400876D0
0x14001c93c  cmp     eax, 5
0x14001c93f  jbe     short loc_14001C990
0x14001c941  mov     edx, 8
0x14001c946  lea     rcx, dword_1400876D0
0x14001c94d  call    _tlgKeywordOn
0x14001c952  test    al, al
0x14001c954  jz      short loc_14001C990
0x14001c956  mov     ecx, 3660h
0x14001c95b  mov     [rsp+238h+var_1F8], r9d
0x14001c960  mov     dword ptr [rsp+238h+var_200], r8d
0x14001c965  mov     dword ptr [rsp+238h+var_208], r12d
0x14001c96a  mov     dword ptr [rsp+238h+var_210], r10d; char
0x14001c96f  lea     rax, aVhdmpiprocesss_6; "VhdmpiProcessSrbRange: BlockRelativeByt"...
0x14001c976  mov     [rsp+238h+var_218], rax; char *
0x14001c97b  mov     r9d, edx; int
0x14001c97e  lea     r8d, [rdx-3]; int
0x14001c982  mov     edx, ecx; int
0x14001c984  lea     rcx, aVhdmpiprocesss_3; "VhdmpiProcessSrbRange"
0x14001c98b  call    TraceEvents
0x14001c990  mov     r8, [r14+0EE8h]
0x14001c997  mov     [rsp+238h+var_180], r8
0x14001c99f  mov     ecx, [rsp+238h+var_1E8]
0x14001c9a3  mov     r9d, 92h
0x14001c9a9  mov     rdx, qword ptr [rsp+238h+var_1C8]
0x14001c9ae  cmp     ecx, 7
0x14001c9b1  ja      loc_14001CAA6
0x14001c9b7  bt      r9d, ecx
0x14001c9bb  jnb     loc_14001CAA6
0x14001c9c1  cmp     [rdi+50h], sil
0x14001c9c5  jnz     loc_14001CAA6
0x14001c9cb  mov     eax, edx
0x14001c9cd  mov     [rsp+238h+var_148], rax
0x14001c9d5  cmp     dword ptr [r8+rax*4], 0FFFFFFFFh
0x14001c9da  jnz     loc_14001CAA6
0x14001c9e0  mov     rdx, rdi; struct _VHD_SRB_RANGE *
0x14001c9e3  mov     rcx, r14; struct _VHD1_BACKING_STORE *
0x14001c9e6  call    ?VhdmpiVhd1IsAnyPortionOfSrbRangeDefinedByAnyParent@@YAEPEAU_VHD1_BACKING_STORE@@PEAU_VHD_SRB_RANGE@@@Z; VhdmpiVhd1IsAnyPortionOfSrbRangeDefinedByAnyParent(_VHD1_BACKING_STORE *,_VHD_SRB_RANGE *)
0x14001c9eb  test    al, al
0x14001c9ed  jnz     short loc_14001CA6A
0x14001c9ef  mov     edx, [rdi+3Ch]
0x14001c9f2  sub     edx, [r13+58h]
0x14001c9f6  add     edx, [rdi+30h]
0x14001c9f9  lea     r9, [rsp+238h+var_1D0]
0x14001c9fe  mov     r8d, r12d
0x14001ca01  mov     rcx, r13; struct VHD_SRB_PART *
  ... truncated ...
```
