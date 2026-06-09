# VdiClient::ExecuteSql(void)

- ea: `0x100704b80`
- end: `0x100705eb2`
- name: `?ExecuteSql@VdiClient@@AEAAXXZ`
- size: `4914`
- prototype: `void __fastcall(VdiClient *__hidden this)`
- caller_count: `1`
- callee_count: `24`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x100704950`

## callees

- `0x100401380`
- `0x1004013f0`
- `0x100401490`
- `0x1004022e0`
- `0x10041e3e0`
- `0x10042d9c0`
- `0x10046cee0`
- `0x10046ebb0`
- `0x1004ab3d0`
- `0x1004abbd0`
- `0x100704b80`
- `0x100706b10`
- `0x100706f40`
- `0x100707170`
- `0x100707390`
- `0x100707c00`
- `0x100710240`
- `0x1007102e0`
- `0x10071ea50`
- `0x10071eb90`
- `0x100ac3f50`
- `0x100ac4180`
- `0x1016f7780`
- `0x1023aa3e0`

## import_xrefs

- `ole32!StringFromGUID2` at `0x1007058c7`
- `ole32!StringFromGUID2` at `0x1007058c7`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x1007051ab`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x1007051ab`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x100704e7d`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x100704fe0`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x100705000`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x1007053d8`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x1007053f8`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x1007055ed`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x10070560d`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x100705779`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x100705799`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x100705abc`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x100705adc`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x100705c8c`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x100705cac`
- `sqldk!?ReleaseLock@SOS_RWLock@@QEAAXW4RWLockMode@@@Z` at `0x100705e45`
- `sqldk!?ReleaseLock@SOS_RWLock@@QEAAXW4RWLockMode@@@Z` at `0x100705e45`
- `sqldk!?CreateExecSql@@YAPEAVIExecSql@@PEAVIMemObj@@PEAVICallerParse@@@Z` at `0x1007052d1`
- `sqldk!?CreateExecSql@@YAPEAVIExecSql@@PEAVIMemObj@@PEAVICallerParse@@@Z` at `0x1007052d1`
- `sqldk!?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z` at `0x1007054d7`
- `sqldk!?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z` at `0x1007054d7`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100705d2f`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100705d2f`
- `sqldk!?hdl_prntbackout@@YAHHHHHPEAD@Z` at `0x100704cec`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100704c42`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100704c74`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100704c9f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100704cde`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100704db2`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100704f18`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100705093`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100705b7b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100704c42`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100704c74`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100704c9f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100704cde`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100704db2`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100704f18`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100705093`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100705b7b`
- `sqldk!SystemThread_TlsIndex` at `0x100704bc8`
- `sqldk!SystemThread_TlsIndex` at `0x100704d2a`
- `sqldk!SystemThread_TlsIndex` at `0x100704d74`
- `sqldk!SystemThread_TlsIndex` at `0x100704e40`
- `sqldk!SystemThread_TlsIndex` at `0x100704ebf`
- `sqldk!SystemThread_TlsIndex` at `0x100704fa3`
- `sqldk!SystemThread_TlsIndex` at `0x100705042`
- `sqldk!SystemThread_TlsIndex` at `0x1007050de`
- `sqldk!SystemThread_TlsIndex` at `0x1007051bf`
- `sqldk!SystemThread_TlsIndex` at `0x100705244`
- `sqldk!SystemThread_TlsIndex` at `0x100705318`
- `sqldk!SystemThread_TlsIndex` at `0x100705351`
- `sqldk!SystemThread_TlsIndex` at `0x10070539b`
- `sqldk!SystemThread_TlsIndex` at `0x10070543a`
- `sqldk!SystemThread_TlsIndex` at `0x100705519`
- `sqldk!SystemThread_TlsIndex` at `0x100705552`
- `sqldk!SystemThread_TlsIndex` at `0x10070559c`
- `sqldk!SystemThread_TlsIndex` at `0x10070564f`
- `sqldk!SystemThread_TlsIndex` at `0x1007056a5`
- `sqldk!SystemThread_TlsIndex` at `0x1007056de`
- `sqldk!SystemThread_TlsIndex` at `0x100705728`
- `sqldk!SystemThread_TlsIndex` at `0x1007057db`
- `sqldk!SystemThread_TlsIndex` at `0x100705811`
- `sqldk!SystemThread_TlsIndex` at `0x1007059e8`
- `sqldk!SystemThread_TlsIndex` at `0x100705a21`
- `sqldk!SystemThread_TlsIndex` at `0x100705a6b`
- `sqldk!SystemThread_TlsIndex` at `0x100705b1e`
- `sqldk!SystemThread_TlsIndex` at `0x100705bb8`
- `sqldk!SystemThread_TlsIndex` at `0x100705bf1`
- `sqldk!SystemThread_TlsIndex` at `0x100705c3b`
- `sqldk!SystemThread_TlsIndex` at `0x100705cf7`
- `sqldk!SystemThread_TlsIndex` at `0x100705d92`
- `sqldk!SystemThread_TlsIndex` at `0x100705e60`
- `sqldk!SystemThread_TlsOffset` at `0x100704bd9`
- `sqldk!SystemThread_TlsOffset` at `0x100704d33`
- `sqldk!SystemThread_TlsOffset` at `0x100704d7d`
- `sqldk!SystemThread_TlsOffset` at `0x100704e49`
- `sqldk!SystemThread_TlsOffset` at `0x100704ec8`
- `sqldk!SystemThread_TlsOffset` at `0x100704fac`
- `sqldk!SystemThread_TlsOffset` at `0x10070504b`
- `sqldk!SystemThread_TlsOffset` at `0x1007050ef`
- `sqldk!SystemThread_TlsOffset` at `0x1007051d0`
- `sqldk!SystemThread_TlsOffset` at `0x10070524d`
- `sqldk!SystemThread_TlsOffset` at `0x100705321`
- `sqldk!SystemThread_TlsOffset` at `0x10070535a`
- `sqldk!SystemThread_TlsOffset` at `0x1007053a4`
- `sqldk!SystemThread_TlsOffset` at `0x100705443`
- `sqldk!SystemThread_TlsOffset` at `0x100705522`
- `sqldk!SystemThread_TlsOffset` at `0x10070555b`
- `sqldk!SystemThread_TlsOffset` at `0x1007055a5`
- `sqldk!SystemThread_TlsOffset` at `0x100705658`
- `sqldk!SystemThread_TlsOffset` at `0x1007056ae`
- `sqldk!SystemThread_TlsOffset` at `0x1007056e7`
- `sqldk!SystemThread_TlsOffset` at `0x100705731`
- `sqldk!SystemThread_TlsOffset` at `0x1007057e4`
- `sqldk!SystemThread_TlsOffset` at `0x10070581a`
- `sqldk!SystemThread_TlsOffset` at `0x1007059f1`
- `sqldk!SystemThread_TlsOffset` at `0x100705a2a`
- `sqldk!SystemThread_TlsOffset` at `0x100705a74`
- `sqldk!SystemThread_TlsOffset` at `0x100705b27`
- `sqldk!SystemThread_TlsOffset` at `0x100705bc1`
- `sqldk!SystemThread_TlsOffset` at `0x100705bfa`
- `sqldk!SystemThread_TlsOffset` at `0x100705c44`
- `sqldk!SystemThread_TlsOffset` at `0x100705d00`
- `sqldk!SystemThread_TlsOffset` at `0x100705d9b`
- `sqldk!SystemThread_TlsOffset` at `0x100705e69`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100705d19`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100705db6`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100705d19`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100705db6`
- `api-ms-win-crt-string-l1-1-0!strcpy_s` at `0x10070589c`
- `api-ms-win-crt-string-l1-1-0!strcpy_s` at `0x10070589c`
- `sqllang!?SetContextInfo@CUEnvTransient@@QEAAXPEBEK@Z` at `0x10070594f`
- `sqllang!?SetContextInfo@CUEnvTransient@@QEAAXPEBEK@Z` at `0x10070594f`

## string_xrefs

- `0x100704c31`: `DbCopyVdi.cpp`
- `0x100704c61`: `DbCopyVdi.cpp`
- `0x100704c8c`: `DbCopyVdi.cpp`
- `0x100704ccb`: `DbCopyVdi.cpp`
- `0x100704f05`: `DbCopyVdi.cpp`
- `0x100705082`: `DbCopyVdi.cpp`
- `0x100705b68`: `DbCopyVdi.cpp`
- `0x100704da0`: `DbCopyDirectory.cpp`
- `0x100704c38`: `nullptr != m_apTsqlTask`

## pseudocode

```c
// Hidden C++ exception states: #wind=33 #try_helpers=1
void __fastcall VdiClient::ExecuteSql(VdiClient *this)
{
  __int64 v2; // r9
  char v3; // r15
  unsigned __int16 MasterDbId; // ax
  __int64 v5; // r14
  const wchar_t *v6; // rdx
  __int64 v7; // rax
  unsigned int v8; // ebx
  int v9; // eax
  __int64 v10; // r9
  unsigned int v11; // ecx
  const wchar_t *v12; // r8
  __int64 v13; // rcx
  __int64 v14; // r9
  int v15; // eax
  struct BaseXact *v16; // rax
  __int64 v17; // rax
  struct IExecSql *ExecSql; // rax
  struct IExecSql *v19; // rbx
  unsigned int v20; // eax
  __int64 SosResultString; // rax
  __int64 v22; // rbx
  const char *v23; // r8
  __int64 v24; // rdx
  __int64 v25; // rbx
  __int64 v26; // rbx
  struct Worker *v27; // rcx
  __int64 v28; // rbx
  __int64 v29; // rsi
  int v30; // eax
  int v31; // ebx
  int Lock; // eax
  __int64 v33; // rdx
  _QWORD *v34; // r9
  _QWORD *v35; // r8
  __int64 v36; // rax
  int v37; // [rsp+20h] [rbp-298h]
  char v38; // [rsp+30h] [rbp-288h]
  char v39; // [rsp+31h] [rbp-287h]
  int v40; // [rsp+34h] [rbp-284h] BYREF
  unsigned int v41; // [rsp+38h] [rbp-280h] BYREF
  int v42; // [rsp+3Ch] [rbp-27Ch]
  int v43; // [rsp+40h] [rbp-278h]
  char v44; // [rsp+48h] [rbp-270h]
  int v45; // [rsp+4Ch] [rbp-26Ch]
  __int64 v46; // [rsp+50h] [rbp-268h]
  __int64 v47; // [rsp+58h] [rbp-260h] BYREF
  _BYTE v48[8]; // [rsp+60h] [rbp-258h] BYREF
  _QWORD *v49; // [rsp+68h] [rbp-250h]
  _BYTE v50[8]; // [rsp+70h] [rbp-248h] BYREF
  __int64 v51; // [rsp+78h] [rbp-240h]
  __int64 v52; // [rsp+80h] [rbp-238h] BYREF
  int v53; // [rsp+88h] [rbp-230h]
  __int64 *v54; // [rsp+90h] [rbp-228h]
  unsigned int v55; // [rsp+98h] [rbp-220h]
  struct IExecSql *v56; // [rsp+A0h] [rbp-218h]
  VdiClient *v57; // [rsp+A8h] [rbp-210h]
  _BYTE v58[24]; // [rsp+B0h] [rbp-208h] BYREF
  _WORD v59[2]; // [rsp+C8h] [rbp-1F0h] BYREF
  unsigned int v60; // [rsp+CCh] [rbp-1ECh]
  int v61; // [rsp+D4h] [rbp-1E4h]
  _BYTE v62[40]; // [rsp+F8h] [rbp-1C0h] BYREF
  int v63; // [rsp+120h] [rbp-198h]
  __int64 v64; // [rsp+128h] [rbp-190h]
  int v65; // [rsp+130h] [rbp-188h] BYREF
  __int64 v66; // [rsp+138h] [rbp-180h]
  __int64 v67; // [rsp+140h] [rbp-178h]
  __int64 v68; // [rsp+148h] [rbp-170h]
  __int64 v69; // [rsp+150h] [rbp-168h]
  int v70; // [rsp+158h] [rbp-160h] BYREF
  __int64 v71; // [rsp+160h] [rbp-158h]
  __int64 v72; // [rsp+168h] [rbp-150h]
  __int64 v73; // [rsp+170h] [rbp-148h]
  __int64 v74; // [rsp+178h] [rbp-140h]
  __int64 v75; // [rsp+180h] [rbp-138h]
  __int64 v76; // [rsp+188h] [rbp-130h]
  __int64 v77; // [rsp+190h] [rbp-128h]
  __int128 v78; // [rsp+1B0h] [rbp-108h]
  OLECHAR sz; // [rsp+1C0h] [rbp-F8h] BYREF
  __int128 v80; // [rsp+1C2h] [rbp-F6h]
  __int128 v81; // [rsp+1D2h] [rbp-E6h]
  __int128 v82; // [rsp+1E2h] [rbp-D6h]
  __int128 v83; // [rsp+1F2h] [rbp-C6h]
  __int64 v84; // [rsp+202h] [rbp-B6h]
  int v85; // [rsp+20Ah] [rbp-AEh]
  char Destination[16]; // [rsp+210h] [rbp-A8h] BYREF
  __int128 v87; // [rsp+220h] [rbp-98h]
  __int128 v88; // [rsp+230h] [rbp-88h]
  __int128 v89; // [rsp+240h] [rbp-78h]
  __int128 v90; // [rsp+250h] [rbp-68h]
  __int128 v91; // [rsp+260h] [rbp-58h]
  __int128 v92; // [rsp+270h] [rbp-48h]
  __int128 v93; // [rsp+280h] [rbp-38h]

  v75 = -2;
  v57 = this;
  v2 = 8LL * SystemThread_TlsIndex;
  v42 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(SystemThread_TlsOffset
                                          + *(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer + v2)
                                          + 8LL)
                              + 96LL)
                  + 1456LL);
  *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(SystemThread_TlsOffset
                                    + *(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer + v2)
                                    + 8LL)
                        + 96LL)
            + 1456LL) = 1;
  if ( !*((_QWORD *)this + 59) )
    utassert_fail(1u, "nullptr != m_apTsqlTask", "DbCopyVdi.cpp", 937, 0);
  if ( !*((_QWORD *)this + 21) )
    utassert_fail(1u, "nullptr != m_pDatabaseName", "DbCopyVdi.cpp", 938, 0);
  if ( (*((_DWORD *)this + 10) & 1) != 0 )
    utassert_fail(1u, "IS_OFF (InProgress, m_state)", "DbCopyVdi.cpp", 939, 0);
  v48[0] = 0;
  v49 = (_QWORD *)((char *)this + 272);
  if ( *((_QWORD *)this + 35) )
    utassert_fail(1u, "!m_vdiNotify.m_listElem.IsInList ()", "DbCopyVdi.cpp", 945, 0);
  ExcHandler::ExcHandler((ExcHandler *)v62, 0, 0, 0, hdl_prntbackout, 0);
  v47 = 0;
  v40 = 0;
  v41 = 0;
  v56 = 0;
  v43 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                          + SystemThread_TlsOffset
                                          + 8LL)
                              + 96LL)
                  + 1156LL);
  v52 = 0;
  v53 = 0;
  v50[0] = 0;
  v51 = 0;
  if ( !*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                              + SystemThread_TlsOffset
                              + 8LL)
                  + 96LL) )
    utassert_fail(1u, "nullptr != SE_TLS", "DbCopyDirectory.cpp", 68, 0);
  v44 = 0;
  v45 = 0;
  v3 = 0;
  v38 = 0;
  v39 = 0;
  AutoSimpleXact::Begin((AutoSimpleXact *)&v47, L"INTERNAL VDI CLIENT XACT", 8, 0);
  MasterDbId = GetMasterDbId();
  if ( !CAutoDb::FUse((CAutoDb *)&v40, MasterDbId, 0, 1, 1, 0) )
  {
    VdiClient::ReportError(this, 4);
    AutoBulkOpLockNotifier::~AutoBulkOpLockNotifier((AutoBulkOpLockNotifier *)v50);
    AutoOpenDB::CloseDB((AutoOpenDB *)&v52);
    *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                      + SystemThread_TlsOffset
                                      + 8LL)
                          + 96LL)
              + 1156LL) = v43;
    if ( v40 )
    {
      v40 = 0;
      ((void (__fastcall *)(__int64, __int64))g_dbtableFactory[6])(0xFFFFFFFFLL, 16);
    }
    if ( !v47 )
      goto LABEL_99;
    goto LABEL_98;
  }
  if ( GetMasterDbId() != v40 )
    utassert_fail(1u, "MASTERDBID == masterDb.GetDbId ()", "DbCopyVdi.cpp", 967, 0);
  v5 = -1;
  if ( *((_BYTE *)this + 144) )
  {
    v6 = (const wchar_t *)*((_QWORD *)this + 21);
    v7 = -1;
    do
      ++v7;
    while ( v6[v7] );
    v46 = 2 * v7;
    if ( !CAutoDb::FUse((CAutoDb *)&v41, v6, 2 * v7, 1, 1, 0) )
    {
      VdiClient::ReportError(this, 5);
      AutoBulkOpLockNotifier::~AutoBulkOpLockNotifier((AutoBulkOpLockNotifier *)v50);
      AutoOpenDB::CloseDB((AutoOpenDB *)&v52);
      *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                        + SystemThread_TlsOffset
                                        + 8LL)
                            + 96LL)
                + 1156LL) = v43;
      if ( v41 )
      {
        v41 = 0;
        ((void (__fastcall *)(__int64, __int64))g_dbtableFactory[6])(0xFFFFFFFFLL, 16);
      }
      if ( v40 )
      {
        v40 = 0;
        ((void (__fastcall *)(__int64, __int64))g_dbtableFactory[6])(0xFFFFFFFFLL, 16);
      }
      if ( !v47 )
        goto LABEL_99;
      goto LABEL_98;
    }
    v8 = v41;
    if ( !v41 )
      utassert_fail(1u, "x_MDDatabaseIdBad != userDb.GetDbId ()", "DbCopyVdi.cpp", 977, 0);
    AutoBulkOpLockNotifier::Set((AutoBulkOpLockNotifier *)v50, (VdiClient *)((char *)this + 216));
  }
  else
  {
    v8 = v41;
  }
  HadrDbMgrAutoSetupContainedAgMaster::HadrDbMgrAutoSetupContainedAgMaster(
    (HadrDbMgrAutoSetupContainedAgMaster *)v58,
    v8,
    (const struct _GUID *)this + 11);
  v9 = *((_DWORD *)this + 35);
  if ( v9 )
  {
    LODWORD(v46) = *((_DWORD *)this + 35);
    v10 = 8LL * SystemThread_TlsIndex;
    v45 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(SystemThread_TlsOffset
                                            + *(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer + v10)
                                            + 8LL)
                                + 96LL)
                    + 1164LL);
    *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(SystemThread_TlsOffset
                                      + *(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer + v10)
                                      + 8LL)
                          + 96LL)
              + 1164LL) = v9;
    v44 = 1;
    v3 = 0;
  }
  if ( dword_1031852C8 )
  {
    v11 = *((_DWORD *)this + 35);
    if ( v11 )
    {
      if ( FSystemDBId(v11, 0x50u) )
        goto LABEL_40;
    }
    v12 = (const wchar_t *)*((_QWORD *)this + 21);
    v13 = -1;
    do
      ++v13;
    while ( v12[v13] );
    v76 = 2 * v13;
    if ( CompareStringWEnglishNoCase(
           1u,
           0,
           v12,
           (unsigned __int64)(2 * (int)v13) >> 1,
           L"msdb",
           (unsigned __int64)(int)dword_1031C47DC >> 1) == 2 )
    {
LABEL_40:
      v14 = 8LL * SystemThread_TlsIndex;
      v39 = *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(SystemThread_TlsOffset
                                             + *(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer + v14)
                                             + 8LL)
                                 + 96LL)
                     + 1168LL);
      *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(SystemThread_TlsOffset
                                       + *(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer + v14)
                                       + 8LL)
                           + 96LL)
               + 1168LL) = 1;
      v3 = 1;
      v38 = 1;
    }
  }
  if ( *((_DWORD *)this + 33) == 1 )
  {
    v15 = *((_DWORD *)this + 34);
    if ( v15 )
    {
      if ( !dword_103172528 )
      {
        LODWORD(v46) = *((_DWORD *)this + 34);
        *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                          + SystemThread_TlsOffset
                                          + 8LL)
                              + 96LL)
                  + 1156LL) = v15;
        if ( v47 )
          v16 = (struct BaseXact *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v47 + 64LL))(v47);
        else
          v16 = 0;
        AutoOpenDB::Open((AutoOpenDB *)&v52, v16, *((_DWORD *)this + 34), 0x80u, 1);
        v3 = v38;
      }
    }
  }
  v17 = *((_QWORD *)this + 21);
  *((_QWORD *)this + 36) = this;
  *((_QWORD *)this + 37) = v17;
  CAutoVdiNotification::Register((CAutoVdiNotification *)v48);
  ExecSql = CreateExecSql(*((struct IMemObj **)this + 2), 0);
  v19 = ExecSql;
  v46 = (__int64)ExecSql;
  v56 = ExecSql;
  if ( !ExecSql )
  {
    VdiClient::ReportError(this, 6);
    HadrDbMgrAutoSetupContainedAgMaster::~HadrDbMgrAutoSetupContainedAgMaster((HadrDbMgrAutoSetupContainedAgMaster *)v58);
    if ( v3 )
      *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                       + SystemThread_TlsOffset
                                       + 8LL)
                           + 96LL)
               + 1168LL) = v39;
    if ( v44 )
      *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                        + SystemThread_TlsOffset
                                        + 8LL)
                            + 96LL)
                + 1164LL) = v45;
    AutoBulkOpLockNotifier::~AutoBulkOpLockNotifier((AutoBulkOpLockNotifier *)v50);
    AutoOpenDB::CloseDB((AutoOpenDB *)&v52);
    *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                      + SystemThread_TlsOffset
                                      + 8LL)
                          + 96LL)
              + 1156LL) = v43;
    if ( v41 )
    {
      v41 = 0;
      ((void (__fastcall *)(__int64, __int64))g_dbtableFactory[6])(0xFFFFFFFFLL, 16);
    }
    if ( v40 )
    {
      v40 = 0;
      ((void (__fastcall *)(__int64, __int64))g_dbtableFactory[6])(0xFFFFFFFFLL, 16);
    }
    if ( !v47 )
      goto LABEL_99;
    goto LABEL_98;
  }
  (*(void (__fastcall **)(struct IExecSql *))(*(_QWORD *)ExecSql + 48LL))(ExecSql);
  (*(void (__fastcall **)(struct IExecSql *))(*(_QWORD *)v19 + 56LL))(v19);
  (*(void (__fastcall **)(struct IExecSql *))(*(_QWORD *)v19 + 120LL))(v19);
  EventManualInternal<SuspendQueueSLock>::Signal((char *)this + 376, 0);
  v65 = 4195282;
  v66 = 0;
  v68 = 0;
  v67 = 0;
  v69 = 0;
  LOBYTE(v37) = 1;
  v20 = WaitableBase::Wait((char *)this + 424, 30000, &v65, 0, v37);
  if ( v20 )
  {
    SosResultString = VdiClient::GetSosResultString(v20);
    VdiClient::ReportError(this, 24, SosResultString);
    HadrDbMgrAutoSetupContainedAgMaster::~HadrDbMgrAutoSetupContainedAgMaster((HadrDbMgrAutoSetupContainedAgMaster *)v58);
    if ( v3 )
      *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                       + SystemThread_TlsOffset
                                       + 8LL)
                           + 96LL)
               + 1168LL) = v39;
    if ( v44 )
      *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                        + SystemThread_TlsOffset
                                        + 8LL)
                            + 96LL)
                + 1164LL) = v45;
    AutoBulkOpLockNotifier::~AutoBulkOpLockNotifier((AutoBulkOpLockNotifier *)v50);
    AutoOpenDB::CloseDB((AutoOpenDB *)&v52);
    *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                      + SystemThread_TlsOffset
                                      + 8LL)
                          + 96LL)
              + 1156LL) = v43;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v46 + 224LL))(v46, 1);
    if ( v41 )
    {
      v41 = 0;
      ((void (__fastcall *)(__int64, __int64))g_dbtableFactory[6])(0xFFFFFFFFLL, 16);
    }
    if ( v40 )
    {
      v40 = 0;
      ((void (__fastcall *)(__int64, __int64))g_dbtableFactory[6])(0xFFFFFFFFLL, 16);
    }
    if ( !v47 )
      goto LABEL_99;
    goto LABEL_98;
  }
  if ( (*((_DWORD *)this + 10) & 8) != 0 )
  {
    HadrDbMgrAutoSetupContainedAgMaster::~HadrDbMgrAutoSetupContainedAgMaster((HadrDbMgrAutoSetupContainedAgMaster *)v58);
    if ( v38 )
      *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                       + SystemThread_TlsOffset
                                       + 8LL)
                           + 96LL)
               + 1168LL) = v39;
    if ( v44 )
      *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                        + SystemThread_TlsOffset
                                        + 8LL)
                            + 96LL)
                + 1164LL) = v45;
    AutoBulkOpLockNotifier::~AutoBulkOpLockNotifier((AutoBulkOpLockNotifier *)v50);
    AutoOpenDB::CloseDB((AutoOpenDB *)&v52);
    *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                      + SystemThread_TlsOffset
                                      + 8LL)
                          + 96LL)
              + 1156LL) = v43;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v46 + 224LL))(v46, 1);
    if ( v41 )
    {
      v41 = 0;
      ((void (__fastcall *)(__int64, __int64))g_dbtableFactory[6])(0xFFFFFFFFLL, 16);
    }
    if ( v40 )
    {
      v40 = 0;
      ((void (__fastcall *)(__int64, __int64))g_dbtableFactory[6])(0xFFFFFFFFLL, 16);
    }
    if ( !v47 )
      goto LABEL_99;
    goto LABEL_98;
  }
  v22 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                  + SystemThread_TlsOffset);
  *(_OWORD *)Destination = 0;
  v87 = 0;
  v88 = 0;
  v89 = 0;
  v90 = 0;
  v91 = 0;
  v92 = 0;
  v93 = 0;
  if ( *((_DWORD *)this + 33) == 1 )
  {
    v23 = "CleanupOnFailure";
    if ( *((_BYTE *)this + 192) )
      v23 = "CleanupOnFailureChimeraDb";
    strcpy_s(Destination, 0x80u, v23);
  }
  else
  {
    v78 = *(_OWORD *)((char *)this + 196);
    StringFromGUID2((const GUID *const)((char *)this + 196), &sz, 39);
    v85 = 0;
    *(_OWORD *)Destination = v80;
    v87 = v81;
    v88 = v82;
    v89 = v83;
    *(_QWORD *)&v90 = v84;
    DWORD2(v90) = 0;
  }
  CUEnvTransient::SetContextInfo(*(CUEnvTransient **)(v22 + 120), (const unsigned __int8 *)Destination, 0x80u);
  v24 = *((_QWORD *)this + 20);
  do
    ++v5;
  while ( *(_WORD *)(v24 + 2 * v5) );
  v77 = v5;
  v25 = v46;
  if ( !(*(unsigned int (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v46 + 8LL))(v46, v24, (unsigned int)v5) )
  {
    (*(void (__fastcall **)(__int64, _WORD *))(*(_QWORD *)v25 + 176LL))(v25, v59);
    VdiClient::ReportError(this, 27, v59[0], v60, v61);
    HadrDbMgrAutoSetupContainedAgMaster::~HadrDbMgrAutoSetupContainedAgMaster((HadrDbMgrAutoSetupContainedAgMaster *)v58);
    if ( v38 )
      *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                       + SystemThread_TlsOffset
                                       + 8LL)
                           + 96LL)
               + 1168LL) = v39;
    if ( v44 )
      *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                        + SystemThread_TlsOffset
                                        + 8LL)
                            + 96LL)
                + 1164LL) = v45;
    AutoBulkOpLockNotifier::~AutoBulkOpLockNotifier((AutoBulkOpLockNotifier *)v50);
    AutoOpenDB::CloseDB((AutoOpenDB *)&v52);
    *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                      + SystemThread_TlsOffset
                                      + 8LL)
                          + 96LL)
              + 1156LL) = v43;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v46 + 224LL))(v46, 1);
    if ( v41 )
    {
      v41 = 0;
      ((void (__fastcall *)(__int64, __int64))g_dbtableFactory[6])(0xFFFFFFFFLL, 16);
    }
    if ( v40 )
    {
      v40 = 0;
      ((void (__fastcall *)(__int64, __int64))g_dbtableFactory[6])(0xFFFFFFFFLL, 16);
    }
    if ( !v47 )
      goto LABEL_99;
LABEL_98:
    (**(void (__fastcall ***)(__int64, __int64))v47)(v47, 1);
LABEL_99:
    ExcHandler::~ExcHandler((ExcHandler *)v62);
    CAutoVdiNotification::~CAutoVdiNotification((CAutoVdiNotification *)v48);
    *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                      + SystemThread_TlsOffset
                                      + 8LL)
                          + 96LL)
              + 1456LL) = v42;
    return;
  }
  if ( *((_BYTE *)this + 144) && *((_DWORD *)this + 54) != 1 )
    utassert_fail(
      1u,
      "!m_fGetBulkOpLock || BulkOpLockStatusHeld == m_bulkOpStatus.GetBulkOpLockResult ()",
      "DbCopyVdi.cpp",
      1078,
      0);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 32LL))(v47);
  VdiClient::ChangeState(this, 5);
  HadrDbMgrAutoSetupContainedAgMaster::~HadrDbMgrAutoSetupContainedAgMaster((HadrDbMgrAutoSetupContainedAgMaster *)v58);
  if ( v38 )
    *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                     + SystemThread_TlsOffset
                                     + 8LL)
                         + 96LL)
             + 1168LL) = v39;
  if ( v44 )
    *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                      + SystemThread_TlsOffset
                                      + 8LL)
                          + 96LL)
              + 1164LL) = v45;
  AutoBulkOpLockNotifier::~AutoBulkOpLockNotifier((AutoBulkOpLockNotifier *)v50);
  AutoOpenDB::CloseDB((AutoOpenDB *)&v52);
  *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                    + SystemThread_TlsOffset
                                    + 8LL)
                        + 96LL)
            + 1156LL) = v43;
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v46 + 224LL))(v46, 1);
  if ( v41 )
  {
    v41 = 0;
    ((void (__fastcall *)(__int64, __int64))g_dbtableFactory[6])(0xFFFFFFFFLL, 16);
  }
  if ( v40 )
  {
    v40 = 0;
    ((void (__fastcall *)(__int64, __int64))g_dbtableFactory[6])(0xFFFFFFFFLL, 16);
  }
  if ( v47 )
    (**(void (__fastcall ***)(__int64, __int64))v47)(v47, 1);
  ExcHandler::~ExcHandler((ExcHandler *)v62);
  v26 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v27 = *(struct Worker **)(v26 + 256);
  if ( !v27 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v27 = *(struct Worker **)(v26 + 256);
  }
  if ( *((_DWORD *)v27 + 139) )
    ExceptionPostCatchActions(v27);
  if ( v48[0] )
  {
    v70 = 4195283;
    v71 = 0;
    v73 = 0;
    v72 = 0;
    v74 = 0;
    v54 = &g_vdiNotificationDirectory;
    v55 = 0;
    v63 = 0;
    v28 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v29 = *(_QWORD *)(v28 + 256);
    if ( !v29 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v29 = *(_QWORD *)(v28 + 256);
    }
    v64 = v29;
    v30 = *(_DWORD *)(v29 + 616);
    v31 = !(*(_BYTE *)(v29 + 616) & 1);
    v63 = v31;
    *(_DWORD *)(v29 + 616) = v30 | 1;
    Lock = SOS_RWLock::GetLock(&g_vdiNotificationDirectory, 2, 0xFFFFFFFFLL, &v70);
    v33 = v55;
    if ( !Lock )
      v33 = 2;
    v55 = v33;
    v34 = v49;
    v35 = (_QWORD *)v49[1];
    v36 = *v49;
    *(_QWORD *)(v36 + 8) = v35;
    *v35 = v36;
    v34[1] = 0;
    *v34 = 0;
    *(_DWORD *)(v29 + 616) &= ~v31;
    if ( (_DWORD)v33 )
    {
      SOS_RWLock::ReleaseLock(&g_vdiNotificationDirectory, v33);
      v55 = 0;
    }
    v48[0] = 0;
  }
  *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                    + SystemThread_TlsOffset
                                    + 8LL)
                        + 96LL)
            + 1456LL) = v42;
}

```

## disassembly

```asm
0x100704b80  mov     rax, rsp
0x100704b83  push    rdi
0x100704b84  push    r14
0x100704b86  push    r15
0x100704b88  sub     rsp, 2A0h
0x100704b8f  mov     qword ptr [rax-138h], 0FFFFFFFFFFFFFFFEh
0x100704b9a  mov     [rax+10h], rbx
0x100704b9e  mov     [rax+18h], rsi
0x100704ba2  mov     rax, cs:__security_cookie
0x100704ba9  xor     rax, rsp
0x100704bac  mov     [rsp+2B8h+var_28], rax
0x100704bb4  mov     rsi, rcx
0x100704bb7  mov     [rsp+2B8h+var_210], rcx
0x100704bbf  mov     rdx, gs:58h
0x100704bc8  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100704bcf  mov     ecx, [rax]
0x100704bd1  lea     r9, ds:0[rcx*8]
0x100704bd9  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100704be0  mov     r8d, [rax]
0x100704be3  mov     rax, [r9+rdx]
0x100704be7  mov     rcx, [r8+rax+8]
0x100704bec  mov     rax, [rcx+60h]
0x100704bf0  mov     ecx, [rax+5B0h]
0x100704bf6  mov     [rsp+2B8h+var_27C], ecx
0x100704bfa  mov     rax, gs:58h
0x100704c03  mov     rcx, [r9+rax]
0x100704c07  mov     rax, [r8+rcx+8]
0x100704c0c  mov     rcx, [rax+60h]
0x100704c10  mov     dword ptr [rcx+5B0h], 1
0x100704c1a  cmp     qword ptr [rsi+1D8h], 0
0x100704c22  jnz     short loc_100704C4A
0x100704c24  xor     edi, edi
0x100704c26  mov     [rsp+2B8h+var_298], rdi
0x100704c2b  mov     r9d, 3A9h
0x100704c31  lea     r8, aDbcopyvdiCpp; "DbCopyVdi.cpp"
0x100704c38  lea     rdx, aNullptrMAptsql; "nullptr != m_apTsqlTask"
0x100704c3f  lea     ecx, [rdi+1]
0x100704c42  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x100704c48  jmp     short loc_100704C4C
0x100704c4a  xor     edi, edi
0x100704c4c  cmp     qword ptr [rsi+0A8h], 0
0x100704c54  jnz     short loc_100704C7A
0x100704c56  mov     [rsp+2B8h+var_298], rdi
0x100704c5b  mov     r9d, 3AAh
0x100704c61  lea     r8, aDbcopyvdiCpp; "DbCopyVdi.cpp"
0x100704c68  lea     rdx, aNullptrMPdatab; "nullptr != m_pDatabaseName"
0x100704c6f  mov     ecx, 1
0x100704c74  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x100704c7a  mov     eax, [rsi+28h]
0x100704c7d  test    al, 1
0x100704c7f  jz      short loc_100704CA5
0x100704c81  mov     [rsp+2B8h+var_298], rdi
0x100704c86  mov     r9d, 3ABh
0x100704c8c  lea     r8, aDbcopyvdiCpp; "DbCopyVdi.cpp"
0x100704c93  lea     rdx, aIsOffInprogres; "IS_OFF (InProgress, m_state)"
0x100704c9a  mov     ecx, 1
0x100704c9f  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x100704ca5  mov     [rsp+2B8h+var_258], 0
0x100704caa  lea     rax, [rsi+110h]
0x100704cb1  mov     [rsp+2B8h+var_250], rax
0x100704cb6  cmp     qword ptr [rsi+118h], 0
0x100704cbe  jz      short loc_100704CE5
0x100704cc0  mov     [rsp+2B8h+var_298], rdi
0x100704cc5  mov     r9d, 3B1h
0x100704ccb  lea     r8, aDbcopyvdiCpp; "DbCopyVdi.cpp"
0x100704cd2  lea     rdx, aMVdinotifyMLis; "!m_vdiNotify.m_listElem.IsInList ()"
0x100704cd9  mov     ecx, 1
0x100704cde  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x100704ce4  nop
0x100704ce5  xor     edx, edx; unsigned __int16
0x100704ce7  mov     [rsp+2B8h+var_290], rdi; struct Worker *
0x100704cec  mov     rax, cs:__imp_?hdl_prntbackout@@YAHHHHHPEAD@Z; hdl_prntbackout(int,int,int,int,char *)
0x100704cf3  mov     [rsp+2B8h+var_298], rax; int (*)(int, int, int, int, char *)
0x100704cf8  xor     r9d, r9d; unsigned __int8
0x100704cfb  xor     r8d, r8d; unsigned __int8
0x100704cfe  lea     rcx, [rsp+2B8h+var_1C0]; this
0x100704d06  call    ??0ExcHandler@@QEAA@GEEP6AHHHHHPEAD@ZPEAVWorker@@@Z; ExcHandler::ExcHandler(ushort,uchar,uchar,int (*)(int,int,int,int,char *),Worker *)
0x100704d0b  nop
0x100704d0c  mov     [rsp+2B8h+var_260], rdi
0x100704d11  mov     [rsp+2B8h+var_284], edi
0x100704d15  mov     [rsp+2B8h+var_280], edi
0x100704d19  mov     [rsp+2B8h+var_218], rdi
0x100704d21  mov     rdx, gs:58h
0x100704d2a  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100704d31  mov     ecx, [rax]
0x100704d33  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100704d3a  mov     eax, [rax]
0x100704d3c  add     rax, [rdx+rcx*8]
0x100704d40  mov     rax, [rax+8]
0x100704d44  mov     rcx, [rax+60h]
0x100704d48  mov     eax, [rcx+484h]
0x100704d4e  mov     [rsp+2B8h+var_278], eax
0x100704d52  mov     [rsp+2B8h+var_238], rdi
0x100704d5a  mov     [rsp+2B8h+var_230], edi
0x100704d61  mov     [rsp+2B8h+var_248], 0
0x100704d66  mov     [rsp+2B8h+var_240], rdi
0x100704d6b  mov     rdx, gs:58h
0x100704d74  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100704d7b  mov     ecx, [rax]
0x100704d7d  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100704d84  mov     eax, [rax]
0x100704d86  add     rax, [rdx+rcx*8]
0x100704d8a  mov     rax, [rax+8]
0x100704d8e  cmp     qword ptr [rax+60h], 0
0x100704d93  jnz     short loc_100704DB9
0x100704d95  mov     [rsp+2B8h+var_298], rdi
0x100704d9a  mov     r9d, 44h ; 'D'
0x100704da0  lea     r8, aDbcopydirector; "DbCopyDirectory.cpp"
0x100704da7  lea     rdx, aNullptrSeTls; "nullptr != SE_TLS"
0x100704dae  lea     ecx, [r9-43h]
0x100704db2  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x100704db8  nop
0x100704db9  mov     [rsp+2B8h+var_270], 0
0x100704dbe  mov     [rsp+2B8h+var_26C], edi
0x100704dc2  xor     r15b, r15b
0x100704dc5  mov     [rsp+2B8h+var_288], r15b
0x100704dca  mov     [rsp+2B8h+var_287], r15b
0x100704dcf  xor     r9d, r9d; bool
0x100704dd2  lea     r8d, [r9+8]; int
0x100704dd6  lea     rdx, aInternalVdiCli; "INTERNAL VDI CLIENT XACT"
0x100704ddd  lea     rcx, [rsp+2B8h+var_260]; this
0x100704de2  call    ?Begin@AutoSimpleXact@@QEAAXPEB_WH_N@Z; AutoSimpleXact::Begin(wchar_t const *,int,bool)
0x100704de7  call    ?GetMasterDbId@@YAGXZ; GetMasterDbId(void)
0x100704dec  movzx   edx, ax; unsigned int
0x100704def  mov     dword ptr [rsp+2B8h+var_290], edi; unsigned int
0x100704df3  mov     byte ptr [rsp+2B8h+var_298], 1; bool
0x100704df8  mov     r9b, 1; bool
0x100704dfb  xor     r8d, r8d; struct BaseXact *
0x100704dfe  lea     rcx, [rsp+2B8h+var_284]; this
0x100704e03  call    ?FUse@CAutoDb@@QEAA_NKPEAVBaseXact@@_N1K@Z; CAutoDb::FUse(ulong,BaseXact *,bool,bool,ulong)
0x100704e08  test    al, al
0x100704e0a  jnz     loc_100704EEC
0x100704e10  mov     edx, 4
0x100704e15  mov     rcx, rsi
0x100704e18  call    ?ReportError@VdiClient@@AEAAXW4ErrorCode@1@@Z; VdiClient::ReportError(VdiClient::ErrorCode)
0x100704e1d  nop
0x100704e1e  lea     rcx, [rsp+2B8h+var_248]; this
0x100704e23  call    ??1AutoBulkOpLockNotifier@@QEAA@XZ; AutoBulkOpLockNotifier::~AutoBulkOpLockNotifier(void)
0x100704e28  nop
0x100704e29  lea     rcx, [rsp+2B8h+var_238]; this
0x100704e31  call    ?CloseDB@AutoOpenDB@@AEAAXXZ; AutoOpenDB::CloseDB(void)
0x100704e36  nop
0x100704e37  mov     rdx, gs:58h
0x100704e40  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100704e47  mov     ecx, [rax]
0x100704e49  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100704e50  mov     eax, [rax]
0x100704e52  add     rax, [rdx+rcx*8]
0x100704e56  mov     rax, [rax+8]
0x100704e5a  mov     rcx, [rax+60h]
0x100704e5e  mov     eax, [rsp+2B8h+var_278]
0x100704e62  mov     [rcx+484h], eax
0x100704e68  cmp     [rsp+2B8h+var_284], 0
0x100704e6d  jz      short loc_100704E88
0x100704e6f  mov     [rsp+2B8h+var_284], edi
0x100704e73  mov     edx, 10h
0x100704e78  mov     ecx, 0FFFFFFFFh
0x100704e7d  mov     rax, cs:__imp_?g_dbtableFactory@@3UDBTableFactory@@A; DBTableFactory g_dbtableFactory
0x100704e84  call    qword ptr [rax+30h]
0x100704e87  nop
0x100704e88  mov     rcx, [rsp+2B8h+var_260]
0x100704e8d  test    rcx, rcx
0x100704e90  jz      short loc_100704E9D
0x100704e92  mov     rax, [rcx]
0x100704e95  mov     edx, 1
0x100704e9a  call    qword ptr [rax]
0x100704e9c  nop
0x100704e9d  lea     rcx, [rsp+2B8h+var_1C0]; this
0x100704ea5  call    ??1ExcHandler@@QEAA@XZ; ExcHandler::~ExcHandler(void)
0x100704eaa  nop
0x100704eab  lea     rcx, [rsp+2B8h+var_258]; this
0x100704eb0  call    ??1CAutoVdiNotification@@QEAA@XZ; CAutoVdiNotification::~CAutoVdiNotification(void)
0x100704eb5  nop
0x100704eb6  mov     rdx, gs:58h
0x100704ebf  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100704ec6  mov     ecx, [rax]
0x100704ec8  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100704ecf  mov     eax, [rax]
0x100704ed1  add     rax, [rdx+rcx*8]
0x100704ed5  mov     rax, [rax+8]
0x100704ed9  mov     rcx, [rax+60h]
0x100704edd  mov     eax, [rsp+2B8h+var_27C]
0x100704ee1  mov     [rcx+5B0h], eax
0x100704ee7  jmp     loc_100705E89
0x100704eec  call    ?GetMasterDbId@@YAGXZ; GetMasterDbId(void)
0x100704ef1  movzx   eax, ax
0x100704ef4  cmp     eax, [rsp+2B8h+var_284]
0x100704ef8  jz      short loc_100704F1E
0x100704efa  mov     [rsp+2B8h+var_298], rdi
0x100704eff  mov     r9d, 3C7h
0x100704f05  lea     r8, aDbcopyvdiCpp; "DbCopyVdi.cpp"
0x100704f0c  lea     rdx, aMasterdbidMast; "MASTERDBID == masterDb.GetDbId ()"
0x100704f13  mov     ecx, 1
0x100704f18  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x100704f1e  mov     r14, 0FFFFFFFFFFFFFFFFh
0x100704f25  cmp     byte ptr [rsi+90h], 0
0x100704f2c  jz      loc_1007050AC
0x100704f32  mov     rdx, [rsi+0A8h]; wchar_t *
0x100704f39  mov     rax, r14
0x100704f3c  nop     dword ptr [rax+00h]
0x100704f40  inc     rax
0x100704f43  cmp     word ptr [rdx+rax*2], 0
0x100704f48  jnz     short loc_100704F40
0x100704f4a  add     rax, rax
0x100704f4d  mov     [rsp+2B8h+var_268], rax
0x100704f52  mov     dword ptr [rsp+2B8h+var_290], edi; unsigned int
0x100704f56  mov     byte ptr [rsp+2B8h+var_298], 1; bool
0x100704f5b  mov     r9b, 1; bool
0x100704f5e  mov     r8d, eax; unsigned int
0x100704f61  lea     rcx, [rsp+2B8h+var_280]; this
0x100704f66  call    ?FUse@CAutoDb@@QEAA_NPEB_WK_N1K@Z; CAutoDb::FUse(wchar_t const *,ulong,bool,bool,ulong)
0x100704f6b  test    al, al
0x100704f6d  jnz     loc_10070506F
0x100704f73  mov     edx, 5
0x100704f78  mov     rcx, rsi
0x100704f7b  call    ?ReportError@VdiClient@@AEAAXW4ErrorCode@1@@Z; VdiClient::ReportError(VdiClient::ErrorCode)
0x100704f80  nop
0x100704f81  lea     rcx, [rsp+2B8h+var_248]; this
0x100704f86  call    ??1AutoBulkOpLockNotifier@@QEAA@XZ; AutoBulkOpLockNotifier::~AutoBulkOpLockNotifier(void)
0x100704f8b  nop
0x100704f8c  lea     rcx, [rsp+2B8h+var_238]; this
0x100704f94  call    ?CloseDB@AutoOpenDB@@AEAAXXZ; AutoOpenDB::CloseDB(void)
0x100704f99  nop
0x100704f9a  mov     rdx, gs:58h
0x100704fa3  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100704faa  mov     ecx, [rax]
0x100704fac  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100704fb3  mov     eax, [rax]
0x100704fb5  add     rax, [rdx+rcx*8]
0x100704fb9  mov     rax, [rax+8]
0x100704fbd  mov     rcx, [rax+60h]
0x100704fc1  mov     eax, [rsp+2B8h+var_278]
0x100704fc5  mov     [rcx+484h], eax
0x100704fcb  cmp     [rsp+2B8h+var_280], 0
0x100704fd0  jz      short loc_100704FEB
0x100704fd2  mov     [rsp+2B8h+var_280], edi
0x100704fd6  mov     edx, 10h
0x100704fdb  mov     ecx, 0FFFFFFFFh
0x100704fe0  mov     rax, cs:__imp_?g_dbtableFactory@@3UDBTableFactory@@A; DBTableFactory g_dbtableFactory
0x100704fe7  call    qword ptr [rax+30h]
0x100704fea  nop
0x100704feb  cmp     [rsp+2B8h+var_284], 0
0x100704ff0  jz      short loc_10070500B
0x100704ff2  mov     [rsp+2B8h+var_284], edi
0x100704ff6  mov     edx, 10h
0x100704ffb  mov     ecx, 0FFFFFFFFh
0x100705000  mov     rax, cs:__imp_?g_dbtableFactory@@3UDBTableFactory@@A; DBTableFactory g_dbtableFactory
0x100705007  call    qword ptr [rax+30h]
0x10070500a  nop
0x10070500b  mov     rcx, [rsp+2B8h+var_260]
0x100705010  test    rcx, rcx
0x100705013  jz      short loc_100705020
0x100705015  mov     rax, [rcx]
0x100705018  mov     edx, 1
0x10070501d  call    qword ptr [rax]
0x10070501f  nop
0x100705020  lea     rcx, [rsp+2B8h+var_1C0]; this
0x100705028  call    ??1ExcHandler@@QEAA@XZ; ExcHandler::~ExcHandler(void)
0x10070502d  nop
0x10070502e  lea     rcx, [rsp+2B8h+var_258]; this
0x100705033  call    ??1CAutoVdiNotification@@QEAA@XZ; CAutoVdiNotification::~CAutoVdiNotification(void)
0x100705038  nop
0x100705039  mov     rdx, gs:58h
0x100705042  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100705049  mov     ecx, [rax]
0x10070504b  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100705052  mov     eax, [rax]
0x100705054  add     rax, [rdx+rcx*8]
0x100705058  mov     rax, [rax+8]
0x10070505c  mov     rcx, [rax+60h]
0x100705060  mov     eax, [rsp+2B8h+var_27C]
0x100705064  mov     [rcx+5B0h], eax
0x10070506a  jmp     loc_100705E89
0x10070506f  mov     ebx, [rsp+2B8h+var_280]
0x100705073  test    ebx, ebx
0x100705075  jnz     short loc_100705099
0x100705077  mov     [rsp+2B8h+var_298], rdi
0x10070507c  mov     r9d, 3D1h
0x100705082  lea     r8, aDbcopyvdiCpp; "DbCopyVdi.cpp"
0x100705089  lea     rdx, aXMddatabaseidb_0; "x_MDDatabaseIdBad != userDb.GetDbId ()"
0x100705090  lea     ecx, [rbx+1]
0x100705093  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x100705099  lea     rdx, [rsi+0D8h]; struct CBulkOpLockNotifier *
0x1007050a0  lea     rcx, [rsp+2B8h+var_248]; this
0x1007050a5  call    ?Set@AutoBulkOpLockNotifier@@QEAAXPEAVCBulkOpLockNotifier@@@Z; AutoBulkOpLockNotifier::Set(CBulkOpLockNotifier *)
0x1007050aa  jmp     short loc_1007050B0
0x1007050ac  mov     ebx, [rsp+2B8h+var_280]
0x1007050b0  lea     r8, [rsi+0B0h]; struct _GUID *
0x1007050b7  mov     edx, ebx; unsigned int
0x1007050b9  lea     rcx, [rsp+2B8h+var_208]; this
0x1007050c1  call    ??0HadrDbMgrAutoSetupContainedAgMaster@@QEAA@KAEBU_GUID@@@Z; HadrDbMgrAutoSetupContainedAgMaster::HadrDbMgrAutoSetupContainedAgMaster(ulong,_GUID const &)
0x1007050c6  nop
0x1007050c7  mov     eax, [rsi+8Ch]
0x1007050cd  test    eax, eax
0x1007050cf  jz      short loc_10070513B
0x1007050d1  mov     dword ptr [rsp+2B8h+var_268], eax
0x1007050d5  mov     rdx, gs:58h
0x1007050de  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1007050e5  mov     ecx, [rax]
0x1007050e7  lea     r9, ds:0[rcx*8]
  ... truncated ...
```
