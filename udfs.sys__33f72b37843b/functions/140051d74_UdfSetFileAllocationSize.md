# UdfSetFileAllocationSize

- ea: `0x140051d74`
- end: `0x14005285c`
- name: `UdfSetFileAllocationSize`
- size: `2792`
- prototype: ``
- caller_count: `4`
- callee_count: `22`
- tags: `file_ops, installer_update`

## callers

- `0x1400316e8`
- `0x140032ccc`
- `0x140050ee0`
- `0x140059988`

## callees

- `0x1400050d8`
- `0x140005e80`
- `0x14000b24c`
- `0x14000ca10`
- `0x14000ca54`
- `0x14000cad4`
- `0x14000cb6c`
- `0x14000eb04`
- `0x14000ed4c`
- `0x14000f8cc`
- `0x14001047c`
- `0x14001093c`
- `0x140010bd0`
- `0x14001758c`
- `0x1400193f0`
- `0x14001c080`
- `0x140030738`
- `0x14003be8c`
- `0x140051d74`
- `0x140056cb8`
- `0x140057330`
- `0x1400591e0`

## import_xrefs

- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x14005284b`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x14005aad9`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x14005284b`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x14005aad9`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14005202d`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140052796`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14005202d`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140052796`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140052076`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400520c3`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400527da`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140052076`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400520c3`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400527da`
- `ntoskrnl!CcSetFileSizes` at `0x140052429`
- `ntoskrnl!CcSetFileSizes` at `0x140052429`
- `ntoskrnl!MmCanFileBeTruncated` at `0x140051f09`
- `ntoskrnl!MmCanFileBeTruncated` at `0x140051f09`
- `ntoskrnl!FsRtlInitializeLargeMcb` at `0x140052255`
- `ntoskrnl!FsRtlInitializeLargeMcb` at `0x140052255`
- `ntoskrnl!FsRtlTruncateLargeMcb` at `0x1400522c1`
- `ntoskrnl!FsRtlTruncateLargeMcb` at `0x1400522f6`
- `ntoskrnl!FsRtlTruncateLargeMcb` at `0x1400522c1`
- `ntoskrnl!FsRtlTruncateLargeMcb` at `0x1400522f6`

## pseudocode

```c
__int64 __fastcall UdfSetFileAllocationSize(
        __int64 a1,
        struct _FILE_OBJECT *a2,
        __int64 a3,
        __int64 a4,
        union _LARGE_INTEGER *a5,
        char a6,
        char a7)
{
  __int64 v9; // rdi
  __int64 v10; // r8
  unsigned __int64 v11; // r14
  __int64 QuadPart; // rcx
  union _LARGE_INTEGER *v13; // r15
  __int64 result; // rax
  union _LARGE_INTEGER v15; // rax
  char v16; // r13
  int v17; // r8d
  unsigned int v18; // esi
  unsigned int v19; // eax
  int v20; // r8d
  unsigned int v21; // r9d
  unsigned int v22; // eax
  char v23; // r12
  char v24; // al
  char v25; // si
  int v26; // eax
  unsigned __int64 v27; // r10
  __int64 v28; // rcx
  __int64 v29; // rcx
  int v30; // r13d
  struct _CC_FILE_SIZES *v31; // rdx
  union _LARGE_INTEGER v32; // r8
  unsigned __int64 v33; // rax
  struct _FILE_OBJECT *v34; // r13
  __int64 v35; // rsi
  __int64 v36; // rax
  DWORD LowPart; // edx
  __int64 v38; // r8
  LONGLONG v39; // r13
  bool v40; // zf
  __int64 v41; // rsi
  __int64 v42; // r8
  unsigned int v43; // ecx
  char v44; // cl
  __int64 v45; // r9
  unsigned int v46; // esi
  int v47; // [rsp+20h] [rbp-D8h]
  int v48; // [rsp+28h] [rbp-D0h]
  ULONG v49; // [rsp+30h] [rbp-C8h]
  char v50; // [rsp+40h] [rbp-B8h]
  char v51; // [rsp+41h] [rbp-B7h]
  char v52; // [rsp+42h] [rbp-B6h]
  char v53; // [rsp+44h] [rbp-B4h]
  char v54; // [rsp+45h] [rbp-B3h]
  union _LARGE_INTEGER NewFileSize; // [rsp+48h] [rbp-B0h] BYREF
  char v56; // [rsp+50h] [rbp-A8h]
  int v57; // [rsp+54h] [rbp-A4h]
  int v58; // [rsp+58h] [rbp-A0h]
  LONGLONG v59; // [rsp+60h] [rbp-98h]
  union _LARGE_INTEGER v60; // [rsp+68h] [rbp-90h]
  __int64 v61; // [rsp+70h] [rbp-88h]
  LARGE_MCB Mcb; // [rsp+78h] [rbp-80h] BYREF
  _OWORD v63[2]; // [rsp+98h] [rbp-60h] BYREF
  __int64 v64; // [rsp+B8h] [rbp-40h]
  struct _FILE_OBJECT *FileObject; // [rsp+108h] [rbp+10h]
  char v68; // [rsp+120h] [rbp+28h]

  FileObject = a2;
  v9 = *(_QWORD *)(a1 + 16);
  NewFileSize.QuadPart = 0;
  v57 = 0;
  v58 = 0;
  memset(&Mcb, 0, sizeof(Mcb));
  v10 = 1;
  v11 = (~(unsigned __int64)(unsigned int)(*(_DWORD *)(v9 + 68) - 1)
       & (a5->QuadPart + (unsigned int)(*(_DWORD *)(v9 + 68) - 1))) >> *(_DWORD *)(v9 + 72);
  QuadPart = *(_QWORD *)&WPP_GLOBAL_Control;
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 1) != 0 )
  {
    LOBYTE(v10) = a7 != 0 ? 89 : 78;
    LOBYTE(a2) = a6 != 0 ? 89 : 78;
    WPP_SF_qiDcc(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
      a2,
      v10,
      a3,
      a5->QuadPart,
      v11,
      (_BYTE)a2,
      (_BYTE)v10);
  }
  if ( a7 )
  {
    if ( a5->QuadPart != *(_QWORD *)(a3 + 32) )
      goto LABEL_6;
    return 0;
  }
  if ( (*(_DWORD *)(a3 + 212) & 2) != 0
    && a5->QuadPart <= (unsigned int)(*(_DWORD *)(*(_QWORD *)(a1 + 16) + 68LL) - *(_DWORD *)(a3 + 224))
    && !a6 )
  {
    return 0;
  }
LABEL_6:
  v54 = 0;
  v13 = (union _LARGE_INTEGER *)(a3 + 32);
  if ( a6 )
  {
    NewFileSize.QuadPart = 0;
  }
  else if ( a7 && (v15 = *a5, a5->QuadPart > v13->QuadPart)
         || (QuadPart = v13->QuadPart, v15 = *a5, a5->QuadPart < v13->QuadPart) )
  {
    NewFileSize = v15;
    v54 = 1;
  }
  else
  {
    NewFileSize = *v13;
  }
  v59 = NewFileSize.QuadPart - v13->QuadPart;
  if ( v59 >= 0 )
  {
    v51 = 0;
  }
  else
  {
    v51 = 1;
    if ( !MmCanFileBeTruncated((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(a3 + 424) + 8LL), &NewFileSize) )
      return 3221226051LL;
  }
  v16 = 0;
  v50 = 0;
  v17 = *(_DWORD *)(a3 + 212);
  if ( (v17 & 2) != 0 )
  {
    if ( a5->QuadPart > (unsigned int)(*(_DWORD *)(*(_QWORD *)(a1 + 16) + 68LL) - *(_DWORD *)(a3 + 224)) )
    {
      UdfDeEmbedFileData(QuadPart, (struct _CC_FILE_SIZES *)a3, FileObject, *(_QWORD *)(a3 + 40) != 0);
      v16 = 1;
      v17 = *(_DWORD *)(a3 + 212);
      goto LABEL_30;
    }
    goto LABEL_29;
  }
  if ( (v17 & 0x2000) == 0
    && a5->QuadPart <= (unsigned int)(*(_DWORD *)(*(_QWORD *)(a1 + 16) + 68LL) - *(_DWORD *)(a3 + 224))
    && !NewFileSize.QuadPart )
  {
    v50 = 1;
LABEL_29:
    LODWORD(v11) = 0;
  }
LABEL_30:
  if ( (v17 & 0x2002) != 0 )
    goto LABEL_45;
  if ( *(_QWORD *)(v9 + 352) || (*(_DWORD *)(v9 + 48) & 0x20000000) != 0 )
  {
    if ( v59 > 0 )
    {
      LOBYTE(v49) = (*(_DWORD *)(a1 + 28) & 0x10) != 0;
      LOBYTE(v48) = 1;
      result = UdfSeqCacheReserveFileRegion(
                 a1,
                 a3,
                 (unsigned __int64)v13->QuadPart >> *(_DWORD *)(v9 + 72),
                 (~(unsigned __int64)(unsigned int)(*(_DWORD *)(v9 + 68) - 1)
                & ((unsigned int)(*(_DWORD *)(v9 + 68) - 1)
                 + v59
                 + ((unsigned int)(*(_DWORD *)(v9 + 68) - 1) & v13->QuadPart))) >> *(_DWORD *)(v9 + 72),
                 0,
                 v48,
                 v49);
      if ( (int)result < 0 )
        return result;
    }
LABEL_45:
    v23 = 0;
    v24 = 0;
    v68 = 0;
    v52 = 0;
    v53 = 0;
    v60.QuadPart = 0;
    v61 = 0;
    v25 = v51;
    if ( v51 )
    {
      v26 = *(_DWORD *)(a3 + 212);
      if ( (v26 & 2) == 0 )
      {
        if ( (v26 & 0x2000) != 0 )
        {
          result = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))UdfUnReserveSparseFileRegion)(
                     a1,
                     a3,
                     (union _LARGE_INTEGER)NewFileSize.QuadPart);
          if ( (int)result < 0 )
            return result;
        }
        else if ( *(_QWORD *)(v9 + 352) || (*(_DWORD *)(v9 + 48) & 0x20000000) != 0 )
        {
          v27 = ~(unsigned __int64)(unsigned int)(*(_DWORD *)(v9 + 68) - 1);
          LOBYTE(v47) = 1;
          UdfSeqCacheUnReserveFileRegion(
            a1,
            a3,
            (v27 & ((unsigned int)(*(_DWORD *)(v9 + 68) - 1) + NewFileSize.QuadPart)) >> *(_DWORD *)(v9 + 72),
            (unsigned int)((v27 & ((unsigned int)(*(_DWORD *)(v9 + 68) - 1) + v13->QuadPart)) >> *(_DWORD *)(v9 + 72))
          - (unsigned int)((v27 & ((unsigned int)(*(_DWORD *)(v9 + 68) - 1) + NewFileSize.QuadPart)) >> *(_DWORD *)(v9 + 72)),
            v47);
        }
      }
      v24 = 0;
    }
    if ( *(_DWORD *)(a3 + 296) > (unsigned int)v11 )
    {
      if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 1) != 0 )
      {
        WPP_SF_d(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
          77,
          WPP_3702783af02333f5d52357996bb663b1_Traceguids);
      }
      FsRtlInitializeLargeMcb(&Mcb, PagedPool);
      v52 = 1;
      UdfCopyMoveMcbAllocation(v28, a3 + 232, &Mcb, (unsigned int)v11);
      if ( !*(_QWORD *)(v9 + 352) && (*(_DWORD *)(v9 + 48) & 0x20000000) == 0 )
        UdfCopyMoveMcbAllocation(v29, a3 + 264, &Mcb, (unsigned int)v11);
      FsRtlTruncateLargeMcb((PLARGE_MCB)(a3 + 232), (unsigned int)v11);
      v30 = v57;
      *(_DWORD *)(a3 + 320) -= v57;
      if ( !*(_QWORD *)(v9 + 352) && (*(_DWORD *)(v9 + 48) & 0x20000000) == 0 )
      {
        FsRtlTruncateLargeMcb((PLARGE_MCB)(a3 + 264), (unsigned int)v11);
        *(_DWORD *)(a3 + 324) -= v30 + v58;
      }
      v53 = 1;
      v24 = 1;
      v68 = 1;
      v56 = 1;
      v25 = v51;
    }
    if ( v25 )
    {
      if ( v24 )
      {
        *(_DWORD *)(a3 + 300) = v11;
        *(_DWORD *)(a3 + 296) = v11;
      }
      *(union _LARGE_INTEGER *)(a3 + 304) = NewFileSize;
      *(_DWORD *)(a3 + 212) &= ~0x2000000u;
    }
    if ( v50 )
    {
      if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 1) != 0 )
      {
        WPP_SF_q(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
          78,
          WPP_3702783af02333f5d52357996bb663b1_Traceguids,
          a3);
      }
      *(_DWORD *)(a3 + 212) |= 2u;
      *(_DWORD *)(a3 + 212) &= ~0x20000u;
      UdfUninitializeScbMcb(a3);
      v23 = 1;
    }
    UdfUpdateScbTimeStamps(QuadPart, a3, a4);
    *(_DWORD *)(a3 + 220) |= 0x20u;
    v60 = *v13;
    v31 = (struct _CC_FILE_SIZES *)(a3 + 24);
    v61 = *(_QWORD *)(a3 + 24);
    v32 = NewFileSize;
    *(union _LARGE_INTEGER *)(a3 + 40) = NewFileSize;
    *v13 = v32;
    if ( (*(_DWORD *)(a3 + 212) & 2) != 0 )
      v33 = ~(unsigned __int64)(unsigned int)(*(_DWORD *)(v9 + 68) - 1)
          & (v32.QuadPart + (unsigned int)(*(_DWORD *)(v9 + 68) - 1));
    else
      v33 = (unsigned __int64)(unsigned int)v11 << *(_DWORD *)(v9 + 72);
    v31->AllocationSize.QuadPart = v33;
    v34 = FileObject;
    CcSetFileSizes(FileObject, v31);
    if ( v25 )
    {
      if ( (*(_QWORD *)(v9 + 352) || (*(_DWORD *)(v9 + 48) & 0x20000000) != 0) && *(_DWORD *)(a3 + 376) )
        UdfSeqCacheTruncateDataForFile(
          a1,
          a3,
          (~(unsigned __int64)(unsigned int)(*(_DWORD *)(v9 + 68) - 1)
         & ((unsigned int)(*(_DWORD *)(v9 + 68) - 1) + NewFileSize.QuadPart)) >> *(_DWORD *)(v9 + 72));
      if ( (*(_DWORD *)(a3 + 212) & 0x2000000) != 0 )
        v23 = 1;
    }
    if ( (*(_DWORD *)(a3 + 212) & 2) != 0 && (!v23 || v50) )
    {
      v64 = 0;
      memset(v63, 0, sizeof(v63));
      if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 1) != 0 )
      {
        WPP_SF_(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 79, WPP_3702783af02333f5d52357996bb663b1_Traceguids);
      }
      UdfPrepareModifyIcbForScb(a1, a3, v63);
      v35 = *(_QWORD *)&v63[0];
      v36 = 172;
      if ( **(_WORD **)&v63[0] != 261 )
        v36 = 212;
      LowPart = NewFileSize.LowPart;
      if ( *(_DWORD *)(v36 + *(_QWORD *)&v63[0]) < NewFileSize.LowPart )
        LowPart = *(_DWORD *)(v36 + *(_QWORD *)&v63[0]);
      memset(
        (void *)(*(_QWORD *)&v63[0] + LowPart + *(_DWORD *)(a3 + 224)),
        0,
        *(_DWORD *)(v9 + 68) - (LowPart + *(_DWORD *)(a3 + 224)));
      v39 = NewFileSize.QuadPart - *(_QWORD *)(v35 + 56);
      *(union _LARGE_INTEGER *)(v35 + 56) = NewFileSize;
      v40 = *(_WORD *)v35 == 266;
      if ( *(_WORD *)v35 == 266 )
        *(_DWORD *)(v35 + 212) = NewFileSize.LowPart;
      else
        *(_DWORD *)(v35 + 172) = NewFileSize.LowPart;
      if ( v40 )
        *(_QWORD *)(v35 + 64) += v39;
      if ( v50 )
      {
        *(_WORD *)(v35 + 34) &= 0xFFF8u;
        *(_WORD *)(v35 + 34) |= 3u;
      }
      LOBYTE(v38) = 1;
      v41 = a1;
      UdfFinishModifyIcb(a1, v63, v38, a3);
      if ( (*(_DWORD *)(a3 + 212) & 0x10) != 0 && v39 )
      {
        UdfPrepareModifyIcbForScb(a1, *(_QWORD *)(*(_QWORD *)(a3 + 136) + 16LL), v63);
        *(_QWORD *)(*(_QWORD *)&v63[0] + 64LL) += v39;
        LOBYTE(v42) = 1;
        UdfFinishModifyIcb(a1, v63, v42, *(_QWORD *)(*(_QWORD *)(a3 + 136) + 16LL));
      }
      v34 = FileObject;
    }
    else
    {
      v41 = a1;
    }
    v43 = *(_DWORD *)(a3 + 296);
    if ( (unsigned int)v11 <= v43
      || (*(_DWORD *)(a3 + 212) & 0x2000) != 0
      || *(_QWORD *)(v9 + 352)
      || (*(_DWORD *)(v9 + 48) & 0x20000000) != 0 )
    {
      v44 = v68;
    }
    else
    {
      UdfAllocateAtFileTail(v41, a3, (unsigned int)v11 - v43, &NewFileSize);
      v44 = 1;
      v56 = 1;
      v23 = 0;
    }
    if ( v44 )
    {
      *(_DWORD *)(a3 + 296) = v11;
    }
    else if ( !v59 || (*(_DWORD *)(a3 + 212) & 2) != 0 )
    {
LABEL_128:
      if ( v53 )
      {
        if ( !*(_QWORD *)(v9 + 352) && (*(_DWORD *)(v9 + 48) & 0x20000000) == 0 )
        {
          LOBYTE(v47) = 0;
          UdfFreeAllocation(v41, a3, &Mcb, (unsigned int)v11, v47, 0);
          if ( (*(_DWORD *)(a3 + 212) & 0x2000) == 0 )
          {
            if ( a6 )
            {
              v46 = v57 + v58;
              ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v9 + 1584));
              *(_QWORD *)(v9 + 1640) = KeGetCurrentThread();
              if ( v46 <= (unsigned int)UdfAvailableFreeBlocks(v9, 0) )
              {
                *(_DWORD *)(v9 + 672) += v46;
                *(_DWORD *)(a3 + 328) += v46;
              }
              *(_QWORD *)(v9 + 1640) = 0;
              ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v9 + 1584));
            }
          }
        }
      }
      if ( v54 && a4 )
        UdfNotifyReportChange(a1, a4, *(_QWORD *)(a4 + 16), (int)v34, a3, 8u, 3u);
      v34->Flags |= 0x1000u;
      if ( !a7 )
        *(_DWORD *)(a3 + 212) |= 0x400u;
      if ( v52 )
        FsRtlUninitializeLargeMcb(&Mcb);
      return 0;
    }
    *(union _LARGE_INTEGER *)(a3 + 304) = NewFileSize;
    if ( !v23 )
    {
      if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 1) != 0 )
      {
        WPP_SF_d(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
          80,
          WPP_3702783af02333f5d52357996bb663b1_Traceguids);
      }
      if ( (_DWORD)v11 )
        v45 = (unsigned int)(v11 - 1);
      else
        v45 = 0;
      UdfUpdateAdsFromScb(v41, a3, 0, v45);
    }
    goto LABEL_128;
  }
  v18 = 0;
  v19 = *(_DWORD *)(a3 + 296);
  if ( v19 < (unsigned int)v11 )
    v18 = v11 - v19 + 1;
  v20 = *(_DWORD *)(a3 + 328);
  if ( v18 == v20 )
    goto LABEL_45;
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 1) != 0 )
  {
    WPP_SF_dd(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
      76,
      WPP_3702783af02333f5d52357996bb663b1_Traceguids,
      v18,
      v20);
  }
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v9 + 1584));
  *(_QWORD *)(v9 + 1640) = KeGetCurrentThread();
  v21 = *(_DWORD *)(a3 + 328);
  if ( v21 >= v18 || (v22 = UdfAvailableFreeBlocks(v9, 0), v18 - v21 <= v22) )
  {
    *(_DWORD *)(v9 + 672) += v18 - v21;
    *(_DWORD *)(a3 + 328) = v18;
    *(_QWORD *)(v9 + 1640) = 0;
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v9 + 1584));
    goto LABEL_45;
  }
  *(_QWORD *)(v9 + 1640) = 0;
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v9 + 1584));
  if ( v16 )
    *(_DWORD *)(a3 + 212) = *(_DWORD *)(a3 + 212) & 0xFFF7FFFD | 2;
  return 3221225599LL;
}

```

## disassembly

```asm
0x140051d74  mov     rax, rsp
0x140051d77  mov     [rax+20h], r9
0x140051d7b  mov     [rax+18h], r8
0x140051d7f  mov     [rax+10h], rdx
0x140051d83  mov     [rax+8], rcx
0x140051d87  push    rbx
0x140051d88  push    rsi
0x140051d89  push    rdi
0x140051d8a  push    r12
0x140051d8c  push    r13
0x140051d8e  push    r14
0x140051d90  push    r15
0x140051d92  sub     rsp, 0C0h
0x140051d99  mov     rbx, r8
0x140051d9c  mov     r12, rcx
0x140051d9f  mov     rdi, [rcx+10h]
0x140051da3  xor     r11d, r11d
0x140051da6  mov     qword ptr [rsp+0F8h+NewFileSize], r11
0x140051dab  mov     [rsp+0F8h+var_A4], r11d
0x140051db0  mov     [rsp+0F8h+var_A0], r11d
0x140051db5  xorps   xmm0, xmm0
0x140051db8  movups  xmmword ptr [rax-80h], xmm0
0x140051dbc  movups  xmmword ptr [rax-70h], xmm0
0x140051dc0  mov     eax, [rdi+44h]
0x140051dc3  lea     r8d, [r11+1]
0x140051dc7  sub     eax, r8d
0x140051dca  mov     ecx, eax
0x140051dcc  mov     rsi, [rsp+0F8h+arg_20]
0x140051dd4  mov     r9, [rsi]
0x140051dd7  lea     r14, [r9+rax]
0x140051ddb  not     rcx
0x140051dde  and     r14, rcx
0x140051de1  mov     ecx, [rdi+48h]
0x140051de4  shr     r14, cl
0x140051de7  lea     rax, WPP_GLOBAL_Control
0x140051dee  mov     rcx, cs:WPP_GLOBAL_Control
0x140051df5  cmp     rcx, rax
0x140051df8  jz      short loc_140051E4D
0x140051dfa  mov     eax, [rcx+2Ch]
0x140051dfd  test    r8b, al
0x140051e00  jz      short loc_140051E4D
0x140051e02  mov     al, [rsp+0F8h+arg_30]
0x140051e09  neg     al
0x140051e0b  sbb     r8b, r8b
0x140051e0e  and     r8b, 0Bh
0x140051e12  add     r8b, 4Eh ; 'N'
0x140051e16  mov     al, [rsp+0F8h+arg_28]
0x140051e1d  neg     al
0x140051e1f  sbb     dl, dl
0x140051e21  and     dl, 0Bh
0x140051e24  add     dl, 4Eh ; 'N'
0x140051e27  mov     [rsp+0F8h+var_C0], r8b
0x140051e2c  mov     byte ptr [rsp+0F8h+var_C8], dl
0x140051e30  mov     [rsp+0F8h+var_D0], r14d
0x140051e35  mov     [rsp+0F8h+var_D8], r9
0x140051e3a  mov     r9, rbx
0x140051e3d  mov     rcx, [rcx+18h]
0x140051e41  call    WPP_SF_qiDcc
0x140051e46  xor     r11d, r11d
0x140051e49  lea     r8d, [r11+1]
0x140051e4d  cmp     [rsp+0F8h+arg_30], r11b
0x140051e55  jz      short loc_140051E7A
0x140051e57  mov     rax, [rbx+20h]
0x140051e5b  cmp     [rsi], rax
0x140051e5e  jz      short loc_140051EA1
0x140051e60  mov     [rsp+0F8h+var_B3], r11b
0x140051e65  lea     r15, [rbx+20h]
0x140051e69  cmp     [rsp+0F8h+arg_28], r11b
0x140051e71  jz      short loc_140051EB7
0x140051e73  mov     qword ptr [rsp+0F8h+NewFileSize], r11
0x140051e78  jmp     short loc_140051EE5
0x140051e7a  mov     eax, [rbx+0D4h]
0x140051e80  test    al, 2
0x140051e82  jz      short loc_140051E60
0x140051e84  mov     rax, [r12+10h]
0x140051e89  mov     eax, [rax+44h]
0x140051e8c  sub     eax, [rbx+0E0h]
0x140051e92  cmp     [rsi], rax
0x140051e95  jg      short loc_140051E60
0x140051e97  cmp     [rsp+0F8h+arg_28], r11b
0x140051e9f  jnz     short loc_140051E60
0x140051ea1  xor     eax, eax
0x140051ea3  add     rsp, 0C0h
0x140051eaa  pop     r15
0x140051eac  pop     r14
0x140051eae  pop     r13
0x140051eb0  pop     r12
0x140051eb2  pop     rdi
0x140051eb3  pop     rsi
0x140051eb4  pop     rbx
0x140051eb5  retn
0x140051eb7  cmp     [rsp+0F8h+arg_30], r11b
0x140051ebf  jz      short loc_140051EC9
0x140051ec1  mov     rax, [rsi]
0x140051ec4  cmp     rax, [r15]
0x140051ec7  jg      short loc_140051ED4
0x140051ec9  mov     rcx, [r15]
0x140051ecc  mov     rax, [rsi]
0x140051ecf  cmp     rax, rcx
0x140051ed2  jge     short loc_140051EE0
0x140051ed4  mov     qword ptr [rsp+0F8h+NewFileSize], rax
0x140051ed9  mov     [rsp+0F8h+var_B3], r8b
0x140051ede  jmp     short loc_140051EE5
0x140051ee0  mov     qword ptr [rsp+0F8h+NewFileSize], rcx
0x140051ee5  mov     rax, qword ptr [rsp+0F8h+NewFileSize]
0x140051eea  sub     rax, [r15]
0x140051eed  mov     [rsp+0F8h+var_98], rax
0x140051ef2  jns     short loc_140051F23
0x140051ef4  mov     [rsp+0F8h+var_B7], r8b
0x140051ef9  mov     rcx, [rbx+1A8h]
0x140051f00  add     rcx, 8; SectionPointer
0x140051f04  lea     rdx, [rsp+0F8h+NewFileSize]; NewFileSize
0x140051f09  call    cs:__imp_MmCanFileBeTruncated
0x140051f10  nop     dword ptr [rax+rax+00h]
0x140051f15  xor     r11d, r11d
0x140051f18  test    al, al
0x140051f1a  jnz     short loc_140051F28
0x140051f1c  mov     eax, 0C0000243h
0x140051f21  jmp     short loc_140051EA3
0x140051f23  mov     [rsp+0F8h+var_B7], r11b
0x140051f28  mov     r13b, r11b
0x140051f2b  mov     [rsp+0F8h+var_B8], r11b
0x140051f30  mov     r8d, [rbx+0D4h]
0x140051f37  test    r8b, 2
0x140051f3b  jz      short loc_140051F77
0x140051f3d  mov     rax, [r12+10h]
0x140051f42  mov     eax, [rax+44h]
0x140051f45  sub     eax, [rbx+0E0h]
0x140051f4b  cmp     [rsi], rax
0x140051f4e  jle     short loc_140051F9D
0x140051f50  cmp     [rbx+28h], r11
0x140051f54  setnz   r9b
0x140051f58  mov     r8, [rsp+0F8h+FileObject]
0x140051f60  mov     rdx, rbx
0x140051f63  call    UdfDeEmbedFileData
0x140051f68  mov     r13b, 1
0x140051f6b  mov     r8d, [rbx+0D4h]
0x140051f72  xor     r11d, r11d
0x140051f75  jmp     short loc_140051FA0
0x140051f77  bt      r8d, 0Dh
0x140051f7c  jb      short loc_140051FA0
0x140051f7e  mov     rax, [r12+10h]
0x140051f83  mov     eax, [rax+44h]
0x140051f86  sub     eax, [rbx+0E0h]
0x140051f8c  cmp     [rsi], rax
0x140051f8f  jg      short loc_140051FA0
0x140051f91  cmp     qword ptr [rsp+0F8h+NewFileSize], r11
0x140051f96  jnz     short loc_140051FA0
0x140051f98  mov     [rsp+0F8h+var_B8], 1
0x140051f9d  mov     r14d, r11d
0x140051fa0  test    r8d, 2002h
0x140051fa7  jnz     loc_1400520CF
0x140051fad  cmp     [rdi+160h], r11
0x140051fb4  jnz     loc_140052147
0x140051fba  test    dword ptr [rdi+30h], 20000000h
0x140051fc1  jnz     loc_140052147
0x140051fc7  mov     esi, r11d
0x140051fca  mov     eax, [rbx+128h]
0x140051fd0  cmp     eax, r14d
0x140051fd3  jnb     short loc_140051FDC
0x140051fd5  mov     esi, r14d
0x140051fd8  sub     esi, eax
0x140051fda  inc     esi
0x140051fdc  mov     r8d, [rbx+148h]
0x140051fe3  cmp     esi, r8d
0x140051fe6  jz      loc_1400520CF
0x140051fec  mov     rcx, cs:WPP_GLOBAL_Control
0x140051ff3  lea     rax, WPP_GLOBAL_Control
0x140051ffa  cmp     rcx, rax
0x140051ffd  jz      short loc_140052023
0x140051fff  mov     eax, [rcx+2Ch]
0x140052002  test    al, 1
0x140052004  jz      short loc_140052023
0x140052006  mov     edx, 4Ch ; 'L'
0x14005200b  mov     dword ptr [rsp+0F8h+var_D8], r8d
0x140052010  mov     r9d, esi
0x140052013  lea     r8, WPP_3702783af02333f5d52357996bb663b1_Traceguids
0x14005201a  mov     rcx, [rcx+18h]
0x14005201e  call    WPP_SF_dd
0x140052023  lea     r12, [rdi+630h]
0x14005202a  mov     rcx, r12; FastMutex
0x14005202d  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140052034  nop     dword ptr [rax+rax+00h]
0x140052039  mov     rax, gs:188h
0x140052042  mov     [rdi+668h], rax
0x140052049  mov     r9d, [rbx+148h]
0x140052050  cmp     r9d, esi
0x140052053  jnb     short loc_1400520A4
0x140052055  xor     edx, edx
0x140052057  mov     rcx, rdi
0x14005205a  call    UdfAvailableFreeBlocks
0x14005205f  mov     edx, esi
0x140052061  sub     edx, r9d
0x140052064  cmp     edx, eax
0x140052066  jbe     short loc_1400520A4
0x140052068  mov     qword ptr [rdi+668h], 0
0x140052073  mov     rcx, r12; FastMutex
0x140052076  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14005207d  nop     dword ptr [rax+rax+00h]
0x140052082  test    r13b, r13b
0x140052085  jz      short loc_14005209A
0x140052087  mov     eax, [rbx+0D4h]
0x14005208d  btr     eax, 13h
0x140052091  or      eax, 2
0x140052094  mov     [rbx+0D4h], eax
0x14005209a  mov     eax, 0C000007Fh
0x14005209f  jmp     loc_140051EA3
0x1400520a4  mov     eax, esi
0x1400520a6  sub     eax, r9d
0x1400520a9  add     [rdi+2A0h], eax
0x1400520af  mov     [rbx+148h], esi
0x1400520b5  mov     qword ptr [rdi+668h], 0
0x1400520c0  mov     rcx, r12; FastMutex
0x1400520c3  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1400520ca  nop     dword ptr [rax+rax+00h]
0x1400520cf  mov     r13d, 1
0x1400520d5  xor     r12b, r12b
0x1400520d8  xor     al, al
0x1400520da  mov     byte ptr [rsp+0F8h+arg_20], al
0x1400520e1  mov     [rsp+0F8h+var_B6], al
0x1400520e5  mov     [rsp+0F8h+var_B4], al
0x1400520e9  mov     [rsp+0F8h+var_B2], al
0x1400520ed  mov     [rsp+0F8h+var_90], 0
0x1400520f6  mov     [rsp+0F8h+var_88], 0
0x1400520ff  mov     sil, [rsp+0F8h+var_B7]
0x140052104  test    sil, sil
0x140052107  jz      loc_14005220D
0x14005210d  mov     eax, [rbx+0D4h]
0x140052113  test    al, 2
0x140052115  jnz     loc_140052206
0x14005211b  bt      eax, 0Dh
0x14005211f  jnb     loc_1400521B0
0x140052125  mov     r8, qword ptr [rsp+0F8h+NewFileSize]
0x14005212a  mov     rdx, rbx
0x14005212d  mov     rcx, qword ptr [rsp+0F8h+arg_0]
0x140052135  call    UdfUnReserveSparseFileRegion
0x14005213a  test    eax, eax
0x14005213c  jns     loc_140052206
0x140052142  jmp     loc_140051EA3
0x140052147  mov     r10, [rsp+0F8h+var_98]
0x14005214c  mov     r13d, 1
0x140052152  test    r10, r10
0x140052155  jle     loc_1400520D5
0x14005215b  mov     ecx, [rdi+48h]
0x14005215e  mov     edx, [rdi+44h]
0x140052161  sub     edx, r13d
0x140052164  mov     r8, [r15]
0x140052167  mov     eax, [r12+1Ch]
0x14005216c  shr     eax, 4
0x14005216f  and     al, r13b
0x140052172  mov     r9, r8
0x140052175  and     r9, rdx
0x140052178  add     r9, r10
0x14005217b  add     r9, rdx
0x14005217e  not     rdx
0x140052181  and     r9, rdx
0x140052184  shr     r9, cl
0x140052187  shr     r8, cl
0x14005218a  mov     byte ptr [rsp+0F8h+var_C8], al
0x14005218e  mov     byte ptr [rsp+0F8h+var_D0], r13b
0x140052193  mov     [rsp+0F8h+var_D8], r11
0x140052198  mov     rdx, rbx
0x14005219b  mov     rcx, r12
0x14005219e  call    UdfSeqCacheReserveFileRegion
0x1400521a3  test    eax, eax
0x1400521a5  js      loc_140051EA3
0x1400521ab  jmp     loc_1400520D5
0x1400521b0  cmp     qword ptr [rdi+160h], 0
0x1400521b8  jnz     short loc_1400521C3
0x1400521ba  test    dword ptr [rdi+30h], 20000000h
0x1400521c1  jz      short loc_140052206
0x1400521c3  mov     ecx, [rdi+48h]
0x1400521c6  mov     eax, [rdi+44h]
0x1400521c9  sub     eax, r13d
0x1400521cc  mov     edx, eax
0x1400521ce  mov     r10d, eax
0x1400521d1  not     r10
0x1400521d4  mov     r8, qword ptr [rsp+0F8h+NewFileSize]
0x1400521d9  add     r8, rdx
0x1400521dc  and     r8, r10
0x1400521df  shr     r8, cl
0x1400521e2  mov     r9, [r15]
0x1400521e5  add     r9, rdx
0x1400521e8  and     r9, r10
0x1400521eb  shr     r9, cl
0x1400521ee  sub     r9d, r8d
0x1400521f1  mov     byte ptr [rsp+0F8h+var_D8], r13b
0x1400521f6  mov     rdx, rbx
0x1400521f9  mov     rcx, qword ptr [rsp+0F8h+arg_0]
0x140052201  call    UdfSeqCacheUnReserveFileRegion
0x140052206  mov     al, byte ptr [rsp+0F8h+arg_20]
0x14005220d  mov     r9d, [rbx+128h]
0x140052214  cmp     r9d, r14d
0x140052217  jbe     loc_14005232D
0x14005221d  mov     rcx, cs:WPP_GLOBAL_Control
0x140052224  lea     rax, WPP_GLOBAL_Control
0x14005222b  cmp     rcx, rax
0x14005222e  jz      short loc_14005224D
0x140052230  mov     eax, [rcx+2Ch]
0x140052233  test    r13b, al
  ... truncated ...
```
