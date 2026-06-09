# UdfCreateLink

- ea: `0x140004514`
- end: `0x1400050d2`
- name: `UdfCreateLink`
- size: `3006`
- prototype: `void __fastcall(__int64, __int64, __int64, int, int, char, char, unsigned __int16 *, _QWORD *, char)`
- caller_count: `3`
- callee_count: `32`
- tags: `file_ops, installer_update`

## callers

- `0x140031144`
- `0x140033548`
- `0x140034450`

## callees

- `0x140004514`
- `0x1400050d8`
- `0x140005e80`
- `0x14000653c`
- `0x140009014`
- `0x140009450`
- `0x14000b2b0`
- `0x14000b648`
- `0x14000ca10`
- `0x14000cb6c`
- `0x14000eb04`
- `0x14000eda0`
- `0x1400103d8`
- `0x14001093c`
- `0x140011c30`
- `0x1400121e0`
- `0x140012308`
- `0x140012cc8`
- `0x1400137cc`
- `0x140016cc8`
- `0x14001758c`
- `0x1400193f0`
- `0x1400195a4`
- `0x14001bd80`
- `0x14001c080`
- `0x140041110`
- `0x140041860`
- `0x14004ce50`
- `0x140055f00`
- `0x1400567cc`
- `0x140059090`
- `0x1400591e0`

## import_xrefs

- `ntoskrnl!FsRtlLookupLargeMcbEntry` at `0x140004d42`
- `ntoskrnl!FsRtlLookupLargeMcbEntry` at `0x140004d7d`
- `ntoskrnl!FsRtlLookupLargeMcbEntry` at `0x140004f05`
- `ntoskrnl!FsRtlLookupLargeMcbEntry` at `0x140004f4f`
- `ntoskrnl!FsRtlLookupLargeMcbEntry` at `0x140004d42`
- `ntoskrnl!FsRtlLookupLargeMcbEntry` at `0x140004d7d`
- `ntoskrnl!FsRtlLookupLargeMcbEntry` at `0x140004f05`
- `ntoskrnl!FsRtlLookupLargeMcbEntry` at `0x140004f4f`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400050b2`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001ccab`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400050b2`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001ccab`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000487d`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000487d`
- `ntoskrnl!CcSetFileSizes` at `0x140004b3d`
- `ntoskrnl!CcSetFileSizes` at `0x140004b3d`
- `ntoskrnl!CcSetDirtyPinnedData` at `0x140004e1d`
- `ntoskrnl!CcSetDirtyPinnedData` at `0x140004e1d`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400047a5`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400048d9`
- `ntoskrnl!ExAcquireFastMutex` at `0x140004992`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400047a5`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400048d9`
- `ntoskrnl!ExAcquireFastMutex` at `0x140004992`
- `ntoskrnl!ExReleaseFastMutex` at `0x140004893`
- `ntoskrnl!ExReleaseFastMutex` at `0x140004a66`
- `ntoskrnl!ExReleaseFastMutex` at `0x140004b16`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000509b`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001cc8d`
- `ntoskrnl!ExReleaseFastMutex` at `0x140004893`
- `ntoskrnl!ExReleaseFastMutex` at `0x140004a66`
- `ntoskrnl!ExReleaseFastMutex` at `0x140004b16`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000509b`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001cc8d`

## pseudocode

```c
void __fastcall UdfCreateLink(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        int a5,
        char a6,
        char a7,
        unsigned __int16 *a8,
        _QWORD *a9,
        char a10)
{
  __int64 v14; // r14
  char v15; // bl
  char v16; // r12
  int v17; // r9d
  unsigned int v18; // eax
  unsigned int v19; // r15d
  __int64 v20; // rcx
  int v21; // edx
  unsigned int v22; // r8d
  size_t v23; // r13
  __int64 v24; // r15
  size_t v25; // r12
  __int64 v26; // r15
  signed __int64 v27; // rcx
  __int64 v28; // r9
  unsigned int v29; // ebx
  __int64 v30; // r15
  _DWORD *v31; // r12
  char v32; // al
  unsigned __int64 v33; // r9
  unsigned __int64 v34; // rax
  __int64 v35; // r8
  int v36; // edx
  __int64 v37; // r15
  unsigned int v38; // r13d
  __int64 v39; // rcx
  int v40; // eax
  __int64 v41; // r8
  bool v42; // zf
  char v43; // r15
  unsigned __int16 v44; // cx
  __int64 v45; // rcx
  unsigned int v46; // r12d
  char v47; // r15
  int v48; // edx
  unsigned int v49; // r8d
  char *v50; // rcx
  char *v51; // rbx
  __int64 v52; // rcx
  __int64 v53; // r8
  __int64 v54; // rcx
  _DWORD *v55; // rbx
  __int64 v56; // r8
  int v57; // edx
  int v58; // ecx
  __int64 *v59; // rax
  __int64 v60; // rcx
  __int64 v61; // r8
  int SectorCountFromStartingLbn; // [rsp+28h] [rbp-1A0h]
  char v63; // [rsp+50h] [rbp-178h] BYREF
  char v64; // [rsp+51h] [rbp-177h]
  char v65; // [rsp+52h] [rbp-176h]
  __int64 Lbn; // [rsp+58h] [rbp-170h] BYREF
  unsigned int v67; // [rsp+60h] [rbp-168h] BYREF
  unsigned int v68; // [rsp+64h] [rbp-164h] BYREF
  unsigned int v69; // [rsp+68h] [rbp-160h]
  unsigned int v70; // [rsp+6Ch] [rbp-15Ch] BYREF
  unsigned int v71; // [rsp+70h] [rbp-158h] BYREF
  int v72; // [rsp+74h] [rbp-154h]
  size_t Size; // [rsp+78h] [rbp-150h]
  int v74; // [rsp+80h] [rbp-148h]
  __int64 v75; // [rsp+88h] [rbp-140h] BYREF
  unsigned int v76; // [rsp+90h] [rbp-138h] BYREF
  size_t v77; // [rsp+98h] [rbp-130h] BYREF
  int v78; // [rsp+A0h] [rbp-128h]
  int v79; // [rsp+A4h] [rbp-124h]
  unsigned int v80; // [rsp+A8h] [rbp-120h]
  __int64 v81; // [rsp+B0h] [rbp-118h] BYREF
  _OWORD v82[2]; // [rsp+B8h] [rbp-110h] BYREF
  __int64 v83; // [rsp+D8h] [rbp-F0h]
  char *v84; // [rsp+E0h] [rbp-E8h]
  void *v85[27]; // [rsp+F0h] [rbp-D8h] BYREF

  v14 = *(_QWORD *)(a1 + 16);
  v69 = (*(_DWORD *)(v14 + 48) >> 26) & 1;
  v68 = 0;
  v70 = 0;
  v71 = 0;
  v67 = 0;
  v74 = 0;
  Lbn = 0;
  v75 = 0;
  v63 = 0;
  v15 = 0;
  v64 = 0;
  v65 = 0;
  v16 = 0;
  memset(v82, 0, sizeof(v82));
  v83 = 0;
  v76 = 0;
  v81 = 0;
  memset(v85, 0, 0x98u);
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x10000000) != 0 )
  {
    WPP_SF_qqD(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
      11,
      WPP_3e271ebed6f63f8fe36d0f7ec1e80eae_Traceguids,
      a2,
      a3,
      a4);
  }
  v82[0] = 0;
  v18 = *a8;
  if ( a10 )
    v18 >>= 1;
  v19 = v18 + 1;
  Size = *(_QWORD *)(a2 + 552);
  v77 = Size;
  if ( Size == -1 )
  {
LABEL_16:
    v23 = Size;
  }
  else
  {
    UdfLookupInitialDirEntry(a1, a2, a9, &v77, 0, 0);
    while ( 1 )
    {
      v20 = a9[4];
      if ( (*(_BYTE *)(v20 + 18) & 4) != 0 )
      {
        if ( !*(_QWORD *)(a2 + 552) )
          *(_QWORD *)(a2 + 552) = a9[6];
        v21 = *(unsigned __int8 *)(v20 + 19);
        if ( v21 == v19 )
          break;
        v22 = v21 + *(unsigned __int16 *)(v20 + 36);
        if ( v22 == v19 || v22 >= v19 + 32 )
          break;
      }
      if ( !(unsigned __int8)UdfLookupNextDirEntry(a1, a2, (int)a9) )
        goto LABEL_16;
    }
    v74 = v21 + *(unsigned __int16 *)(v20 + 36) - v19;
    v78 = v74;
    UdfPrepareDirContextForModify(a1, a9, a2);
    v23 = a9[6];
    v77 = v23;
    v16 = 1;
  }
  if ( v16 )
  {
LABEL_68:
    v43 = 0;
    if ( !a3 )
    {
      LODWORD(v81) = a4;
      if ( *(_QWORD *)(v14 + 352) )
      {
        v44 = *(_WORD *)(*(_QWORD *)(v14 + 16) + 90LL);
      }
      else
      {
        v54 = *(_QWORD *)(v14 + 16);
        if ( (*(_DWORD *)(v14 + 48) & 0x4000000) != 0 )
          v44 = *(_WORD *)(v54 + 84);
        else
          v44 = *(_WORD *)(v54 + 92);
      }
      HIDWORD(v81) = v44;
    }
    v55 = (_DWORD *)(a2 + 212);
    if ( (*(_DWORD *)(a2 + 212) & 2) != 0 )
    {
      v56 = *(unsigned int *)(a2 + 184);
LABEL_107:
      Lbn = v56;
LABEL_108:
      if ( (*v55 & 2) != 0 || a6 )
      {
        v43 = 1;
        UdfPrepareModifyIcbForScb(a1, a2, v82);
        LODWORD(v56) = Lbn;
      }
      if ( a3 )
        v58 = *(_DWORD *)(*(_QWORD *)(a3 + 136) + 96LL);
      else
        v58 = a5;
      v59 = (__int64 *)(a3 + 184);
      if ( !a3 )
        v59 = &v81;
      LOBYTE(v17) = a6;
      UdfInitializeFid(a1, a9[4], v56, v17, a7, (__int64)v59, v58, v74, (__int64)a8, a10);
      UdfSetDirtyFid(a1, a9);
      UdfUpdateScbTimeStamps(v60, a2, 0);
      v15 = 0;
      v64 = 0;
      if ( v43 )
      {
        if ( a6 )
          ++*(_WORD *)(a2 + 500);
        LOBYTE(v61) = 1;
        UdfFinishModifyIcb(a1, v82, v61, a2);
        v64 = 0;
      }
      goto LABEL_120;
    }
    LODWORD(v56) = 0;
    Lbn = 0;
    if ( *(_QWORD *)(v14 + 352) )
      goto LABEL_108;
    if ( FsRtlLookupLargeMcbEntry(
           (PLARGE_MCB)(a2 + 264),
           (unsigned int)(v23 >> *(_DWORD *)(v14 + 72)),
           &Lbn,
           0,
           0,
           0,
           0) )
    {
      v57 = Lbn;
      if ( Lbn != -1 )
      {
LABEL_106:
        v56 = (unsigned int)(v57 - *(_DWORD *)(200LL * v69 + *(_QWORD *)(a1 + 16) + 656));
        goto LABEL_107;
      }
      v55 = (_DWORD *)(a2 + 212);
    }
    FsRtlLookupLargeMcbEntry((PLARGE_MCB)(a2 + 232), (unsigned int)(v23 >> *(_DWORD *)(v14 + 72)), &Lbn, 0, 0, 0, 0);
    v57 = Lbn;
    goto LABEL_106;
  }
  if ( !*(_QWORD *)(a2 + 552) )
    *(_QWORD *)(a2 + 552) = -1;
  v24 = (v19 + 41) & 0xFFFFFFFC;
  v72 = v24;
  v79 = v24;
  v25 = *(_QWORD *)(a2 + 32);
  Size = v25;
  v77 = v25;
  if ( (v25 & 3) != 0 )
    UdfRaiseStatusEx(a1, 3221225730LL, 0);
  UdfAcquireResource(a1, *(_QWORD *)(a2 + 16), 0, 0);
  v65 = 1;
  if ( !*(_QWORD *)(v14 + 352) && (*(_DWORD *)(v14 + 48) & 0x20000000) == 0 )
  {
    v26 = *(_QWORD *)(a2 + 32) + v24;
    v75 = v26;
    ExAcquireFastMutex(*(PFAST_MUTEX *)(a2 + 48));
    v15 = 1;
    v64 = 1;
    UdfGetBlocksNeeded(
      v14,
      a2,
      (unsigned int)&v75,
      (unsigned int)&v68,
      (__int64)&v70,
      (__int64)&v71,
      (__int64)&v67,
      (__int64)&v63);
    if ( v68 )
    {
      if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x10000000) != 0 )
      {
        WPP_SF_dd(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
          12,
          WPP_3e271ebed6f63f8fe36d0f7ec1e80eae_Traceguids,
          v70,
          *(_DWORD *)(a2 + 328));
      }
      v29 = v70;
      v30 = v69;
      UdfPrepareForAllocationChange(a1, v14, v69, v70);
      *(_DWORD *)(200 * v30 + v14 + 672) += v29;
      *(_QWORD *)(v14 + 1640) = 0;
      ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v14 + 1584));
      *(_DWORD *)(a2 + 328) += v29;
      ExReleaseFastMutex(*(PFAST_MUTEX *)(a2 + 48));
      v15 = 0;
      v64 = 0;
    }
    else
    {
      *(_QWORD *)(a2 + 304) = v26;
    }
    v31 = (_DWORD *)(v14 + 68);
    LODWORD(v24) = v72;
    goto LABEL_31;
  }
  LOBYTE(SectorCountFromStartingLbn) = 0;
  UdfSeqCacheReserveFileRegion(
    a1,
    a2,
    *(_DWORD *)(v14 + 76) & (unsigned int)(v25 >> *(_DWORD *)(v14 + 72)),
    *(unsigned int *)(v14 + 80),
    0,
    SectorCountFromStartingLbn,
    1);
  v35 = *(_QWORD *)(a2 + 32);
  v31 = (_DWORD *)(v14 + 68);
  v36 = *(_DWORD *)(v14 + 68);
  v27 = v36 - ((unsigned int)v35 & (v36 - 1));
  if ( (unsigned int)v27 > (unsigned int)v24 )
  {
    v27 = (unsigned int)(v27 - v24);
    if ( (unsigned int)v27 < 0x10 )
    {
      v74 = 32;
      v78 = 32;
      v24 = (unsigned int)(v24 + 32);
      v72 = v24;
      v79 = v24;
    }
  }
  if ( (*(_DWORD *)(v14 + 48) & 0x20000000) == 0 )
  {
    if ( (*(_DWORD *)(a2 + 212) & 2) != 0 )
    {
      v27 = (unsigned int)(v36 - *(_DWORD *)(a2 + 224));
      if ( v35 + (unsigned int)v24 > v27 )
      {
        v32 = 1;
        v63 = 1;
LABEL_32:
        if ( v32 )
        {
          LOBYTE(v28) = 1;
          UdfDeEmbedFileData(v27, a2, *(_QWORD *)(a2 + 504), v28);
        }
        if ( !v15 )
          ExAcquireFastMutex(*(PFAST_MUTEX *)(a2 + 48));
        *(_QWORD *)(a2 + 32) += (unsigned int)v24;
        v33 = *(_QWORD *)(a2 + 32);
        *(_QWORD *)(a2 + 40) = v33;
        if ( (*(_DWORD *)(a2 + 212) & 2) != 0 )
          v34 = v33;
        else
          v34 = ~(unsigned __int64)(unsigned int)(*v31 - 1) & (v33 + (unsigned int)(*v31 - 1));
        *(_QWORD *)(a2 + 24) = v34;
        if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x10000000) != 0 )
        {
          WPP_SF_qD(
            *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
            14,
            WPP_3e271ebed6f63f8fe36d0f7ec1e80eae_Traceguids,
            v33,
            *(_DWORD *)(a2 + 296));
        }
        ExReleaseFastMutex(*(PFAST_MUTEX *)(a2 + 48));
        v15 = 0;
        v64 = 0;
        if ( !_bittest((const signed __int32 *)(a2 + 212), 0x1Bu) )
          CcSetFileSizes(*(PFILE_OBJECT *)(a2 + 504), (PCC_FILE_SIZES)(a2 + 24));
        if ( (*(_DWORD *)(a2 + 212) & 2) != 0 )
        {
          UdfPrepareModifyIcbForScb(a1, a2, v82);
          v39 = *(_QWORD *)&v82[0];
          *(_QWORD *)(*(_QWORD *)&v82[0] + 56LL) = *(_QWORD *)(a2 + 32);
          v40 = *(_DWORD *)(a2 + 32);
          v41 = 266;
          v42 = *(_WORD *)v39 == 266;
          if ( *(_WORD *)v39 == 266 )
            *(_DWORD *)(v39 + 212) = v40;
          else
            *(_DWORD *)(v39 + 172) = v40;
          if ( v42 )
            *(_QWORD *)(v39 + 64) += (unsigned int)v24;
          LOBYTE(v41) = 1;
          UdfFinishModifyIcb(a1, v82, v41, a2);
          goto LABEL_66;
        }
        if ( *(_QWORD *)(v14 + 352) )
        {
LABEL_66:
          v23 = Size;
LABEL_67:
          UdfLookupInitialDirEntry(a1, a2, a9, &v77, 1, v72);
          goto LABEL_68;
        }
        v45 = v68;
        if ( v68 )
        {
          if ( (*(_DWORD *)(v14 + 48) & 0x20000000) == 0 )
          {
            UdfAllocateAtFileTail(a1, a2, v68, &v75);
            v46 = v67;
            if ( _bittest((const signed __int32 *)(a2 + 212), 0x1Bu) )
              UdfMarkRegionRecorded(v45, a2, v67 - v71, v67);
            goto LABEL_76;
          }
          if ( (int)UdfPowAllocateAtFileTail(v68, a2, v76, v68, &v75) < 0 )
            goto LABEL_120;
        }
        v46 = v67;
LABEL_76:
        if ( v63 )
        {
          UdfInitializeDirContext(v45, v85);
          v47 = 0;
          UdfMapViewOfDirectory(a1, a2, v85);
          if ( (*(_DWORD *)(a2 + 212) & 0x8000000) != 0 )
          {
            UdfPrepareModifyIcbForScb(a1, a2, v82);
            v47 = 1;
            v23 = Size;
            memmove(v85[0], (const void *)(*(_QWORD *)&v82[0] + *(unsigned int *)(a2 + 224)), (unsigned int)Size);
          }
          else
          {
            v23 = Size;
          }
          if ( !FsRtlLookupLargeMcbEntry((PLARGE_MCB)(a2 + 264), 0, &Lbn, 0, 0, 0, 0) || (v48 = Lbn, Lbn == -1) )
          {
            FsRtlLookupLargeMcbEntry((PLARGE_MCB)(a2 + 232), 0, &Lbn, 0, 0, 0, 0);
            v48 = Lbn;
          }
          v49 = v48 - *(_DWORD *)(200LL * v69 + *(_QWORD *)(a1 + 16) + 656);
          Lbn = v49;
          v50 = (char *)v85[0];
          v51 = (char *)v85[0];
          v84 = (char *)v85[0];
          while ( v51 < &v50[(unsigned int)v23] )
          {
            *((_DWORD *)v51 + 3) = v49;
            UdfUpdateChecksumAndCrc(v51, (*((unsigned __int16 *)v51 + 18) + 41 + (unsigned __int8)v51[19]) & 0xFFFFFFFC);
            v51 += (*((unsigned __int16 *)v51 + 18) + (unsigned __int8)v51[19] + 41LL) & 0xFFFFFFFFFFFFFFFCuLL;
            v84 = v51;
            v49 = Lbn;
            v50 = (char *)v85[0];
          }
          CcSetDirtyPinnedData(v85[1], 0);
          if ( v47 )
            UdfFinishModifyIcb(a1, v82, 0, a2);
          UdfCleanupDirContext(v52, v85);
        }
        else
        {
          v23 = Size;
        }
        v53 = v46 - v71;
        v80 = v46 - v71;
        if ( v46 != v71 )
        {
          v53 = (unsigned int)(v53 - 1);
          v80 = v53;
        }
        UdfUpdateAdsFromScb(a1, a2, v53, v46 - 1);
        goto LABEL_67;
      }
    }
LABEL_31:
    v32 = v63;
    goto LABEL_32;
  }
  ExAcquireFastMutex(*(PFAST_MUTEX *)(a2 + 48));
  v15 = 1;
  v64 = 1;
  v37 = *(_QWORD *)(a2 + 32) + v24;
  v75 = v37;
  UdfGetBlocksNeeded(v14, a2, (unsigned int)&v75, (unsigned int)&v68, 0, 0, (__int64)&v67, (__int64)&v63);
  v70 = 0;
  v38 = v68;
  v71 = v68;
  if ( !v68 )
  {
    *(_QWORD *)(a2 + 304) = v37;
    goto LABEL_49;
  }
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x10000000) != 0 )
  {
    WPP_SF_d(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 13, WPP_3e271ebed6f63f8fe36d0f7ec1e80eae_Traceguids);
  }
  if ( (int)UdfPowReserveMetaDataBlocks(a1, v14, v69, v38, (__int64)&v76) >= 0 )
  {
    ExReleaseFastMutex(*(PFAST_MUTEX *)(a2 + 48));
    v15 = 0;
    v64 = 0;
LABEL_49:
    LODWORD(v24) = v72;
    goto LABEL_31;
  }
LABEL_120:
  UdfUnpinView(a1, v82);
  if ( v15 )
    ExReleaseFastMutex(*(PFAST_MUTEX *)(a2 + 48));
  if ( v65 )
    ExReleaseResourceLite(*(PERESOURCE *)(a2 + 16));
}

```

## disassembly

```asm
0x140004514  mov     r11, rsp
0x140004517  mov     [r11+20h], r9d
0x14000451b  mov     [r11+18h], r8
0x14000451f  mov     [r11+10h], rdx
0x140004523  mov     [r11+8], rcx
0x140004527  push    rbx
0x140004528  push    rsi
0x140004529  push    rdi
0x14000452a  push    r12
0x14000452c  push    r13
0x14000452e  push    r14
0x140004530  push    r15
0x140004532  sub     rsp, 190h
0x140004539  mov     r13d, r9d
0x14000453c  mov     r15, r8
0x14000453f  mov     rdi, rdx
0x140004542  mov     rsi, rcx
0x140004545  mov     r14, [rcx+10h]
0x140004549  mov     eax, [r14+30h]
0x14000454d  shr     eax, 1Ah
0x140004550  and     eax, 1
0x140004553  mov     [rsp+1C8h+var_160], eax
0x140004557  xor     ecx, ecx
0x140004559  mov     [rsp+1C8h+var_164], ecx
0x14000455d  mov     [rsp+1C8h+var_15C], ecx
0x140004561  mov     [rsp+1C8h+var_158], ecx
0x140004565  mov     [rsp+1C8h+var_168], ecx
0x140004569  mov     [rsp+1C8h+var_148], ecx
0x140004570  mov     [rsp+1C8h+Lbn], rcx
0x140004575  mov     [r11-140h], rcx
0x14000457c  mov     [rsp+1C8h+var_178], cl
0x140004580  mov     bl, cl
0x140004582  mov     [rsp+1C8h+var_177], cl
0x140004586  mov     [rsp+1C8h+var_176], cl
0x14000458a  mov     r12b, cl
0x14000458d  xorps   xmm0, xmm0
0x140004590  xor     eax, eax
0x140004592  movups  [rsp+1C8h+var_110], xmm0
0x14000459a  movups  [rsp+1C8h+var_100], xmm0
0x1400045a2  mov     [r11-0F0h], rax
0x1400045a9  mov     [rsp+1C8h+var_138], ecx
0x1400045b0  mov     [r11-118h], rcx
0x1400045b7  xor     edx, edx; Val
0x1400045b9  mov     r8d, 98h; Size
0x1400045bf  lea     rcx, [r11-0D8h]; void *
0x1400045c6  call    memset
0x1400045cb  lea     rax, WPP_GLOBAL_Control
0x1400045d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400045d9  cmp     rcx, rax
0x1400045dc  jz      short loc_140004609
0x1400045de  test    dword ptr [rcx+2Ch], 10000000h
0x1400045e5  jz      short loc_140004609
0x1400045e7  mov     edx, 0Bh
0x1400045ec  mov     dword ptr [rsp+1C8h+SectorCountFromStartingLbn], r13d
0x1400045f1  mov     [rsp+1C8h+StartingLbn], r15
0x1400045f6  mov     r9, rdi
0x1400045f9  lea     r8, WPP_3e271ebed6f63f8fe36d0f7ec1e80eae_Traceguids
0x140004600  mov     rcx, [rcx+18h]
0x140004604  call    WPP_SF_qqD
0x140004609  xorps   xmm0, xmm0
0x14000460c  movdqu  [rsp+1C8h+var_110], xmm0
0x140004615  mov     rax, [rsp+1C8h+arg_38]
0x14000461d  movzx   eax, word ptr [rax]
0x140004620  xor     r13d, r13d
0x140004623  cmp     [rsp+1C8h+arg_48], r13b
0x14000462b  jz      short loc_14000462F
0x14000462d  shr     eax, 1
0x14000462f  lea     r15d, [rax+1]
0x140004633  mov     rax, [rdi+228h]
0x14000463a  mov     [rsp+1C8h+Size], rax
0x14000463f  mov     [rsp+1C8h+var_130], rax
0x140004647  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000464b  jz      loc_140004703
0x140004651  mov     dword ptr [rsp+1C8h+SectorCountFromStartingLbn], r13d; int
0x140004656  mov     byte ptr [rsp+1C8h+StartingLbn], r13b; char
0x14000465b  lea     r9, [rsp+1C8h+var_130]
0x140004663  mov     r13, [rsp+1C8h+arg_40]
0x14000466b  mov     r8, r13; int
0x14000466e  mov     rdx, rdi; int
0x140004671  mov     rcx, rsi; int
0x140004674  call    UdfLookupInitialDirEntry
0x140004679  mov     rcx, [r13+20h]
0x14000467d  test    byte ptr [rcx+12h], 4
0x140004681  jz      short loc_1400046ED
0x140004683  cmp     qword ptr [rdi+228h], 0
0x14000468b  jnz     short loc_140004698
0x14000468d  mov     rax, [r13+30h]
0x140004691  mov     [rdi+228h], rax
0x140004698  movzx   edx, byte ptr [rcx+13h]
0x14000469c  cmp     edx, r15d
0x14000469f  jz      short loc_1400046B7
0x1400046a1  movzx   r8d, word ptr [rcx+24h]
0x1400046a6  add     r8d, edx
0x1400046a9  cmp     r8d, r15d
0x1400046ac  jz      short loc_1400046B7
0x1400046ae  lea     eax, [r15+20h]
0x1400046b2  cmp     r8d, eax
0x1400046b5  jb      short loc_1400046ED
0x1400046b7  movzx   eax, word ptr [rcx+24h]
0x1400046bb  sub     eax, r15d
0x1400046be  add     eax, edx
0x1400046c0  mov     [rsp+1C8h+var_148], eax
0x1400046c7  mov     [rsp+1C8h+var_128], eax
0x1400046ce  mov     r8, rdi
0x1400046d1  mov     rdx, r13
0x1400046d4  mov     rcx, rsi
0x1400046d7  call    UdfPrepareDirContextForModify
0x1400046dc  mov     r13, [r13+30h]
0x1400046e0  mov     [rsp+1C8h+var_130], r13
0x1400046e8  mov     r12b, 1
0x1400046eb  jmp     short loc_140004708
0x1400046ed  mov     r8, r13; int
0x1400046f0  mov     rdx, rdi; int
0x1400046f3  mov     rcx, rsi; int
0x1400046f6  call    UdfLookupNextDirEntry
0x1400046fb  test    al, al
0x1400046fd  jnz     loc_140004679
0x140004703  mov     r13, [rsp+1C8h+Size]
0x140004708  test    r12b, r12b
0x14000470b  jnz     loc_140004BE0
0x140004711  cmp     qword ptr [rdi+228h], 0
0x140004719  jnz     short loc_140004726
0x14000471b  mov     qword ptr [rdi+228h], 0FFFFFFFFFFFFFFFFh
0x140004726  add     r15d, 29h ; ')'
0x14000472a  and     r15d, 0FFFFFFFCh
0x14000472e  mov     [rsp+1C8h+var_154], r15d
0x140004733  mov     [rsp+1C8h+var_124], r15d
0x14000473b  mov     r12, [rdi+20h]
0x14000473f  mov     [rsp+1C8h+Size], r12
0x140004744  mov     [rsp+1C8h+var_130], r12
0x14000474c  xor     r8d, r8d
0x14000474f  mov     rcx, rsi
0x140004752  test    r12b, 3
0x140004756  jz      short loc_140004762
0x140004758  mov     edx, 0C0000102h
0x14000475d  call    UdfRaiseStatusEx
0x140004762  xor     r9d, r9d
0x140004765  mov     rdx, [rdi+10h]
0x140004769  call    UdfAcquireResource
0x14000476e  mov     r13d, 1
0x140004774  mov     [rsp+1C8h+var_176], r13b
0x140004779  cmp     qword ptr [r14+160h], 0
0x140004781  jnz     loc_14000490A
0x140004787  test    dword ptr [r14+30h], 20000000h
0x14000478f  jnz     loc_14000490A
0x140004795  add     r15, [rdi+20h]
0x140004799  mov     [rsp+1C8h+var_140], r15
0x1400047a1  mov     rcx, [rdi+30h]; FastMutex
0x1400047a5  call    cs:__imp_ExAcquireFastMutex
0x1400047ac  nop     dword ptr [rax+rax+00h]
0x1400047b1  mov     bl, r13b
0x1400047b4  mov     [rsp+1C8h+var_177], bl
0x1400047b8  lea     rax, [rsp+1C8h+var_178]
0x1400047bd  mov     [rsp+1C8h+var_190], rax
0x1400047c2  lea     rax, [rsp+1C8h+var_168]
0x1400047c7  mov     [rsp+1C8h+Index], rax
0x1400047cc  lea     rax, [rsp+1C8h+var_158]
0x1400047d1  mov     [rsp+1C8h+SectorCountFromStartingLbn], rax
0x1400047d6  lea     rax, [rsp+1C8h+var_15C]
0x1400047db  mov     [rsp+1C8h+StartingLbn], rax
0x1400047e0  lea     r9, [rsp+1C8h+var_164]
0x1400047e5  lea     r8, [rsp+1C8h+var_140]
0x1400047ed  mov     rdx, rdi
0x1400047f0  mov     rcx, r14
0x1400047f3  call    UdfGetBlocksNeeded
0x1400047f8  cmp     [rsp+1C8h+var_164], 0
0x1400047fd  jz      loc_1400048A7
0x140004803  mov     rcx, cs:WPP_GLOBAL_Control
0x14000480a  lea     rax, WPP_GLOBAL_Control
0x140004811  cmp     rcx, rax
0x140004814  jz      short loc_140004842
0x140004816  test    dword ptr [rcx+2Ch], 10000000h
0x14000481d  jz      short loc_140004842
0x14000481f  lea     edx, [r13+0Bh]
0x140004823  mov     eax, [rdi+148h]
0x140004829  mov     dword ptr [rsp+1C8h+StartingLbn], eax
0x14000482d  mov     r9d, [rsp+1C8h+var_15C]
0x140004832  lea     r8, WPP_3e271ebed6f63f8fe36d0f7ec1e80eae_Traceguids
0x140004839  mov     rcx, [rcx+18h]
0x14000483d  call    WPP_SF_dd
0x140004842  mov     ebx, [rsp+1C8h+var_15C]
0x140004846  mov     r9d, ebx
0x140004849  mov     r15d, [rsp+1C8h+var_160]
0x14000484e  mov     r8d, r15d
0x140004851  mov     rdx, r14
0x140004854  mov     rcx, rsi
0x140004857  call    UdfPrepareForAllocationChange
0x14000485c  imul    rcx, r15, 0C8h
0x140004863  add     [rcx+r14+2A0h], ebx
0x14000486b  mov     qword ptr [r14+668h], 0
0x140004876  lea     rcx, [r14+630h]; FastMutex
0x14000487d  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140004884  nop     dword ptr [rax+rax+00h]
0x140004889  add     [rdi+148h], ebx
0x14000488f  mov     rcx, [rdi+30h]; FastMutex
0x140004893  call    cs:__imp_ExReleaseFastMutex
0x14000489a  nop     dword ptr [rax+rax+00h]
0x14000489f  xor     bl, bl
0x1400048a1  mov     [rsp+1C8h+var_177], bl
0x1400048a5  jmp     short loc_1400048AE
0x1400048a7  mov     [rdi+130h], r15
0x1400048ae  lea     r12, [r14+44h]
0x1400048b2  mov     r15d, [rsp+1C8h+var_154]
0x1400048b7  mov     al, [rsp+1C8h+var_178]
0x1400048bb  test    al, al
0x1400048bd  jz      short loc_1400048D1
0x1400048bf  mov     r9b, r13b
0x1400048c2  mov     r8, [rdi+1F8h]
0x1400048c9  mov     rdx, rdi
0x1400048cc  call    UdfDeEmbedFileData
0x1400048d1  test    bl, bl
0x1400048d3  jnz     short loc_1400048E5
0x1400048d5  mov     rcx, [rdi+30h]; FastMutex
0x1400048d9  call    cs:__imp_ExAcquireFastMutex
0x1400048e0  nop     dword ptr [rax+rax+00h]
0x1400048e5  mov     r13d, r15d
0x1400048e8  add     [rdi+20h], r13
0x1400048ec  mov     r9, [rdi+20h]
0x1400048f0  mov     [rdi+28h], r9
0x1400048f4  mov     eax, [rdi+0D4h]
0x1400048fa  test    al, 2
0x1400048fc  jz      loc_140004AC2
0x140004902  mov     rax, r9
0x140004905  jmp     loc_140004AD3
0x14000490a  mov     r8, r12
0x14000490d  mov     ecx, [r14+48h]
0x140004911  shr     r8, cl
0x140004914  and     r8d, [r14+4Ch]
0x140004918  mov     byte ptr [rsp+1C8h+Index], r13b
0x14000491d  mov     byte ptr [rsp+1C8h+SectorCountFromStartingLbn], 0
0x140004922  mov     [rsp+1C8h+StartingLbn], 0
0x14000492b  mov     r9d, [r14+50h]
0x14000492f  mov     rdx, rdi
0x140004932  mov     rcx, rsi
0x140004935  call    UdfSeqCacheReserveFileRegion
0x14000493a  mov     r8, [rdi+20h]
0x14000493e  lea     r12, [r14+44h]
0x140004942  mov     edx, [r12]
0x140004946  lea     eax, [rdx-1]
0x140004949  and     eax, r8d
0x14000494c  mov     ecx, edx
0x14000494e  sub     ecx, eax
0x140004950  cmp     ecx, r15d
0x140004953  jbe     short loc_140004980
0x140004955  sub     ecx, r15d
0x140004958  cmp     ecx, 10h
0x14000495b  jnb     short loc_140004980
0x14000495d  mov     eax, 20h ; ' '
0x140004962  mov     [rsp+1C8h+var_148], eax
0x140004969  mov     [rsp+1C8h+var_128], eax
0x140004970  add     r15d, eax
0x140004973  mov     [rsp+1C8h+var_154], r15d
0x140004978  mov     [rsp+1C8h+var_124], r15d
0x140004980  test    dword ptr [r14+30h], 20000000h
0x140004988  jz      loc_140004A91
0x14000498e  mov     rcx, [rdi+30h]; FastMutex
0x140004992  call    cs:__imp_ExAcquireFastMutex
0x140004999  nop     dword ptr [rax+rax+00h]
0x14000499e  mov     bl, r13b
0x1400049a1  mov     [rsp+1C8h+var_177], bl
0x1400049a5  add     r15, [rdi+20h]
0x1400049a9  mov     [rsp+1C8h+var_140], r15
0x1400049b1  lea     rax, [rsp+1C8h+var_178]
0x1400049b6  mov     [rsp+1C8h+var_190], rax
0x1400049bb  lea     rax, [rsp+1C8h+var_168]
0x1400049c0  mov     [rsp+1C8h+Index], rax
0x1400049c5  mov     [rsp+1C8h+SectorCountFromStartingLbn], 0
0x1400049ce  mov     [rsp+1C8h+StartingLbn], 0
0x1400049d7  lea     r9, [rsp+1C8h+var_164]
0x1400049dc  lea     r8, [rsp+1C8h+var_140]
0x1400049e4  mov     rdx, rdi
0x1400049e7  mov     rcx, r14
0x1400049ea  call    UdfGetBlocksNeeded
0x1400049ef  mov     [rsp+1C8h+var_15C], 0
0x1400049f7  mov     r13d, [rsp+1C8h+var_164]
0x1400049fc  mov     [rsp+1C8h+var_158], r13d
0x140004a01  test    r13d, r13d
0x140004a04  jz      short loc_140004A7A
0x140004a06  mov     rcx, cs:WPP_GLOBAL_Control
0x140004a0d  lea     rax, WPP_GLOBAL_Control
0x140004a14  cmp     rcx, rax
0x140004a17  jz      short loc_140004A3A
0x140004a19  test    dword ptr [rcx+2Ch], 10000000h
0x140004a20  jz      short loc_140004A3A
0x140004a22  mov     edx, 0Dh
0x140004a27  xor     r9d, r9d
0x140004a2a  lea     r8, WPP_3e271ebed6f63f8fe36d0f7ec1e80eae_Traceguids
0x140004a31  mov     rcx, [rcx+18h]
0x140004a35  call    WPP_SF_d
0x140004a3a  lea     rax, [rsp+1C8h+var_138]
0x140004a42  mov     [rsp+1C8h+StartingLbn], rax
0x140004a47  mov     r9d, r13d
0x140004a4a  mov     r8d, [rsp+1C8h+var_160]
0x140004a4f  mov     rdx, r14
0x140004a52  mov     rcx, rsi
0x140004a55  call    UdfPowReserveMetaDataBlocks
0x140004a5a  test    eax, eax
0x140004a5c  js      loc_140005083
0x140004a62  mov     rcx, [rdi+30h]; FastMutex
0x140004a66  call    cs:__imp_ExReleaseFastMutex
  ... truncated ...
```
