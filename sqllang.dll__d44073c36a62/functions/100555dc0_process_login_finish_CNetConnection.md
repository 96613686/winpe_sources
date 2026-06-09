# process_login_finish(CNetConnection *)

- ea: `0x100555dc0`
- end: `0x100555e0b`
- name: `?process_login_finish@@YA?AW4ECommandResult@@PEAVCNetConnection@@@Z`
- size: `75`
- prototype: ``
- caller_count: `0`
- callee_count: `31`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x100401070`
- `0x100401090`
- `0x1004012d0`
- `0x100401340`
- `0x100401433`
- `0x1004019c0`
- `0x100401a90`
- `0x100401b90`
- `0x1004026b0`
- `0x1004036f0`
- `0x100403b40`
- `0x100404720`
- `0x1004054f0`
- `0x100419b40`
- `0x10041a970`
- `0x10041e0c0`
- `0x100430ea0`
- `0x100430f60`
- `0x100432300`
- `0x10054cdb0`
- `0x10054d130`
- `0x10054e540`
- `0x10054f2e0`
- `0x1005509f0`
- `0x100550fe0`
- `0x100555dc0`
- `0x100555e20`
- `0x100f04930`
- `0x100f08630`
- `0x101ec64a0`
- `0x101ed2740`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x1005498f4`
- `KERNEL32!QueryPerformanceCounter` at `0x100549992`
- `KERNEL32!QueryPerformanceCounter` at `0x1005498f4`
- `KERNEL32!QueryPerformanceCounter` at `0x100549992`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x100549bb7`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x100549bcc`
- `sqldk!?sm_CommonCriteriaModeEnabled@SOS_PublicGlobals@@2HA` at `0x100549c36`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10054992b`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x1005499db`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1005498dc`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10054997d`
- `sqldk!?hdl_backout@@YAHHHHHPEAD@Z` at `0x100549ec3`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100549b7e`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100549b7e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100f05d3d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100f05d3d`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100f06436`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100f06436`
- `sqldk!SystemThread_TlsIndex` at `0x1005499fb`
- `sqldk!SystemThread_TlsIndex` at `0x100549aa8`
- `sqldk!SystemThread_TlsIndex` at `0x100549c70`
- `sqldk!SystemThread_TlsIndex` at `0x100549d31`
- `sqldk!SystemThread_TlsIndex` at `0x100549d6a`
- `sqldk!SystemThread_TlsIndex` at `0x100549e89`
- `sqldk!SystemThread_TlsIndex` at `0x100549f0c`
- `sqldk!SystemThread_TlsIndex` at `0x100549f51`
- `sqldk!SystemThread_TlsIndex` at `0x100f05bdb`
- `sqldk!SystemThread_TlsIndex` at `0x100f05c14`
- `sqldk!SystemThread_TlsIndex` at `0x100f05d86`
- `sqldk!SystemThread_TlsIndex` at `0x100f05e60`
- `sqldk!SystemThread_TlsIndex` at `0x100f05e99`
- `sqldk!SystemThread_TlsIndex` at `0x100f05f99`
- `sqldk!SystemThread_TlsIndex` at `0x100f06073`
- `sqldk!SystemThread_TlsIndex` at `0x100f060ac`
- `sqldk!SystemThread_TlsIndex` at `0x100f061cf`
- `sqldk!SystemThread_TlsIndex` at `0x100f062a9`
- `sqldk!SystemThread_TlsIndex` at `0x100f062e2`
- `sqldk!SystemThread_TlsOffset` at `0x100549a04`
- `sqldk!SystemThread_TlsOffset` at `0x100549ab1`
- `sqldk!SystemThread_TlsOffset` at `0x100549c79`
- `sqldk!SystemThread_TlsOffset` at `0x100549d3a`
- `sqldk!SystemThread_TlsOffset` at `0x100549d73`
- `sqldk!SystemThread_TlsOffset` at `0x100549e92`
- `sqldk!SystemThread_TlsOffset` at `0x100549f15`
- `sqldk!SystemThread_TlsOffset` at `0x100549f5a`
- `sqldk!SystemThread_TlsOffset` at `0x100f05be4`
- `sqldk!SystemThread_TlsOffset` at `0x100f05c1d`
- `sqldk!SystemThread_TlsOffset` at `0x100f05d8f`
- `sqldk!SystemThread_TlsOffset` at `0x100f05e69`
- `sqldk!SystemThread_TlsOffset` at `0x100f05ea2`
- `sqldk!SystemThread_TlsOffset` at `0x100f05fa2`
- `sqldk!SystemThread_TlsOffset` at `0x100f0607c`
- `sqldk!SystemThread_TlsOffset` at `0x100f060b5`
- `sqldk!SystemThread_TlsOffset` at `0x100f061d8`
- `sqldk!SystemThread_TlsOffset` at `0x100f062b2`
- `sqldk!SystemThread_TlsOffset` at `0x100f062eb`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100f06423`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100f06423`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100f05a9c`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100f05b42`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100f05a9c`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100f05b42`
- `sqlmin!??0SEParams@@QEAA@XZ` at `0x100549a98`
- `sqlmin!??0SEParams@@QEAA@XZ` at `0x100549a98`
- `sqlmin!??1SEParams@@UEAA@XZ` at `0x100549cd6`
- `sqlmin!??1SEParams@@UEAA@XZ` at `0x100f05dec`
- `sqlmin!??1SEParams@@UEAA@XZ` at `0x100f05fff`
- `sqlmin!??1SEParams@@UEAA@XZ` at `0x100f06235`
- `sqlmin!??1SEParams@@UEAA@XZ` at `0x100549cd6`
- `sqlmin!??1SEParams@@UEAA@XZ` at `0x100f05dec`
- `sqlmin!??1SEParams@@UEAA@XZ` at `0x100f05fff`
- `sqlmin!??1SEParams@@UEAA@XZ` at `0x100f06235`
- `sqlmin!??1AutoSETLS@@QEAA@XZ` at `0x100549d9b`
- `sqlmin!??1AutoSETLS@@QEAA@XZ` at `0x100f05c45`
- `sqlmin!??1AutoSETLS@@QEAA@XZ` at `0x100f05eca`
- `sqlmin!??1AutoSETLS@@QEAA@XZ` at `0x100f060dd`
- `sqlmin!??1AutoSETLS@@QEAA@XZ` at `0x100f06313`
- `sqlmin!??1AutoSETLS@@QEAA@XZ` at `0x100549d9b`
- `sqlmin!??1AutoSETLS@@QEAA@XZ` at `0x100f05c45`
- `sqlmin!??1AutoSETLS@@QEAA@XZ` at `0x100f05eca`
- `sqlmin!??1AutoSETLS@@QEAA@XZ` at `0x100f060dd`
- `sqlmin!??1AutoSETLS@@QEAA@XZ` at `0x100f06313`
- `sqlmin!?Destroy@AutoSETLS@@QEAAXXZ` at `0x100549d22`
- `sqlmin!?Destroy@AutoSETLS@@QEAAXXZ` at `0x100f05bcc`
- `sqlmin!?Destroy@AutoSETLS@@QEAAXXZ` at `0x100f05e51`
- `sqlmin!?Destroy@AutoSETLS@@QEAAXXZ` at `0x100f06064`
- `sqlmin!?Destroy@AutoSETLS@@QEAAXXZ` at `0x100f0629a`
- `sqlmin!?Destroy@AutoSETLS@@QEAAXXZ` at `0x100549d22`
- `sqlmin!?Destroy@AutoSETLS@@QEAAXXZ` at `0x100f05bcc`
- `sqlmin!?Destroy@AutoSETLS@@QEAAXXZ` at `0x100f05e51`
- `sqlmin!?Destroy@AutoSETLS@@QEAAXXZ` at `0x100f06064`
- `sqlmin!?Destroy@AutoSETLS@@QEAAXXZ` at `0x100f0629a`
- `sqlmin!?UninstallFromTLS@SEParams@@QEAAXXZ` at `0x100549cc3`
- `sqlmin!?UninstallFromTLS@SEParams@@QEAAXXZ` at `0x100f05dd9`
- `sqlmin!?UninstallFromTLS@SEParams@@QEAAXXZ` at `0x100f05fec`
- `sqlmin!?UninstallFromTLS@SEParams@@QEAAXXZ` at `0x100f06222`
- `sqlmin!?UninstallFromTLS@SEParams@@QEAAXXZ` at `0x100549cc3`
- `sqlmin!?UninstallFromTLS@SEParams@@QEAAXXZ` at `0x100f05dd9`
- `sqlmin!?UninstallFromTLS@SEParams@@QEAAXXZ` at `0x100f05fec`
- `sqlmin!?UninstallFromTLS@SEParams@@QEAAXXZ` at `0x100f06222`
- `sqlmin!GetXdbServerGlobals` at `0x100f059c7`
- `sqlmin!GetXdbServerGlobals` at `0x100f059da`
- `sqlmin!GetXdbServerGlobals` at `0x100f059c7`
- `sqlmin!GetXdbServerGlobals` at `0x100f059da`

## string_xrefs

- `0x100f05d19`: `SEParams is being installed more than once. Illegal usage.`

## pseudocode

```c
// Hidden C++ exception states: #wind=72
__int64 __fastcall process_login_finish(struct CNetConnection *a1)
{
  struct CNetConnection *v1; // r14
  __int64 v2; // r15
  __int64 v3; // rsi
  __int64 v4; // rsi
  struct CConnectionOutput ***v5; // r12
  struct CConnection *v6; // r13
  __int64 v7; // rcx
  CSbTransportMgr *QuadPart; // rbx
  _QWORD *v9; // rbx
  char v10; // al
  CSbTransportMgr *v11; // rbx
  unsigned __int64 v12; // rax
  _QWORD *v13; // rbx
  volatile signed __int32 *v14; // rbx
  char v15; // r13
  volatile signed __int32 *v16; // r12
  __int64 v17; // rdx
  __int64 FeatureExtension; // rax
  __int64 v19; // r8
  CUEnvTransient *v20; // rax
  CUEnvTransient *v21; // rax
  unsigned __int8 v22; // bl
  wchar_t *v23; // rax
  struct CConnection *v24; // r15
  __int64 *v25; // rdx
  __int64 v26; // rbx
  __int64 v27; // rbx
  _QWORD *v28; // rdx
  __int64 v29; // rax
  __int64 v30; // rdx
  __int64 v31; // rax
  void (__fastcall ***v32)(_QWORD, __int64); // rcx
  __int64 v33; // r9
  __int64 v34; // rdx
  __int64 v35; // rax
  __int64 v36; // rbx
  struct Worker *v37; // rcx
  __int64 v38; // r8
  __int64 v39; // rax
  __int64 v41; // rcx
  const CERT_CONTEXT *v42; // rbx
  unsigned __int8 v43; // r12
  int v44; // r8d
  int v45; // r8d
  __int64 v46; // rbx
  __int64 v47; // rbx
  _QWORD *v48; // rdx
  __int64 v49; // rax
  __int64 v50; // rdx
  __int64 v51; // rax
  void (__fastcall ***v52)(_QWORD, __int64); // rcx
  bool v53; // zf
  __int64 *v54; // rdx
  __int64 v55; // rbx
  __int64 v56; // rbx
  __int64 v57; // rbx
  _QWORD *v58; // rdx
  __int64 v59; // rax
  __int64 v60; // rdx
  __int64 v61; // rax
  void (__fastcall ***v62)(_QWORD, __int64); // rcx
  __int64 *v63; // rdx
  __int64 v64; // rbx
  __int64 v65; // rbx
  __int64 v66; // rbx
  _QWORD *v67; // rdx
  __int64 v68; // rax
  __int64 v69; // rdx
  __int64 v70; // rax
  void (__fastcall ***v71)(_QWORD, __int64); // rcx
  __int64 *v72; // rdx
  __int64 v73; // rbx
  __int64 v74; // rbx
  __int64 v75; // rbx
  _QWORD *v76; // rdx
  __int64 v77; // rax
  __int64 v78; // rdx
  __int64 v79; // rax
  void (__fastcall ***v80)(_QWORD, __int64); // rcx
  __int64 v81; // rbx
  const struct SQLError *CurrentException; // rax
  volatile signed __int32 *v83; // [rsp+30h] [rbp-1E78h]
  char v84; // [rsp+38h] [rbp-1E70h]
  unsigned __int8 v85; // [rsp+40h] [rbp-1E68h]
  LARGE_INTEGER v86; // [rsp+48h] [rbp-1E60h] BYREF
  __int64 v87; // [rsp+50h] [rbp-1E58h]
  struct CBatch *v88; // [rsp+58h] [rbp-1E50h]
  CUEnvTransient *v89; // [rsp+60h] [rbp-1E48h]
  int v90; // [rsp+68h] [rbp-1E40h]
  SEParams *v91; // [rsp+70h] [rbp-1E38h] BYREF
  __int64 v92; // [rsp+78h] [rbp-1E30h]
  struct CConnection *v93; // [rsp+80h] [rbp-1E28h]
  struct SNI_Conn **v94; // [rsp+88h] [rbp-1E20h]
  __int64 v95; // [rsp+90h] [rbp-1E18h]
  __int64 v96; // [rsp+98h] [rbp-1E10h]
  _DWORD v97[8]; // [rsp+A0h] [rbp-1E08h] BYREF
  _BYTE v98[80]; // [rsp+C0h] [rbp-1DE8h] BYREF
  _BYTE v99[40]; // [rsp+110h] [rbp-1D98h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+138h] [rbp-1D70h] BYREF
  __int64 v101; // [rsp+140h] [rbp-1D68h]
  void **v102; // [rsp+150h] [rbp-1D58h] BYREF
  char v103; // [rsp+158h] [rbp-1D50h]
  _BYTE v104[768]; // [rsp+160h] [rbp-1D48h] BYREF
  _QWORD v105[522]; // [rsp+460h] [rbp-1A48h] BYREF
  _DWORD v106[58]; // [rsp+14B0h] [rbp-9F8h] BYREF
  char v107; // [rsp+1598h] [rbp-910h] BYREF
  _BYTE v108[24]; // [rsp+15A0h] [rbp-908h] BYREF
  __int64 v109; // [rsp+15B8h] [rbp-8F0h]
  __int64 v110; // [rsp+15C0h] [rbp-8E8h]
  __int64 v111; // [rsp+1608h] [rbp-8A0h]
  _BYTE v112[16]; // [rsp+1650h] [rbp-858h] BYREF
  int v113; // [rsp+1660h] [rbp-848h] BYREF
  __int16 v114; // [rsp+1664h] [rbp-844h]
  char v115[2058]; // [rsp+1666h] [rbp-842h] BYREF

  v96 = -2;
  v1 = a1;
  v94 = (struct SNI_Conn **)a1;
  v2 = *((_QWORD *)a1 + 46);
  v3 = *(_QWORD *)(v2 + 24);
  if ( v3 )
  {
    v4 = v3 - 80;
    v95 = v4;
  }
  else
  {
    v4 = 0;
    v95 = 0;
  }
  v5 = (struct CConnectionOutput ***)*((_QWORD *)a1 + 57);
  v88 = (struct CBatch *)v5;
  v6 = (struct CConnection *)v5[4];
  v93 = v6;
  v113 = 0;
  v114 = 0;
  memset_0(v115, 0, 0x800u);
  if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)(v4 + 80) + 48LL))(v4 + 80) )
    goto LABEL_71;
  if ( !*(_DWORD *)(*((_QWORD *)v1 + 65) + 136LL)
    || !*(_DWORD *)(GetXdbServerGlobals(v7) + 20744)
    || !*(_DWORD *)(GetXdbServerGlobals(v41) + 11976) )
  {
    goto LABEL_5;
  }
  v87 = *((_QWORD *)v1 + 19);
  v42 = (const CERT_CONTEXT *)*((_QWORD *)v1 + 129);
  v43 = 0;
  if ( !v42 )
    goto LABEL_71;
  v85 = FCheckCertAllowListed(*((PCCERT_CONTEXT *)v1 + 129));
  if ( v85 )
    goto LABEL_65;
  if ( !ProxyClientTrustValidationSettings::sm_fAllowAll )
  {
    if ( !(unsigned __int8)FCheckCertAllowListed(v42) )
      goto LABEL_71;
LABEL_65:
    v43 = v85;
    if ( VerifyCertificateTrust(
           v42,
           ProxyClientTrustValidationSettings::sm_fIsCacheCertChainEnabled,
           ProxyClientTrustValidationSettings::sm_fOnlineCrlChecksDisabled,
           0) )
    {
      goto LABEL_71;
    }
  }
  *((_DWORD *)v1 + 257) = v43;
  *(_DWORD *)(*((_QWORD *)v1 + 65) + 20LL) = 0;
  v5 = (struct CConnectionOutput ***)v88;
LABEL_5:
  if ( Base_PublicGlobals::sm_invariantTscAvailable )
  {
    QueryPerformanceCounter(&PerformanceCount);
    QuadPart = (CSbTransportMgr *)PerformanceCount.QuadPart;
  }
  else
  {
    QuadPart = MEMORY[0x7FFE0008];
  }
  CNetConnection::GetLock(*(CNetConnection **)(v2 + 16));
  *(_QWORD *)(v2 + 216) = QuadPart;
  *(_DWORD *)(v2 + 232) = 1;
  v9 = *(_QWORD **)(*(_QWORD *)(v2 + 16) + 392LL);
  if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
  {
    v44 = rand();
    if ( v44 == 5 * (v44 / 5) )
      Spinlock<114,16,258>::UpdateStatSnapshot();
  }
  *v9 = 0;
  if ( (int)login(
              *((struct IMemObj **)v1 + 19),
              (struct CBatch *)v5,
              v5[4],
              *((struct SNI_Conn **)v1 + 56),
              (struct CRoutingEnvChangeInfo *)&v113) < 0 )
  {
    BYTE3(PerformanceCount.QuadPart) = -3;
    PerformanceCount.HighPart = 2;
    v101 = 0;
    srv_completioncode_ex<0>(v1, (char *)&PerformanceCount.QuadPart + 3);
  }
  else
  {
    v10 = *(_BYTE *)(v4 + 272);
    if ( (v10 & 0x20) != 0 )
      *(_BYTE *)(v4 + 272) = v10 | 4;
    if ( Base_PublicGlobals::sm_invariantTscAvailable )
    {
      QueryPerformanceCounter(&v86);
      v11 = (CSbTransportMgr *)v86.QuadPart;
    }
    else
    {
      v11 = MEMORY[0x7FFE0008];
    }
    CNetConnection::GetLock(*(CNetConnection **)(v2 + 16));
    if ( *(_DWORD *)(v2 + 232) )
    {
      v12 = *(_QWORD *)(v2 + 216);
      if ( (unsigned __int64)v11 > v12 )
        *(_QWORD *)(v2 + 224) += (char *)v11 - v12;
      *(_DWORD *)(v2 + 232) = 0;
    }
    v13 = *(_QWORD **)(*(_QWORD *)(v2 + 16) + 392LL);
    if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v45 = rand();
      if ( v45 == 5 * (v45 / 5) )
        Spinlock<114,16,258>::UpdateStatSnapshot();
    }
    *v13 = 0;
    LODWORD(v87) = 0;
    if ( !*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                    + SystemThread_TlsOffset
                    + 24LL) )
    {
      ITaskProxy::SetCurrentTaskProxy((struct ITaskProxy *)(v4 + 504));
      LODWORD(v87) = 1;
    }
    CAutoSetupCXCtxtForLoginStatsUpdate::CAutoSetupCXCtxtForLoginStatsUpdate(
      (CAutoSetupCXCtxtForLoginStatsUpdate *)v105,
      (struct CBatch *)v5,
      (struct CSession *)v4,
      v6);
    v14 = 0;
    v83 = 0;
    v15 = 0;
    v84 = 0;
    v16 = *(volatile signed __int32 **)(v4 + 648);
    if ( (*(unsigned __int8 (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)v16 + 24LL))(v16, 0) )
    {
      _InterlockedIncrement(v16 + 35);
      v14 = v16;
      v83 = v16;
      v15 = 1;
      v84 = 1;
    }
    if ( (v84 & 1) == 0 )
    {
      if ( (v15 & 1) != 0 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 32LL))(v14);
        if ( _InterlockedExchangeAdd(v14 + 35, 0xFFFFFFFF) == 1 )
        {
          v46 = *((_QWORD *)v83 + 1);
          (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v83 + 40LL))(v83, 1);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
        }
      }
      v47 = v111;
      AutoSETLS::Destroy((AutoSETLS *)v112);
      v48 = (_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                     + SystemThread_TlsOffset);
      v49 = v48[32];
      *v48 = 0;
      **(_QWORD **)(v49 + 64) = 0;
      CDiagnostics::UnlinkFromTask(*(CDiagnostics **)(v47 + 40));
      v50 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v51 = *(_QWORD *)(v50 + 256);
      *(_QWORD *)(v50 + 8) = 0;
      *(_QWORD *)(*(_QWORD *)(v51 + 64) + 8LL) = 0;
      AutoSETLS::~AutoSETLS((AutoSETLS *)v112);
      v86.QuadPart = (LONGLONG)&v107;
      PerformanceCount.QuadPart = (LONGLONG)v108;
      v52 = (void (__fastcall ***)(_QWORD, __int64))v110;
      if ( v110 )
      {
        v53 = (*(_DWORD *)(v110 + 8))-- == 1;
        if ( v53 )
          (**v52)(v52, 1);
      }
      if ( v109 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v109 + 16LL))(v109);
      v86.QuadPart = (LONGLONG)v105;
      v105[0] = &CDbLockListBase::`vftable';
      PerformanceCount.QuadPart = (LONGLONG)v106;
      v106[0] = 0;
      CTDelayedMapBase<unsigned short,CDbLockListBase::CDatabaseOptions,4,CFnH_Default<unsigned short>,CFnC_Default<unsigned short>,CFnI_Default<CDbLockListBase::CDatabaseOptions>,CFnD_Noop<unsigned short>,CFnD_Noop<CDbLockListBase::CDatabaseOptions>,CMemObjAlloc<1>>::DestroyHashMap(v106);
      goto LABEL_84;
    }
    SEParams::SEParams((SEParams *)v98);
    SetupSEParamsFromExecContexts(
      *(const struct CCompExecCtxtBasic **)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                          + SystemThread_TlsOffset),
      (struct SEParams *)v98);
    v92 = 0;
    AutoInstallParams::Install((AutoInstallParams *)&v91, (struct SEParams *)v98);
    if ( v92 )
      utassert_fail(
        1u,
        "NULL == m_separamsPrev",
        "sephlpr.cpp",
        82,
        "SEParams is being installed more than once. Illegal usage.");
    CAutoSetXLvlIntCtxtImplNoException::CAutoSetXLvlIntCtxtImplNoException(
      (CAutoSetXLvlIntCtxtImplNoException *)&v102,
      (struct CSession *)v4,
      v88);
    if ( (*(_BYTE *)(v2 + 49) & 1) != 0 )
    {
      LOBYTE(v17) = 1;
      FeatureExtension = CPhysicalConnection::GetFeatureExtension(*(_QWORD *)(v4 + 96), v17);
      if ( FeatureExtension )
        v19 = *(_QWORD *)(FeatureExtension + 56);
      else
        v19 = 0;
      *(_QWORD *)(v19 + 8) = 0;
      *(_DWORD *)(v19 + 160) = 0;
      *(_DWORD *)(v19 + 20) |= 1u;
      if ( CUEnvTransient::CalculateDeltaForTDS(*(CUEnvTransient **)(v4 + 104), 0, (struct CTdsSessionState *)v19)
        || ((LODWORD(v88) = 1459,
             v20 = (CUEnvTransient *)operator new(
                                       0x2D0u,
                                       *(struct IMemObj **)(v4 + 88),
                                       1,
                                       "sql\\ntdbms\\msql\\proc\\session.cpp",
                                       1459,
                                       3u),
             (v89 = v20) == 0)
          ? (v21 = 0)
          : (v21 = CUEnvTransient::CUEnvTransient(v20, 0, 0)),
            (*(_QWORD *)(v4 + 112) = v21) == 0) )
      {
        v102 = &CAutoSetXLvlIntCtxtImplNoException::`vftable';
        if ( v103 )
        {
          v103 = 0;
          v63 = (__int64 *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                          + SystemThread_TlsOffset);
          v64 = *v63;
          CExecLvlIntCtxt::ExitBatch(*(CExecLvlIntCtxt **)(*v63 + 128));
          *(_QWORD *)(v64 + 128) = 0;
        }
        CExecLvlIntCtxt::~CExecLvlIntCtxt((CExecLvlIntCtxt *)v104);
        v102 = &XactAccessor::`vftable';
        if ( v91 )
        {
          SEParams::UninstallFromTLS(v91);
          v91 = 0;
        }
        SEParams::~SEParams((SEParams *)v98);
        if ( (v84 & 1) != 0 )
        {
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v83 + 32LL))(v83);
          if ( _InterlockedExchangeAdd(v83 + 35, 0xFFFFFFFF) == 1 )
          {
            v65 = *((_QWORD *)v83 + 1);
            (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v83 + 40LL))(v83, 1);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
          }
        }
        v66 = v111;
        AutoSETLS::Destroy((AutoSETLS *)v112);
        v67 = (_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                       + SystemThread_TlsOffset);
        v68 = v67[32];
        *v67 = 0;
        **(_QWORD **)(v68 + 64) = 0;
        CDiagnostics::UnlinkFromTask(*(CDiagnostics **)(v66 + 40));
        v69 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        v70 = *(_QWORD *)(v69 + 256);
        *(_QWORD *)(v69 + 8) = 0;
        *(_QWORD *)(*(_QWORD *)(v70 + 64) + 8LL) = 0;
        AutoSETLS::~AutoSETLS((AutoSETLS *)v112);
        v89 = (CUEnvTransient *)&v107;
        v86.QuadPart = (LONGLONG)v108;
        v71 = (void (__fastcall ***)(_QWORD, __int64))v110;
        if ( v110 )
        {
          v53 = (*(_DWORD *)(v110 + 8))-- == 1;
          if ( v53 )
            (**v71)(v71, 1);
        }
        if ( v109 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v109 + 16LL))(v109);
        goto LABEL_128;
      }
      CSession::TakeUETransSnapshot((CSession *)v4);
    }
    v22 = (*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 232LL))(s_pServerConf);
    v23 = (wchar_t *)(*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 240LL))(s_pServerConf);
    if ( !FProcessLoginAck(v1, v23, v22, (const struct CRoutingEnvChangeInfo *)&v113) )
    {
      v102 = &CAutoSetXLvlIntCtxtImplNoException::`vftable';
      if ( v103 )
      {
        v103 = 0;
        v54 = (__int64 *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                        + SystemThread_TlsOffset);
        v55 = *v54;
        CExecLvlIntCtxt::ExitBatch(*(CExecLvlIntCtxt **)(*v54 + 128));
        *(_QWORD *)(v55 + 128) = 0;
      }
      CExecLvlIntCtxt::~CExecLvlIntCtxt((CExecLvlIntCtxt *)v104);
      v102 = &XactAccessor::`vftable';
      if ( v91 )
      {
        SEParams::UninstallFromTLS(v91);
        v91 = 0;
      }
      SEParams::~SEParams((SEParams *)v98);
      if ( (v84 & 1) != 0 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v83 + 32LL))(v83);
        if ( _InterlockedExchangeAdd(v83 + 35, 0xFFFFFFFF) == 1 )
        {
          v56 = *((_QWORD *)v83 + 1);
          (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v83 + 40LL))(v83, 1);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
        }
      }
      v57 = v111;
      AutoSETLS::Destroy((AutoSETLS *)v112);
      v58 = (_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                     + SystemThread_TlsOffset);
      v59 = v58[32];
      *v58 = 0;
      **(_QWORD **)(v59 + 64) = 0;
      CDiagnostics::UnlinkFromTask(*(CDiagnostics **)(v57 + 40));
      v60 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v61 = *(_QWORD *)(v60 + 256);
      *(_QWORD *)(v60 + 8) = 0;
      *(_QWORD *)(*(_QWORD *)(v61 + 64) + 8LL) = 0;
      AutoSETLS::~AutoSETLS((AutoSETLS *)v112);
      v89 = (CUEnvTransient *)&v107;
      v86.QuadPart = (LONGLONG)v108;
      v62 = (void (__fastcall ***)(_QWORD, __int64))v110;
      if ( v110 )
      {
        v53 = (*(_DWORD *)(v110 + 8))-- == 1;
        if ( v53 )
          (**v62)(v62, 1);
      }
      if ( v109 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v109 + 16LL))(v109);
      goto LABEL_128;
    }
    if ( (*(_BYTE *)(*((_QWORD *)v1 + 46) + 48LL) & 2) != 0 )
      *(_BYTE *)(v4 + 269) |= 0x40u;
    v24 = v93;
    CDiagnostics::SetOutBuff(
      *((CDiagnostics **)v93 + 5),
      *((const unsigned __int8 **)v1 + 26),
      *((unsigned __int16 *)v1 + 343));
    *(_BYTE *)(v4 + 264) = 0;
    if ( SOS_PublicGlobals::sm_CommonCriteriaModeEnabled && !CSession::FUpdateLoginStats((CSession *)v4, 1, 0) )
    {
      v102 = &CAutoSetXLvlIntCtxtImplNoException::`vftable';
      if ( v103 )
      {
        v103 = 0;
        v72 = (__int64 *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                        + SystemThread_TlsOffset);
        v73 = *v72;
        CExecLvlIntCtxt::ExitBatch(*(CExecLvlIntCtxt **)(*v72 + 128));
        *(_QWORD *)(v73 + 128) = 0;
      }
      CExecLvlIntCtxt::~CExecLvlIntCtxt((CExecLvlIntCtxt *)v104);
      v102 = &XactAccessor::`vftable';
      if ( v91 )
      {
        SEParams::UninstallFromTLS(v91);
        v91 = 0;
      }
      SEParams::~SEParams((SEParams *)v98);
      if ( (v84 & 1) != 0 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v83 + 32LL))(v83);
        if ( _InterlockedExchangeAdd(v83 + 35, 0xFFFFFFFF) == 1 )
        {
          v74 = *((_QWORD *)v83 + 1);
          (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v83 + 40LL))(v83, 1);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
        }
      }
      v75 = v111;
      AutoSETLS::Destroy((AutoSETLS *)v112);
      v76 = (_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                     + SystemThread_TlsOffset);
      v77 = v76[32];
      *v76 = 0;
      **(_QWORD **)(v77 + 64) = 0;
      CDiagnostics::UnlinkFromTask(*(CDiagnostics **)(v75 + 40));
      v78 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v79 = *(_QWORD *)(v78 + 256);
      *(_QWORD *)(v78 + 8) = 0;
      *(_QWORD *)(*(_QWORD *)(v79 + 64) + 8LL) = 0;
      AutoSETLS::~AutoSETLS((AutoSETLS *)v112);
      v89 = (CUEnvTransient *)&v107;
      v86.QuadPart = (LONGLONG)v108;
      v80 = (void (__fastcall ***)(_QWORD, __int64))v110;
      if ( v110 )
      {
        v53 = (*(_DWORD *)(v110 + 8))-- == 1;
        if ( v53 )
          (**v80)(v80, 1);
      }
      if ( v109 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v109 + 16LL))(v109);
LABEL_128:
      v89 = (CUEnvTransient *)v105;
      v105[0] = &CDbLockListBase::`vftable';
      v86.QuadPart = (LONGLONG)v106;
      v106[0] = 0;
      CTDelayedMapBase<unsigned short,CDbLockListBase::CDatabaseOptions,4,CFnH_Default<unsigned short>,CFnC_Default<unsigned short>,CFnI_Default<CDbLockListBase::CDatabaseOptions>,CFnD_Noop<unsigned short>,CFnD_Noop<CDbLockListBase::CDatabaseOptions>,CMemObjAlloc<1>>::DestroyHashMap(v106);
LABEL_84:
      v106[0] = 0;
      CTDelayedMapBase<unsigned short,CDbLockListBase::CDatabaseOptions,4,CFnH_Default<unsigned short>,CFnC_Default<unsigned short>,CFnI_Default<CDbLockListBase::CDatabaseOptions>,CFnD_Noop<unsigned short>,CFnD_Noop<CDbLockListBase::CDatabaseOptions>,CMemObjAlloc<1>>::DestroyHashMap(v106);
      if ( (_DWORD)v87 )
        ITaskProxy::SetCurrentTaskProxy(0);
      goto LABEL_71;
    }
    v102 = &CAutoSetXLvlIntCtxtImplNoException::`vftable';
    if ( v103 )
    {
      v103 = 0;
      v25 = (__int64 *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                      + SystemThread_TlsOffset);
      v26 = *v25;
      CExecLvlIntCtxt::ExitBatch(*(CExecLvlIntCtxt **)(*v25 + 128));
      *(_QWORD *)(v26 + 128) = 0;
    }
    CExecLvlIntCtxt::~CExecLvlIntCtxt((CExecLvlIntCtxt *)v104);
    v102 = &XactAccessor::`vftable';
    if ( v91 )
    {
      SEParams::UninstallFromTLS(v91);
      v91 = 0;
    }
    SEParams::~SEParams((SEParams *)v98);
    if ( (v84 & 1) != 0 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v83 + 32LL))(v83);
      if ( _InterlockedExchangeAdd(v83 + 35, 0xFFFFFFFF) == 1 )
      {
        v81 = *((_QWORD *)v83 + 1);
        (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v83 + 40LL))(v83, 1);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 16LL))(v81);
      }
    }
    v27 = v111;
    AutoSETLS::Destroy((AutoSETLS *)v112);
    v28 = (_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                   + SystemThread_TlsOffset);
    v29 = v28[32];
    *v28 = 0;
    **(_QWORD **)(v29 + 64) = 0;
    CDiagnostics::UnlinkFromTask(*(CDiagnostics **)(v27 + 40));
    v30 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v31 = *(_QWORD *)(v30 + 256);
    *(_QWORD *)(v30 + 8) = 0;
    *(_QWORD *)(*(_QWORD *)(v31 + 64) + 8LL) = 0;
    AutoSETLS::~AutoSETLS((AutoSETLS *)v112);
    v89 = (CUEnvTransient *)&v107;
    v86.QuadPart = (LONGLONG)v108;
    v32 = (void (__fastcall ***)(_QWORD, __int64))v110;
    if ( v110 )
    {
      v53 = (*(_DWORD *)(v110 + 8))-- == 1;
      if ( v53 )
        (**v32)(v32, 1);
    }
    if ( v109 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v109 + 16LL))(v109);
    v89 = (CUEnvTransient *)v105;
    v105[0] = &CDbLockListBase::`vftable';
    v86.QuadPart = (LONGLONG)v106;
    v106[0] = 0;
    CTDelayedMapBase<unsigned short,CDbLockListBase::CDatabaseOptions,4,CFnH_Default<unsigned short>,CFnC_Default<unsigned short>,CFnI_Default<CDbLockListBase::CDatabaseOptions>,CFnD_Noop<unsigned short>,CFnD_Noop<CDbLockListBase::CDatabaseOptions>,CMemObjAlloc<1>>::DestroyHashMap(v106);
    v106[0] = 0;
    CTDelayedMapBase<unsigned short,CDbLockListBase::CDatabaseOptions,4,CFnH_Default<unsigned short>,CFnC_Default<unsigned short>,CFnI_Default<CDbLockListBase::CDatabaseOptions>,CFnD_Noop<unsigned short>,CFnD_Noop<CDbLockListBase::CDatabaseOptions>,CMemObjAlloc<1>>::DestroyHashMap(v106);
    if ( (_DWORD)v87 )
      ITaskProxy::SetCurrentTaskProxy(0);
    if ( !*((_QWORD *)v24 + 6) || !*((_QWORD *)v24 + 5) )
      goto LABEL_57;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)(v4 + 104) + 264LL) + 464LL))(*(_QWORD *)(*(_QWORD *)(v4 + 104) + 264LL));
    v90 = 0;
    v33 = *((_QWORD *)v24 + 6);
    v34 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v35 = *(_QWORD *)(v34 + 256);
    *(_QWORD *)(v34 + 8) = v33;
    *(_QWORD *)(*(_QWORD *)(v35 + 64) + 8LL) = v33;
    CDiagnostics::LinkToCurrentTask(*((CDiagnostics **)v24 + 5));
    try
    {
      ExcHandler::ExcHandler((ExcHandler *)v99, 0, 0, 0, (int (*)(int, int, int, int, char *))hdl_backout, 0);
      TraceLoginEvent((struct CSession *)v4, 1);
      ExcHandler::~ExcHandler((ExcHandler *)v99);
    }
    catch ( SQLError v97 )
    {
      try
      {
        ExceptionBackout::ExceptionBackout((ExceptionBackout *)&PerformanceCount, (const struct SQLError *)v97);
        if ( v97[0] / 100 == 152 && v97[0] == 15247 || v97[0] / 100 == 332 && v97[0] == 33240 )
        {
          v90 = 1;
        }
        else
        {
          ReportProcessLoginFinishEvent((struct CNetConnection *)v94, v94[56], 0, 0, 0);
          CurrentException = ExceptionBackout::GetCurrentException((ExceptionBackout *)&PerformanceCount);
          ExceptionRethrow(CurrentException);
        }
        ExceptionBackout::~ExceptionBackout((ExceptionBackout *)&PerformanceCount);
      }
      catch ( ShortStackException )
      {
      }
      v24 = v93;
      v1 = (struct CNetConnection *)v94;
    }
    v36 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v37 = *(struct Worker **)(v36 + 256);
    if ( !v37 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v37 = *(struct Worker **)(v36 + 256);
    }
    if ( *((_DWORD *)v37 + 139) )
      ExceptionPostCatchActions(v37);
    CDiagnostics::UnlinkFromTask(*((CDiagnostics **)v24 + 5));
    v38 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v39 = *(_QWORD *)(v38 + 256);
    *(_QWORD *)(v38 + 8) = 0;
    *(_QWORD *)(*(_QWORD *)(v39 + 64) + 8LL) = 0;
    if ( !v90 )
    {
LABEL_57:
      ReportProcessLoginFinishEvent(v1, *((struct SNI_Conn **)v1 + 56), 0, 0, 0);
      return 0;
    }
  }
LABEL_71:
  ReportProcessLoginFinishEvent(v1, *((struct SNI_Conn **)v1 + 56), 0, 0, 0);
  return 2;
}

```

## disassembly

```asm
0x100555dc0  push    rdi
0x100555dc2  push    r12
0x100555dc4  push    r13
0x100555dc6  push    r14
0x100555dc8  push    r15
0x100555dca  mov     eax, 1E80h
0x100555dcf  call    _alloca_probe
0x100555dd4  sub     rsp, rax
0x100555dd7  mov     [rsp+1EA8h+var_1E10], 0FFFFFFFFFFFFFFFEh
0x100555de3  mov     [rsp+1EA8h+arg_8], rbx
0x100555deb  mov     [rsp+1EA8h+arg_10], rsi
0x100555df3  mov     rax, cs:__security_cookie
0x100555dfa  xor     rax, rsp
0x100555dfd  mov     [rsp+1EA8h+var_38], rax
0x100555e05  jmp     loc_100549845
0x100549845  mov     r14, rcx
0x100549848  mov     [rsp+1EA8h+var_1E20], rcx
0x100549850  mov     r15, [rcx+170h]
0x100549857  mov     rsi, [r15+18h]
0x10054985b  test    rsi, rsi
0x10054985e  jz      loc_100F059B5
0x100549864  add     rsi, 0FFFFFFFFFFFFFFB0h
0x100549868  mov     [rsp+1EA8h+var_1E18], rsi
0x100549870  xor     edi, edi
0x100549872  jmp     short loc_100549875
0x100549875  mov     r12, [rcx+1C8h]
0x10054987c  mov     [rsp+1EA8h+var_1E50], r12
0x100549881  mov     r13, [r12+20h]
0x100549886  mov     [rsp+1EA8h+var_1E28], r13
0x10054988e  mov     [rsp+1EA8h+var_848], 0
0x100549899  mov     [rsp+1EA8h+var_844], di
0x1005498a1  xor     edx, edx; Val
0x1005498a3  mov     r8d, 800h; Size
0x1005498a9  lea     rcx, [rsp+1EA8h+var_842]; void *
0x1005498b1  call    memset_0
0x1005498b6  lea     rcx, [rsi+50h]
0x1005498ba  mov     rax, [rcx]
0x1005498bd  call    qword ptr [rax+30h]
0x1005498c0  test    al, al
0x1005498c2  jnz     loc_100F05D0E
0x1005498c8  mov     rax, [r14+208h]
0x1005498cf  cmp     dword ptr [rax+88h], 0
0x1005498d6  jnz     loc_100F059C7
0x1005498dc  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x1005498e3  cmp     dword ptr [rax], 0
0x1005498e6  jz      loc_100F05A8E
0x1005498ec  lea     rcx, [rsp+1EA8h+PerformanceCount]; lpPerformanceCount
0x1005498f4  call    cs:__imp_QueryPerformanceCounter
0x1005498fa  mov     rbx, qword ptr [rsp+1EA8h+PerformanceCount]
0x100549902  jmp     short loc_100549905
0x100549905  mov     rcx, [r15+10h]; this
0x100549909  call    ?GetLock@CNetConnection@@QEAAXXZ; CNetConnection::GetLock(void)
0x10054990e  mov     [r15+0D8h], rbx
0x100549915  mov     dword ptr [r15+0E8h], 1
0x100549920  mov     rax, [r15+10h]
0x100549924  mov     rbx, [rax+188h]
0x10054992b  mov     rax, cs:__imp_?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x100549932  cmp     byte ptr [rax], 0
0x100549935  jnz     loc_100F05A9C
0x10054993b  mov     [rbx], rdi
0x10054993e  lea     rax, [rsp+1EA8h+var_848]
0x100549946  mov     [rsp+1EA8h+var_1E88], rax; struct CRoutingEnvChangeInfo *
0x10054994b  mov     r9, [r14+1C0h]; struct SNI_Conn *
0x100549952  mov     r8, [r12+20h]; struct CConnection *
0x100549957  mov     rdx, r12; struct CBatch *
0x10054995a  mov     rcx, [r14+98h]; struct IMemObj *
0x100549961  call    ?login@@YAJPEAVIMemObj@@PEAVCBatch@@PEAVCConnection@@PEAVSNI_Conn@@PEAVCRoutingEnvChangeInfo@@@Z; login(IMemObj *,CBatch *,CConnection *,SNI_Conn *,CRoutingEnvChangeInfo *)
0x100549966  test    eax, eax
0x100549968  js      loc_100F05ACE
0x10054996e  movzx   eax, byte ptr [rsi+110h]
0x100549975  test    al, 20h
0x100549977  jnz     loc_100F05B26
0x10054997d  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100549984  cmp     dword ptr [rax], 0
0x100549987  jz      loc_100F05B34
0x10054998d  lea     rcx, [rsp+1EA8h+var_1E60]; lpPerformanceCount
0x100549992  call    cs:__imp_QueryPerformanceCounter
0x100549998  mov     rbx, qword ptr [rsp+1EA8h+var_1E60]
0x10054999d  jmp     short loc_1005499A0
0x1005499a0  mov     rcx, [r15+10h]; this
0x1005499a4  call    ?GetLock@CNetConnection@@QEAAXXZ; CNetConnection::GetLock(void)
0x1005499a9  cmp     dword ptr [r15+0E8h], 0
0x1005499b1  jz      short loc_1005499D0
0x1005499b3  mov     rax, [r15+0D8h]
0x1005499ba  cmp     rbx, rax
0x1005499bd  jbe     short loc_1005499C9
0x1005499bf  sub     rbx, rax
0x1005499c2  add     [r15+0E0h], rbx
0x1005499c9  mov     [r15+0E8h], edi
0x1005499d0  mov     rcx, [r15+10h]
0x1005499d4  mov     rbx, [rcx+188h]
0x1005499db  mov     rcx, cs:__imp_?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x1005499e2  cmp     byte ptr [rcx], 0
0x1005499e5  jnz     loc_100F05B42
0x1005499eb  mov     [rbx], rdi
0x1005499ee  mov     dword ptr [rsp+1EA8h+var_1E58], edi
0x1005499f2  mov     r8, gs:58h
0x1005499fb  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100549a02  mov     ecx, [rax]
0x100549a04  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100549a0b  mov     edx, [rax]
0x100549a0d  add     rdx, [r8+rcx*8]
0x100549a11  cmp     qword ptr [rdx+18h], 0
0x100549a16  jnz     short loc_100549A2C
0x100549a18  lea     rcx, [rsi+1F8h]; struct ITaskProxy *
0x100549a1f  call    ?SetCurrentTaskProxy@ITaskProxy@@SAXPEAV1@@Z; ITaskProxy::SetCurrentTaskProxy(ITaskProxy *)
0x100549a24  mov     dword ptr [rsp+1EA8h+var_1E58], 1
0x100549a2c  mov     r9, r13; struct CConnection *
0x100549a2f  mov     r8, rsi; struct CSession *
0x100549a32  mov     rdx, r12; struct CBatch *
0x100549a35  lea     rcx, [rsp+1EA8h+var_1A48]; this
0x100549a3d  call    ??0CAutoSetupCXCtxtForLoginStatsUpdate@@QEAA@PEAVCBatch@@PEAVCSession@@PEAVCConnection@@@Z; CAutoSetupCXCtxtForLoginStatsUpdate::CAutoSetupCXCtxtForLoginStatsUpdate(CBatch *,CSession *,CConnection *)
0x100549a42  nop
0x100549a43  mov     rbx, rdi
0x100549a46  mov     [rsp+1EA8h+var_1E78], rbx
0x100549a4b  mov     r13d, edi
0x100549a4e  mov     dword ptr [rsp+1EA8h+var_1E70], edi
0x100549a52  mov     r12, [rsi+288h]
0x100549a59  mov     rax, [r12]
0x100549a5d  xor     edx, edx
0x100549a5f  mov     rcx, r12
0x100549a62  call    qword ptr [rax+18h]
0x100549a65  test    al, al
0x100549a67  jz      short loc_100549A85
0x100549a69  lock inc dword ptr [r12+8Ch]
0x100549a72  mov     rbx, r12
0x100549a75  mov     [rsp+1EA8h+var_1E78], rbx
0x100549a7a  mov     r13d, 1
0x100549a80  mov     dword ptr [rsp+1EA8h+var_1E70], r13d
0x100549a85  test    [rsp+1EA8h+var_1E70], 1
0x100549a8a  jz      loc_100F05B74
0x100549a90  lea     rcx, [rsp+1EA8h+var_1DE8]
0x100549a98  call    cs:__imp_??0SEParams@@QEAA@XZ; SEParams::SEParams(void)
0x100549a9e  nop
0x100549a9f  mov     rdx, gs:58h
0x100549aa8  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100549aaf  mov     ecx, [rax]
0x100549ab1  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100549ab8  mov     r8d, [rax]
0x100549abb  add     r8, [rdx+rcx*8]
0x100549abf  lea     rdx, [rsp+1EA8h+var_1DE8]; struct SEParams *
0x100549ac7  mov     rcx, [r8]; struct CCompExecCtxtBasic *
0x100549aca  call    ?SetupSEParamsFromExecContexts@@YAXAEBVCCompExecCtxtBasic@@PEAVSEParams@@@Z; SetupSEParamsFromExecContexts(CCompExecCtxtBasic const &,SEParams *)
0x100549acf  mov     [rsp+1EA8h+var_1E30], rdi
0x100549ad4  lea     rdx, [rsp+1EA8h+var_1DE8]; struct SEParams *
0x100549adc  lea     rcx, [rsp+1EA8h+var_1E38]; this
0x100549ae1  call    ?Install@AutoInstallParams@@QEAAXPEAVSEParams@@@Z; AutoInstallParams::Install(SEParams *)
0x100549ae6  cmp     [rsp+1EA8h+var_1E30], 0
0x100549aec  jnz     loc_100F05D19
0x100549af2  mov     r8, [rsp+1EA8h+var_1E50]; struct CBatch *
0x100549af7  mov     rdx, rsi; struct CSession *
0x100549afa  lea     rcx, [rsp+1EA8h+var_1D58]; this
0x100549b02  call    ??0CAutoSetXLvlIntCtxtImplNoException@@QEAA@PEAVCSession@@PEAVCBatch@@@Z; CAutoSetXLvlIntCtxtImplNoException::CAutoSetXLvlIntCtxtImplNoException(CSession *,CBatch *)
0x100549b07  nop
0x100549b08  test    byte ptr [r15+31h], 1
0x100549b0d  jz      loc_100549BB7
0x100549b13  mov     dl, 1
0x100549b15  mov     rcx, [rsi+60h]
0x100549b19  call    ?GetFeatureExtension@CPhysicalConnection@@QEBAPEAVCFeatureExtension@@W4EFeatureExtensionId@@@Z; CPhysicalConnection::GetFeatureExtension(EFeatureExtensionId)
0x100549b1e  test    rax, rax
0x100549b21  jz      loc_100F05D4A
0x100549b27  mov     r8, [rax+38h]; struct CTdsSessionState *
0x100549b2b  jmp     short loc_100549B2E
0x100549b2e  mov     qword ptr [r8+8], 0
0x100549b36  mov     [r8+0A0h], edi
0x100549b3d  or      dword ptr [r8+14h], 1
0x100549b42  xor     edx, edx; struct CUEnvTransient *
0x100549b44  mov     rcx, [rsi+68h]; this
0x100549b48  call    ?CalculateDeltaForTDS@CUEnvTransient@@QEAAKPEAV1@PEAVCTdsSessionState@@@Z; CUEnvTransient::CalculateDeltaForTDS(CUEnvTransient *,CTdsSessionState *)
0x100549b4d  test    eax, eax
0x100549b4f  jnz     loc_100F05F6F
0x100549b55  mov     dword ptr [rsp+1EA8h+var_1E50], 5B3h
0x100549b5d  mov     byte ptr [rsp+1EA8h+var_1E80], 3
0x100549b62  mov     dword ptr [rsp+1EA8h+var_1E88], 5B3h
0x100549b6a  lea     r9, aSqlNtdbmsMsqlP_60; "sql\\ntdbms\\msql\\proc\\session.cpp"
0x100549b71  lea     r8d, [rax+1]
0x100549b75  mov     rdx, [rsi+58h]
0x100549b79  mov     ecx, 2D0h
0x100549b7e  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x100549b84  mov     [rsp+1EA8h+var_1E48], rax
0x100549b89  test    rax, rax
0x100549b8c  jz      loc_100F05D53
0x100549b92  xor     r8d, r8d; unsigned int
0x100549b95  xor     edx, edx; struct SOS_ResourceGroup *
0x100549b97  mov     rcx, rax; this
0x100549b9a  call    ??0CUEnvTransient@@QEAA@PEAVSOS_ResourceGroup@@K@Z; CUEnvTransient::CUEnvTransient(SOS_ResourceGroup *,ulong)
0x100549b9f  jmp     short loc_100549BA2
0x100549ba2  mov     [rsi+70h], rax
0x100549ba6  test    rax, rax
0x100549ba9  jz      loc_100F05F6F
0x100549baf  mov     rcx, rsi; this
0x100549bb2  call    ?TakeUETransSnapshot@CSession@@QEAAXXZ; CSession::TakeUETransSnapshot(void)
0x100549bb7  mov     rax, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x100549bbe  mov     rcx, [rax]
0x100549bc1  mov     rax, [rcx]
0x100549bc4  call    qword ptr [rax+0E8h]
0x100549bca  mov     ebx, eax
0x100549bcc  mov     rcx, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x100549bd3  mov     rcx, [rcx]
0x100549bd6  mov     rdx, [rcx]
0x100549bd9  call    qword ptr [rdx+0F0h]
0x100549bdf  lea     r9, [rsp+1EA8h+var_848]; struct CRoutingEnvChangeInfo *
0x100549be7  movzx   r8d, bl; unsigned __int8
0x100549beb  mov     rdx, rax; wchar_t *
0x100549bee  mov     rcx, r14; this
0x100549bf1  call    ?FProcessLoginAck@@YA_NPEAVCNetConnection@@PEA_WEAEBVCRoutingEnvChangeInfo@@@Z; FProcessLoginAck(CNetConnection *,wchar_t *,uchar,CRoutingEnvChangeInfo const &)
0x100549bf6  test    al, al
0x100549bf8  jz      loc_100F05D5C
0x100549bfe  mov     rax, [r14+170h]
0x100549c05  test    byte ptr [rax+30h], 2
0x100549c09  jnz     loc_100F06183
0x100549c0f  movzx   r8d, word ptr [r14+2AEh]; unsigned int
0x100549c17  mov     rdx, [r14+0D0h]; unsigned __int8 *
0x100549c1e  mov     r15, [rsp+1EA8h+var_1E28]
0x100549c26  mov     rcx, [r15+28h]; this
0x100549c2a  call    ?SetOutBuff@CDiagnostics@@QEAAXPEBEK@Z; CDiagnostics::SetOutBuff(uchar const *,ulong)
0x100549c2f  mov     byte ptr [rsi+108h], 0
0x100549c36  mov     rax, cs:__imp_?sm_CommonCriteriaModeEnabled@SOS_PublicGlobals@@2HA; int SOS_PublicGlobals::sm_CommonCriteriaModeEnabled
0x100549c3d  cmp     dword ptr [rax], 0
0x100549c40  jnz     loc_100F06190
0x100549c46  lea     rax, ??_7CAutoSetXLvlIntCtxtImplNoException@@6B@; const CAutoSetXLvlIntCtxtImplNoException::`vftable'
0x100549c4d  mov     [rsp+1EA8h+var_1D58], rax
0x100549c55  cmp     [rsp+1EA8h+var_1D50], 0
0x100549c5d  jz      short loc_100549C9C
0x100549c5f  mov     [rsp+1EA8h+var_1D50], 0
0x100549c67  mov     r8, gs:58h
0x100549c70  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100549c77  mov     ecx, [rax]
0x100549c79  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100549c80  mov     edx, [rax]
0x100549c82  add     rdx, [r8+rcx*8]
0x100549c86  mov     rbx, [rdx]
0x100549c89  mov     rcx, [rbx+80h]; this
0x100549c90  call    ?ExitBatch@CExecLvlIntCtxt@@QEAAXXZ; CExecLvlIntCtxt::ExitBatch(void)
0x100549c95  mov     [rbx+80h], rdi
0x100549c9c  lea     rcx, [rsp+1EA8h+var_1D48]; this
0x100549ca4  call    ??1CExecLvlIntCtxt@@QEAA@XZ; CExecLvlIntCtxt::~CExecLvlIntCtxt(void)
0x100549ca9  nop
0x100549caa  lea     rax, ??_7XactAccessor@@6B@; const XactAccessor::`vftable'
0x100549cb1  mov     [rsp+1EA8h+var_1D58], rax
0x100549cb9  mov     rcx, [rsp+1EA8h+var_1E38]
0x100549cbe  test    rcx, rcx
0x100549cc1  jz      short loc_100549CCE
0x100549cc3  call    cs:__imp_?UninstallFromTLS@SEParams@@QEAAXXZ; SEParams::UninstallFromTLS(void)
0x100549cc9  mov     [rsp+1EA8h+var_1E38], rdi
0x100549cce  lea     rcx, [rsp+1EA8h+var_1DE8]
0x100549cd6  call    cs:__imp_??1SEParams@@UEAA@XZ; SEParams::~SEParams(void)
0x100549cdc  nop
0x100549cdd  test    [rsp+1EA8h+var_1E70], 1
0x100549ce2  jz      short loc_100549D12
0x100549ce4  mov     rbx, [rsp+1EA8h+var_1E78]
0x100549ce9  mov     rax, [rbx]
0x100549cec  mov     rcx, rbx
0x100549cef  call    qword ptr [rax+20h]
0x100549cf2  mov     eax, 0FFFFFFFFh
0x100549cf7  lock xadd [rbx+8Ch], eax
0x100549cff  cmp     eax, 1
0x100549d02  jz      loc_100F063BF
0x100549d08  mov     [rsp+1EA8h+var_1E78], rdi
0x100549d0d  and     dword ptr [rsp+1EA8h+var_1E70], 0FFFFFFFEh
0x100549d12  mov     rbx, [rsp+1EA8h+var_8A0]
0x100549d1a  lea     rcx, [rsp+1EA8h+var_858]
0x100549d22  call    cs:__imp_?Destroy@AutoSETLS@@QEAAXXZ; AutoSETLS::Destroy(void)
0x100549d28  mov     r8, gs:58h
0x100549d31  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100549d38  mov     ecx, [rax]
0x100549d3a  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100549d41  mov     edx, [rax]
0x100549d43  add     rdx, [r8+rcx*8]
0x100549d47  mov     rax, [rdx+100h]
0x100549d4e  mov     [rdx], rdi
0x100549d51  mov     rax, [rax+40h]
0x100549d55  mov     [rax], rdi
0x100549d58  mov     rcx, [rbx+28h]; this
0x100549d5c  call    ?UnlinkFromTask@CDiagnostics@@QEAAXXZ; CDiagnostics::UnlinkFromTask(void)
0x100549d61  mov     r8, gs:58h
0x100549d6a  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100549d71  mov     ecx, [rax]
0x100549d73  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100549d7a  mov     edx, [rax]
0x100549d7c  add     rdx, [r8+rcx*8]
0x100549d80  mov     rax, [rdx+100h]
0x100549d87  mov     [rdx+8], rdi
0x100549d8b  mov     rax, [rax+40h]
0x100549d8f  mov     [rax+8], rdi
0x100549d93  lea     rcx, [rsp+1EA8h+var_858]
0x100549d9b  call    cs:__imp_??1AutoSETLS@@QEAA@XZ; AutoSETLS::~AutoSETLS(void)
0x100549da1  nop
0x100549da2  lea     rax, [rsp+1EA8h+var_910]
0x100549daa  mov     [rsp+1EA8h+var_1E48], rax
0x100549daf  lea     rax, [rsp+1EA8h+var_908]
0x100549db7  mov     qword ptr [rsp+1EA8h+var_1E60], rax
0x100549dbc  mov     rcx, [rsp+1EA8h+var_8E8]
0x100549dc4  test    rcx, rcx
0x100549dc7  jnz     loc_100F063E3
0x100549dcd  mov     rcx, [rsp+1EA8h+var_8F0]
0x100549dd5  test    rcx, rcx
0x100549dd8  jnz     loc_100F063FE
0x100549dde  lea     rax, [rsp+1EA8h+var_1A48]
0x100549de6  mov     [rsp+1EA8h+var_1E48], rax
  ... truncated ...
```
