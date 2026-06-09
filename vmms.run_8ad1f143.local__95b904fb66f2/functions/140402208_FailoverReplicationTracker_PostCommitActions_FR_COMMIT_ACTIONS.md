# FailoverReplicationTracker::PostCommitActions(_FR_COMMIT_ACTIONS *)

- ea: `0x140402208`
- end: `0x140402ee4`
- name: `?PostCommitActions@FailoverReplicationTracker@@IEAAXPEAU_FR_COMMIT_ACTIONS@@@Z`
- size: `3292`
- prototype: `void __fastcall(FailoverReplicationTracker *__hidden this, struct _FR_COMMIT_ACTIONS *)`
- caller_count: `3`
- callee_count: `37`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x1402aa6c0`
- `0x14033bbe4`
- `0x140533eb4`

## callees

- `0x140022640`
- `0x14004a3d8`
- `0x14004f3c4`
- `0x14005c630`
- `0x1400916d8`
- `0x14009bc08`
- `0x14009d144`
- `0x1400a9dc8`
- `0x1400b4590`
- `0x1400f682c`
- `0x1401586a4`
- `0x14017902c`
- `0x1401879a4`
- `0x14019b3fc`
- `0x1401a2a9c`
- `0x1401e34f8`
- `0x1401f3e34`
- `0x140212220`
- `0x14021566c`
- `0x140281220`
- `0x1402a6c54`
- `0x1402e909c`
- `0x140313400`
- `0x140319b38`
- `0x1403dd6f4`
- `0x140402208`
- `0x140403808`
- `0x140403840`
- `0x1404828e0`
- `0x140486529`
- `0x140497234`
- `0x1404d5640`
- `0x140522bdc`
- `0x14053047c`
- `0x1405364d8`
- `0x140581564`
- `0x1408aa010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x140402d8b`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x140402e06`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x140402d8b`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x140402e06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14040261a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14040294c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14040261a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14040294c`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x140402c9d`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x140402c9d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140402cc9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140402cc9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x140402e35`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x140402e35`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140402e4c`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140402e7e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140402e4c`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140402e7e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140402d6f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140402d6f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1404025a8`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1404028f4`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1404025a8`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1404028f4`

## string_xrefs

- `0x140402deb`: `onecore\vm\common\vml\VmReaderWriterLock.h`

## pseudocode

```c
void __fastcall FailoverReplicationTracker::PostCommitActions(
        FailoverReplicationTracker *this,
        struct _FR_COMMIT_ACTIONS *a2)
{
  int v4; // r15d
  unsigned __int64 i; // rbx
  int v6; // eax
  const struct _GUID *j; // rbx
  __m128i si128; // xmm6
  __int64 v9; // r14
  __int64 v10; // r12
  __int64 v11; // rcx
  int v12; // r13d
  __int64 v13; // r8
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // r8
  __int64 v17; // r9
  __int128 *v18; // r9
  const struct Vml::VmGuid *k; // rbx
  __int64 v20; // rcx
  int v21; // r14d
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rax
  __int64 v25; // r8
  __int64 v26; // r12
  __int64 v27; // r9
  __int128 *v28; // r9
  const struct Vml::VmGuid *m; // rbx
  int v30; // eax
  int v31; // ecx
  const WCHAR **v32; // r13
  const WCHAR *n; // rbx
  const WCHAR *v34; // rcx
  __int64 v35; // rdx
  __int64 v36; // rcx
  __int64 v37; // rax
  __int64 v38; // r8
  __int64 v39; // r9
  signed int LastError; // eax
  unsigned int v41; // r14d
  const WCHAR *v42; // rax
  struct VirtualHardDiskReference **v43; // r9
  const WCHAR *v44; // rax
  int v45; // eax
  __int64 v46; // rcx
  int v47; // eax
  unsigned int v48; // ebx
  __int64 v49; // rdx
  __int64 v50; // rax
  __int64 v51; // rcx
  __int64 v52; // rax
  __int64 v53; // r8
  __int64 v54; // r14
  __int64 v55; // r9
  struct VirtualHardDiskReference **v56; // r9
  int v57; // r13d
  __int64 ***v58; // r15
  __int64 v59; // rdx
  __int64 v60; // rcx
  __int64 v61; // rax
  __int64 v62; // r8
  __int64 v63; // r12
  __int64 v64; // r9
  __int64 v65; // rcx
  const WCHAR *v66; // rbx
  const WCHAR *v67; // rcx
  struct VirtualHardDiskReference **v68; // r8
  signed int v69; // eax
  unsigned int v70; // r14d
  const WCHAR *v71; // rax
  struct VirtualHardDiskReference **v72; // r9
  __int64 v73; // rax
  __int64 v74; // r11
  __int64 (__fastcall *v75)(__int64, struct VirtualHardDiskReference **, _QWORD, __int64, _QWORD, const WCHAR *); // r10
  int v76; // r15d
  struct VirtualHardDiskReference *ii; // rbx
  __int64 v78; // rdx
  __int64 v79; // rdx
  __int64 v80; // rcx
  __int64 v81; // rax
  __int64 v82; // r8
  __int64 v83; // rbx
  __int64 v84; // r9
  __int128 *v85; // r9
  __int64 v86; // rbx
  struct _TP_TIMER *v87; // rcx
  __int64 v88; // rax
  __int64 v89; // rax
  __int128 v90; // xmm0
  signed __int32 *v91; // r14
  signed __int32 v92; // eax
  signed __int32 v93; // ebx
  __int64 v94; // rax
  DWORD v95; // r15d
  signed __int32 v96; // edx
  __int64 v97; // rax
  char v98; // al
  unsigned int Value; // ebx
  __int128 v100; // xmm0
  unsigned int v101[2]; // [rsp+28h] [rbp-99h]
  const WCHAR *v102; // [rsp+30h] [rbp-91h]
  __int64 v103; // [rsp+38h] [rbp-89h] BYREF
  int v104; // [rsp+40h] [rbp-81h]
  __int128 Buf2; // [rsp+48h] [rbp-79h] BYREF
  struct VirtualHardDiskReference *v106[2]; // [rsp+58h] [rbp-69h] BYREF
  _BYTE v107[20]; // [rsp+68h] [rbp-59h]
  int v108; // [rsp+7Ch] [rbp-45h]
  __int128 v109; // [rsp+80h] [rbp-41h] BYREF
  __m128i v110; // [rsp+90h] [rbp-31h]
  struct _GUID Buf1; // [rsp+C0h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+120h] [rbp+5Fh]

  LODWORD(v103) = 0;
  v104 = 0;
  v4 = 0;
  (*(void (__fastcall **)(FailoverReplicationTracker *))(*(_QWORD *)this + 152LL))(this);
  if ( (*(unsigned int (__fastcall **)(FailoverReplicationTracker *))(*(_QWORD *)this + 392LL))(this) )
    (*(void (__fastcall **)(FailoverReplicationTracker *))(*(_QWORD *)this + 400LL))(this);
  for ( i = 0; i < 7; ++i )
  {
    Buf2 = 0;
    Buf1 = (struct _GUID)*((_OWORD *)a2 + i);
    if ( memcmp_0(&Buf1, &Buf2, 0x10u) )
    {
      v6 = FailoverReplicationTracker::DeleteRecoverySnapshot(this, &Buf1);
      *((_OWORD *)a2 + i) = 0;
      if ( !v6 )
        v4 = 1;
    }
  }
  for ( j = (const struct _GUID *)*((_QWORD *)a2 + 34); j != *((const struct _GUID **)a2 + 35); ++j )
  {
    if ( !(unsigned int)FailoverReplicationTracker::DeleteRecoverySnapshot(this, j) )
      v4 = 1;
  }
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v9 = 7;
  v10 = 4;
  do
  {
    v109 = 0;
    Buf2 = *((_OWORD *)a2 + v9);
    if ( memcmp_0(&Buf2, &v109, 0x10u) )
    {
      v11 = *((_QWORD *)this + 677) + 8LL + *(int *)(*(_QWORD *)(*((_QWORD *)this + 677) + 8LL) + 12LL);
      *(_OWORD *)v106 = *(_OWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 24LL))(v11);
      v12 = FrCtUtilities::DeleteRecoveryPoint((const struct Vml::VmGuid *)v106, (const struct Vml::VmGuid *)&Buf2, 0);
      if ( v12 < 0 )
      {
        v13 = *((_QWORD *)this + 677);
        v110 = si128;
        v109 = 0;
        LOWORD(v109) = 0;
        v14 = *(int *)(*(_QWORD *)(v13 + 8) + 12LL) + v13 + 8;
        v15 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 32LL))(v14);
        v16 = *((_QWORD *)this + 677);
        *(_QWORD *)&Buf2 = v15;
        v17 = *(int *)(*(_QWORD *)(v16 + 8) + 12LL);
        (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)(v17 + v16 + 8) + 8LL))(v17 + v16 + 8, &v109);
        if ( (unsigned int)VmlIsDebugTraceEnabled(33184) )
        {
          v18 = &v109;
          if ( v110.m128i_i64[1] > 7uLL )
            v18 = (__int128 *)v109;
          VmlDebugTraceWithError(33184, &off_14090CCE0, (unsigned int)v12, v18, Buf2);
        }
        std::wstring::_Tidy_deallocate(&v109);
      }
      *((_OWORD *)a2 + v9) = 0;
    }
    ++v9;
    --v10;
  }
  while ( v10 );
  for ( k = (const struct Vml::VmGuid *)*((_QWORD *)a2 + 22);
        k != *((const struct Vml::VmGuid **)a2 + 23);
        k = (const struct Vml::VmGuid *)((char *)k + 16) )
  {
    v20 = *((_QWORD *)this + 677) + 8LL + *(int *)(*(_QWORD *)(*((_QWORD *)this + 677) + 8LL) + 12LL);
    *(_OWORD *)v106 = *(_OWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v20 + 24LL))(v20);
    v21 = FrCtUtilities::DeleteRecoveryPoint((const struct Vml::VmGuid *)v106, k, 0);
    if ( v21 < 0 )
    {
      v22 = *((_QWORD *)this + 677);
      v110 = si128;
      LODWORD(v103) = 1;
      v109 = 0;
      LOWORD(v109) = 0;
      v23 = *(int *)(*(_QWORD *)(v22 + 8) + 12LL) + v22 + 8;
      v24 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v23 + 32LL))(v23);
      v25 = *((_QWORD *)this + 677);
      v26 = v24;
      v27 = *(int *)(*(_QWORD *)(v25 + 8) + 12LL);
      (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)(v27 + v25 + 8) + 8LL))(v27 + v25 + 8, &v109);
      if ( (unsigned int)VmlIsDebugTraceEnabled(33184) )
      {
        v28 = &v109;
        if ( v110.m128i_i64[1] > 7uLL )
          v28 = (__int128 *)v109;
        VmlDebugTraceWithError(33184, &off_14090CCC8, (unsigned int)v21, v28, v26);
      }
      std::wstring::_Tidy_deallocate(&v109);
    }
    *(_OWORD *)k = 0;
  }
  for ( m = (const struct Vml::VmGuid *)*((_QWORD *)a2 + 26);
        m != *((const struct Vml::VmGuid **)a2 + 27);
        m = (const struct Vml::VmGuid *)((char *)m + 16) )
  {
    v30 = FailoverReplicationTracker::DeleteContinuousDatapointReference(this, m);
    v31 = v104;
    if ( v30 < 0 )
      v31 = 1;
    *(_OWORD *)m = 0;
    v104 = v31;
  }
  v32 = (const WCHAR **)*((_QWORD *)a2 + 38);
  for ( n = (const WCHAR *)*((_QWORD *)a2 + 37); n != (const WCHAR *)v32; n += 16 )
  {
    if ( *((_QWORD *)n + 3) <= 7u )
      v34 = n;
    else
      v34 = *(const WCHAR **)n;
    if ( !DeleteFileW(v34) )
    {
      v35 = *((_QWORD *)this + 677);
      *(_OWORD *)v106 = 0;
      LOWORD(v106[0]) = 0;
      *(__m128i *)v107 = si128;
      v36 = v35 + 8 + *(int *)(*(_QWORD *)(v35 + 8) + 12LL);
      v37 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v36 + 32LL))(v36);
      v38 = *((_QWORD *)this + 677);
      *(_QWORD *)&Buf2 = v37;
      v39 = *(int *)(*(_QWORD *)(v38 + 8) + 12LL);
      (*(void (__fastcall **)(__int64, struct VirtualHardDiskReference **))(*(_QWORD *)(v39 + v38 + 8) + 8LL))(
        v39 + v38 + 8,
        v106);
      LastError = GetLastError();
      v41 = LastError;
      if ( LastError > 0 )
        v41 = (unsigned __int16)LastError | 0x80070000;
      if ( (unsigned int)VmlIsDebugTraceEnabled(16800) )
      {
        if ( *((_QWORD *)n + 3) <= 7u )
          v42 = n;
        else
          v42 = *(const WCHAR **)n;
        v43 = v106;
        v102 = v42;
        if ( *(_QWORD *)&v107[8] > 7u )
          v43 = (struct VirtualHardDiskReference **)v106[0];
        VmlDebugTraceWithError(16800, &off_1408C2C20, v41, v43, Buf2);
      }
      if ( *((_QWORD *)n + 3) <= 7u )
        v44 = n;
      else
        v44 = *(const WCHAR **)n;
      *(_QWORD *)&Buf2 = v44;
      LogVmErrorMessage1<unsigned short const *>(&MSVM_VMMS_VM_DELETE_FILE_WARNING, (__int64)&Buf2);
      std::wstring::_Tidy_deallocate(v106);
    }
  }
  std::vector<std::wstring>::clear((char *)a2 + 296);
  if ( v4 )
    FailoverReplicationTracker::KickOffOrphanedSnapshotsTimer(this);
  if ( v104 )
    FailoverReplicationTracker::KickOffOrphanedContinuousDataPointsTimer(this);
  if ( *((_DWORD *)a2 + 64) )
  {
    v45 = ReplicationDeltaTracker::RemoveDeltaFromApplyPendingQueue(*((ReplicationDeltaTracker **)this + 716));
    if ( v45 < 0 )
      *((_DWORD *)this + 1421) = v45;
    *((_DWORD *)a2 + 64) = 0;
  }
  if ( *((_DWORD *)a2 + 65) )
  {
    v46 = *((_QWORD *)this + 677) + 8LL + *(int *)(*(_QWORD *)(*((_QWORD *)this + 677) + 8LL) + 12LL);
    *(_OWORD *)v106 = *(_OWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v46 + 24LL))(v46);
    v47 = FrCtUtilities::DeleteUndoLogConfiguration((const struct Vml::VmGuid *)v106, 1);
    v48 = v47;
    if ( v47 < 0 && v47 != -2147188519 )
    {
      v49 = *((_QWORD *)this + 677);
      *(_OWORD *)v106 = 0;
      LOWORD(v106[0]) = 0;
      *(__m128i *)v107 = si128;
      v50 = *(_QWORD *)(v49 + 8);
      LODWORD(v103) = 1;
      v51 = v49 + 8 + *(int *)(v50 + 12);
      v52 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v51 + 32LL))(v51);
      v53 = *((_QWORD *)this + 677);
      v54 = v52;
      v55 = *(int *)(*(_QWORD *)(v53 + 8) + 12LL);
      (*(void (__fastcall **)(__int64, struct VirtualHardDiskReference **))(*(_QWORD *)(v55 + v53 + 8) + 8LL))(
        v55 + v53 + 8,
        v106);
      if ( (unsigned int)VmlIsDebugTraceEnabled(33184) )
      {
        v56 = v106;
        if ( *(_QWORD *)&v107[8] > 7u )
          v56 = (struct VirtualHardDiskReference **)v106[0];
        VmlDebugTraceWithError(33184, &off_14090CBF8, v48, v56, v54);
      }
      std::wstring::_Tidy_deallocate(v106);
    }
    *((_DWORD *)a2 + 65) = 0;
  }
  if ( *((_DWORD *)a2 + 66) )
  {
    v57 = 1;
    *((_DWORD *)a2 + 66) = 0;
  }
  else
  {
    v57 = v103;
  }
  v58 = (__int64 ***)((char *)a2 + 200);
  if ( *((_QWORD *)a2 + 25) )
  {
    v59 = *((_QWORD *)this + 677);
    *(_OWORD *)v106 = 0;
    LOWORD(v106[0]) = 0;
    *(__m128i *)v107 = si128;
    v60 = v59 + 8 + *(int *)(*(_QWORD *)(v59 + 8) + 12LL);
    v61 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v60 + 32LL))(v60);
    v62 = *((_QWORD *)this + 677);
    v63 = v61;
    v64 = *(int *)(*(_QWORD *)(v62 + 8) + 12LL);
    (*(void (__fastcall **)(__int64, struct VirtualHardDiskReference **))(*(_QWORD *)(v64 + v62 + 8) + 8LL))(
      v64 + v62 + 8,
      v106);
    v65 = ***v58;
    v103 = v65;
    while ( (__int64 *)v65 != **v58 )
    {
      v66 = (const WCHAR *)(v65 + 32);
      if ( *(_QWORD *)(v65 + 56) <= 7u )
        v67 = (const WCHAR *)(v65 + 32);
      else
        v67 = *(const WCHAR **)v66;
      if ( DeleteFileW(v67) )
      {
        if ( (unsigned int)VmlIsDebugTraceEnabled(49568) )
        {
          if ( *((_QWORD *)v66 + 3) > 7u )
            v66 = *(const WCHAR **)v66;
          v68 = v106;
          *(_QWORD *)v101 = v66;
          if ( *(_QWORD *)&v107[8] > 7u )
            v68 = (struct VirtualHardDiskReference **)v106[0];
          VmlDebugTraceEx(49568, &off_1408C2C08, v68, v63);
        }
      }
      else
      {
        v69 = GetLastError();
        v70 = v69;
        if ( v69 > 0 )
          v70 = (unsigned __int16)v69 | 0x80070000;
        if ( v70 != -2147024894 )
        {
          if ( (unsigned int)VmlIsDebugTraceEnabled(16800) )
          {
            if ( *((_QWORD *)v66 + 3) <= 7u )
              v71 = v66;
            else
              v71 = *(const WCHAR **)v66;
            v72 = v106;
            v102 = v71;
            if ( *(_QWORD *)&v107[8] > 7u )
              v72 = (struct VirtualHardDiskReference **)v106[0];
            VmlDebugTraceWithError(16800, &off_1408C2BF0, v70, v72, v63);
          }
          if ( *((_QWORD *)v66 + 3) > 7u )
            v66 = *(const WCHAR **)v66;
          *(_QWORD *)&Buf2 = v66;
          LogVmErrorMessage1<unsigned short const *>(&MSVM_VMMS_VM_DELETE_FILE_WARNING, (__int64)&Buf2);
        }
      }
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<Vml::VmGuid const,Vml::VmReferencePtr<IVmmsVirtualMachineObject,Vml::VmUserReferenceTraits>>>>,std::_Iterator_base0>::operator++(&v103);
      v65 = v103;
    }
    Vml::VmAutoArray<std::set<std::wstring,Vml::CaseInsensitiveLess,std::allocator<std::wstring>>>::Reset(
      (char *)a2 + 200,
      0);
    std::wstring::_Tidy_deallocate(v106);
  }
  FailoverReplicationTracker::ClearOperationalFlag<enum FailoverReplicationTracker::FrOperationalFlags>(this, 512);
  std::vector<std::wstring>::clear((char *)this + 4616);
  FailoverReplicationTracker::ClearOperationalFlag<enum FailoverReplicationTracker::FrOperationalFlags>(this, 1024);
  FailoverReplicationTracker::ClearOperationalFlag<enum FailoverReplicationTracker::FrOperationalFlags>(this, 0x10000);
  FailoverReplicationTracker::ClearOperationalFlag<enum FailoverReplicationTracker::FrOperationalFlags>(this, 0x40000);
  FailoverReplicationTracker::ClearOperationalFlag<enum FailoverReplicationTracker::FrOperationalFlags>(this, 0x100000);
  if ( v57 )
    goto LABEL_123;
  if ( *((_QWORD *)a2 + 29) != *((_QWORD *)a2 + 30) )
  {
    *(_QWORD *)v107 = 0;
    *(_OWORD *)v106 = 0;
    *(_QWORD *)&Buf2 = VirtualHardDiskReference::ExcludeSharedVhdFilter;
    v73 = std::function<bool (VirtualHardDiskReference const &)>::function<bool (VirtualHardDiskReference const &)>(
            &v109,
            &Buf2);
    v76 = v75(v74 + 8, v106, 0, v73, *(_QWORD *)v101, v102);
    if ( v76 < 0 )
      goto LABEL_117;
    for ( ii = v106[0]; ii != v106[1]; ii = (struct VirtualHardDiskReference *)((char *)ii + 184) )
    {
      if ( (unsigned int)FrUtilities::IsIncludedDisk((char *)ii + 64, (char *)a2 + 232) )
      {
        v78 = *((_QWORD *)this + 677);
        if ( v78 )
          v78 += *(int *)(*(_QWORD *)(v78 + 8) + 12LL) + 8LL;
        v76 = FrUtilities::RemoveVhdFromVm(ii, (struct IVmmsVirtualMachineObject *)v78);
        if ( v76 >= 0 )
          std::remove<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,std::wstring>(
            &Buf2,
            *((_QWORD *)a2 + 29),
            *((_QWORD *)a2 + 30),
            (char *)ii + 64);
      }
    }
    if ( v76 < 0 )
    {
LABEL_117:
      v79 = *((_QWORD *)this + 677);
      v109 = 0;
      LOWORD(v109) = 0;
      v57 = 1;
      v110 = si128;
      v80 = v79 + 8 + *(int *)(*(_QWORD *)(v79 + 8) + 12LL);
      v81 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v80 + 32LL))(v80);
      v82 = *((_QWORD *)this + 677);
      v83 = v81;
      v84 = *(int *)(*(_QWORD *)(v82 + 8) + 12LL);
      (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)(v84 + v82 + 8) + 8LL))(v84 + v82 + 8, &v109);
      if ( (unsigned int)VmlIsDebugTraceEnabled(33184) )
      {
        v85 = &v109;
        if ( v110.m128i_i64[1] > 7uLL )
          v85 = (__int128 *)v109;
        VmlDebugTraceWithError(33184, &off_14090CC10, (unsigned int)v76, v85, v83);
      }
      std::wstring::_Tidy_deallocate(&v109);
    }
    std::vector<VirtualHardDiskReference>::_Tidy(v106);
    if ( v57 )
    {
LABEL_123:
      if ( *((_QWORD *)a2 + 29) != *((_QWORD *)a2 + 30) )
      {
        *(_QWORD *)v107 = 0;
        *(_OWORD *)v106 = 0;
        std::vector<std::wstring>::operator=(v106, (char *)a2 + 232);
        if ( *((_QWORD *)this + 561) == *((_QWORD *)this + 562) )
        {
          std::vector<_FR_POST_COMMIT_PENDING_ACTIONS>::_Emplace_reallocate<_FR_POST_COMMIT_PENDING_ACTIONS const &>(
            (char *)this + 4480,
            *((_QWORD *)this + 561),
            v106);
        }
        else
        {
          std::vector<std::wstring>::vector<std::wstring>(*((_QWORD *)this + 561));
          *((_QWORD *)this + 561) += 24LL;
        }
        std::vector<std::wstring>::_Tidy(v106);
      }
      v103 = 0;
      if ( (unsigned __int8)Vml::VmSingletonObject<VmmsFailoverReplicationManager,VmmsFailoverReplicationManager>::TryOpenShared(&v103) )
      {
        v86 = v103;
        if ( !IsThreadpoolTimerSet(*(PTP_TIMER *)(v103 + 32)) )
        {
          v87 = *(struct _TP_TIMER **)(v86 + 32);
          *(_QWORD *)&Buf2 = -18000000000LL;
          SetThreadpoolTimer(v87, (PFILETIME)&Buf2, 0, 0);
        }
      }
      Vml::VmReferencePtr<FrCtSmartBitmapManager,Vml::VmUserReferenceTraits>::~VmReferencePtr<FrCtSmartBitmapManager,Vml::VmUserReferenceTraits>(&v103);
    }
  }
  v88 = *((_QWORD *)a2 + 26);
  if ( v88 != *((_QWORD *)a2 + 27) )
    *((_QWORD *)a2 + 27) = v88;
  v89 = *((_QWORD *)a2 + 34);
  if ( v89 != *((_QWORD *)a2 + 35) )
    *((_QWORD *)a2 + 35) = v89;
  if ( *((_DWORD *)a2 + 84) )
  {
    FailoverReplicationTracker::ClearOperationalFlag<enum FailoverReplicationTracker::FrOperationalFlags>(this, 0x80000);
    v108 = 0;
    *(GUID *)&v107[4] = GUID_NULL;
    v90 = *(_OWORD *)((char *)this + 4856);
    Buf2 = 0;
    *(_OWORD *)v106 = v90;
    *(_DWORD *)v107 = FailoverReplicationTracker::GetReplicationStateInternal(this);
    v91 = (signed __int32 *)((char *)this + 4720);
    v92 = _InterlockedCompareExchange((volatile signed __int32 *)this + 1180, 4, 0);
    v93 = v92;
    if ( v92 )
    {
      if ( (v92 & 1) != 0 && *((_DWORD *)this + 1181) == GetCurrentThreadId() )
      {
        _InterlockedIncrement((volatile signed __int32 *)this + 1182);
      }
      else
      {
        do
        {
          while ( (v93 & 1) != 0 )
          {
            if ( !(unsigned int)RrwpLockWait((char *)this + 4720, 0xFFFFFFFFLL, 0) )
              wil::details::in1diag3::Throw_Win32(
                retaddr,
                (void *)0x249,
                (unsigned int)"onecore\\vm\\common\\vml\\VmReaderWriterLock.h",
                (const char *)0x102,
                v101[0]);
            _m_prefetchw(v91);
            v93 = *v91;
          }
          v96 = v93;
          v93 = _InterlockedCompareExchange(v91, v93 + 4, v93);
        }
        while ( v93 != v96 );
      }
    }
    v94 = __RTtypeid(this);
    if ( (unsigned __int8)type_info::operator==(v94, &FailoverReplicationTracker `RTTI Type Descriptor') )
    {
      v95 = FailoverReplicationTracker::gm_FrTlsIndex;
    }
    else
    {
      v97 = __RTtypeid(this);
      v98 = type_info::operator==(v97, &ExtendedReplicationTracker `RTTI Type Descriptor');
      v95 = SharedReplicationTracker::gm_SrTlsIndex;
      if ( v98 )
        v95 = ExtendedReplicationTracker::gm_ErTlsIndex;
    }
    Value = (unsigned int)TlsGetValue(v95);
    TlsSetValue(v95, (LPVOID)(Value | 0x10LL));
    v100 = *((_OWORD *)a2 + 20);
    v108 = *((_DWORD *)this + 1200);
    *(_OWORD *)&v107[4] = v100;
    Buf2 = *((_OWORD *)this + 294);
    TlsSetValue(v95, (LPVOID)Value);
    RrwLockRelease((char *)this + 4720);
    FailoverReplicationTracker::QueueMessageToTimer(
      this,
      (unsigned __int8 *)v106,
      0x28u,
      (const struct Vml::VmGuid *)&Buf2,
      1);
    *((_DWORD *)a2 + 84) = 0;
  }
}

```

## disassembly

```asm
0x140402208  mov     rax, rsp
0x14040220b  mov     [rax+18h], rbx
0x14040220f  push    rbp
0x140402210  push    rsi
0x140402211  push    rdi
0x140402212  push    r12
0x140402214  push    r13
0x140402216  push    r14
0x140402218  push    r15
0x14040221a  lea     rbp, [rax-5Fh]
0x14040221e  sub     rsp, 0E0h
0x140402225  movaps  xmmword ptr [rax-48h], xmm6
0x140402229  mov     rax, cs:__security_cookie
0x140402230  xor     rax, rsp
0x140402233  mov     [rbp+57h+var_48], rax
0x140402237  xor     eax, eax
0x140402239  mov     rsi, rdx
0x14040223c  mov     dword ptr [rsp+110h+var_E0], eax
0x140402240  mov     rdi, rcx
0x140402243  mov     [rsp+110h+var_D8], eax
0x140402247  xor     r15d, r15d
0x14040224a  mov     rax, [rcx]
0x14040224d  mov     rax, [rax+98h]
0x140402254  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140402259  mov     rax, [rdi]
0x14040225c  mov     rcx, rdi
0x14040225f  mov     rax, [rax+188h]
0x140402266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14040226b  test    eax, eax
0x14040226d  jz      short loc_140402281
0x14040226f  mov     rax, [rdi]
0x140402272  mov     rcx, rdi
0x140402275  mov     rax, [rax+190h]
0x14040227c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140402281  xor     ebx, ebx
0x140402283  lea     r13d, [rbx+1]
0x140402287  xorps   xmm1, xmm1
0x14040228a  lea     rdx, [rbp+57h+Buf2]; Buf2
0x14040228e  mov     r14, rbx
0x140402291  lea     rcx, [rbp+57h+Buf1]; Buf1
0x140402295  add     r14, r14
0x140402298  mov     r8d, 10h; Size
0x14040229e  movups  [rbp+57h+Buf2], xmm1
0x1404022a2  movups  xmm0, xmmword ptr [rsi+r14*8]
0x1404022a7  movdqu  [rbp+57h+Buf1], xmm0
0x1404022ac  call    memcmp_0
0x1404022b1  test    eax, eax
0x1404022b3  jz      short loc_1404022D0
0x1404022b5  lea     rdx, [rbp+57h+Buf1]; struct _GUID *
0x1404022b9  mov     rcx, rdi; this
0x1404022bc  call    ?DeleteRecoverySnapshot@FailoverReplicationTracker@@AEBAHAEBU_GUID@@@Z; FailoverReplicationTracker::DeleteRecoverySnapshot(_GUID const &)
0x1404022c1  test    eax, eax
0x1404022c3  xorps   xmm0, xmm0
0x1404022c6  movdqu  xmmword ptr [rsi+r14*8], xmm0
0x1404022cc  cmovz   r15d, r13d
0x1404022d0  add     rbx, r13
0x1404022d3  cmp     rbx, 7
0x1404022d7  jb      short loc_140402287
0x1404022d9  mov     rbx, [rsi+110h]
0x1404022e0  cmp     rbx, [rsi+118h]
0x1404022e7  jz      short loc_140402300
0x1404022e9  mov     rdx, rbx; struct _GUID *
0x1404022ec  mov     rcx, rdi; this
0x1404022ef  call    ?DeleteRecoverySnapshot@FailoverReplicationTracker@@AEBAHAEBU_GUID@@@Z; FailoverReplicationTracker::DeleteRecoverySnapshot(_GUID const &)
0x1404022f4  test    eax, eax
0x1404022f6  cmovz   r15d, r13d
0x1404022fa  add     rbx, 10h
0x1404022fe  jmp     short loc_1404022E0
0x140402300  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x140402308  mov     r14d, 7
0x14040230e  lea     r12d, [r14-3]
0x140402312  xorps   xmm1, xmm1
0x140402315  lea     rdx, [rbp+57h+var_98]; Buf2
0x140402319  mov     rbx, r14
0x14040231c  lea     rcx, [rbp+57h+Buf2]; Buf1
0x140402320  add     rbx, rbx
0x140402323  mov     r8d, 10h; Size
0x140402329  movups  [rbp+57h+var_98], xmm1
0x14040232d  movups  xmm0, xmmword ptr [rsi+rbx*8]
0x140402331  movdqu  [rbp+57h+Buf2], xmm0
0x140402336  call    memcmp_0
0x14040233b  test    eax, eax
0x14040233d  jz      loc_140402438
0x140402343  mov     rdx, [rdi+1528h]
0x14040234a  mov     rax, [rdx+8]
0x14040234e  add     rdx, 8
0x140402352  movsxd  rcx, dword ptr [rax+0Ch]
0x140402356  add     rcx, rdx
0x140402359  mov     rax, [rcx]
0x14040235c  mov     rax, [rax+18h]
0x140402360  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140402365  xor     r8d, r8d; int
0x140402368  lea     rdx, [rbp+57h+Buf2]; struct Vml::VmGuid *
0x14040236c  lea     rcx, [rbp+57h+var_C0]; struct Vml::VmGuid *
0x140402370  movups  xmm0, xmmword ptr [rax]
0x140402373  movdqu  xmmword ptr [rbp+57h+var_C0], xmm0
0x140402378  call    ?DeleteRecoveryPoint@FrCtUtilities@@SAJAEBVVmGuid@Vml@@0H@Z; FrCtUtilities::DeleteRecoveryPoint(Vml::VmGuid const &,Vml::VmGuid const &,int)
0x14040237d  mov     r13d, eax
0x140402380  test    eax, eax
0x140402382  jns     loc_14040242A
0x140402388  mov     r8, [rdi+1528h]
0x14040238f  xor     ecx, ecx
0x140402391  movdqu  [rbp+57h+var_88], xmm6
0x140402396  xorps   xmm0, xmm0
0x140402399  movups  [rbp+57h+var_98], xmm0
0x14040239d  mov     word ptr [rbp+57h+var_98], cx
0x1404023a1  mov     rcx, [r8+8]
0x1404023a5  movsxd  rdx, dword ptr [rcx+0Ch]
0x1404023a9  lea     rcx, [r8+8]
0x1404023ad  add     rcx, rdx
0x1404023b0  mov     rax, [rcx]
0x1404023b3  mov     rax, [rax+20h]
0x1404023b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1404023bc  mov     r8, [rdi+1528h]
0x1404023c3  lea     rdx, [rbp+57h+var_98]
0x1404023c7  mov     qword ptr [rbp+57h+Buf2], rax
0x1404023cb  mov     rcx, [r8+8]
0x1404023cf  movsxd  r9, dword ptr [rcx+0Ch]
0x1404023d3  mov     rcx, [r9+r8+8]
0x1404023d8  mov     rax, [rcx+8]
0x1404023dc  lea     rcx, [r8+8]
0x1404023e0  add     rcx, r9
0x1404023e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1404023e8  mov     ecx, 81A0h
0x1404023ed  call    VmlIsDebugTraceEnabled
0x1404023f2  test    eax, eax
0x1404023f4  jz      short loc_140402421
0x1404023f6  cmp     qword ptr [rbp+57h+var_88+8], 7
0x1404023fb  lea     r9, [rbp+57h+var_98]
0x1404023ff  mov     rax, qword ptr [rbp+57h+Buf2]
0x140402403  lea     rdx, off_14090CCE0; "%ws::%ws Could not delete recovery poin"...
0x14040240a  cmova   r9, qword ptr [rbp+57h+var_98]
0x14040240f  mov     r8d, r13d
0x140402412  mov     ecx, 81A0h
0x140402417  mov     qword ptr [rsp+110h+var_F0], rax
0x14040241c  call    VmlDebugTraceWithError
0x140402421  lea     rcx, [rbp+57h+var_98]
0x140402425  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14040242a  xorps   xmm0, xmm0
0x14040242d  mov     r13d, 1
0x140402433  movdqu  xmmword ptr [rsi+rbx*8], xmm0
0x140402438  add     r14, r13
0x14040243b  sub     r12, r13
0x14040243e  jnz     loc_140402312
0x140402444  mov     rbx, [rsi+0B0h]
0x14040244b  cmp     rbx, [rsi+0B8h]
0x140402452  jz      loc_14040254E
0x140402458  mov     rdx, [rdi+1528h]
0x14040245f  mov     rax, [rdx+8]
0x140402463  add     rdx, 8
0x140402467  movsxd  rcx, dword ptr [rax+0Ch]
0x14040246b  add     rcx, rdx
0x14040246e  mov     rax, [rcx]
0x140402471  mov     rax, [rax+18h]
0x140402475  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14040247a  xor     r8d, r8d; int
0x14040247d  lea     rcx, [rbp+57h+var_C0]; struct Vml::VmGuid *
0x140402481  mov     rdx, rbx; struct Vml::VmGuid *
0x140402484  movups  xmm0, xmmword ptr [rax]
0x140402487  movdqu  xmmword ptr [rbp+57h+var_C0], xmm0
0x14040248c  call    ?DeleteRecoveryPoint@FrCtUtilities@@SAJAEBVVmGuid@Vml@@0H@Z; FrCtUtilities::DeleteRecoveryPoint(Vml::VmGuid const &,Vml::VmGuid const &,int)
0x140402491  mov     r14d, eax
0x140402494  test    eax, eax
0x140402496  jns     loc_14040253E
0x14040249c  mov     rdx, [rdi+1528h]
0x1404024a3  xor     ecx, ecx
0x1404024a5  movdqu  [rbp+57h+var_88], xmm6
0x1404024aa  mov     dword ptr [rsp+110h+var_E0], r13d
0x1404024af  xorps   xmm0, xmm0
0x1404024b2  movups  [rbp+57h+var_98], xmm0
0x1404024b6  mov     word ptr [rbp+57h+var_98], cx
0x1404024ba  mov     rcx, [rdx+8]
0x1404024be  movsxd  rax, dword ptr [rcx+0Ch]
0x1404024c2  lea     rcx, [rdx+8]
0x1404024c6  add     rcx, rax
0x1404024c9  mov     rax, [rcx]
0x1404024cc  mov     rax, [rax+20h]
0x1404024d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1404024d5  mov     r8, [rdi+1528h]
0x1404024dc  lea     rdx, [rbp+57h+var_98]
0x1404024e0  mov     r12, rax
0x1404024e3  mov     rcx, [r8+8]
0x1404024e7  movsxd  r9, dword ptr [rcx+0Ch]
0x1404024eb  mov     rcx, [r9+r8+8]
0x1404024f0  mov     rax, [rcx+8]
0x1404024f4  lea     rcx, [r8+8]
0x1404024f8  add     rcx, r9
0x1404024fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140402500  mov     ecx, 81A0h
0x140402505  call    VmlIsDebugTraceEnabled
0x14040250a  test    eax, eax
0x14040250c  jz      short loc_140402535
0x14040250e  cmp     qword ptr [rbp+57h+var_88+8], 7
0x140402513  lea     r9, [rbp+57h+var_98]
0x140402517  mov     r8d, r14d
0x14040251a  mov     qword ptr [rsp+110h+var_F0], r12
0x14040251f  cmova   r9, qword ptr [rbp+57h+var_98]
0x140402524  lea     rdx, off_14090CCC8; "%ws::%ws Could not delete recovery poin"...
0x14040252b  mov     ecx, 81A0h
0x140402530  call    VmlDebugTraceWithError
0x140402535  lea     rcx, [rbp+57h+var_98]
0x140402539  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14040253e  xorps   xmm0, xmm0
0x140402541  movdqu  xmmword ptr [rbx], xmm0
0x140402545  add     rbx, 10h
0x140402549  jmp     loc_14040244B
0x14040254e  mov     rbx, [rsi+0D0h]
0x140402555  cmp     rbx, [rsi+0D8h]
0x14040255c  jz      short loc_140402584
0x14040255e  mov     rdx, rbx; struct Vml::VmGuid *
0x140402561  mov     rcx, rdi; this
0x140402564  call    ?DeleteContinuousDatapointReference@FailoverReplicationTracker@@QEBAJAEBVVmGuid@Vml@@@Z; FailoverReplicationTracker::DeleteContinuousDatapointReference(Vml::VmGuid const &)
0x140402569  mov     ecx, [rsp+110h+var_D8]
0x14040256d  test    eax, eax
0x14040256f  xorps   xmm0, xmm0
0x140402572  cmovs   ecx, r13d
0x140402576  movdqu  xmmword ptr [rbx], xmm0
0x14040257a  mov     [rsp+110h+var_D8], ecx
0x14040257e  add     rbx, 10h
0x140402582  jmp     short loc_140402555
0x140402584  lea     r12, [rsi+128h]
0x14040258b  mov     r13, [r12+8]
0x140402590  mov     rbx, [r12]
0x140402594  jmp     loc_1404026DF
0x140402599  cmp     qword ptr [rbx+18h], 7
0x14040259e  jbe     short loc_1404025A5
0x1404025a0  mov     rcx, [rbx]
0x1404025a3  jmp     short loc_1404025A8
0x1404025a5  mov     rcx, rbx; lpFileName
0x1404025a8  call    cs:__imp_DeleteFileW
0x1404025af  nop     dword ptr [rax+rax+00h]
0x1404025b4  test    eax, eax
0x1404025b6  jnz     loc_1404026DB
0x1404025bc  mov     rdx, [rdi+1528h]
0x1404025c3  xorps   xmm0, xmm0
0x1404025c6  movups  xmmword ptr [rbp+57h+var_C0], xmm0
0x1404025ca  mov     word ptr [rbp+57h+var_C0], ax
0x1404025ce  movdqu  xmmword ptr [rbp+57h+var_B0], xmm6
0x1404025d3  mov     rax, [rdx+8]
0x1404025d7  add     rdx, 8
0x1404025db  movsxd  rcx, dword ptr [rax+0Ch]
0x1404025df  add     rcx, rdx
0x1404025e2  mov     rax, [rcx]
0x1404025e5  mov     rax, [rax+20h]
0x1404025e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1404025ee  mov     r8, [rdi+1528h]
0x1404025f5  lea     rdx, [rbp+57h+var_C0]
0x1404025f9  mov     qword ptr [rbp+57h+Buf2], rax
0x1404025fd  mov     rcx, [r8+8]
0x140402601  movsxd  r9, dword ptr [rcx+0Ch]
0x140402605  mov     rcx, [r9+r8+8]
0x14040260a  mov     rax, [rcx+8]
0x14040260e  lea     rcx, [r8+8]
0x140402612  add     rcx, r9
0x140402615  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14040261a  call    cs:__imp_GetLastError
0x140402621  nop     dword ptr [rax+rax+00h]
0x140402626  mov     r14d, eax
0x140402629  test    eax, eax
0x14040262b  jle     short loc_140402638
0x14040262d  movzx   r14d, ax
0x140402631  or      r14d, 80070000h
0x140402638  mov     ecx, 41A0h
0x14040263d  call    VmlIsDebugTraceEnabled
0x140402642  test    eax, eax
0x140402644  jz      short loc_140402685
0x140402646  cmp     qword ptr [rbx+18h], 7
0x14040264b  jbe     short loc_140402652
0x14040264d  mov     rax, [rbx]
0x140402650  jmp     short loc_140402655
0x140402652  mov     rax, rbx
0x140402655  cmp     qword ptr [rbp+57h+var_B0+8], 7
0x14040265a  lea     r9, [rbp+57h+var_C0]
0x14040265e  mov     [rsp+110h+var_E8], rax
0x140402663  lea     rdx, off_1408C2C20; "%ws::%ws Failed to delete vm data file "...
0x14040266a  mov     rax, qword ptr [rbp+57h+Buf2]
0x14040266e  mov     r8d, r14d
0x140402671  cmova   r9, [rbp+57h+var_C0]
0x140402676  mov     ecx, 41A0h
0x14040267b  mov     qword ptr [rsp+110h+var_F0], rax
0x140402680  call    VmlDebugTraceWithError
0x140402685  cmp     qword ptr [rbx+18h], 7
0x14040268a  jbe     short loc_140402691
0x14040268c  mov     rax, [rbx]
0x14040268f  jmp     short loc_140402694
0x140402691  mov     rax, rbx
0x140402694  mov     rdx, [rdi+1528h]
0x14040269b  mov     qword ptr [rbp+57h+Buf2], rax
0x14040269f  test    rdx, rdx
0x1404026a2  jnz     short loc_1404026A9
0x1404026a4  xor     r8d, r8d
0x1404026a7  jmp     short loc_1404026B8
0x1404026a9  mov     rax, [rdx+8]
0x1404026ad  movsxd  r8, dword ptr [rax+0Ch]
0x1404026b1  add     r8, 8
0x1404026b5  add     r8, rdx
0x1404026b8  lea     rax, [rbp+57h+Buf2]
0x1404026bc  mov     r9d, r14d
0x1404026bf  xor     edx, edx
0x1404026c1  mov     qword ptr [rsp+110h+var_F0], rax; __int64
  ... truncated ...
```
