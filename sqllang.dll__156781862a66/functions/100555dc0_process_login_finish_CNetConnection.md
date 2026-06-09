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
  __int64 v7; // rdx
  __int64 v8; // rcx
  CSbTransportMgr *QuadPart; // rbx
  _QWORD *v10; // rbx
  char v11; // al
  CSbTransportMgr *v12; // rbx
  unsigned __int64 v13; // rax
  _QWORD *v14; // rbx
  volatile signed __int32 *v15; // rbx
  char v16; // r13
  volatile signed __int32 *v17; // r12
  __int64 v18; // rdx
  __int64 FeatureExtension; // rax
  __int64 v20; // r8
  CUEnvTransient *v21; // rax
  CUEnvTransient *v22; // rax
  unsigned __int8 v23; // bl
  wchar_t *v24; // rax
  struct CConnection *v25; // r15
  __int64 *v26; // rdx
  __int64 v27; // rbx
  __int64 v28; // rbx
  _QWORD *v29; // rdx
  __int64 v30; // rax
  __int64 v31; // rdx
  __int64 v32; // rax
  void (__fastcall ***v33)(_QWORD, __int64); // rcx
  __int64 v34; // r9
  __int64 v35; // rdx
  __int64 v36; // rax
  __int64 v37; // rbx
  struct Worker *v38; // rcx
  __int64 v39; // r8
  __int64 v40; // rax
  __int64 v42; // rdx
  __int64 v43; // rcx
  const CERT_CONTEXT *v44; // rbx
  unsigned __int8 v45; // r12
  int v46; // r8d
  int v47; // r8d
  __int64 v48; // rbx
  __int64 v49; // rbx
  _QWORD *v50; // rdx
  __int64 v51; // rax
  __int64 v52; // rdx
  __int64 v53; // rax
  void (__fastcall ***v54)(_QWORD, __int64); // rcx
  bool v55; // zf
  __int64 *v56; // rdx
  __int64 v57; // rbx
  __int64 v58; // rbx
  __int64 v59; // rbx
  _QWORD *v60; // rdx
  __int64 v61; // rax
  __int64 v62; // rdx
  __int64 v63; // rax
  void (__fastcall ***v64)(_QWORD, __int64); // rcx
  __int64 *v65; // rdx
  __int64 v66; // rbx
  __int64 v67; // rbx
  __int64 v68; // rbx
  _QWORD *v69; // rdx
  __int64 v70; // rax
  __int64 v71; // rdx
  __int64 v72; // rax
  void (__fastcall ***v73)(_QWORD, __int64); // rcx
  __int64 *v74; // rdx
  __int64 v75; // rbx
  __int64 v76; // rbx
  __int64 v77; // rbx
  _QWORD *v78; // rdx
  __int64 v79; // rax
  __int64 v80; // rdx
  __int64 v81; // rax
  void (__fastcall ***v82)(_QWORD, __int64); // rcx
  __int64 v83; // rbx
  const struct SQLError *CurrentException; // rax
  volatile signed __int32 *v85; // [rsp+30h] [rbp-1E78h]
  char v86; // [rsp+38h] [rbp-1E70h]
  unsigned __int8 v87; // [rsp+40h] [rbp-1E68h]
  LARGE_INTEGER v88; // [rsp+48h] [rbp-1E60h] BYREF
  __int64 v89; // [rsp+50h] [rbp-1E58h]
  struct CBatch *v90; // [rsp+58h] [rbp-1E50h]
  CUEnvTransient *v91; // [rsp+60h] [rbp-1E48h]
  int v92; // [rsp+68h] [rbp-1E40h]
  SEParams *v93; // [rsp+70h] [rbp-1E38h] BYREF
  __int64 v94; // [rsp+78h] [rbp-1E30h]
  struct CConnection *v95; // [rsp+80h] [rbp-1E28h]
  struct SNI_Conn **v96; // [rsp+88h] [rbp-1E20h]
  __int64 v97; // [rsp+90h] [rbp-1E18h]
  __int64 v98; // [rsp+98h] [rbp-1E10h]
  _DWORD v99[8]; // [rsp+A0h] [rbp-1E08h] BYREF
  _BYTE v100[80]; // [rsp+C0h] [rbp-1DE8h] BYREF
  _BYTE v101[40]; // [rsp+110h] [rbp-1D98h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+138h] [rbp-1D70h] BYREF
  __int64 v103; // [rsp+140h] [rbp-1D68h]
  void **v104; // [rsp+150h] [rbp-1D58h] BYREF
  char v105; // [rsp+158h] [rbp-1D50h]
  _BYTE v106[768]; // [rsp+160h] [rbp-1D48h] BYREF
  _QWORD v107[522]; // [rsp+460h] [rbp-1A48h] BYREF
  _DWORD v108[58]; // [rsp+14B0h] [rbp-9F8h] BYREF
  char v109; // [rsp+1598h] [rbp-910h] BYREF
  _BYTE v110[24]; // [rsp+15A0h] [rbp-908h] BYREF
  __int64 v111; // [rsp+15B8h] [rbp-8F0h]
  __int64 v112; // [rsp+15C0h] [rbp-8E8h]
  __int64 v113; // [rsp+1608h] [rbp-8A0h]
  _BYTE v114[16]; // [rsp+1650h] [rbp-858h] BYREF
  int v115; // [rsp+1660h] [rbp-848h] BYREF
  __int16 v116; // [rsp+1664h] [rbp-844h]
  char v117[2058]; // [rsp+1666h] [rbp-842h] BYREF

  v98 = -2;
  v1 = a1;
  v96 = (struct SNI_Conn **)a1;
  v2 = *((_QWORD *)a1 + 46);
  v3 = *(_QWORD *)(v2 + 24);
  if ( v3 )
  {
    v4 = v3 - 80;
    v97 = v4;
  }
  else
  {
    v4 = 0;
    v97 = 0;
  }
  v5 = (struct CConnectionOutput ***)*((_QWORD *)a1 + 57);
  v90 = (struct CBatch *)v5;
  v6 = (struct CConnection *)v5[4];
  v95 = v6;
  v115 = 0;
  v116 = 0;
  memset_0(v117, 0, 0x800u);
  if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)(v4 + 80) + 48LL))(v4 + 80) )
    goto LABEL_71;
  if ( !*(_DWORD *)(*((_QWORD *)v1 + 65) + 136LL)
    || !*(_DWORD *)(GetXdbServerGlobals(v8, v7) + 20744)
    || !*(_DWORD *)(GetXdbServerGlobals(v43, v42) + 11976) )
  {
    goto LABEL_5;
  }
  v89 = *((_QWORD *)v1 + 19);
  v44 = (const CERT_CONTEXT *)*((_QWORD *)v1 + 129);
  v45 = 0;
  if ( !v44 )
    goto LABEL_71;
  v87 = FCheckCertAllowListed(*((PCCERT_CONTEXT *)v1 + 129));
  if ( v87 )
    goto LABEL_65;
  if ( !ProxyClientTrustValidationSettings::sm_fAllowAll )
  {
    if ( !(unsigned __int8)FCheckCertAllowListed(v44) )
      goto LABEL_71;
LABEL_65:
    v45 = v87;
    if ( VerifyCertificateTrust(
           v44,
           ProxyClientTrustValidationSettings::sm_fIsCacheCertChainEnabled,
           ProxyClientTrustValidationSettings::sm_fOnlineCrlChecksDisabled,
           0) )
    {
      goto LABEL_71;
    }
  }
  *((_DWORD *)v1 + 257) = v45;
  *(_DWORD *)(*((_QWORD *)v1 + 65) + 20LL) = 0;
  v5 = (struct CConnectionOutput ***)v90;
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
  v10 = *(_QWORD **)(*(_QWORD *)(v2 + 16) + 392LL);
  if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
  {
    v46 = rand();
    if ( v46 == 5 * (v46 / 5) )
      Spinlock<114,16,258>::UpdateStatSnapshot();
  }
  *v10 = 0;
  if ( (int)login(
              *((struct IMemObj **)v1 + 19),
              (struct CBatch *)v5,
              v5[4],
              *((struct SNI_Conn **)v1 + 56),
              (struct CRoutingEnvChangeInfo *)&v115) < 0 )
  {
    BYTE3(PerformanceCount.QuadPart) = -3;
    PerformanceCount.HighPart = 2;
    v103 = 0;
    srv_completioncode_ex<0>(v1, (char *)&PerformanceCount.QuadPart + 3);
  }
  else
  {
    v11 = *(_BYTE *)(v4 + 272);
    if ( (v11 & 0x20) != 0 )
      *(_BYTE *)(v4 + 272) = v11 | 4;
    if ( Base_PublicGlobals::sm_invariantTscAvailable )
    {
      QueryPerformanceCounter(&v88);
      v12 = (CSbTransportMgr *)v88.QuadPart;
    }
    else
    {
      v12 = MEMORY[0x7FFE0008];
    }
    CNetConnection::GetLock(*(CNetConnection **)(v2 + 16));
    if ( *(_DWORD *)(v2 + 232) )
    {
      v13 = *(_QWORD *)(v2 + 216);
      if ( (unsigned __int64)v12 > v13 )
        *(_QWORD *)(v2 + 224) += (char *)v12 - v13;
      *(_DWORD *)(v2 + 232) = 0;
    }
    v14 = *(_QWORD **)(*(_QWORD *)(v2 + 16) + 392LL);
    if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v47 = rand();
      if ( v47 == 5 * (v47 / 5) )
        Spinlock<114,16,258>::UpdateStatSnapshot();
    }
    *v14 = 0;
    LODWORD(v89) = 0;
    if ( !*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                    + SystemThread_TlsOffset
                    + 24LL) )
    {
      ITaskProxy::SetCurrentTaskProxy((struct ITaskProxy *)(v4 + 504));
      LODWORD(v89) = 1;
    }
    CAutoSetupCXCtxtForLoginStatsUpdate::CAutoSetupCXCtxtForLoginStatsUpdate(
      (CAutoSetupCXCtxtForLoginStatsUpdate *)v107,
      (struct CBatch *)v5,
      (struct CSession *)v4,
      v6);
    v15 = 0;
    v85 = 0;
    v16 = 0;
    v86 = 0;
    v17 = *(volatile signed __int32 **)(v4 + 648);
    if ( (*(unsigned __int8 (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)v17 + 24LL))(v17, 0) )
    {
      _InterlockedIncrement(v17 + 35);
      v15 = v17;
      v85 = v17;
      v16 = 1;
      v86 = 1;
    }
    if ( (v86 & 1) == 0 )
    {
      if ( (v16 & 1) != 0 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 32LL))(v15);
        if ( _InterlockedExchangeAdd(v15 + 35, 0xFFFFFFFF) == 1 )
        {
          v48 = *((_QWORD *)v85 + 1);
          (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v85 + 40LL))(v85, 1);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
        }
      }
      v49 = v113;
      AutoSETLS::Destroy((AutoSETLS *)v114);
      v50 = (_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                     + SystemThread_TlsOffset);
      v51 = v50[32];
      *v50 = 0;
      **(_QWORD **)(v51 + 64) = 0;
      CDiagnostics::UnlinkFromTask(*(CDiagnostics **)(v49 + 40));
      v52 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v53 = *(_QWORD *)(v52 + 256);
      *(_QWORD *)(v52 + 8) = 0;
      *(_QWORD *)(*(_QWORD *)(v53 + 64) + 8LL) = 0;
      AutoSETLS::~AutoSETLS((AutoSETLS *)v114);
      v88.QuadPart = (LONGLONG)&v109;
      PerformanceCount.QuadPart = (LONGLONG)v110;
      v54 = (void (__fastcall ***)(_QWORD, __int64))v112;
      if ( v112 )
      {
        v55 = (*(_DWORD *)(v112 + 8))-- == 1;
        if ( v55 )
          (**v54)(v54, 1);
      }
      if ( v111 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v111 + 16LL))(v111);
      v88.QuadPart = (LONGLONG)v107;
      v107[0] = &CDbLockListBase::`vftable';
      PerformanceCount.QuadPart = (LONGLONG)v108;
      v108[0] = 0;
      CTDelayedMapBase<unsigned short,CDbLockListBase::CDatabaseOptions,4,CFnH_Default<unsigned short>,CFnC_Default<unsigned short>,CFnI_Default<CDbLockListBase::CDatabaseOptions>,CFnD_Noop<unsigned short>,CFnD_Noop<CDbLockListBase::CDatabaseOptions>,CMemObjAlloc<1>>::DestroyHashMap(v108);
      goto LABEL_84;
    }
    SEParams::SEParams((SEParams *)v100);
    SetupSEParamsFromExecContexts(
      *(const struct CCompExecCtxtBasic **)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                          + SystemThread_TlsOffset),
      (struct SEParams *)v100);
    v94 = 0;
    AutoInstallParams::Install((AutoInstallParams *)&v93, (struct SEParams *)v100);
    if ( v94 )
      utassert_fail(
        1u,
        "NULL == m_separamsPrev",
        "sephlpr.cpp",
        82,
        "SEParams is being installed more than once. Illegal usage.");
    CAutoSetXLvlIntCtxtImplNoException::CAutoSetXLvlIntCtxtImplNoException(
      (CAutoSetXLvlIntCtxtImplNoException *)&v104,
      (struct CSession *)v4,
      v90);
    if ( (*(_BYTE *)(v2 + 49) & 1) != 0 )
    {
      LOBYTE(v18) = 1;
      FeatureExtension = CPhysicalConnection::GetFeatureExtension(*(_QWORD *)(v4 + 96), v18);
      if ( FeatureExtension )
        v20 = *(_QWORD *)(FeatureExtension + 56);
      else
        v20 = 0;
      *(_QWORD *)(v20 + 8) = 0;
      *(_DWORD *)(v20 + 160) = 0;
      *(_DWORD *)(v20 + 20) |= 1u;
      if ( CUEnvTransient::CalculateDeltaForTDS(*(CUEnvTransient **)(v4 + 104), 0, (struct CTdsSessionState *)v20)
        || ((LODWORD(v90) = 1459,
             v21 = (CUEnvTransient *)operator new(
                                       0x2D0u,
                                       *(struct IMemObj **)(v4 + 88),
                                       1,
                                       "sql\\ntdbms\\msql\\proc\\session.cpp",
                                       1459,
                                       3u),
             (v91 = v21) == 0)
          ? (v22 = 0)
          : (v22 = CUEnvTransient::CUEnvTransient(v21, 0, 0)),
            (*(_QWORD *)(v4 + 112) = v22) == 0) )
      {
        v104 = &CAutoSetXLvlIntCtxtImplNoException::`vftable';
        if ( v105 )
        {
          v105 = 0;
          v65 = (__int64 *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                          + SystemThread_TlsOffset);
          v66 = *v65;
          CExecLvlIntCtxt::ExitBatch(*(CExecLvlIntCtxt **)(*v65 + 128));
          *(_QWORD *)(v66 + 128) = 0;
        }
        CExecLvlIntCtxt::~CExecLvlIntCtxt((CExecLvlIntCtxt *)v106);
        v104 = &XactAccessor::`vftable';
        if ( v93 )
        {
          SEParams::UninstallFromTLS(v93);
          v93 = 0;
        }
        SEParams::~SEParams((SEParams *)v100);
        if ( (v86 & 1) != 0 )
        {
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v85 + 32LL))(v85);
          if ( _InterlockedExchangeAdd(v85 + 35, 0xFFFFFFFF) == 1 )
          {
            v67 = *((_QWORD *)v85 + 1);
            (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v85 + 40LL))(v85, 1);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
          }
        }
        v68 = v113;
        AutoSETLS::Destroy((AutoSETLS *)v114);
        v69 = (_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                       + SystemThread_TlsOffset);
        v70 = v69[32];
        *v69 = 0;
        **(_QWORD **)(v70 + 64) = 0;
        CDiagnostics::UnlinkFromTask(*(CDiagnostics **)(v68 + 40));
        v71 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        v72 = *(_QWORD *)(v71 + 256);
        *(_QWORD *)(v71 + 8) = 0;
        *(_QWORD *)(*(_QWORD *)(v72 + 64) + 8LL) = 0;
        AutoSETLS::~AutoSETLS((AutoSETLS *)v114);
        v91 = (CUEnvTransient *)&v109;
        v88.QuadPart = (LONGLONG)v110;
        v73 = (void (__fastcall ***)(_QWORD, __int64))v112;
        if ( v112 )
        {
          v55 = (*(_DWORD *)(v112 + 8))-- == 1;
          if ( v55 )
            (**v73)(v73, 1);
        }
        if ( v111 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v111 + 16LL))(v111);
        goto LABEL_128;
      }
      CSession::TakeUETransSnapshot((CSession *)v4);
    }
    v23 = (*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 232LL))(s_pServerConf);
    v24 = (wchar_t *)(*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 240LL))(s_pServerConf);
    if ( !FProcessLoginAck(v1, v24, v23, (const struct CRoutingEnvChangeInfo *)&v115) )
    {
      v104 = &CAutoSetXLvlIntCtxtImplNoException::`vftable';
      if ( v105 )
      {
        v105 = 0;
        v56 = (__int64 *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                        + SystemThread_TlsOffset);
        v57 = *v56;
        CExecLvlIntCtxt::ExitBatch(*(CExecLvlIntCtxt **)(*v56 + 128));
        *(_QWORD *)(v57 + 128) = 0;
      }
      CExecLvlIntCtxt::~CExecLvlIntCtxt((CExecLvlIntCtxt *)v106);
      v104 = &XactAccessor::`vftable';
      if ( v93 )
      {
        SEParams::UninstallFromTLS(v93);
        v93 = 0;
      }
      SEParams::~SEParams((SEParams *)v100);
      if ( (v86 & 1) != 0 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v85 + 32LL))(v85);
        if ( _InterlockedExchangeAdd(v85 + 35, 0xFFFFFFFF) == 1 )
        {
          v58 = *((_QWORD *)v85 + 1);
          (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v85 + 40LL))(v85, 1);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
        }
      }
      v59 = v113;
      AutoSETLS::Destroy((AutoSETLS *)v114);
      v60 = (_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                     + SystemThread_TlsOffset);
      v61 = v60[32];
      *v60 = 0;
      **(_QWORD **)(v61 + 64) = 0;
      CDiagnostics::UnlinkFromTask(*(CDiagnostics **)(v59 + 40));
      v62 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v63 = *(_QWORD *)(v62 + 256);
      *(_QWORD *)(v62 + 8) = 0;
      *(_QWORD *)(*(_QWORD *)(v63 + 64) + 8LL) = 0;
      AutoSETLS::~AutoSETLS((AutoSETLS *)v114);
      v91 = (CUEnvTransient *)&v109;
      v88.QuadPart = (LONGLONG)v110;
      v64 = (void (__fastcall ***)(_QWORD, __int64))v112;
      if ( v112 )
      {
        v55 = (*(_DWORD *)(v112 + 8))-- == 1;
        if ( v55 )
          (**v64)(v64, 1);
      }
      if ( v111 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v111 + 16LL))(v111);
      goto LABEL_128;
    }
    if ( (*(_BYTE *)(*((_QWORD *)v1 + 46) + 48LL) & 2) != 0 )
      *(_BYTE *)(v4 + 269) |= 0x40u;
    v25 = v95;
    CDiagnostics::SetOutBuff(
      *((CDiagnostics **)v95 + 5),
      *((const unsigned __int8 **)v1 + 26),
      *((unsigned __int16 *)v1 + 343));
    *(_BYTE *)(v4 + 264) = 0;
    if ( SOS_PublicGlobals::sm_CommonCriteriaModeEnabled && !CSession::FUpdateLoginStats((CSession *)v4, 1, 0) )
    {
      v104 = &CAutoSetXLvlIntCtxtImplNoException::`vftable';
      if ( v105 )
      {
        v105 = 0;
        v74 = (__int64 *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                        + SystemThread_TlsOffset);
        v75 = *v74;
        CExecLvlIntCtxt::ExitBatch(*(CExecLvlIntCtxt **)(*v74 + 128));
        *(_QWORD *)(v75 + 128) = 0;
      }
      CExecLvlIntCtxt::~CExecLvlIntCtxt((CExecLvlIntCtxt *)v106);
      v104 = &XactAccessor::`vftable';
      if ( v93 )
      {
        SEParams::UninstallFromTLS(v93);
        v93 = 0;
      }
      SEParams::~SEParams((SEParams *)v100);
      if ( (v86 & 1) != 0 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v85 + 32LL))(v85);
        if ( _InterlockedExchangeAdd(v85 + 35, 0xFFFFFFFF) == 1 )
        {
          v76 = *((_QWORD *)v85 + 1);
          (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v85 + 40LL))(v85, 1);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
        }
      }
      v77 = v113;
      AutoSETLS::Destroy((AutoSETLS *)v114);
      v78 = (_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                     + SystemThread_TlsOffset);
      v79 = v78[32];
      *v78 = 0;
      **(_QWORD **)(v79 + 64) = 0;
      CDiagnostics::UnlinkFromTask(*(CDiagnostics **)(v77 + 40));
      v80 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v81 = *(_QWORD *)(v80 + 256);
      *(_QWORD *)(v80 + 8) = 0;
      *(_QWORD *)(*(_QWORD *)(v81 + 64) + 8LL) = 0;
      AutoSETLS::~AutoSETLS((AutoSETLS *)v114);
      v91 = (CUEnvTransient *)&v109;
      v88.QuadPart = (LONGLONG)v110;
      v82 = (void (__fastcall ***)(_QWORD, __int64))v112;
      if ( v112 )
      {
        v55 = (*(_DWORD *)(v112 + 8))-- == 1;
        if ( v55 )
          (**v82)(v82, 1);
      }
      if ( v111 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v111 + 16LL))(v111);
LABEL_128:
      v91 = (CUEnvTransient *)v107;
      v107[0] = &CDbLockListBase::`vftable';
      v88.QuadPart = (LONGLONG)v108;
      v108[0] = 0;
      CTDelayedMapBase<unsigned short,CDbLockListBase::CDatabaseOptions,4,CFnH_Default<unsigned short>,CFnC_Default<unsigned short>,CFnI_Default<CDbLockListBase::CDatabaseOptions>,CFnD_Noop<unsigned short>,CFnD_Noop<CDbLockListBase::CDatabaseOptions>,CMemObjAlloc<1>>::DestroyHashMap(v108);
LABEL_84:
      v108[0] = 0;
      CTDelayedMapBase<unsigned short,CDbLockListBase::CDatabaseOptions,4,CFnH_Default<unsigned short>,CFnC_Default<unsigned short>,CFnI_Default<CDbLockListBase::CDatabaseOptions>,CFnD_Noop<unsigned short>,CFnD_Noop<CDbLockListBase::CDatabaseOptions>,CMemObjAlloc<1>>::DestroyHashMap(v108);
      if ( (_DWORD)v89 )
        ITaskProxy::SetCurrentTaskProxy(0);
      goto LABEL_71;
    }
    v104 = &CAutoSetXLvlIntCtxtImplNoException::`vftable';
    if ( v105 )
    {
      v105 = 0;
      v26 = (__int64 *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                      + SystemThread_TlsOffset);
      v27 = *v26;
      CExecLvlIntCtxt::ExitBatch(*(CExecLvlIntCtxt **)(*v26 + 128));
      *(_QWORD *)(v27 + 128) = 0;
    }
    CExecLvlIntCtxt::~CExecLvlIntCtxt((CExecLvlIntCtxt *)v106);
    v104 = &XactAccessor::`vftable';
    if ( v93 )
    {
      SEParams::UninstallFromTLS(v93);
      v93 = 0;
    }
    SEParams::~SEParams((SEParams *)v100);
    if ( (v86 & 1) != 0 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v85 + 32LL))(v85);
      if ( _InterlockedExchangeAdd(v85 + 35, 0xFFFFFFFF) == 1 )
      {
        v83 = *((_QWORD *)v85 + 1);
        (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v85 + 40LL))(v85, 1);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
      }
    }
    v28 = v113;
    AutoSETLS::Destroy((AutoSETLS *)v114);
    v29 = (_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                   + SystemThread_TlsOffset);
    v30 = v29[32];
    *v29 = 0;
    **(_QWORD **)(v30 + 64) = 0;
    CDiagnostics::UnlinkFromTask(*(CDiagnostics **)(v28 + 40));
    v31 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v32 = *(_QWORD *)(v31 + 256);
    *(_QWORD *)(v31 + 8) = 0;
    *(_QWORD *)(*(_QWORD *)(v32 + 64) + 8LL) = 0;
    AutoSETLS::~AutoSETLS((AutoSETLS *)v114);
    v91 = (CUEnvTransient *)&v109;
    v88.QuadPart = (LONGLONG)v110;
    v33 = (void (__fastcall ***)(_QWORD, __int64))v112;
    if ( v112 )
    {
      v55 = (*(_DWORD *)(v112 + 8))-- == 1;
      if ( v55 )
        (**v33)(v33, 1);
    }
    if ( v111 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v111 + 16LL))(v111);
    v91 = (CUEnvTransient *)v107;
    v107[0] = &CDbLockListBase::`vftable';
    v88.QuadPart = (LONGLONG)v108;
    v108[0] = 0;
    CTDelayedMapBase<unsigned short,CDbLockListBase::CDatabaseOptions,4,CFnH_Default<unsigned short>,CFnC_Default<unsigned short>,CFnI_Default<CDbLockListBase::CDatabaseOptions>,CFnD_Noop<unsigned short>,CFnD_Noop<CDbLockListBase::CDatabaseOptions>,CMemObjAlloc<1>>::DestroyHashMap(v108);
    v108[0] = 0;
    CTDelayedMapBase<unsigned short,CDbLockListBase::CDatabaseOptions,4,CFnH_Default<unsigned short>,CFnC_Default<unsigned short>,CFnI_Default<CDbLockListBase::CDatabaseOptions>,CFnD_Noop<unsigned short>,CFnD_Noop<CDbLockListBase::CDatabaseOptions>,CMemObjAlloc<1>>::DestroyHashMap(v108);
    if ( (_DWORD)v89 )
      ITaskProxy::SetCurrentTaskProxy(0);
    if ( !*((_QWORD *)v25 + 6) || !*((_QWORD *)v25 + 5) )
      goto LABEL_57;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)(v4 + 104) + 264LL) + 464LL))(*(_QWORD *)(*(_QWORD *)(v4 + 104) + 264LL));
    v92 = 0;
    v34 = *((_QWORD *)v25 + 6);
    v35 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v36 = *(_QWORD *)(v35 + 256);
    *(_QWORD *)(v35 + 8) = v34;
    *(_QWORD *)(*(_QWORD *)(v36 + 64) + 8LL) = v34;
    CDiagnostics::LinkToCurrentTask(*((CDiagnostics **)v25 + 5));
    try
    {
      ExcHandler::ExcHandler((ExcHandler *)v101, 0, 0, 0, (int (*)(int, int, int, int, char *))hdl_backout, 0);
      TraceLoginEvent((struct CSession *)v4, 1);
      ExcHandler::~ExcHandler((ExcHandler *)v101);
    }
    catch ( SQLError v99 )
    {
      try
      {
        ExceptionBackout::ExceptionBackout((ExceptionBackout *)&PerformanceCount, (const struct SQLError *)v99);
        if ( v99[0] / 100 == 152 && v99[0] == 15247 || v99[0] / 100 == 332 && v99[0] == 33240 )
        {
          v92 = 1;
        }
        else
        {
          ReportProcessLoginFinishEvent((struct CNetConnection *)v96, v96[56], 0, 0, 0);
          CurrentException = ExceptionBackout::GetCurrentException((ExceptionBackout *)&PerformanceCount);
          ExceptionRethrow(CurrentException);
        }
        ExceptionBackout::~ExceptionBackout((ExceptionBackout *)&PerformanceCount);
      }
      catch ( ShortStackException )
      {
      }
      v25 = v95;
      v1 = (struct CNetConnection *)v96;
    }
    v37 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v38 = *(struct Worker **)(v37 + 256);
    if ( !v38 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v38 = *(struct Worker **)(v37 + 256);
    }
    if ( *((_DWORD *)v38 + 139) )
      ExceptionPostCatchActions(v38);
    CDiagnostics::UnlinkFromTask(*((CDiagnostics **)v25 + 5));
    v39 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v40 = *(_QWORD *)(v39 + 256);
    *(_QWORD *)(v39 + 8) = 0;
    *(_QWORD *)(*(_QWORD *)(v40 + 64) + 8LL) = 0;
    if ( !v92 )
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
