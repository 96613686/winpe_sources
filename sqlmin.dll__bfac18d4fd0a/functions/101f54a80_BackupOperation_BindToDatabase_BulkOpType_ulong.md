# BackupOperation::BindToDatabase(BulkOpType,ulong)

- ea: `0x101f54a80`
- end: `0x101f55e9e`
- name: `?BindToDatabase@BackupOperation@@QEAAXW4BulkOpType@@K@Z`
- size: `5150`
- prototype: ``
- caller_count: `4`
- callee_count: `31`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x101f68510`
- `0x101f6b990`
- `0x1020446a0`
- `0x10204e550`

## callees

- `0x100401490`
- `0x100402200`
- `0x1004049f0`
- `0x100415c30`
- `0x100426ff0`
- `0x10042d9c0`
- `0x1004ab250`
- `0x100569d30`
- `0x1005737d0`
- `0x1005f1f00`
- `0x10072d4d0`
- `0x10072d690`
- `0x100ac2160`
- `0x100ac2440`
- `0x100ac3270`
- `0x100ac3490`
- `0x100ac3700`
- `0x10171f610`
- `0x101cb2900`
- `0x101eb6990`
- `0x101f54710`
- `0x101f54760`
- `0x101f54a80`
- `0x101f67cf0`
- `0x101f726e0`
- `0x101f72da0`
- `0x101f736b0`
- `0x101f73c90`
- `0x101fed5e0`
- `0x101ff4750`
- `0x1023ae3e0`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x101f55104`
- `KERNEL32!QueryPerformanceCounter` at `0x101f55172`
- `KERNEL32!QueryPerformanceCounter` at `0x101f55104`
- `KERNEL32!QueryPerformanceCounter` at `0x101f55172`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x101f551e4`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x101f550a2`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x101f55134`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101f550f0`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101f5515e`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x101f54c6a`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x101f54fc2`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x101f54fe6`
- `sqldk!?SetDeadlockPriority@SOS_Task@@QEAAXW4TASK_DEADLOCK_PRIORITY@1@@Z` at `0x101f55a33`
- `sqldk!?SetDeadlockPriority@SOS_Task@@QEAAXW4TASK_DEADLOCK_PRIORITY@1@@Z` at `0x101f55bba`
- `sqldk!?SetDeadlockPriority@SOS_Task@@QEAAXW4TASK_DEADLOCK_PRIORITY@1@@Z` at `0x101f55a33`
- `sqldk!?SetDeadlockPriority@SOS_Task@@QEAAXW4TASK_DEADLOCK_PRIORITY@1@@Z` at `0x101f55bba`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x101f54d94`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x101f54d94`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f54b24`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f54b80`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f556f9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f55c91`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f55e8a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f54b24`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f54b80`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f556f9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f55c91`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f55e8a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101f54d25`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101f54e3d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101f54f8e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101f55011`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101f55337`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101f55423`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101f554f5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101f555a0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101f555d9`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101f5563c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101f556b8`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101f55774`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101f55984`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101f55c5e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101f55cb6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101f55de8`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101f55e18`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101f55e50`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101f54d25`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101f54e3d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101f54f8e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101f55011`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101f55337`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101f55423`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101f554f5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101f555a0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101f555d9`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101f5563c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101f556b8`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101f55774`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101f55984`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101f55c5e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101f55cb6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101f55de8`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101f55e18`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101f55e50`
- `sqldk!SystemThread_TlsIndex` at `0x101f54d5c`
- `sqldk!SystemThread_TlsIndex` at `0x101f54db0`
- `sqldk!SystemThread_TlsIndex` at `0x101f54dee`
- `sqldk!SystemThread_TlsIndex` at `0x101f54e73`
- `sqldk!SystemThread_TlsIndex` at `0x101f550c2`
- `sqldk!SystemThread_TlsIndex` at `0x101f557d9`
- `sqldk!SystemThread_TlsIndex` at `0x101f55993`
- `sqldk!SystemThread_TlsIndex` at `0x101f559c7`
- `sqldk!SystemThread_TlsIndex` at `0x101f559f8`
- `sqldk!SystemThread_TlsIndex` at `0x101f55a49`
- `sqldk!SystemThread_TlsIndex` at `0x101f55b1a`
- `sqldk!SystemThread_TlsIndex` at `0x101f55b4e`
- `sqldk!SystemThread_TlsIndex` at `0x101f55b7f`
- `sqldk!SystemThread_TlsIndex` at `0x101f55bd0`
- `sqldk!SystemThread_TlsIndex` at `0x101f55cfa`
- `sqldk!SystemThread_TlsOffset` at `0x101f54d65`
- `sqldk!SystemThread_TlsOffset` at `0x101f54db9`
- `sqldk!SystemThread_TlsOffset` at `0x101f54df7`
- `sqldk!SystemThread_TlsOffset` at `0x101f54e7c`
- `sqldk!SystemThread_TlsOffset` at `0x101f550cb`
- `sqldk!SystemThread_TlsOffset` at `0x101f557e2`
- `sqldk!SystemThread_TlsOffset` at `0x101f5599c`
- `sqldk!SystemThread_TlsOffset` at `0x101f559d0`
- `sqldk!SystemThread_TlsOffset` at `0x101f55a01`
- `sqldk!SystemThread_TlsOffset` at `0x101f55a52`
- `sqldk!SystemThread_TlsOffset` at `0x101f55b23`
- `sqldk!SystemThread_TlsOffset` at `0x101f55b57`
- `sqldk!SystemThread_TlsOffset` at `0x101f55b88`
- `sqldk!SystemThread_TlsOffset` at `0x101f55bd9`
- `sqldk!SystemThread_TlsOffset` at `0x101f55d03`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101f54d7e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101f55a1a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101f55a6d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101f55ba1`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101f55bf4`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101f54d7e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101f55a1a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101f55a6d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101f55ba1`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101f55bf4`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x101f551f0`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x101f551f0`
- `sqllang!?GetEncryptorType@CSECDEK@@QEAAPEB_WPEA_K@Z` at `0x101f54f2c`
- `sqllang!?GetEncryptorType@CSECDEK@@QEAAPEB_WPEA_K@Z` at `0x101f54f2c`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x101f54dd6`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x101f54e57`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x101f54f94`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x101f54dd6`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x101f54e57`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x101f54f94`
- `sqllang!?Release@CSECDEK@@QEAAXXZ` at `0x101f553dc`
- `sqllang!?Release@CSECDEK@@QEAAXXZ` at `0x101f553dc`

## string_xrefs

- `0x101f556ef`: `CanBackupLogForceAccess ()`
- `0x101f55e67`: `Invalid command type`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall BackupOperation::BindToDatabase(signed __int64 a1, unsigned int a2, int a3)
{
  unsigned int v6; // r12d
  char v7; // r13
  int v8; // edx
  unsigned int v9; // r8d
  bool v10; // si
  unsigned int v11; // ecx
  __int64 v12; // rax
  int v13; // ecx
  __int64 v14; // rdx
  unsigned int v15; // ecx
  __int64 v16; // rdx
  __int64 v17; // rbx
  struct Worker *v18; // rcx
  _QWORD *ThreadLocalStoragePointer; // rdx
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rcx
  struct CSECDEK *DEKWithRef; // rax
  unsigned __int64 v24; // rdx
  __int64 v25; // rcx
  CSECDEK *v26; // r12
  bool v27; // bl
  const wchar_t *EncryptorType; // rax
  const wchar_t *v29; // rcx
  wchar_t v30; // r8
  bool v31; // cf
  __int64 v32; // rbx
  __int64 v33; // rcx
  volatile signed __int64 *v34; // r13
  DirtyPageMgr *QuadPart; // rbx
  signed __int64 UniqueThread_low; // rdx
  __int64 v37; // r12
  __int64 v38; // r8
  DirtyPageMgr *v39; // rax
  signed __int64 v40; // rcx
  __int64 v41; // rbx
  int v42; // eax
  __int64 v43; // rcx
  unsigned int v44; // ebx
  __int64 v45; // rcx
  __int64 v46; // rcx
  __int64 v47; // rdx
  __int64 v48; // rcx
  __int64 v49; // rcx
  __int64 v50; // rdx
  __int64 v51; // rcx
  RecoveryUnit *v52; // rcx
  __int64 v53; // rcx
  __int64 v54; // rdx
  __int64 v55; // rcx
  __int64 v56; // rcx
  __int64 v57; // rbx
  int v58; // edx
  unsigned __int16 v59; // dx
  __int64 v60; // rdx
  __int64 v61; // rax
  __int64 v62; // rax
  __int64 v63; // rax
  struct RecoveryUnit *v64; // rcx
  unsigned int v65; // ebx
  struct XDES *Transaction; // rax
  volatile signed __int32 *v67; // rcx
  struct RecoveryUnit *v68; // rcx
  __int64 v69; // r8
  LSN *RedoneLSN; // rax
  DWORD v71; // eax
  __int64 v72; // rdx
  __int64 v73; // rbx
  __int64 v74; // rcx
  __int64 v75; // rbx
  __int64 v76; // rdx
  __int64 v77; // rax
  __int64 v78; // rcx
  __int64 v79; // rcx
  __int64 v80; // rbx
  __int64 v81; // rcx
  __int64 v82; // rbx
  __int64 v83; // rdx
  __int64 v84; // rax
  __int64 v85; // rcx
  signed __int64 v86; // r13
  __int64 v87; // rax
  __int64 v88; // r9
  __int64 result; // rax
  DBTABLE *v90; // rax
  int IsDatabaseOnlineNotStandby; // eax
  BackupRestoreSynchronization *v92; // rcx
  unsigned int *v93; // [rsp+20h] [rbp-488h]
  unsigned __int8 *v94; // [rsp+30h] [rbp-478h]
  rsize_t DestinationSize; // [rsp+48h] [rbp-460h]
  rsize_t DestinationSizea; // [rsp+48h] [rbp-460h]
  unsigned __int8 v97; // [rsp+70h] [rbp-438h] BYREF
  unsigned __int8 v98[7]; // [rsp+71h] [rbp-437h] BYREF
  signed __int64 v99; // [rsp+78h] [rbp-430h]
  unsigned __int16 v100[2]; // [rsp+80h] [rbp-428h] BYREF
  int v101; // [rsp+84h] [rbp-424h] BYREF
  unsigned int v102; // [rsp+88h] [rbp-420h] BYREF
  unsigned int v103; // [rsp+8Ch] [rbp-41Ch]
  signed __int64 v104; // [rsp+90h] [rbp-418h]
  CSECDEK *v105; // [rsp+98h] [rbp-410h]
  __int64 v106; // [rsp+A0h] [rbp-408h]
  int v107; // [rsp+A8h] [rbp-400h] BYREF
  unsigned int v108; // [rsp+ACh] [rbp-3FCh] BYREF
  unsigned int v109; // [rsp+B0h] [rbp-3F8h] BYREF
  char v110[4]; // [rsp+B4h] [rbp-3F4h] BYREF
  signed __int64 v111; // [rsp+B8h] [rbp-3F0h]
  LSN v112; // [rsp+C0h] [rbp-3E8h] BYREF
  DWORD LowPart; // [rsp+C8h] [rbp-3E0h]
  unsigned __int64 v114; // [rsp+D0h] [rbp-3D8h] BYREF
  unsigned int v115; // [rsp+D8h] [rbp-3D0h] BYREF
  unsigned int v116; // [rsp+DCh] [rbp-3CCh] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+E0h] [rbp-3C8h] BYREF
  LARGE_INTEGER v118; // [rsp+E8h] [rbp-3C0h] BYREF
  unsigned __int64 v119; // [rsp+F0h] [rbp-3B8h] BYREF
  unsigned __int64 v120; // [rsp+F8h] [rbp-3B0h] BYREF
  unsigned __int64 v121; // [rsp+100h] [rbp-3A8h] BYREF
  unsigned int v122; // [rsp+108h] [rbp-3A0h]
  unsigned int v123[4]; // [rsp+110h] [rbp-398h] BYREF
  _BYTE v124[32]; // [rsp+120h] [rbp-388h] BYREF
  _QWORD v125[2]; // [rsp+140h] [rbp-368h] BYREF
  __int128 v126; // [rsp+150h] [rbp-358h]
  __int16 v127; // [rsp+160h] [rbp-348h]
  DBMgr *v128; // [rsp+168h] [rbp-340h]
  __int64 v129; // [rsp+170h] [rbp-338h]
  struct CSECDEK *v130; // [rsp+178h] [rbp-330h]
  __int64 v131; // [rsp+188h] [rbp-320h]
  char v132[40]; // [rsp+190h] [rbp-318h] BYREF
  unsigned int v133[6]; // [rsp+1B8h] [rbp-2F0h] BYREF
  wchar_t v134[48]; // [rsp+1D0h] [rbp-2D8h] BYREF
  wchar_t v135[48]; // [rsp+230h] [rbp-278h] BYREF
  unsigned __int8 Destination[4]; // [rsp+290h] [rbp-218h] BYREF
  unsigned int v137; // [rsp+294h] [rbp-214h]

  v131 = -2;
  v103 = a2;
  v99 = a1;
  v111 = a1;
  v104 = a1;
  LODWORD(v105) = a2;
  v6 = 2 * ((__int64)(*(_QWORD *)(a1 + 168) - *(_QWORD *)(a1 + 176)) >> 1);
  v7 = 0;
  if ( !*(_DWORD *)(a1 + 5264) )
    utassert_fail(1u, "IsDatabaseIdKnown ()", "backup.cpp", 103, 0);
  if ( !(unsigned int)BackupOperation::IsDatabaseLocked((BackupOperation *)a1) && v8 != 1 )
  {
    if ( (unsigned int)IsReplicatedMasterEnabled() || (unsigned int)IsContainedAGEnabledInstance() )
      IsContainedAGEnabledInstance();
    utassert_fail(1u, "IsDatabaseLocked () || IsMaster ()", "backup.cpp", 104, 0);
    v9 = *(_DWORD *)(a1 + 5264);
  }
  v10 = (a3 & 8) == 0;
  switch ( *(_DWORD *)(a1 + 2260) )
  {
    case 1:
    case 2:
      v11 = *(_DWORD *)(a1 + 5264);
      if ( v11 == 32764 )
      {
        v12 = *((_QWORD *)qword_10316ECA0 + 13);
      }
      else if ( *(_DWORD *)(a1 + 5264) == 32765 )
      {
        v12 = *((_QWORD *)qword_10316ECA0 + 14);
      }
      else if ( *(_DWORD *)(a1 + 5264) == 0x7FFF )
      {
        v12 = *((_QWORD *)qword_10316ECA0 + 11);
      }
      else
      {
        if ( v11 > *((_DWORD *)qword_10316ECA0 + 19) || !v11 )
          goto LABEL_23;
        _mm_lfence();
        v12 = *(_QWORD *)(*((_QWORD *)qword_10316ECA0 + 5) + 8LL * (int)(v11 - 1));
      }
      if ( v12 )
      {
        v13 = a3 | 0x1000;
        if ( !*(_BYTE *)(*(_QWORD *)(v12 + 4624) + 8272LL) )
          v13 = a3;
        a3 = v13;
        goto LABEL_26;
      }
LABEL_23:
      if ( *(int *)(a1 + 5268) >= 0 && *(_BYTE *)(a1 + 5272) )
      {
        v7 = 1;
        AutoDbLock::~AutoDbLock((AutoDbLock *)(a1 + 5268));
      }
LABEL_26:
      LODWORD(v106) = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, __int64, int, char, bool, char))g_dbtableFactory[5])(
                        0,
                        *(_QWORD *)(a1 + 176),
                        v6,
                        20,
                        a3,
                        1,
                        v10,
                        1);
      if ( !(_DWORD)v106 )
      {
        *(_QWORD *)(a1 + 5152) = 0;
LABEL_42:
        ex_raise(30, 0, 25, 1);
        goto LABEL_43;
      }
      if ( v7 )
      {
        LOBYTE(v14) = 3;
        BackupRestoreSynchronization::LockDatabase(a1 + 5256, v14, 20000, 0);
      }
      v15 = *(_DWORD *)(a1 + 5264);
      v122 = v15;
      v128 = qword_10316ECA0;
      switch ( v15 )
      {
        case 0x7FFCu:
          v16 = *((_QWORD *)qword_10316ECA0 + 13);
          break;
        case 0x7FFDu:
          v16 = *((_QWORD *)qword_10316ECA0 + 14);
          break;
        case 0x7FFFu:
          v16 = *((_QWORD *)qword_10316ECA0 + 11);
          break;
        default:
          if ( v15 <= *((_DWORD *)qword_10316ECA0 + 19) && v15 )
            v16 = *(_QWORD *)(*((_QWORD *)qword_10316ECA0 + 5) + 8LL * (int)(v15 - 1));
          else
            v16 = 0;
          break;
      }
      v129 = v16;
      *(_QWORD *)(a1 + 5152) = v16;
      if ( !v16 )
        goto LABEL_42;
LABEL_43:
      v17 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v18 = *(struct Worker **)(v17 + 256);
      if ( !v18 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v18 = *(struct Worker **)(v17 + 256);
      }
      if ( *((_DWORD *)v18 + 139) )
        ExceptionPostCatchActions(v18);
      if ( dword_1031852C8 )
      {
        ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
        v20 = *(_QWORD *)(*(_QWORD *)(ThreadLocalStoragePointer[SystemThread_TlsIndex] + SystemThread_TlsOffset) + 72LL);
        if ( (*(_BYTE *)(v20 + 270) & 2) == 0 )
        {
          if ( !*(_BYTE *)(CFeatureSwitchesLangSvc::GetCurrentInstance(v20, ThreadLocalStoragePointer) + 636)
            || (ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer,
                v20 = *(_QWORD *)(*(_QWORD *)(ThreadLocalStoragePointer[SystemThread_TlsIndex] + SystemThread_TlsOffset)
                                + 72LL),
                *(_DWORD *)(v20 + 636)) )
          {
            if ( *(_DWORD *)(a1 + 2268) != 68 || (*(_DWORD *)(a1 + 5636) & 0x80000) == 0 )
              ex_raise(419, 4, 16, 2);
          }
        }
        if ( dword_1031852C8 )
        {
          if ( *(_BYTE *)(CFeatureSwitchesLangSvc::GetCurrentInstance(v20, ThreadLocalStoragePointer) + 263) )
          {
            if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                     + SystemThread_TlsIndex)
                                                   + SystemThread_TlsOffset)
                                       + 72LL)
                           + 270LL)
                & 2) == 0 )
            {
              v21 = *(_QWORD *)(a1 + 5856);
              if ( v21 )
              {
                v22 = *(_QWORD *)(v21 + 392);
                if ( v22 )
                {
                  if ( *(_DWORD *)(v22 + 548) == 9
                    && *(_DWORD *)(a1 + 2268) == 68
                    && (*(_DWORD *)(a1 + 5636) & 0x80000) != 0 )
                  {
                    DEKWithRef = DBTABLE::GetDEKWithRef(*(DBTABLE **)(a1 + 5152));
                    v26 = DEKWithRef;
                    v105 = DEKWithRef;
                    v130 = DEKWithRef;
                    v27 = 0;
                    if ( DEKWithRef && *((_BYTE *)DEKWithRef + 608) )
                    {
                      v114 = 0;
                      EncryptorType = CSECDEK::GetEncryptorType(DEKWithRef, &v114);
                      v24 = v114;
                      v29 = L"CERTIFICATE";
                      if ( v114 )
                      {
                        while ( 1 )
                        {
                          v30 = *(const wchar_t *)((char *)v29 + (char *)EncryptorType - (char *)L"CERTIFICATE");
                          v31 = v30 < *v29;
                          if ( v30 != *v29 )
                            break;
                          ++v29;
                          if ( !--v24 )
                            goto LABEL_67;
                        }
                        v25 = 1;
                        v24 = 0xFFFFFFFFLL;
                        if ( v31 )
                          v25 = 0xFFFFFFFFLL;
                      }
                      else
                      {
LABEL_67:
                        v25 = 0;
                      }
                      v27 = (_DWORD)v25 == 0;
                      if ( (*(_BYTE *)v26 & 0x1F) != 1 && !(_DWORD)v25 )
                        ex_raise(419, 22, 16, 1);
                    }
                    if ( *(_BYTE *)(CFeatureSwitchesLangSvc::GetCurrentInstance(v25, v24) + 264) )
                    {
                      if ( v27 )
                      {
                        v107 = 0;
                        v32 = ((__int64 (__fastcall *)(_QWORD, int *))g_dbtableFactory[2])(
                                *(_QWORD *)(a1 + 5152),
                                &v107);
                        v101 = 0;
                        ((void (__fastcall *)(_QWORD, int *))g_dbtableFactory[2])(*(_QWORD *)(a1 + 5152), &v101);
                        LODWORD(v93) = v101;
                        ex_raise(419, 38, 16, 1, v93, v32);
                      }
                      v33 = *(_QWORD *)(a1 + 5152);
                      v111 = *(_QWORD *)(v33 + 4624);
                      v106 = *(_QWORD *)(v111 + 1736);
                      v125[0] = *(_QWORD *)(v111 + 1696);
                      v125[1] = v106;
                      v127 = 0;
                      v126 = 0;
                      v34 = (volatile signed __int64 *)(v33 + 5376);
                      QuadPart = 0;
                      UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
                      v104 = UniqueThread_low;
                      if ( *(_DWORD *)(v33 + 5376) || _InterlockedCompareExchange64(v34, UniqueThread_low, 0) )
                      {
                        v37 = 0;
                        if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
                        {
                          v38 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                              + SystemThread_TlsOffset;
                          if ( v38 && *(_QWORD *)(v38 + 272) == v38 )
                            v37 = *(_QWORD *)(v38 + 256);
                          if ( v37 )
                          {
                            if ( Base_PublicGlobals::sm_invariantTscAvailable )
                            {
                              QueryPerformanceCounter(&PerformanceCount);
                              QuadPart = (DirtyPageMgr *)PerformanceCount.QuadPart;
                            }
                            else
                            {
                              QuadPart = MEMORY[0x7FFE0008];
                            }
                          }
                          UniqueThread_low = v104;
                        }
                        if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
                          Spinlock<148,10,258>::SpinToAcquireWithExponentialBackoff(v34, UniqueThread_low);
                        else
                          Spinlock<148,10,258>::SpinToAcquireOptimistic(v34, v37, UniqueThread_low);
                        if ( v37 )
                        {
                          if ( Base_PublicGlobals::sm_invariantTscAvailable )
                          {
                            QueryPerformanceCounter(&v118);
                            v39 = (DirtyPageMgr *)v118.QuadPart;
                          }
                          else
                          {
                            v39 = MEMORY[0x7FFE0008];
                          }
                          v40 = v39 - QuadPart;
                          if ( v39 < QuadPart )
                            v40 = 0;
                          *(_QWORD *)(v37 + 3192) += v40;
                        }
                        v26 = v105;
                      }
                      LogTruncMgr::GetStartLogSansBackupWithReason(
                        (LogTruncMgr *)(v111 + 2168),
                        (struct LSN *)v123,
                        (enum _TruncationHoldup *)v110,
                        *(_BYTE *)(v111 + 8272),
                        0,
                        0);
                      v41 = *(_QWORD *)(a1 + 5152);
                      if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
                      {
                        v42 = rand();
                        if ( v42 == 5 * (v42 / 5) )
                          Spinlock<148,10,258>::UpdateStatSnapshot(v43);
                      }
                      *(_QWORD *)(v41 + 5376) = 0;
                      (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v106 + 368LL))(v106, v133);
                      LODWORD(DestinationSize) = 464;
                      if ( (unsigned int)LogInfoIter::GetNext(
                                           (LogInfoIter *)v125,
                                           v100,
                                           &v121,
                                           &v120,
                                           &v102,
                                           &v109,
                                           v98,
                                           (struct LSN *)v124,
                                           Destination,
                                           DestinationSize,
                                           &v119,
                                           &v108,
                                           &v97) )
                      {
                        v44 = v123[0];
                        do
                        {
                          if ( v102 <= v133[0]
                            && v102 >= v44
                            && (Destination[0] == 1 || (unsigned int)Destination[0] - 2 <= 1)
                            && v137 <= 0x14
                            && ((Destination[0] - 1) & 0xFD) == 0
                            && v137 - 1 <= 0x13 )
                          {
                            ex_raise(419, 37, 16, 1);
                          }
                          LODWORD(DestinationSizea) = 464;
                        }
                        while ( (unsigned int)LogInfoIter::GetNext(
                                                (LogInfoIter *)v125,
                                                v100,
                                                &v121,
                                                &v120,
                                                &v102,
                                                &v109,
                                                v98,
                                                (struct LSN *)v124,
                                                Destination,
                                                DestinationSizea,
                                                &v119,
                                                &v108,
                                                &v97) );
                      }
                    }
                    if ( v26 )
                      CSECDEK::Release(v26);
                  }
                }
              }
            }
          }
        }
      }
      if ( !BackupOperation::IsBackupOnSecondaryAllowed((BackupOperation *)a1) )
      {
        v45 = *(_QWORD *)(*(_QWORD *)(a1 + 5152) + 4624LL);
        if ( *(_BYTE *)(v45 + 8272) )
        {
          if ( !*(_BYTE *)(v45 + 27672) )
            ex_raise(30, 59, 16, 1);
        }
      }
      v46 = *(_QWORD *)(*(_QWORD *)(a1 + 5152) + 4624LL);
      if ( *(_BYTE *)(v46 + 8272) && (*(_DWORD *)(a1 + 5636) & 0x80000) == 0 )
      {
        if ( (v47 = *(_QWORD *)(v46 + 9216), *(_BYTE *)(v46 + 27672))
          && v47
          && (v48 = v47 + 136 + *(int *)(*(_QWORD *)(v47 + 136) + 8LL),
              (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v48 + 32LL))(v48))
          && !byte_10316E805
          || (v49 = *(_QWORD *)(*(_QWORD *)(a1 + 5152) + 4624LL), v50 = *(_QWORD *)(v49 + 9216), *(_BYTE *)(v49 + 27672))
          && v50
          && (v51 = v50 + 136 + *(int *)(*(_QWORD *)(v50 + 136) + 8LL),
              (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v51 + 32LL))(v51))
          && byte_10316E805
          && *(_DWORD *)(a1 + 2268) == 73 )
        {
          ex_raise(30, 59, 16, 6);
        }
      }
      if ( dword_103172528 )
      {
        v52 = *(RecoveryUnit **)(*(_QWORD *)(a1 + 5152) + 4624LL);
        if ( *((_BYTE *)v52 + 8272) )
        {
          if ( RecoveryUnit::IsForwarder(v52) )
          {
            v53 = *(_QWORD *)(*(_QWORD *)(a1 + 5152) + 4624LL);
            v54 = *(_QWORD *)(v53 + 9216);
            if ( !*(_BYTE *)(v53 + 27672)
              || !v54
              || (v55 = v54 + 136 + *(int *)(*(_QWORD *)(v54 + 136) + 8LL),
                  !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v55 + 32LL))(v55))
              || !byte_10316E805 )
            {
              if ( (unsigned int)(*(_DWORD *)(a1 + 2260) - 1) <= 1 && (*(_DWORD *)(a1 + 5636) & 0x80000) == 0 )
                ex_raise(30, 59, 16, 5);
            }
          }
        }
      }
      v56 = *(_QWORD *)(a1 + 5152);
      if ( *(_BYTE *)(*(_QWORD *)(v56 + 4624) + 8272LL) && (*(_DWORD *)(a1 + 5624) & 0x80000) != 0 )
      {
        ex_raise(30, 59, 16, 3);
        v57 = v99;
        v56 = *(_QWORD *)(v99 + 5152);
      }
      else
      {
        v57 = v99;
      }
      if ( *(_BYTE *)(*(_QWORD *)(v56 + 4624) + 8272LL) )
      {
        if ( *(_DWORD *)(a1 + 2260) == 1 )
        {
          v58 = *(_DWORD *)(a1 + 2268);
          if ( ((v58 - 71) & 0xFFFFFFF5) == 0 && v58 != 79 && (*(_DWORD *)(a1 + 5636) & 0x80000) != 0 )
          {
            ex_raise(30, 59, 16, 4);
            v56 = *(_QWORD *)(v57 + 5152);
          }
        }
      }
      if ( *(_BYTE *)(v56 + 2361) )
        v59 = 904;
      else
        v59 = word_10317F774;
      if ( v59 > *(_WORD *)(*(_QWORD *)(v56 + 4624) + 1662LL)
        && !(unsigned int)DBMgr::IsDownlevelDbVerAllowed((struct DBTABLE *)v56) )
      {
        v60 = *(_QWORD *)(a1 + 5152);
        LODWORD(v94) = *(unsigned __int16 *)(*(_QWORD *)(v60 + 4624) + 1662LL);
        LODWORD(v93) = *(_DWORD *)(v60 + 928);
        ex_raise(9, 46, 14, 2, v93, v60 + 936, v94);
      }
      v61 = *(_QWORD *)(a1 + 5152);
      if ( (*(_DWORD *)(v61 + 632) & 0x140) != 0 )
      {
        if ( (*(_DWORD *)(a1 + 5624) & 0x2000000) == 0 )
          utassert_fail(1u, "CanBackupLogForceAccess ()", "backup.cpp", 376, 0);
        BackupRestoreSynchronization::ObtainExclusiveAccess((BackupRestoreSynchronization *)(a1 + 5256), 0);
        v62 = *(_QWORD *)(a1 + 5152);
        if ( v62 )
          v63 = *(_QWORD *)(v62 + 4624);
        else
          v63 = 0;
        *(_BYTE *)(v63 + 9244) = 0;
        v61 = *(_QWORD *)(v57 + 5152);
      }
      v64 = *(struct RecoveryUnit **)(v61 + 4624);
      if ( *((_BYTE *)v64 + 8272)
        && !*((_BYTE *)v64 + 27672)
        && !HadrBackupCallbacks::IsBackupAllowed(v64, (*(_DWORD *)(a1 + 5636) & 0x80000) != 0) )
      {
        ex_raise(30, 62, 16, 1);
      }
      if ( (*(_DWORD *)(a1 + 5624) & 0x80000) == 0 )
      {
        v65 = v103;
        if ( !v103
          && (*(_DWORD *)(a1 + 5636) & 0x80000) != 0
          && *(_DWORD *)(a1 + 2260) == 1
          && *(_DWORD *)(a1 + 2268) == 68 )
        {
          v65 = 16;
        }
        Transaction = BackupOperation::GetTransaction((BackupOperation *)a1, 0);
        BackupRestoreSynchronization::AcquireTxBulkOpLock(a1 + 5256, Transaction, v65);
        v67 = *(volatile signed __int32 **)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                    + SystemThread_TlsIndex)
                                                                  + SystemThread_TlsOffset
                                                                  + 8LL)
                                                      + 96LL)
                                          + 1192LL);
        if ( v67 && !_InterlockedCompareExchange(v67, 1, 0) )
          EventManualInternal<SuspendQueueSLock>::Signal(v67 + 2, 0);
        HadrBackupCallbacks::DoXevent(*(_QWORD *)(*(_QWORD *)(a1 + 5152) + 4624LL));
      }
      v68 = *(struct RecoveryUnit **)(*(_QWORD *)(a1 + 5152) + 4624LL);
      if ( *((_BYTE *)v68 + 8272) && !*((_BYTE *)v68 + 27672) && *(_DWORD *)(a1 + 2260) == 2 )
      {
        HadrBackupCallbacks::StartLogBackup(
          v68,
          (struct LSN *)(a1 + 5944),
          (struct LSN *)(a1 + 5954),
          (struct LSN *)(a1 + 5964));
        *(_DWORD *)(a1 + 5636) |= 0x8000000u;
        LOBYTE(v69) = 1;
        RedoneLSN = (LSN *)RecoveryMgr::GetRedoneLSN(
                             *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 5152) + 4624LL) + 1832LL),
                             v132,
                             v69);
        v112 = *RedoneLSN;
        LowPart = RedoneLSN[1].LowPart;
        v71 = *(_DWORD *)(a1 + 5944);
        if ( v71 > v112.LowPart
          || v71 == v112.LowPart
          && (*(_DWORD *)(a1 + 5948) > v112.HighPart
           || *(_DWORD *)(a1 + 5948) == v112.HighPart && *(_WORD *)(a1 + 5952) > (unsigned __int16)LowPart) )
        {
          LSN::FormatAsHexString((LSN *)(a1 + 5944), v135, &v115);
          LSN::FormatAsHexString(&v112, v134, &v116);
          v72 = *(_QWORD *)(a1 + 5152);
          LODWORD(v93) = *(_DWORD *)(v72 + 928);
          ex_raise(352, 95, 16, 1, v93, v72 + 936, v135, v134);
        }
        *(_BYTE *)(a1 + 6056) = *(_BYTE *)(**(_QWORD **)(*(_QWORD *)(SystemThread_TlsOffset
                                                                   + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                     + SystemThread_TlsIndex))
                                                       + 64LL)
                                         + 72LL);
        *(_DWORD *)(**(_QWORD **)(*(_QWORD *)(SystemThread_TlsOffset
                                            + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                              + SystemThread_TlsIndex))
                                + 64LL)
                  + 72LL) = -5;
        v73 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        v74 = *(_QWORD *)(v73 + 256);
        if ( !v74 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v74 = *(_QWORD *)(v73 + 256);
        }
        SOS_Task::SetDeadlockPriority(*(_QWORD *)(v74 + 600), 5);
        *(_DWORD *)(a1 + 5652) |= 1u;
        v75 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        v76 = *(_QWORD *)(v75 + 256);
        if ( !v76 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v76 = *(_QWORD *)(v75 + 256);
        }
        v77 = *(_QWORD *)(a1 + 5152);
        if ( v77 )
          v78 = *(_QWORD *)(v77 + 4624);
        else
          v78 = 0;
        HadrBackupCallbacks::RegisterTask(v78, *(_QWORD *)(v76 + 600), a1, 76);
      }
      if ( BackupOperation::IsBackupOnSecondaryAllowed((BackupOperation *)a1) )
      {
        v79 = *(_QWORD *)(*(_QWORD *)(a1 + 5152) + 4624LL);
        if ( *(_BYTE *)(v79 + 8272) )
        {
          if ( !*(_BYTE *)(v79 + 27672) && *(_DWORD *)(a1 + 2260) == 1 && (*(_DWORD *)(a1 + 5636) & 0x80000) == 0 )
          {
            HadrBackupCallbacks::StartDatabaseBackup(v79, *(unsigned int *)(a1 + 2268));
            *(_DWORD *)(a1 + 5636) |= 0x8000000u;
            *(_BYTE *)(a1 + 6056) = *(_BYTE *)(**(_QWORD **)(*(_QWORD *)(SystemThread_TlsOffset
                                                                       + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                         + SystemThread_TlsIndex))
                                                           + 64LL)
                                             + 72LL);
            *(_DWORD *)(**(_QWORD **)(*(_QWORD *)(SystemThread_TlsOffset
                                                + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                  + SystemThread_TlsIndex))
                                    + 64LL)
                      + 72LL) = -5;
            v80 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                + SystemThread_TlsOffset;
            v81 = *(_QWORD *)(v80 + 256);
            if ( !v81 )
            {
              SystemThread::MakeMiniSOSThread(0);
              v81 = *(_QWORD *)(v80 + 256);
            }
            SOS_Task::SetDeadlockPriority(*(_QWORD *)(v81 + 600), 5);
            *(_DWORD *)(a1 + 5652) |= 1u;
            v82 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                + SystemThread_TlsOffset;
            v83 = *(_QWORD *)(v82 + 256);
            if ( !v83 )
            {
              SystemThread::MakeMiniSOSThread(0);
              v83 = *(_QWORD *)(v82 + 256);
            }
            v84 = *(_QWORD *)(a1 + 5152);
            if ( v84 )
              v85 = *(_QWORD *)(v84 + 4624);
            else
              v85 = 0;
            HadrBackupCallbacks::RegisterTask(v85, *(_QWORD *)(v83 + 600), a1, *(unsigned int *)(a1 + 2268));
          }
        }
      }
      if ( ((*(_DWORD *)(a1 + 5624) & 0x40000000) != 0 || (*(_BYTE *)(a1 + 5652) & 4) != 0)
        && !BackupOperation::AllFilesInXStore((BackupOperation *)a1) )
      {
        ex_raise(30, 73, 16, 1);
      }
      v86 = v99;
LABEL_212:
      v87 = *(_QWORD *)(a1 + 5152);
      if ( !v87 )
      {
        utassert_fail(1u, "m_pDbTable", "backup.cpp", 577, 0);
        v87 = *(_QWORD *)(v86 + 5152);
      }
      if ( *(_WORD *)(v87 + 1528) )
        ex_raise(30, 2, 16, 1);
      if ( (unsigned int)(*(_DWORD *)(a1 + 2260) - 1) <= 1 )
      {
        v88 = *(_QWORD *)(a1 + 5152);
        if ( *(_DWORD *)(v88 + 1512) == 5
          || !*(_BYTE *)(v88 + 2253)
          && ((*(_DWORD *)(v88 + 632) & 0x400) != 0
           || (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(SystemThread_TlsOffset
                                                + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                  + SystemThread_TlsIndex))
                                    + 72LL)
                        + 270LL)
             & 4) != 0
           && dword_103172528
           && !dword_1031852C8
           && (*(_BYTE *)(v88 + 2256) & 2) != 0) )
        {
          *(_DWORD *)(a1 + 5628) |= 0x10000u;
        }
      }
      *(_DWORD *)(a1 + 5756) = *(_DWORD *)(a1 + 5264);
      *(_QWORD *)(a1 + 5760) = 320;
      *(_DWORD *)(a1 + 5752) = 5;
      result = *(_QWORD *)(a1 + 176);
      *(_QWORD *)(a1 + 5768) = result;
      *(_DWORD *)(a1 + 5776) = 1;
      return result;
    case 5:
    case 6:
    case 7:
    case 8:
    case 9:
      v90 = DBMgr::OpenDB((__int64)qword_10316ECA0, 0, v9, 0x14u, 1, a3 | 0x24u);
      *(_QWORD *)(a1 + 5152) = v90;
      if ( !v90 )
      {
        ex_raise(31, 67, 16, 2, *(_QWORD *)(a1 + 176));
        v90 = *(DBTABLE **)(a1 + 5152);
      }
      v86 = a1;
      if ( *(_BYTE *)(*((_QWORD *)v90 + 578) + 8272LL) )
        ex_raise(30, 59, 16, 2);
      IsDatabaseOnlineNotStandby = BackupOperation::IsDatabaseOnlineNotStandby((BackupOperation *)a1);
      v92 = (BackupRestoreSynchronization *)(a1 + 5256);
      if ( IsDatabaseOnlineNotStandby )
      {
        if ( !(unsigned int)BackupRestoreSynchronization::AcquireSessionBulkOpLock(v92, 14) )
          ex_raise(30, 23, 16, 5);
      }
      else
      {
        BackupRestoreSynchronization::ObtainExclusiveAccess(v92, 0);
      }
      goto LABEL_212;
    default:
      utassert_fail(1u, "0", "backup.cpp", 574, "Invalid command type");
      v86 = a1;
      goto LABEL_212;
  }
}

```

## disassembly

```asm
0x101f54a80  push    rbx
0x101f54a82  push    rsi
0x101f54a83  push    rdi
0x101f54a84  push    r12
0x101f54a86  push    r13
0x101f54a88  push    r14
0x101f54a8a  push    r15
0x101f54a8c  sub     rsp, 470h
0x101f54a93  mov     [rsp+4A8h+var_320], 0FFFFFFFFFFFFFFFEh
0x101f54a9f  mov     rax, cs:__security_cookie
0x101f54aa6  xor     rax, rsp
0x101f54aa9  mov     [rsp+4A8h+var_48], rax
0x101f54ab1  mov     ebx, r8d
0x101f54ab4  mov     [rsp+4A8h+var_41C], edx
0x101f54abb  mov     rsi, rcx
0x101f54abe  mov     [rsp+4A8h+var_430], rcx
0x101f54ac3  mov     [rsp+4A8h+var_3F0], rcx
0x101f54acb  mov     rdi, rcx
0x101f54ace  mov     [rsp+4A8h+var_418], rcx
0x101f54ad6  mov     dword ptr [rsp+4A8h+var_410], edx
0x101f54add  mov     r12, [rcx+0A8h]
0x101f54ae4  sub     r12, [rcx+0B0h]
0x101f54aeb  sar     r12, 1
0x101f54aee  add     r12d, r12d
0x101f54af1  xor     r13b, r13b
0x101f54af4  mov     edx, [rcx+1490h]
0x101f54afa  mov     r8d, edx
0x101f54afd  test    edx, edx
0x101f54aff  jnz     short loc_101F54B35
0x101f54b01  xor     r15d, r15d
0x101f54b04  mov     [rsp+4A8h+var_488], r15
0x101f54b09  lea     r9d, [rdx+67h]
0x101f54b0d  lea     r8, aBackupCpp; "backup.cpp"
0x101f54b14  lea     rdx, aIsdatabaseidkn; "IsDatabaseIdKnown ()"
0x101f54b1b  mov     r14d, 1
0x101f54b21  mov     ecx, r14d
0x101f54b24  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x101f54b2a  mov     edx, [rdi+1490h]
0x101f54b30  mov     r8d, edx
0x101f54b33  jmp     short loc_101F54B3C
0x101f54b35  xor     r15d, r15d
0x101f54b38  lea     r14d, [r15+1]
0x101f54b3c  mov     rcx, rdi; this
0x101f54b3f  call    ?IsDatabaseLocked@BackupOperation@@QEBAHXZ; BackupOperation::IsDatabaseLocked(void)
0x101f54b44  test    eax, eax
0x101f54b46  jnz     short loc_101F54B8D
0x101f54b48  cmp     edx, 1
0x101f54b4b  jz      short loc_101F54B8D
0x101f54b4d  call    ?IsReplicatedMasterEnabled@@YAHXZ; IsReplicatedMasterEnabled(void)
0x101f54b52  test    eax, eax
0x101f54b54  jnz     short loc_101F54B5F
0x101f54b56  call    ?IsContainedAGEnabledInstance@@YAHXZ; IsContainedAGEnabledInstance(void)
0x101f54b5b  test    eax, eax
0x101f54b5d  jz      short loc_101F54B64
0x101f54b5f  call    ?IsContainedAGEnabledInstance@@YAHXZ; IsContainedAGEnabledInstance(void)
0x101f54b64  mov     [rsp+4A8h+var_488], r15
0x101f54b69  mov     r9d, 68h ; 'h'
0x101f54b6f  lea     r8, aBackupCpp; "backup.cpp"
0x101f54b76  lea     rdx, aIsdatabaselock; "IsDatabaseLocked () || IsMaster ()"
0x101f54b7d  mov     ecx, r14d
0x101f54b80  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x101f54b86  mov     r8d, [rsi+1490h]
0x101f54b8d  mov     esi, ebx
0x101f54b8f  shr     esi, 3
0x101f54b92  not     sil
0x101f54b95  and     sil, 1
0x101f54b99  mov     eax, [rdi+8D4h]
0x101f54b9f  dec     eax; switch 9 cases
0x101f54ba1  cmp     eax, 8
0x101f54ba4  ja      def_101F54BBD; jumptable 0000000101F54BBD default case, cases 3,4
0x101f54baa  cdqe
0x101f54bac  lea     rdx, __@@_PchSym_@00@UwyhUhsUFfqFUBAAIPAFECAJUxnwUtUlyqUcGEivgzroUhjoUmgwynhUsvpzglmUfgroUnrmUnrmfgroOexckilqUyzhvfgroOlyq@4B2008FD98C1DD4
0x101f54bb3  mov     ecx, ds:(jpt_101F54BBD - 100400000h)[rdx+rax*4]
0x101f54bba  add     rcx, rdx
0x101f54bbd  jmp     rcx; switch jump
0x101f54bbf  mov     ecx, [rdi+1490h]; jumptable 0000000101F54BBD cases 1,2
0x101f54bc5  mov     rdx, cs:qword_10316ECA0
0x101f54bcc  mov     eax, ecx
0x101f54bce  sub     eax, 7FFCh
0x101f54bd3  jz      short loc_101F54C07
0x101f54bd5  sub     eax, 1
0x101f54bd8  jz      short loc_101F54C01
0x101f54bda  cmp     eax, 2
0x101f54bdd  jz      short loc_101F54BFB
0x101f54bdf  cmp     ecx, [rdx+4Ch]
0x101f54be2  ja      short loc_101F54C2B
0x101f54be4  test    ecx, ecx
0x101f54be6  jz      short loc_101F54C2B
0x101f54be8  lfence
0x101f54beb  lea     eax, [rcx-1]
0x101f54bee  movsxd  rcx, eax
0x101f54bf1  mov     rax, [rdx+28h]
0x101f54bf5  mov     rax, [rax+rcx*8]
0x101f54bf9  jmp     short loc_101F54C0B
0x101f54bfb  mov     rax, [rdx+58h]
0x101f54bff  jmp     short loc_101F54C0B
0x101f54c01  mov     rax, [rdx+70h]
0x101f54c05  jmp     short loc_101F54C0B
0x101f54c07  mov     rax, [rdx+68h]
0x101f54c0b  test    rax, rax
0x101f54c0e  jz      short loc_101F54C2B
0x101f54c10  mov     rax, [rax+1210h]
0x101f54c17  mov     ecx, ebx
0x101f54c19  bts     ecx, 0Ch
0x101f54c1d  cmp     [rax+2050h], r13b
0x101f54c24  cmovz   ecx, ebx
0x101f54c27  mov     ebx, ecx
0x101f54c29  jmp     short loc_101F54C45
0x101f54c2b  lea     rcx, [rdi+1494h]; this
0x101f54c32  cmp     dword ptr [rcx], 0
0x101f54c35  jl      short loc_101F54C45
0x101f54c37  cmp     [rcx+4], r13b
0x101f54c3b  jz      short loc_101F54C45
0x101f54c3d  mov     r13b, 1
0x101f54c40  call    ??1AutoDbLock@@QEAA@XZ; AutoDbLock::~AutoDbLock(void)
0x101f54c45  mov     byte ptr [rsp+4A8h+var_470], 1
0x101f54c4a  mov     byte ptr [rsp+4A8h+var_478], sil
0x101f54c4f  mov     byte ptr [rsp+4A8h+var_480], 1
0x101f54c54  mov     dword ptr [rsp+4A8h+var_488], ebx
0x101f54c58  mov     r9d, 14h
0x101f54c5e  mov     r8d, r12d
0x101f54c61  mov     rdx, [rdi+0B0h]
0x101f54c68  xor     ecx, ecx
0x101f54c6a  mov     rax, cs:__imp_?g_dbtableFactory@@3UDBTableFactory@@A; DBTableFactory g_dbtableFactory
0x101f54c71  call    qword ptr [rax+28h]
0x101f54c74  mov     dword ptr [rsp+4A8h+var_408], eax
0x101f54c7b  test    eax, eax
0x101f54c7d  jz      loc_101F54D12
0x101f54c83  test    r13b, r13b
0x101f54c86  jz      short loc_101F54C9F
0x101f54c88  lea     rcx, [rdi+1488h]
0x101f54c8f  xor     r9d, r9d
0x101f54c92  mov     r8d, 4E20h
0x101f54c98  mov     dl, 3
0x101f54c9a  call    ?LockDatabase@BackupRestoreSynchronization@@QEAAXW4LCK_MODE@@KH@Z; BackupRestoreSynchronization::LockDatabase(LCK_MODE,ulong,int)
0x101f54c9f  mov     ecx, [rdi+1490h]
0x101f54ca5  mov     [rsp+4A8h+var_3A0], ecx
0x101f54cac  mov     rdx, cs:qword_10316ECA0
0x101f54cb3  mov     [rsp+4A8h+var_340], rdx
0x101f54cbb  mov     eax, ecx
0x101f54cbd  sub     eax, 7FFCh
0x101f54cc2  jz      short loc_101F54CF8
0x101f54cc4  sub     eax, 1
0x101f54cc7  jz      short loc_101F54CF2
0x101f54cc9  cmp     eax, 2
0x101f54ccc  jz      short loc_101F54CEC
0x101f54cce  cmp     ecx, [rdx+4Ch]
0x101f54cd1  ja      short loc_101F54CE7
0x101f54cd3  test    ecx, ecx
0x101f54cd5  jz      short loc_101F54CE7
0x101f54cd7  lea     eax, [rcx-1]
0x101f54cda  movsxd  rcx, eax
0x101f54cdd  mov     rax, [rdx+28h]
0x101f54ce1  mov     rdx, [rax+rcx*8]
0x101f54ce5  jmp     short loc_101F54CFC
0x101f54ce7  mov     rdx, r15
0x101f54cea  jmp     short loc_101F54CFC
0x101f54cec  mov     rdx, [rdx+58h]
0x101f54cf0  jmp     short loc_101F54CFC
0x101f54cf2  mov     rdx, [rdx+70h]
0x101f54cf6  jmp     short loc_101F54CFC
0x101f54cf8  mov     rdx, [rdx+68h]
0x101f54cfc  mov     [rsp+4A8h+var_338], rdx
0x101f54d04  mov     [rdi+1420h], rdx
0x101f54d0b  test    rdx, rdx
0x101f54d0e  jz      short loc_101F54D19
0x101f54d10  jmp     short loc_101F54D2C
0x101f54d12  mov     [rdi+1420h], r15
0x101f54d19  mov     r9d, r14d
0x101f54d1c  xor     edx, edx
0x101f54d1e  lea     ecx, [rdx+1Eh]
0x101f54d21  lea     r8d, [rdx+19h]
0x101f54d25  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x101f54d2b  nop
0x101f54d2c  jmp     short loc_101F54D53
0x101f54d2e  xor     r15d, r15d
0x101f54d31  lea     r14d, [r15+1]
0x101f54d35  mov     r13, [rsp+4A8h+var_3F0]
0x101f54d3d  mov     [rsp+4A8h+var_430], r13
0x101f54d42  mov     rdi, r13
0x101f54d45  mov     edx, dword ptr [rsp+4A8h+var_410]
0x101f54d4c  mov     [rsp+4A8h+var_41C], edx
0x101f54d53  mov     rdx, gs:58h
0x101f54d5c  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101f54d63  mov     ecx, [rax]
0x101f54d65  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101f54d6c  mov     ebx, [rax]
0x101f54d6e  add     rbx, [rdx+rcx*8]
0x101f54d72  mov     rcx, [rbx+100h]
0x101f54d79  test    rcx, rcx
0x101f54d7c  jnz     short loc_101F54D8B
0x101f54d7e  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x101f54d84  mov     rcx, [rbx+100h]
0x101f54d8b  cmp     dword ptr [rcx+22Ch], 0
0x101f54d92  jz      short loc_101F54D9A
0x101f54d94  call    cs:__imp_?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z; ExceptionPostCatchActions(Worker *)
0x101f54d9a  cmp     cs:dword_1031852C8, 0
0x101f54da1  jz      loc_101F553E4
0x101f54da7  mov     rdx, gs:58h
0x101f54db0  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101f54db7  mov     ecx, [rax]
0x101f54db9  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101f54dc0  mov     eax, [rax]
0x101f54dc2  add     rax, [rdx+rcx*8]
0x101f54dc6  mov     rax, [rax]
0x101f54dc9  mov     rcx, [rax+48h]
0x101f54dcd  test    byte ptr [rcx+10Eh], 2
0x101f54dd4  jnz     short loc_101F54E45
0x101f54dd6  call    cs:__imp_?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ; CFeatureSwitchesLangSvc::GetCurrentInstance(void)
0x101f54ddc  cmp     byte ptr [rax+27Ch], 0
0x101f54de3  jz      short loc_101F54E14
0x101f54de5  mov     rdx, gs:58h
0x101f54dee  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101f54df5  mov     ecx, [rax]
0x101f54df7  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101f54dfe  mov     eax, [rax]
0x101f54e00  add     rax, [rdx+rcx*8]
0x101f54e04  mov     rax, [rax]
0x101f54e07  mov     rcx, [rax+48h]
0x101f54e0b  cmp     dword ptr [rcx+27Ch], 0
0x101f54e12  jz      short loc_101F54E45
0x101f54e14  cmp     dword ptr [rdi+8DCh], 44h ; 'D'
0x101f54e1b  jnz     short loc_101F54E29
0x101f54e1d  test    dword ptr [rdi+1604h], 80000h
0x101f54e27  jnz     short loc_101F54E45
0x101f54e29  mov     esi, 10h
0x101f54e2e  lea     r9d, [rsi-0Eh]
0x101f54e32  mov     r8d, esi
0x101f54e35  lea     edx, [rsi-0Ch]
0x101f54e38  mov     ecx, 1A3h
0x101f54e3d  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x101f54e43  jmp     short loc_101F54E4A
0x101f54e45  mov     esi, 10h
0x101f54e4a  cmp     cs:dword_1031852C8, 0
0x101f54e51  jz      loc_101F553E9
0x101f54e57  call    cs:__imp_?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ; CFeatureSwitchesLangSvc::GetCurrentInstance(void)
0x101f54e5d  cmp     byte ptr [rax+107h], 0
0x101f54e64  jz      loc_101F553E9
0x101f54e6a  mov     rdx, gs:58h
0x101f54e73  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101f54e7a  mov     ecx, [rax]
0x101f54e7c  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101f54e83  mov     eax, [rax]
0x101f54e85  add     rax, [rdx+rcx*8]
0x101f54e89  mov     rax, [rax]
0x101f54e8c  mov     rcx, [rax+48h]
0x101f54e90  test    byte ptr [rcx+10Eh], 2
0x101f54e97  jnz     loc_101F553E9
0x101f54e9d  mov     rax, [rdi+16E0h]
0x101f54ea4  test    rax, rax
0x101f54ea7  jz      loc_101F553E9
0x101f54ead  mov     rcx, [rax+188h]
0x101f54eb4  test    rcx, rcx
0x101f54eb7  jz      loc_101F553E9
0x101f54ebd  cmp     dword ptr [rcx+224h], 9
0x101f54ec4  jnz     loc_101F553E9
0x101f54eca  cmp     dword ptr [rdi+8DCh], 44h ; 'D'
0x101f54ed1  jnz     loc_101F553E9
0x101f54ed7  test    dword ptr [rdi+1604h], 80000h
0x101f54ee1  jz      loc_101F553E9
0x101f54ee7  mov     rcx, [rdi+1420h]; this
0x101f54eee  call    ?GetDEKWithRef@DBTABLE@@QEAAPEAVCSECDEK@@XZ; DBTABLE::GetDEKWithRef(void)
0x101f54ef3  mov     r12, rax
0x101f54ef6  mov     [rsp+4A8h+var_410], rax
0x101f54efe  mov     [rsp+4A8h+var_330], rax
0x101f54f06  xor     bl, bl
0x101f54f08  test    rax, rax
0x101f54f0b  jz      loc_101F54F94
0x101f54f11  cmp     [rax+260h], bl
0x101f54f17  jz      short loc_101F54F94
0x101f54f19  mov     [rsp+4A8h+var_3D8], r15
0x101f54f21  lea     rdx, [rsp+4A8h+var_3D8]
0x101f54f29  mov     rcx, rax
0x101f54f2c  call    cs:__imp_?GetEncryptorType@CSECDEK@@QEAAPEB_WPEA_K@Z; CSECDEK::GetEncryptorType(unsigned __int64 *)
0x101f54f32  mov     r9, rax
0x101f54f35  mov     rdx, [rsp+4A8h+var_3D8]
0x101f54f3d  lea     rcx, aCertificate; "CERTIFICATE"
0x101f54f44  test    rdx, rdx
0x101f54f47  jz      short loc_101F54F69
0x101f54f49  sub     r9, rcx
0x101f54f4c  nop     dword ptr [rax+00h]
0x101f54f50  movzx   r8d, word ptr [r9+rcx]
0x101f54f55  cmp     r8w, [rcx]
0x101f54f59  jnz     loc_101F55114
0x101f54f5f  add     rcx, 2
0x101f54f63  sub     rdx, 1
0x101f54f67  jnz     short loc_101F54F50
0x101f54f69  mov     ecx, r15d
0x101f54f6c  test    ecx, ecx
0x101f54f6e  setz    bl
0x101f54f71  movzx   eax, byte ptr [r12]
0x101f54f76  and     al, 1Fh
0x101f54f78  cmp     al, 1
0x101f54f7a  jz      short loc_101F54F94
0x101f54f7c  test    ecx, ecx
0x101f54f7e  jnz     short loc_101F54F94
0x101f54f80  mov     r9d, r14d
0x101f54f83  mov     r8d, esi
0x101f54f86  lea     edx, [rcx+16h]
0x101f54f89  mov     ecx, 1A3h
  ... truncated ...
```
