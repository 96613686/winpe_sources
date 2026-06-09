# UdfSetLinkInfo

- ea: `0x140033548`
- end: `0x140034409`
- name: `UdfSetLinkInfo`
- size: `3777`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `37`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140031f84`

## callees

- `0x140004514`
- `0x140005e80`
- `0x14000653c`
- `0x140008b0c`
- `0x14000a288`
- `0x14000a7e0`
- `0x14000c3e8`
- `0x14000cad4`
- `0x1400121e0`
- `0x140012298`
- `0x140012308`
- `0x140012a8c`
- `0x140012cc8`
- `0x140012d1c`
- `0x140013600`
- `0x14001662c`
- `0x140016f68`
- `0x14001758c`
- `0x140017ecc`
- `0x14001bc30`
- `0x14001c080`
- `0x14002cca0`
- `0x1400322f4`
- `0x140033548`
- `0x14003dec8`
- `0x1400401a0`
- `0x140041110`
- `0x140041900`
- `0x140041de0`
- `0x14004ce50`
- `0x14004fc70`
- `0x140050a8c`
- `0x140054fa0`
- `0x140055cd0`
- `0x1400567cc`
- `0x140056af8`
- `0x140057330`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x1400336b6`
- `ntoskrnl!ExRaiseStatus` at `0x1400336b6`
- `ntoskrnl!ExReleaseResourceLite` at `0x140034185`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400341ac`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400341dc`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400343a3`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400343c2`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005ba55`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005ba8e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005bab7`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005bb23`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005bb4c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140034185`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400341ac`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400341dc`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400343a3`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400343c2`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005ba55`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005ba8e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005bab7`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005bb23`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005bb4c`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140033c08`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140033ca2`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140033e31`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140033edb`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14005b930`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140033c08`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140033ca2`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140033e31`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140033edb`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14005b930`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140033c70`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140033d0e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140033f71`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140033f93`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14005b988`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14005b9d8`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14005ba00`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140033c70`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140033d0e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140033f71`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140033f93`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14005b988`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14005b9d8`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14005ba00`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x1400338ac`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x1400338ac`
- `ntoskrnl!FsRtlAreNamesEqual` at `0x1400337cd`
- `ntoskrnl!FsRtlAreNamesEqual` at `0x1400339ab`
- `ntoskrnl!FsRtlAreNamesEqual` at `0x1400337cd`
- `ntoskrnl!FsRtlAreNamesEqual` at `0x1400339ab`

## pseudocode

```c
__int64 __fastcall UdfSetLinkInfo(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rcx
  __int64 v7; // rdi
  char v8; // r12
  __int64 v9; // rsi
  int v10; // eax
  __int64 v12; // rbx
  int v13; // r8d
  bool v14; // zf
  __int64 v15; // r13
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  int v19; // r12d
  __int64 inserted; // rbx
  __int64 v21; // rcx
  const void **p_ConstantNameA; // rax
  char DirEntry; // si
  __int64 v24; // r8
  _QWORD *i; // rcx
  _QWORD *v26; // rsi
  __int64 v27; // r12
  struct _FAST_MUTEX *v28; // rbx
  __int64 v29; // r8
  PWSTR Buffer; // rsi
  int v31; // eax
  __int64 v32; // rbx
  struct _FAST_MUTEX *v33; // rsi
  _QWORD *v34; // rdi
  __int64 v35; // rbx
  __int64 v36; // r8
  __int64 v37; // rdi
  __int64 v38; // rcx
  __int64 v39; // r8
  __int64 v40; // r8
  char v41; // di
  char v42; // r9
  __int64 v43; // r8
  char v44; // bl
  __int64 v45; // rdi
  char ExtraFileAttributes; // al
  __int64 v47; // rsi
  __int64 v48; // r8
  __int64 v49; // r12
  __int64 v50; // rcx
  __int64 v51; // r12
  ULONG v52; // ecx
  ULONG v53; // eax
  __int64 v54; // rcx
  char v55; // [rsp+50h] [rbp-578h]
  char v56; // [rsp+51h] [rbp-577h]
  char v57; // [rsp+52h] [rbp-576h]
  char v58; // [rsp+56h] [rbp-572h]
  char v59; // [rsp+57h] [rbp-571h]
  char v60; // [rsp+59h] [rbp-56Fh] BYREF
  char v61; // [rsp+5Ah] [rbp-56Eh]
  char v62; // [rsp+5Bh] [rbp-56Dh] BYREF
  char v63[4]; // [rsp+5Ch] [rbp-56Ch] BYREF
  int v64; // [rsp+60h] [rbp-568h]
  __int64 v65; // [rsp+68h] [rbp-560h]
  __int64 v66; // [rsp+70h] [rbp-558h]
  _QWORD *v67; // [rsp+78h] [rbp-550h]
  UNICODE_STRING ConstantNameA; // [rsp+80h] [rbp-548h] BYREF
  int v69[2]; // [rsp+90h] [rbp-538h] BYREF
  __int64 v70; // [rsp+98h] [rbp-530h]
  _QWORD *v71; // [rsp+A0h] [rbp-528h]
  __int64 v72; // [rsp+A8h] [rbp-520h]
  __int64 v73; // [rsp+B0h] [rbp-518h]
  struct _UNICODE_STRING DestinationString; // [rsp+B8h] [rbp-510h] BYREF
  int v75[2]; // [rsp+C8h] [rbp-500h]
  __int64 v76; // [rsp+D0h] [rbp-4F8h]
  __int128 v77; // [rsp+D8h] [rbp-4F0h] BYREF
  _OWORD v78[2]; // [rsp+E8h] [rbp-4E0h] BYREF
  __int64 v79; // [rsp+108h] [rbp-4C0h]
  __int64 v80; // [rsp+110h] [rbp-4B8h] BYREF
  __int128 v81; // [rsp+118h] [rbp-4B0h] BYREF
  __int64 v82; // [rsp+128h] [rbp-4A0h]
  int v83[40]; // [rsp+130h] [rbp-498h] BYREF
  UNICODE_STRING FileOffset[25]; // [rsp+1D0h] [rbp-3F8h] BYREF
  char v85; // [rsp+360h] [rbp-268h] BYREF
  char v86; // [rsp+380h] [rbp-248h] BYREF

  *(_QWORD *)v75 = a3;
  v72 = a2;
  v73 = a1;
  v6 = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 184LL);
  v7 = *(_QWORD *)(v6 + 24);
  v8 = *(_BYTE *)(v6 + 32);
  v60 = v8;
  v9 = 0;
  *(_QWORD *)v69 = 0;
  v81 = 0;
  ConstantNameA = 0;
  DestinationString = 0;
  v77 = 0;
  v59 = 0;
  v62 = 0;
  memset(FileOffset, 0, 0x188u);
  memset(v83, 0, 0x98u);
  memset(v78, 0, sizeof(v78));
  v79 = 0;
  v10 = *(_DWORD *)(a2 + 212);
  if ( (v10 & 0x10) != 0 )
    return 3221225485LL;
  if ( *(_WORD *)a2 == 2355 )
    return 3221225658LL;
  v12 = *(_QWORD *)(a3 + 16);
  if ( !v12 )
  {
    if ( (*(_DWORD *)(a3 + 4) & 3) != 0 && !*(_WORD *)(a2 + 500) )
      return 3221225506LL;
    if ( v7 )
    {
      v70 = 0;
      goto LABEL_11;
    }
    return 3221225485LL;
  }
  v9 = *(_QWORD *)(v12 + 24);
  v70 = v9;
  if ( (*(_BYTE *)(v12 + 68) & 2) != 0 || (v10 & 0x200) != 0 )
    return 3221225763LL;
LABEL_11:
  if ( (*(_DWORD *)(a1 + 28) & 4) == 0 )
  {
    *(_DWORD *)(a1 + 24) = -1073741608;
    ExRaiseStatus(-1073741608);
  }
  v65 = *(_QWORD *)(a1 + 16);
  UdfFindTargetElements(a1, v7, v9, (unsigned int)v69, (__int64)&v81, (__int64)&ConstantNameA);
  v14 = (*(_DWORD *)(a3 + 4) & 4) == 0;
  LODWORD(v66) = *(_DWORD *)(a3 + 4) & 4;
  v61 = !v14;
  v15 = *(_QWORD *)v69;
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x200) != 0 )
  {
    WPP_SF_qqqZ(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 31, v13, a2, v9, v69[0], (__int64)&ConstantNameA);
  }
  if ( !(unsigned __int8)UdfIsFileNameValid(&ConstantNameA, 0)
    || !(unsigned __int8)UdfUnicodeLengthAsCS0Dstring(v16, &ConstantNameA, v63, &v62) )
  {
    return 3221225523LL;
  }
  v56 = 0;
  UdfIs8dot3Name(v17, &ConstantNameA);
  v63[0] = UdfCandidateShortName(v18, &ConstantNameA);
  if ( v15 == v9 )
  {
    if ( FsRtlAreNamesEqual(&ConstantNameA, (PCUNICODE_STRING)(v12 + 128), 0, 0) )
      return v8 == 0 ? 0xC0000035 : 0;
    v57 = 0;
    if ( v8 )
    {
      UdfAcquireResource(a1, *(_QWORD *)(*(_QWORD *)(v9 + 136) + 80LL) + 8LL, 0, 0);
      v56 = 1;
    }
  }
  else
  {
    UdfAcquireResource(a1, *(_QWORD *)(*(_QWORD *)(v15 + 136) + 80LL) + 8LL, 0, 0);
    v57 = 1;
  }
  v19 = 0;
  v64 = 0;
  v76 = v65;
  inserted = 0;
  v71 = 0;
  v67 = 0;
  v58 = 0;
  *(_DWORD *)&DestinationString.Length = 33292288;
  DestinationString.Buffer = (PWSTR)&v86;
  RtlUpcaseUnicodeString(&DestinationString, &ConstantNameA, 0);
  LODWORD(v77) = 1572864;
  *((_QWORD *)&v77 + 1) = &v85;
  if ( (*(_DWORD *)(v15 + 212) & 0x800000) != 0 && !(unsigned __int8)UdfIs8dot3Name(v21, &ConstantNameA) )
    UdfGenerate8dot3Name(v21, &ConstantNameA, 0, &v77);
  UdfInitializeCompoundDirContext(v21, FileOffset);
  v55 = 1;
  v78[0] = 0;
  p_ConstantNameA = (const void **)&ConstantNameA;
  if ( (_DWORD)v66 )
    p_ConstantNameA = (const void **)&DestinationString;
  *(_QWORD *)&v81 = p_ConstantNameA;
  DirEntry = UdfFindDirEntry(a1, v15, p_ConstantNameA, v61, 0, 0, (union _LARGE_INTEGER)FileOffset);
  if ( DirEntry && (_DWORD)v66 && !FsRtlAreNamesEqual(&ConstantNameA, &FileOffset[4], 0, 0) )
  {
    v80 = *(_QWORD *)&FileOffset[1].Length + HIDWORD(FileOffset[1].Buffer);
    if ( UdfFindDirEntry(a1, v15, (const void **)&ConstantNameA, 0, 0, 0, (union _LARGE_INTEGER)FileOffset) )
    {
      i = *(_QWORD **)&WPP_GLOBAL_Control;
      if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x200) != 0 )
      {
        WPP_SF_(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 32, WPP_0dbe93714b6730a9f09221a306b03890_Traceguids);
      }
LABEL_37:
      v19 = -1073741771;
      v64 = -1073741771;
      goto LABEL_95;
    }
    if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x200) != 0 )
    {
      WPP_SF_(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 33, WPP_0dbe93714b6730a9f09221a306b03890_Traceguids);
    }
    DirEntry = 1;
    UdfLookupInitialDirEntry(a1, v15, FileOffset, &v80, 0, 0);
    UdfUpdateDirNames(a1, (__int64)FileOffset, 0, 0);
  }
  if ( DirEntry )
    goto LABEL_46;
  if ( v63[0] )
    DirEntry = UdfFindDirEntry(a1, v15, (const void **)v81, v61, 1, 1, (union _LARGE_INTEGER)FileOffset);
  if ( DirEntry )
  {
LABEL_46:
    i = *(_QWORD **)&WPP_GLOBAL_Control;
    if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x200) != 0 )
    {
      WPP_SF_(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 34, WPP_0dbe93714b6730a9f09221a306b03890_Traceguids);
    }
    if ( v60 && (*(_BYTE *)(*(_QWORD *)&FileOffset[2].Length + 18LL) & 2) == 0 )
    {
      for ( i = *(_QWORD **)(v15 + 536); ; i = (_QWORD *)*i )
      {
        if ( i == (_QWORD *)(v15 + 536) )
        {
          v26 = v67;
LABEL_68:
          if ( !v26 )
          {
            inserted = 0;
            v71 = 0;
            FileOffset[17].Buffer = (PWSTR)1;
            UdfLookupFileEntryInEnumeration(a1, v15, FileOffset);
            Buffer = FileOffset[10].Buffer;
            if ( FileOffset[10].Buffer[24] == 1 )
            {
              v60 = 0;
              v66 = 0;
              if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x200) != 0 )
              {
                WPP_SF_(
                  *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
                  37,
                  WPP_0dbe93714b6730a9f09221a306b03890_Traceguids);
              }
              LODWORD(v66) = *(_DWORD *)(*(_QWORD *)&FileOffset[2].Length + 24LL);
              v31 = *(unsigned __int16 *)(*(_QWORD *)&FileOffset[2].Length + 28LL);
              HIDWORD(v66) = v31;
              if ( *((_BYTE *)Buffer + 27) == 4 )
                HIDWORD(v66) = v31 | 0x80000000;
              v32 = v65;
              v33 = (struct _FAST_MUTEX *)(v65 + 1648);
              ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v65 + 1648));
              *(_QWORD *)(v32 + 1704) = KeGetCurrentThread();
              v34 = UdfCreateScb(a1, v66, 0x934u, 0, &v60);
              v67 = v34;
              UdfInitializeScbFromIcbContext(a1, (__int64)v34, &FileOffset[9].Buffer, 0);
              v35 = *(_QWORD *)&FileOffset[3].Length;
              UdfCleanupCompoundDirContext(a1, FileOffset, v36);
              v55 = 0;
              UdfAcquireResource(a1, *(_QWORD *)(v34[17] + 80LL) + 8LL, 0, 0);
              v58 = 1;
              v37 = v65;
              ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v65 + 1584));
              *(_QWORD *)(v37 + 1640) = KeGetCurrentThread();
              inserted = UdfInsertPrefix(a1, (_DWORD)v67, 0, 0, 0, v15, v35);
              v71 = (_QWORD *)inserted;
              ++*(_DWORD *)(v15 + 204);
              ++*(_DWORD *)(v15 + 208);
              ++*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v15 + 136) + 8LL) + 256LL);
              ++*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v15 + 136) + 8LL) + 260LL);
              *(_QWORD *)(v37 + 1640) = 0;
              ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v37 + 1584));
              *(_QWORD *)(v37 + 1704) = 0;
              ExReleaseFastMutexUnsafe(v33);
            }
            else
            {
              if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x200) != 0 )
              {
                WPP_SF_(
                  *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
                  38,
                  WPP_0dbe93714b6730a9f09221a306b03890_Traceguids);
              }
              UdfPrepareDirContextForModify(a1, FileOffset, v15);
              if ( (*(_DWORD *)(v15 + 212) & 2) != 0 )
                UdfPrepareModifyIcbForScb(a1, v15, v78);
              UdfMarkFidDeleted(v38, FileOffset);
              UdfSetDirtyFid(a1, FileOffset);
              if ( (*(_DWORD *)(v15 + 212) & 2) != 0 )
              {
                LOBYTE(v39) = 1;
                UdfFinishModifyIcb(a1, v78, v39, v15);
              }
              UdfPrepareIcbContextForModify(a1, &FileOffset[9].Buffer);
              --Buffer[24];
              LOBYTE(v40) = 1;
              UdfFinishModifyIcb(a1, &FileOffset[10].Buffer, v40, 0);
            }
          }
          v41 = v55;
          if ( v55 )
          {
            UdfCleanupCompoundDirContext(a1, FileOffset, v24);
            v41 = 0;
          }
          if ( inserted )
          {
            if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x200) != 0 )
            {
              WPP_SF_(
                *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
                39,
                WPP_0dbe93714b6730a9f09221a306b03890_Traceguids);
            }
            v59 = 1;
            *(_DWORD *)(inserted + 68) |= 2u;
            UdfDeleteLinkAndTruncateScbs(a1);
          }
          goto LABEL_96;
        }
        inserted = (__int64)(i - 1);
        v71 = i - 1;
        if ( (*((_DWORD *)i + 15) & 8) == 0 && *(_QWORD *)(inserted + 56) == *(_QWORD *)&FileOffset[3].Length )
          break;
      }
      v26 = *(_QWORD **)(inserted + 48);
      v67 = v26;
      UdfAcquireResource(a1, *(_QWORD *)(v26[17] + 80LL) + 8LL, 0, 0);
      v58 = 1;
      if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x200) != 0 )
      {
        WPP_SF_qD(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
          35,
          WPP_0dbe93714b6730a9f09221a306b03890_Traceguids,
          v26,
          *(_DWORD *)(inserted + 64));
      }
      v27 = v65;
      v28 = (struct _FAST_MUTEX *)(v65 + 1584);
      ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v65 + 1584));
      *(_QWORD *)(v27 + 1640) = KeGetCurrentThread();
      ++*((_DWORD *)v26 + 51);
      *((_DWORD *)v26 + 52) = *((_DWORD *)v26 + 52);
      ++*(_DWORD *)(*(_QWORD *)(v26[17] + 8LL) + 256LL);
      *(_DWORD *)(*(_QWORD *)(v26[17] + 8LL) + 260LL) = *(_DWORD *)(*(_QWORD *)(v26[17] + 8LL) + 260LL);
      *(_QWORD *)(v27 + 1640) = 0;
      ExReleaseFastMutexUnsafe(v28);
      *(_QWORD *)(*(_QWORD *)(a1 + 8) + 56LL) = 0;
      v19 = UdfValidateSubtreeForRename((PVOID)a1);
      v64 = v19;
      ExAcquireFastMutexUnsafe(v28);
      v29 = v65;
      *(_QWORD *)(v65 + 1640) = KeGetCurrentThread();
      --*((_DWORD *)v26 + 51);
      *((_DWORD *)v26 + 52) = *((_DWORD *)v26 + 52);
      --*(_DWORD *)(*(_QWORD *)(v26[17] + 8LL) + 256LL);
      *(_DWORD *)(*(_QWORD *)(v26[17] + 8LL) + 260LL) = *(_DWORD *)(*(_QWORD *)(v26[17] + 8LL) + 260LL);
      *(_QWORD *)(v29 + 1640) = 0;
      ExReleaseFastMutexUnsafe(v28);
      inserted = (__int64)v71;
      if ( !v19 )
      {
        if ( *((_DWORD *)v71 + 16) )
        {
          i = *(_QWORD **)&WPP_GLOBAL_Control;
          if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x200) != 0 )
          {
            WPP_SF_(
              *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
              36,
              WPP_0dbe93714b6730a9f09221a306b03890_Traceguids);
          }
          v19 = -1073741790;
          v64 = -1073741790;
        }
        if ( !v19 )
          goto LABEL_68;
      }
      goto LABEL_95;
    }
    goto LABEL_37;
  }
  i = *(_QWORD **)&WPP_GLOBAL_Control;
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x200) != 0 )
  {
    WPP_SF_(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 40, WPP_0dbe93714b6730a9f09221a306b03890_Traceguids);
  }
LABEL_95:
  v41 = 1;
LABEL_96:
  if ( v59 )
  {
    v42 = *(_QWORD *)(inserted + 32) != *(_QWORD *)(inserted + 40);
    UdfRemovePrefix((__int64)i, inserted, v42, v42);
  }
  UdfUnpinView(a1, v78);
  if ( v41 )
    UdfCleanupCompoundDirContext(a1, FileOffset, v43);
  if ( v58 )
    ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(v67[17] + 80LL) + 8LL));
  if ( v19 >= 0 )
  {
    v44 = v56;
    v45 = v70;
  }
  else
  {
    if ( v57 )
    {
      ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(v15 + 136) + 80LL) + 8LL));
      v57 = 0;
    }
    v44 = v56;
    v45 = v70;
    if ( v56 )
    {
      ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(v70 + 136) + 80LL) + 8LL));
      v44 = 0;
    }
  }
  if ( v19 < 0 )
    return (unsigned int)v19;
  if ( !v44 )
    UdfAcquireResource(a1, *(_QWORD *)(*(_QWORD *)(v45 + 136) + 80LL) + 8LL, 0, 0);
  memset(v83, 0, 0x98u);
  ExtraFileAttributes = UdfGetExtraFileAttributes(*(_QWORD *)v75);
  v47 = v72;
  UdfCreateLink(a1, v15, v72, 0, 0, 0, (ExtraFileAttributes & 2) != 0, &ConstantNameA.Length, v83, v62);
  UdfUpdateLvidCounts(a1, 0, 1);
  UdfPrepareModifyIcbForScb(a1, v47, v78);
  ++*(_WORD *)(v47 + 500);
  LOBYTE(v48) = 1;
  UdfFinishModifyIcb(a1, v78, v48, v47);
  v49 = *(_QWORD *)&v83[12];
  v82 = *(_QWORD *)&v83[12];
  UdfCleanupDirContext(v50, v83);
  v51 = UdfInsertPrefix(
          a1,
          v47,
          (unsigned int)&ConstantNameA,
          (unsigned int)&DestinationString,
          (__int64)&v77,
          v15,
          v49);
  if ( v59 )
  {
    v52 = 252;
    v53 = 3;
  }
  else
  {
    v52 = 1;
    v53 = 1;
  }
  UdfNotifyReportChange(a1, v75[0], v51, 0, v47, v52, v53);
  UdfRemovePrefix(v54, v51, 1, 1);
  UdfUnpinView(a1, v78);
  if ( v57 )
    ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(v15 + 136) + 80LL) + 8LL));
  ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(v45 + 136) + 80LL) + 8LL));
  return 0;
}

```

## disassembly

```asm
0x140033548  push    rbx
0x14003354a  push    rsi
0x14003354b  push    rdi
0x14003354c  push    r12
0x14003354e  push    r13
0x140033550  push    r14
0x140033552  push    r15
0x140033554  sub     rsp, 590h
0x14003355b  mov     rax, cs:__security_cookie
0x140033562  xor     rax, rsp
0x140033565  mov     [rsp+5C8h+var_48], rax
0x14003356d  mov     r13, r8
0x140033570  mov     qword ptr [rsp+5C8h+var_500], r8
0x140033578  mov     r15, rdx
0x14003357b  mov     [rsp+5C8h+var_520], rdx
0x140033583  mov     r14, rcx
0x140033586  mov     [rsp+5C8h+var_518], rcx
0x14003358e  mov     rax, [rcx+8]
0x140033592  mov     rcx, [rax+0B8h]
0x140033599  mov     rdi, [rcx+18h]
0x14003359d  mov     r12b, [rcx+20h]
0x1400335a1  mov     [rsp+5C8h+var_56F], r12b
0x1400335a6  xor     esi, esi
0x1400335a8  mov     qword ptr [rsp+5C8h+var_538], rsi
0x1400335b0  xorps   xmm0, xmm0
0x1400335b3  movups  [rsp+5C8h+var_4B0], xmm0
0x1400335bb  xorps   xmm1, xmm1
0x1400335be  movups  xmmword ptr [rsp+5C8h+ConstantNameA.Length], xmm1
0x1400335c6  movups  xmmword ptr [rsp+5C8h+DestinationString.Length], xmm0
0x1400335ce  movups  [rsp+5C8h+var_4F0], xmm1
0x1400335d6  mov     [rsp+5C8h+var_571], sil
0x1400335db  mov     [rsp+5C8h+var_56D], sil
0x1400335e0  xor     edx, edx; Val
0x1400335e2  mov     r8d, 188h; Size
0x1400335e8  lea     rcx, [rsp+5C8h+FileOffset]; void *
0x1400335f0  call    memset
0x1400335f5  xor     edx, edx; Val
0x1400335f7  mov     r8d, 98h; Size
0x1400335fd  lea     rcx, [rsp+5C8h+var_498]; void *
0x140033605  call    memset
0x14003360a  xorps   xmm0, xmm0
0x14003360d  xor     eax, eax
0x14003360f  movups  [rsp+5C8h+var_4E0], xmm0
0x140033617  movups  [rsp+5C8h+var_4D0], xmm0
0x14003361f  mov     [rsp+5C8h+var_4C0], rax
0x140033627  mov     eax, [r15+0D4h]
0x14003362e  test    al, 10h
0x140033630  jnz     loc_1400343E0
0x140033636  mov     ecx, 933h
0x14003363b  cmp     [r15], cx
0x14003363f  jnz     short loc_14003364B
0x140033641  mov     eax, 0C00000BAh
0x140033646  jmp     loc_1400343E5
0x14003364b  mov     rbx, [r13+10h]
0x14003364f  test    rbx, rbx
0x140033652  jnz     short loc_140033683
0x140033654  mov     eax, [r13+4]
0x140033658  test    al, 3
0x14003365a  jz      short loc_140033670
0x14003365c  cmp     [r15+1F4h], si
0x140033664  jnz     short loc_140033670
0x140033666  mov     eax, 0C0000022h
0x14003366b  jmp     loc_1400343E5
0x140033670  test    rdi, rdi
0x140033673  jz      loc_1400343E0
0x140033679  mov     [rsp+5C8h+var_530], rsi
0x140033681  jmp     short loc_1400336A5
0x140033683  mov     rsi, [rbx+18h]
0x140033687  mov     [rsp+5C8h+var_530], rsi
0x14003368f  test    byte ptr [rbx+44h], 2
0x140033693  setz    cl
0x140033696  bt      eax, 9
0x14003369a  setnb   al
0x14003369d  test    al, cl
0x14003369f  jz      loc_1400343D9
0x1400336a5  mov     eax, [r14+1Ch]
0x1400336a9  test    al, 4
0x1400336ab  jnz     short loc_1400336C3
0x1400336ad  mov     ecx, 0C00000D8h; Status
0x1400336b2  mov     [r14+18h], ecx
0x1400336b6  call    cs:__imp_ExRaiseStatus
0x1400336c3  mov     rax, [r14+10h]
0x1400336c7  mov     [rsp+5C8h+var_560], rax
0x1400336cc  lea     rcx, [rsp+5C8h+ConstantNameA]
0x1400336d4  mov     qword ptr [rsp+5C8h+var_5A0], rcx
0x1400336d9  lea     rax, [rsp+5C8h+var_4B0]
0x1400336e1  mov     qword ptr [rsp+5C8h+var_5A8], rax
0x1400336e6  lea     r9, [rsp+5C8h+var_538]
0x1400336ee  mov     r8, rsi
0x1400336f1  mov     rdx, rdi
0x1400336f4  mov     rcx, r14
0x1400336f7  call    UdfFindTargetElements
0x1400336fc  mov     eax, [r13+4]
0x140033700  and     eax, 4
0x140033703  mov     dword ptr [rsp+5C8h+var_558], eax
0x140033707  setnz   [rsp+5C8h+var_56E]
0x14003370c  lea     rax, WPP_GLOBAL_Control
0x140033713  mov     rcx, cs:WPP_GLOBAL_Control
0x14003371a  mov     edi, 200h
0x14003371f  mov     r13, qword ptr [rsp+5C8h+var_538]
0x140033727  cmp     rcx, rax
0x14003372a  jz      short loc_140033759
0x14003372c  test    [rcx+2Ch], edi
0x14003372f  jz      short loc_140033759
0x140033731  mov     edx, 1Fh
0x140033736  lea     rax, [rsp+5C8h+ConstantNameA]
0x14003373e  mov     qword ptr [rsp+5C8h+var_598], rax
0x140033743  mov     qword ptr [rsp+5C8h+var_5A0], r13
0x140033748  mov     qword ptr [rsp+5C8h+var_5A8], rsi
0x14003374d  mov     r9, r15
0x140033750  mov     rcx, [rcx+18h]
0x140033754  call    WPP_SF_qqqZ
0x140033759  xor     edx, edx
0x14003375b  lea     rcx, [rsp+5C8h+ConstantNameA]
0x140033763  call    UdfIsFileNameValid
0x140033768  test    al, al
0x14003376a  jz      loc_1400343D2
0x140033770  lea     r9, [rsp+5C8h+var_56D]
0x140033775  lea     r8, [rsp+5C8h+var_56C]
0x14003377a  lea     rdx, [rsp+5C8h+ConstantNameA]
0x140033782  call    UdfUnicodeLengthAsCS0Dstring
0x140033787  test    al, al
0x140033789  jz      loc_1400343D2
0x14003378f  xor     al, al
0x140033791  mov     [rsp+5C8h+var_577], al
0x140033795  lea     rdx, [rsp+5C8h+ConstantNameA]
0x14003379d  call    UdfIs8dot3Name
0x1400337a2  lea     rdx, [rsp+5C8h+ConstantNameA]
0x1400337aa  call    UdfCandidateShortName
0x1400337af  mov     [rsp+5C8h+var_56C], al
0x1400337b3  xor     r8d, r8d; IgnoreCase
0x1400337b6  cmp     r13, rsi
0x1400337b9  jnz     short loc_14003382A
0x1400337bb  lea     rdx, [rbx+80h]; ConstantNameB
0x1400337c2  xor     r9d, r9d; UpcaseTable
0x1400337c5  lea     rcx, [rsp+5C8h+ConstantNameA]; ConstantNameA
0x1400337cd  call    cs:__imp_FsRtlAreNamesEqual
0x1400337d4  nop     dword ptr [rax+rax+00h]
0x1400337d9  test    al, al
0x1400337db  jz      short loc_1400337EE
0x1400337dd  neg     r12b
0x1400337e0  sbb     eax, eax
0x1400337e2  not     eax
0x1400337e4  and     eax, 0C0000035h
0x1400337e9  jmp     loc_1400343E5
0x1400337ee  mov     [rsp+5C8h+var_576], 0
0x1400337f3  test    r12b, r12b
0x1400337f6  jz      short loc_140033822
0x1400337f8  mov     rax, [rsi+88h]
0x1400337ff  mov     rdx, [rax+50h]
0x140033803  add     rdx, 8
0x140033807  xor     r9d, r9d
0x14003380a  xor     r8d, r8d
0x14003380d  mov     rcx, r14
0x140033810  call    UdfAcquireResource
0x140033815  mov     r15d, 1
0x14003381b  mov     [rsp+5C8h+var_577], r15b
0x140033820  jmp     short loc_14003384F
0x140033822  mov     r15d, 1
0x140033828  jmp     short loc_14003384F
0x14003382a  mov     rax, [r13+88h]
0x140033831  mov     rdx, [rax+50h]
0x140033835  add     rdx, 8
0x140033839  xor     r9d, r9d
0x14003383c  mov     rcx, r14
0x14003383f  call    UdfAcquireResource
0x140033844  mov     r15d, 1
0x14003384a  mov     [rsp+5C8h+var_576], r15b
0x14003384f  xor     esi, esi
0x140033851  mov     r12d, esi
0x140033854  mov     [rsp+5C8h+var_568], esi
0x140033858  mov     rcx, [rsp+5C8h+var_560]
0x14003385d  mov     [rsp+5C8h+var_4F8], rcx
0x140033865  mov     ebx, esi
0x140033867  mov     [rsp+5C8h+var_528], rbx
0x14003386f  mov     [rsp+5C8h+var_550], rsi
0x140033874  mov     [rsp+5C8h+var_572], sil
0x140033879  mov     [rsp+5C8h+var_575], sil
0x14003387e  mov     dword ptr [rsp+5C8h+DestinationString.Length], 1FC0000h
0x140033889  lea     rax, [rsp+5C8h+var_248]
0x140033891  mov     [rsp+5C8h+DestinationString.Buffer], rax
0x140033899  xor     r8d, r8d; AllocateDestinationString
0x14003389c  lea     rdx, [rsp+5C8h+ConstantNameA]; SourceString
0x1400338a4  lea     rcx, [rsp+5C8h+DestinationString]; DestinationString
0x1400338ac  call    cs:__imp_RtlUpcaseUnicodeString
0x1400338b3  nop     dword ptr [rax+rax+00h]
0x1400338b8  mov     dword ptr [rsp+5C8h+var_4F0], 180000h
0x1400338c3  lea     rax, [rsp+5C8h+var_268]
0x1400338cb  mov     qword ptr [rsp+5C8h+var_4F0+8], rax
0x1400338d3  mov     eax, [r13+0D4h]
0x1400338da  bt      eax, 17h
0x1400338de  jnb     short loc_140033909
0x1400338e0  lea     rdx, [rsp+5C8h+ConstantNameA]
0x1400338e8  call    UdfIs8dot3Name
0x1400338ed  test    al, al
0x1400338ef  jnz     short loc_140033909
0x1400338f1  lea     r9, [rsp+5C8h+var_4F0]
0x1400338f9  xor     r8d, r8d
0x1400338fc  lea     rdx, [rsp+5C8h+ConstantNameA]
0x140033904  call    UdfGenerate8dot3Name
0x140033909  lea     rdx, [rsp+5C8h+FileOffset]
0x140033911  call    UdfInitializeCompoundDirContext
0x140033916  mov     [rsp+5C8h+var_578], r15b
0x14003391b  xorps   xmm0, xmm0
0x14003391e  movdqu  [rsp+5C8h+var_4E0], xmm0
0x140033927  mov     [rsp+5C8h+var_573], sil
0x14003392c  mov     [rsp+5C8h+var_574], sil
0x140033931  lea     rax, [rsp+5C8h+ConstantNameA]
0x140033939  lea     rcx, [rsp+5C8h+DestinationString]
0x140033941  cmp     dword ptr [rsp+5C8h+var_558], esi
0x140033945  cmovnz  rax, rcx
0x140033949  mov     qword ptr [rsp+5C8h+var_4B0], rax
0x140033951  lea     rcx, [rsp+5C8h+FileOffset]
0x140033959  mov     qword ptr [rsp+5C8h+var_598], rcx; FileOffset
0x14003395e  mov     byte ptr [rsp+5C8h+var_5A0], sil; char
0x140033963  mov     [rsp+5C8h+var_5A8], sil; char
0x140033968  mov     r9b, [rsp+5C8h+var_56E]
0x14003396d  mov     r8, rax
0x140033970  mov     rdx, r13; int
0x140033973  mov     rcx, r14; int
0x140033976  call    UdfFindDirEntry
0x14003397b  mov     sil, al
0x14003397e  mov     [rsp+5C8h+var_570], al
0x140033982  test    al, al
0x140033984  jz      loc_140033ABD
0x14003398a  cmp     dword ptr [rsp+5C8h+var_558], 0
0x14003398f  jz      loc_140033ABD
0x140033995  xor     r9d, r9d; UpcaseTable
0x140033998  xor     r8d, r8d; IgnoreCase
0x14003399b  lea     rdx, [rsp+5C8h+ConstantNameB]; ConstantNameB
0x1400339a3  lea     rcx, [rsp+5C8h+ConstantNameA]; ConstantNameA
0x1400339ab  call    cs:__imp_FsRtlAreNamesEqual
0x1400339b2  nop     dword ptr [rax+rax+00h]
0x1400339b7  test    al, al
0x1400339b9  jnz     loc_140033ABD
0x1400339bf  mov     eax, [rsp+5C8h+var_3DC]
0x1400339c6  add     rax, [rsp+5C8h+var_3E8]
0x1400339ce  mov     [rsp+5C8h+var_4B8], rax
0x1400339d6  lea     rax, [rsp+5C8h+FileOffset]
0x1400339de  mov     qword ptr [rsp+5C8h+var_598], rax; FileOffset
0x1400339e3  xor     esi, esi
0x1400339e5  mov     byte ptr [rsp+5C8h+var_5A0], sil; char
0x1400339ea  mov     [rsp+5C8h+var_5A8], sil; char
0x1400339ef  xor     r9d, r9d
0x1400339f2  lea     r8, [rsp+5C8h+ConstantNameA]
0x1400339fa  mov     rdx, r13; int
0x1400339fd  mov     rcx, r14; int
0x140033a00  call    UdfFindDirEntry
0x140033a05  mov     [rsp+5C8h+var_570], al
0x140033a09  test    al, al
0x140033a0b  jz      short loc_140033A4A
0x140033a0d  mov     rcx, cs:WPP_GLOBAL_Control
0x140033a14  lea     rax, WPP_GLOBAL_Control
0x140033a1b  cmp     rcx, rax
0x140033a1e  jz      short loc_140033A3A
0x140033a20  mov     eax, [rcx+2Ch]
0x140033a23  test    edi, eax
0x140033a25  jz      short loc_140033A3A
0x140033a27  lea     edx, [rsi+20h]
0x140033a2a  lea     r8, WPP_0dbe93714b6730a9f09221a306b03890_Traceguids
0x140033a31  mov     rcx, [rcx+18h]
0x140033a35  call    WPP_SF_
0x140033a3a  mov     r12d, 0C0000035h
0x140033a40  mov     [rsp+5C8h+var_568], r12d
0x140033a45  jmp     loc_140034122
0x140033a4a  mov     rcx, cs:WPP_GLOBAL_Control
0x140033a51  lea     rax, WPP_GLOBAL_Control
0x140033a58  cmp     rcx, rax
0x140033a5b  jz      short loc_140033A77
0x140033a5d  test    [rcx+2Ch], edi
0x140033a60  jz      short loc_140033A77
0x140033a62  mov     edx, 21h ; '!'
0x140033a67  lea     r8, WPP_0dbe93714b6730a9f09221a306b03890_Traceguids
0x140033a6e  mov     rcx, [rcx+18h]
0x140033a72  call    WPP_SF_
0x140033a77  mov     sil, r15b
0x140033a7a  mov     [rsp+5C8h+var_570], r15b
0x140033a7f  mov     [rsp+5C8h+var_5A0], 0; int
0x140033a87  mov     [rsp+5C8h+var_5A8], 0; char
0x140033a8c  lea     r9, [rsp+5C8h+var_4B8]
0x140033a94  lea     r8, [rsp+5C8h+FileOffset]; int
0x140033a9c  mov     rdx, r13; int
0x140033a9f  mov     rcx, r14; int
0x140033aa2  call    UdfLookupInitialDirEntry
0x140033aa7  xor     r9d, r9d
0x140033aaa  xor     r8d, r8d
0x140033aad  lea     rdx, [rsp+5C8h+FileOffset]
0x140033ab5  mov     rcx, r14
0x140033ab8  call    UdfUpdateDirNames
0x140033abd  test    sil, sil
0x140033ac0  jnz     short loc_140033B08
0x140033ac2  cmp     [rsp+5C8h+var_56C], sil
0x140033ac7  jz      short loc_140033AFF
0x140033ac9  lea     rax, [rsp+5C8h+FileOffset]
0x140033ad1  mov     qword ptr [rsp+5C8h+var_598], rax; FileOffset
0x140033ad6  mov     byte ptr [rsp+5C8h+var_5A0], r15b; char
0x140033adb  mov     [rsp+5C8h+var_5A8], r15b; char
0x140033ae0  mov     r9b, [rsp+5C8h+var_56E]
0x140033ae5  mov     r8, qword ptr [rsp+5C8h+var_4B0]
0x140033aed  mov     rdx, r13; int
  ... truncated ...
```
