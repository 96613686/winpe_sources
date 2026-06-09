# FindLoginXdb(IMemObj *,SNI_Conn *,CSession *,wchar_t const *,int,bool,bool,ulong *,ELoginFailedState &)

- ea: `0x100f23ba0`
- end: `0x100f273bd`
- name: `?FindLoginXdb@@YAKPEAVIMemObj@@PEAVSNI_Conn@@PEAVCSession@@PEB_WH_N4PEAKAEAW4ELoginFailedState@@@Z`
- size: `14365`
- prototype: `unsigned int __fastcall(struct IMemObj *, struct SNI_Conn *, struct CSession *, const wchar_t *, int, bool, bool, unsigned int *, enum ELoginFailedState *)`
- caller_count: `2`
- callee_count: `50`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x100555e20`
- `0x100f2eaf0`

## callees

- `0x100401070`
- `0x100401090`
- `0x1004012d0`
- `0x100401340`
- `0x100401433`
- `0x100403080`
- `0x1004035f0`
- `0x10040be50`
- `0x10040bf50`
- `0x10041a970`
- `0x10041e0c0`
- `0x100436330`
- `0x100438930`
- `0x100556ce0`
- `0x10055a5d0`
- `0x10055fad0`
- `0x1007d4260`
- `0x1007e3a50`
- `0x10096c070`
- `0x10098ce80`
- `0x100990cf0`
- `0x100992330`
- `0x1009955f0`
- `0x100995720`
- `0x100995b00`
- `0x100a4eca0`
- `0x100a522c0`
- `0x100a52620`
- `0x100f08630`
- `0x100f22700`
- `0x100f228b0`
- `0x100f23270`
- `0x100f23460`
- `0x100f23830`
- `0x100f23ba0`
- `0x100f80720`
- `0x10138eb30`
- `0x1014126f0`
- `0x1014261f0`
- `0x10142c680`
- `0x101432410`
- `0x10143e480`
- `0x101e61840`
- `0x101e88d30`
- `0x101e88fe0`
- `0x101eb1a10`
- `0x101ec7c20`
- `0x101ec8080`
- `0x101ed3280`
- `0x101ed3590`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x100f2479a`
- `KERNEL32!QueryPerformanceCounter` at `0x100f2495a`
- `KERNEL32!QueryPerformanceCounter` at `0x100f24a4f`
- `KERNEL32!QueryPerformanceCounter` at `0x100f24d1d`
- `KERNEL32!QueryPerformanceCounter` at `0x100f25743`
- `KERNEL32!QueryPerformanceCounter` at `0x100f25a7e`
- `KERNEL32!QueryPerformanceCounter` at `0x100f25e23`
- `KERNEL32!QueryPerformanceCounter` at `0x100f25ef0`
- `KERNEL32!QueryPerformanceCounter` at `0x100f261c6`
- `KERNEL32!QueryPerformanceCounter` at `0x100f2479a`
- `KERNEL32!QueryPerformanceCounter` at `0x100f2495a`
- `KERNEL32!QueryPerformanceCounter` at `0x100f24a4f`
- `KERNEL32!QueryPerformanceCounter` at `0x100f24d1d`
- `KERNEL32!QueryPerformanceCounter` at `0x100f25743`
- `KERNEL32!QueryPerformanceCounter` at `0x100f25a7e`
- `KERNEL32!QueryPerformanceCounter` at `0x100f25e23`
- `KERNEL32!QueryPerformanceCounter` at `0x100f25ef0`
- `KERNEL32!QueryPerformanceCounter` at `0x100f261c6`
- `KERNEL32!GetTickCount` at `0x100f27087`
- `KERNEL32!GetTickCount` at `0x100f27087`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100f247d4`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100f249ad`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100f24a94`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100f24d70`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100f2577d`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100f25ad1`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100f25f35`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100f26227`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100f24787`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100f24946`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100f24a3c`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100f24d09`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100f2572f`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100f25a6a`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100f25e0f`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100f25edc`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100f261b2`
- `sqldk!?GetMsg@ErrMsg@@QEBAPEB_WPEAH@Z` at `0x100f26cbb`
- `sqldk!?GetMsg@ErrMsg@@QEBAPEB_WPEAH@Z` at `0x100f26cbb`
- `sqldk!?GetNextErrMsg@ErrMsgsBase@@QEBAPEBVErrMsg@@PEBV2@@Z` at `0x100f26c70`
- `sqldk!?GetNextErrMsg@ErrMsgsBase@@QEBAPEBVErrMsg@@PEBV2@@Z` at `0x100f26e49`
- `sqldk!?GetNextErrMsg@ErrMsgsBase@@QEBAPEBVErrMsg@@PEBV2@@Z` at `0x100f26c70`
- `sqldk!?GetNextErrMsg@ErrMsgsBase@@QEBAPEBVErrMsg@@PEBV2@@Z` at `0x100f26e49`
- `sqldk!?Release@ErrMsgsBase@@QEAAXXZ` at `0x100f2531a`
- `sqldk!?Release@ErrMsgsBase@@QEAAXXZ` at `0x100f27252`
- `sqldk!?Release@ErrMsgsBase@@QEAAXXZ` at `0x100f2735d`
- `sqldk!?Release@ErrMsgsBase@@QEAAXXZ` at `0x100f2531a`
- `sqldk!?Release@ErrMsgsBase@@QEAAXXZ` at `0x100f27252`
- `sqldk!?Release@ErrMsgsBase@@QEAAXXZ` at `0x100f2735d`
- `sqldk!??0ErrMsgsBase@@QEAA@PEAVIMemObj@@@Z` at `0x100f242a0`
- `sqldk!??0ErrMsgsBase@@QEAA@PEAVIMemObj@@@Z` at `0x100f242a0`
- `sqldk!?hdl_prntbackout@@YAHHHHHPEAD@Z` at `0x100f24811`
- `sqldk!?hdl_prntbackout@@YAHHHHHPEAD@Z` at `0x100f24ad1`
- `sqldk!?hdl_prntbackout@@YAHHHHHPEAD@Z` at `0x100f257ba`
- `sqldk!?hdl_prntbackout@@YAHHHHHPEAD@Z` at `0x100f263e7`
- `sqldk!?ReleaseLock@SOS_RWLock@@QEAAXW4RWLockMode@@@Z` at `0x100f25dfb`
- `sqldk!?ReleaseLock@SOS_RWLock@@QEAAXW4RWLockMode@@@Z` at `0x100f25e64`
- `sqldk!?ReleaseLock@SOS_RWLock@@QEAAXW4RWLockMode@@@Z` at `0x100f25e76`
- `sqldk!?ReleaseLock@SOS_RWLock@@QEAAXW4RWLockMode@@@Z` at `0x100f25dfb`
- `sqldk!?ReleaseLock@SOS_RWLock@@QEAAXW4RWLockMode@@@Z` at `0x100f25e64`
- `sqldk!?ReleaseLock@SOS_RWLock@@QEAAXW4RWLockMode@@@Z` at `0x100f25e76`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100f24277`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100f24277`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100f25d26`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100f25d26`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100f24940`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100f24d03`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100f25a64`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100f2691e`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100f24940`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100f24d03`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100f25a64`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100f2691e`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100f26f4b`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100f26f4b`
- `sqldk!SystemThread_TlsIndex` at `0x100f23df5`
- `sqldk!SystemThread_TlsIndex` at `0x100f242fb`
- `sqldk!SystemThread_TlsIndex` at `0x100f243ae`
- `sqldk!SystemThread_TlsIndex` at `0x100f24908`
- `sqldk!SystemThread_TlsIndex` at `0x100f24ccb`
- `sqldk!SystemThread_TlsIndex` at `0x100f257f3`
- `sqldk!SystemThread_TlsIndex` at `0x100f25a2c`
- `sqldk!SystemThread_TlsIndex` at `0x100f268e6`
- `sqldk!SystemThread_TlsOffset` at `0x100f23dfe`
- `sqldk!SystemThread_TlsOffset` at `0x100f24304`
- `sqldk!SystemThread_TlsOffset` at `0x100f243b7`
- `sqldk!SystemThread_TlsOffset` at `0x100f24911`
- `sqldk!SystemThread_TlsOffset` at `0x100f24cd4`
- `sqldk!SystemThread_TlsOffset` at `0x100f257fc`
- `sqldk!SystemThread_TlsOffset` at `0x100f25a35`
- `sqldk!SystemThread_TlsOffset` at `0x100f268ef`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100f2534f`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100f25c5e`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100f25e9c`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100f26385`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100f26399`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100f27044`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100f27287`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100f27392`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100f2534f`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100f25c5e`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100f25e9c`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100f26385`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100f26399`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100f27044`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100f27287`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100f27392`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100f2492a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100f24ced`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100f25a4e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100f26908`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100f2492a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100f24ced`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100f25a4e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100f26908`
- `sqldk!??_V@YAXPEAX@Z` at `0x100f25329`
- `sqldk!??_V@YAXPEAX@Z` at `0x100f25341`
- `sqldk!??_V@YAXPEAX@Z` at `0x100f27261`
- `sqldk!??_V@YAXPEAX@Z` at `0x100f27279`
- `sqldk!??_V@YAXPEAX@Z` at `0x100f2736c`
- `sqldk!??_V@YAXPEAX@Z` at `0x100f27384`
- `sqldk!??_V@YAXPEAX@Z` at `0x100f25329`
- `sqldk!??_V@YAXPEAX@Z` at `0x100f25341`
- `sqldk!??_V@YAXPEAX@Z` at `0x100f27261`
- `sqldk!??_V@YAXPEAX@Z` at `0x100f27279`
- `sqldk!??_V@YAXPEAX@Z` at `0x100f2736c`
- `sqldk!??_V@YAXPEAX@Z` at `0x100f27384`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x100f24475`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x100f24475`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x100f24497`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x100f24497`
- `VCRUNTIME140!wcsstr` at `0x100f245d1`
- `VCRUNTIME140!wcsstr` at `0x100f245d1`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100f247e0`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100f249b9`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100f24aa0`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100f24d7c`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100f25789`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100f25add`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100f25f41`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100f26233`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100f247e0`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100f249b9`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100f24aa0`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100f24d7c`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100f25789`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100f25add`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100f25f41`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100f26233`
- `sqlmin!?FSystemDatabase@@YA_NPEB_WKK_N@Z` at `0x100f244dd`
- `sqlmin!?FSystemDatabase@@YA_NPEB_WKK_N@Z` at `0x100f244dd`
- `sqlmin!?CloseDB@AutoOpenDB@@AEAAXXZ` at `0x100f24b86`
- `sqlmin!?CloseDB@AutoOpenDB@@AEAAXXZ` at `0x100f24b86`
- `sqlmin!?Open@AutoOpenDB@@QEAAXPEAVBaseXact@@KKH@Z` at `0x100f24b2c`
- `sqlmin!?Open@AutoOpenDB@@QEAAXPEAVBaseXact@@KKH@Z` at `0x100f24b2c`
- `sqlmin!?FSystemDBName@@YA_NPEB_WK@Z` at `0x100f2452c`
- `sqlmin!?FSystemDBName@@YA_NPEB_WK@Z` at `0x100f2452c`
- `sqlmin!?FControlNodeDwShellDb@@YA_NXZ` at `0x100f25380`
- `sqlmin!?FControlNodeDwShellDb@@YA_NXZ` at `0x100f25380`
- `sqlmin!?GetMasterDbId@@YAGXZ` at `0x100f26469`
- `sqlmin!?GetMasterDbId@@YAGXZ` at `0x100f26469`
- `sqlmin!GetXdbServerGlobals` at `0x100f23d2e`
- `sqlmin!GetXdbServerGlobals` at `0x100f23d54`
- `sqlmin!GetXdbServerGlobals` at `0x100f23ef4`
- `sqlmin!GetXdbServerGlobals` at `0x100f23fb6`
- `sqlmin!GetXdbServerGlobals` at `0x100f23fec`
- `sqlmin!GetXdbServerGlobals` at `0x100f24502`
- `sqlmin!GetXdbServerGlobals` at `0x100f25693`
- `sqlmin!GetXdbServerGlobals` at `0x100f2593a`
- `sqlmin!GetXdbServerGlobals` at `0x100f25d62`
- `sqlmin!GetXdbServerGlobals` at `0x100f26359`
- `sqlmin!GetXdbServerGlobals` at `0x100f26811`
- `sqlmin!GetXdbServerGlobals` at `0x100f2682b`
- `sqlmin!GetXdbServerGlobals` at `0x100f23d2e`
- `sqlmin!GetXdbServerGlobals` at `0x100f23d54`
- `sqlmin!GetXdbServerGlobals` at `0x100f23ef4`
- `sqlmin!GetXdbServerGlobals` at `0x100f23fb6`
- `sqlmin!GetXdbServerGlobals` at `0x100f23fec`
- `sqlmin!GetXdbServerGlobals` at `0x100f24502`
- `sqlmin!GetXdbServerGlobals` at `0x100f25693`
- `sqlmin!GetXdbServerGlobals` at `0x100f2593a`
- `sqlmin!GetXdbServerGlobals` at `0x100f25d62`
- `sqlmin!GetXdbServerGlobals` at `0x100f26359`
- `sqlmin!GetXdbServerGlobals` at `0x100f26811`
- `sqlmin!GetXdbServerGlobals` at `0x100f2682b`
- `sqlfabric!GetRelativeWinfabServiceUri` at `0x100f24590`
- `sqlfabric!GetRelativeWinfabServiceUri` at `0x100f24590`

## string_xrefs

- `0x100f24b53`: `login error - Open DB failed for DB name: %.*ls id: %u\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=41
__int64 __fastcall FindLoginXdb(
        struct IMemObj *a1,
        struct SNI_Conn *a2,
        struct CSession *a3,
        const wchar_t *a4,
        int a5,
        bool a6,
        bool a7,
        unsigned int *a8,
        enum ELoginFailedState *a9)
{
  int *v11; // r13
  struct CNetConnection *v12; // rdi
  __int64 v13; // r14
  __int64 v15; // rcx
  __int64 XdbServerGlobals; // rax
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rax
  _QWORD *ThreadLocalStoragePointer; // rdx
  __int64 v21; // rax
  __int64 FeatureExtension; // r15
  unsigned int v23; // edi
  __int64 v24; // rcx
  bool v25; // r12
  __int64 v26; // rcx
  __int64 v27; // rax
  __int64 v28; // rcx
  __int64 v29; // rcx
  int v30; // ecx
  ErrMsgsBase *v31; // rax
  ErrMsgsBase *v32; // rbx
  __int64 v33; // rax
  __int64 v34; // rcx
  void ***v35; // rdx
  unsigned int v36; // ebx
  CDefaultCollation *v37; // rax
  int v38; // edi
  __int64 v39; // rcx
  __int64 v40; // rax
  __int64 v41; // rdx
  __int64 v42; // rdx
  CSbTransportMgr *QuadPart; // rbx
  _QWORD *v44; // rbx
  int v45; // r8d
  int v46; // r12d
  __int64 v47; // rbx
  struct Worker *v48; // rcx
  CSbTransportMgr *v49; // rbx
  unsigned __int64 v50; // rax
  _QWORD *v51; // rbx
  int v52; // r8d
  CSbTransportMgr *v53; // rbx
  _QWORD *v54; // rbx
  int v55; // r8d
  unsigned int *v56; // rbx
  ErrMsgsBase *v57; // r12
  __int64 v58; // rbx
  struct Worker *v59; // rcx
  CSbTransportMgr *v60; // rbx
  unsigned __int64 v61; // rax
  _QWORD *v62; // rbx
  int v63; // r8d
  int v64; // ecx
  __int64 v65; // rdx
  ErrMsgsBase *v66; // rcx
  struct FederatedContext *v67; // rbx
  __int64 v68; // rdx
  ErrMsgsBase *v69; // rcx
  __int64 v70; // rdx
  __int32 v71; // ecx
  wchar_t *v72; // rax
  __int64 v73; // rax
  __int64 v74; // rdx
  __int64 v75; // rdx
  void *v76; // rbx
  __int64 v77; // rcx
  __int64 v78; // rcx
  const unsigned __int8 *v79; // rax
  struct CNetConnection *v80; // r12
  int v81; // eax
  __int64 v82; // rax
  __int64 v83; // rbx
  __int64 v84; // rcx
  __int64 v85; // rcx
  int v86; // r15d
  __int64 v87; // rcx
  CSbTransportMgr *v88; // rbx
  _QWORD *v89; // rbx
  int v90; // r8d
  _QWORD *v91; // rdx
  __int64 v92; // rcx
  int v93; // ebx
  __int64 v94; // rbx
  struct Worker *v95; // rcx
  CSbTransportMgr *v96; // rbx
  unsigned __int64 v97; // rax
  _QWORD *v98; // rbx
  int v99; // r8d
  bool v100; // zf
  char v101; // al
  bool v102; // cl
  unsigned int v103; // r15d
  unsigned int v104; // edx
  __int64 v105; // rcx
  __int32 v106; // r15d
  struct FederatedContext *v107; // r12
  ErrMsgsBase *v108; // rax
  __int64 v109; // r15
  __int64 v110; // rbx
  __int64 v111; // r15
  int v112; // ebx
  CSbTransportMgr *v113; // rax
  unsigned int v114; // r14d
  CSbTransportMgr *v115; // rbx
  _QWORD *v116; // rbx
  int v117; // r8d
  bool v118; // r11
  struct CSession *v119; // r15
  CSbTransportMgr *v120; // rbx
  unsigned __int64 v121; // rax
  _QWORD *v122; // rbx
  int v123; // r8d
  char v124; // al
  unsigned int v125; // edx
  __int64 v126; // rcx
  __int64 v127; // rax
  __int32 v128; // ebx
  char v129; // al
  struct FederatedContext *v130; // rbx
  unsigned __int16 MasterDbId; // ax
  struct CSession *v132; // r14
  bool v133; // al
  int v134; // ebx
  char v136; // al
  bool v137; // al
  _QWORD *v138; // rax
  _QWORD *v139; // rax
  __int64 v140; // rax
  __int64 v141; // rcx
  __int64 v142; // rbx
  __int64 v143; // rax
  _QWORD *v144; // rcx
  _QWORD *v145; // rcx
  __int64 v146; // rbx
  struct Worker *v147; // rcx
  __int64 v148; // rdx
  bool v149; // zf
  char v150; // al
  bool v151; // al
  bool v152; // cl
  bool v153; // zf
  const struct ErrMsg *NextErrMsg; // rbx
  int v155; // r12d
  ErrMsgsBase *v156; // rdi
  const wchar_t *Msg; // rax
  bool v158; // al
  struct ILoginToken *LoginTokenFromSid; // rbx
  char v160; // cl
  rsize_t v161; // r12
  unsigned __int64 v162; // rax
  wchar_t *v163; // rax
  wchar_t *v164; // r14
  void *v165; // rbx
  unsigned int v166; // ecx
  char *v167; // rcx
  DWORD TickCount; // eax
  struct CSession *v169; // rbx
  __int64 v170; // rax
  int v171; // eax
  int v172; // eax
  void *v173; // rbx
  unsigned int *v174; // rsi
  void *v175; // rbx
  int v176; // eax
  enum ELoginFailedState *v177; // r8
  int v178; // ecx
  int v179[2]; // [rsp+30h] [rbp-1318h]
  wchar_t *v180; // [rsp+38h] [rbp-1310h]
  __int64 v181; // [rsp+40h] [rbp-1308h]
  int v182; // [rsp+40h] [rbp-1308h]
  int v183; // [rsp+48h] [rbp-1300h]
  int v184; // [rsp+50h] [rbp-12F8h]
  unsigned int *v185; // [rsp+58h] [rbp-12F0h]
  int v186; // [rsp+60h] [rbp-12E8h]
  int v187; // [rsp+68h] [rbp-12E0h]
  __int64 v188; // [rsp+70h] [rbp-12D8h]
  int v189; // [rsp+78h] [rbp-12D0h]
  int v190; // [rsp+88h] [rbp-12C0h]
  __int32 v191; // [rsp+128h] [rbp-1220h]
  bool v192; // [rsp+140h] [rbp-1208h]
  unsigned int Login; // [rsp+144h] [rbp-1204h]
  int v194; // [rsp+144h] [rbp-1204h]
  char v195; // [rsp+148h] [rbp-1200h]
  unsigned int v196; // [rsp+14Ch] [rbp-11FCh]
  bool v197; // [rsp+150h] [rbp-11F8h]
  int v198; // [rsp+154h] [rbp-11F4h]
  char v199; // [rsp+158h] [rbp-11F0h]
  bool v200; // [rsp+159h] [rbp-11EFh]
  char v201; // [rsp+15Ah] [rbp-11EEh]
  bool v202; // [rsp+15Bh] [rbp-11EDh]
  bool v203; // [rsp+15Ch] [rbp-11ECh] BYREF
  struct CSession *v204; // [rsp+160h] [rbp-11E8h]
  rsize_t DestinationSize; // [rsp+168h] [rbp-11E0h]
  wchar_t *v206; // [rsp+170h] [rbp-11D8h]
  unsigned int *v207; // [rsp+178h] [rbp-11D0h]
  int v208; // [rsp+180h] [rbp-11C8h]
  _BYTE v209[2]; // [rsp+184h] [rbp-11C4h] BYREF
  bool v210; // [rsp+186h] [rbp-11C2h] BYREF
  ErrMsgsBase *v211; // [rsp+188h] [rbp-11C0h]
  enum ELoginFailedState *v212; // [rsp+190h] [rbp-11B8h]
  __int128 v213; // [rsp+198h] [rbp-11B0h]
  __int128 v214; // [rsp+1A8h] [rbp-11A0h]
  struct IMemObj *v215; // [rsp+1B8h] [rbp-1190h]
  struct CNetConnection *v216; // [rsp+1C0h] [rbp-1188h]
  int v217; // [rsp+1C8h] [rbp-1180h]
  void *Source; // [rsp+1D0h] [rbp-1178h]
  struct SqlAzureIpAddress *v219; // [rsp+1D8h] [rbp-1170h] BYREF
  __int64 v220; // [rsp+1E0h] [rbp-1168h]
  struct SqlAzureIpAddress *v221; // [rsp+1E8h] [rbp-1160h] BYREF
  wchar_t *v222[2]; // [rsp+1F0h] [rbp-1158h]
  int v224; // [rsp+204h] [rbp-1144h] BYREF
  int v225; // [rsp+208h] [rbp-1140h] BYREF
  int v226[2]; // [rsp+210h] [rbp-1138h]
  __int32 v227; // [rsp+218h] [rbp-1130h]
  int v228; // [rsp+21Ch] [rbp-112Ch]
  unsigned int v229; // [rsp+220h] [rbp-1128h] BYREF
  int v230; // [rsp+224h] [rbp-1124h]
  ErrMsgsBase *v231; // [rsp+228h] [rbp-1120h]
  struct SNI_Conn *v232; // [rsp+230h] [rbp-1118h]
  int v233[2]; // [rsp+238h] [rbp-1110h]
  LARGE_INTEGER v234; // [rsp+240h] [rbp-1108h] BYREF
  int v235[2]; // [rsp+248h] [rbp-1100h] BYREF
  __int64 v236; // [rsp+250h] [rbp-10F8h]
  int v237; // [rsp+258h] [rbp-10F0h]
  __int64 v238; // [rsp+260h] [rbp-10E8h]
  __m128i si128; // [rsp+268h] [rbp-10E0h]
  int v240; // [rsp+278h] [rbp-10D0h]
  wchar_t *v241; // [rsp+280h] [rbp-10C8h] BYREF
  LARGE_INTEGER v242; // [rsp+288h] [rbp-10C0h] BYREF
  unsigned __int64 v243; // [rsp+290h] [rbp-10B8h] BYREF
  LARGE_INTEGER v244; // [rsp+298h] [rbp-10B0h] BYREF
  LARGE_INTEGER v245; // [rsp+2A0h] [rbp-10A8h] BYREF
  LARGE_INTEGER v246; // [rsp+2A8h] [rbp-10A0h] BYREF
  LARGE_INTEGER v247; // [rsp+2B0h] [rbp-1098h] BYREF
  LARGE_INTEGER v248; // [rsp+2B8h] [rbp-1090h] BYREF
  LARGE_INTEGER v249; // [rsp+2C0h] [rbp-1088h] BYREF
  __int64 v250; // [rsp+2C8h] [rbp-1080h]
  ErrMsgsBase *v251; // [rsp+2D0h] [rbp-1078h]
  LARGE_INTEGER PerformanceCount; // [rsp+2D8h] [rbp-1070h] BYREF
  __int128 v253; // [rsp+2E0h] [rbp-1068h]
  __int64 v254; // [rsp+2F0h] [rbp-1058h]
  int v255; // [rsp+2F8h] [rbp-1050h] BYREF
  __int64 v256; // [rsp+300h] [rbp-1048h]
  __int64 v257; // [rsp+308h] [rbp-1040h]
  __int64 v258; // [rsp+310h] [rbp-1038h]
  __int64 v259; // [rsp+318h] [rbp-1030h]
  __int64 v260; // [rsp+320h] [rbp-1028h]
  ErrMsgsBase *v261; // [rsp+328h] [rbp-1020h]
  _QWORD *v262; // [rsp+330h] [rbp-1018h]
  __int64 v263; // [rsp+338h] [rbp-1010h]
  struct FederatedContext *v264; // [rsp+340h] [rbp-1008h]
  _QWORD *v265; // [rsp+348h] [rbp-1000h]
  _BYTE v266[4]; // [rsp+350h] [rbp-FF8h] BYREF
  unsigned int v267; // [rsp+354h] [rbp-FF4h] BYREF
  bool v268; // [rsp+358h] [rbp-FF0h] BYREF
  bool v269; // [rsp+359h] [rbp-FEFh] BYREF
  int v270; // [rsp+35Ah] [rbp-FEEh] BYREF
  int v271; // [rsp+360h] [rbp-FE8h] BYREF
  bool v272; // [rsp+364h] [rbp-FE4h] BYREF
  struct FederatedContext *v273; // [rsp+368h] [rbp-FE0h] BYREF
  int v274; // [rsp+370h] [rbp-FD8h] BYREF
  _WORD v275[2]; // [rsp+374h] [rbp-FD4h] BYREF
  char v276[4]; // [rsp+378h] [rbp-FD0h] BYREF
  int v277; // [rsp+37Ch] [rbp-FCCh] BYREF
  __int64 v278; // [rsp+380h] [rbp-FC8h] BYREF
  wchar_t *v279; // [rsp+388h] [rbp-FC0h] BYREF
  unsigned int v280[4]; // [rsp+390h] [rbp-FB8h] BYREF
  struct _GUID v281; // [rsp+3A0h] [rbp-FA8h] BYREF
  int v282; // [rsp+3B0h] [rbp-F98h] BYREF
  __int64 v283; // [rsp+3B8h] [rbp-F90h] BYREF
  int v284; // [rsp+3C0h] [rbp-F88h] BYREF
  int v285; // [rsp+3C4h] [rbp-F84h] BYREF
  int v286; // [rsp+3C8h] [rbp-F80h] BYREF
  struct in_addr v287[2]; // [rsp+3D0h] [rbp-F78h] BYREF
  int v288; // [rsp+3D8h] [rbp-F70h] BYREF
  __int64 v289; // [rsp+3DCh] [rbp-F6Ch] BYREF
  int v290; // [rsp+3E4h] [rbp-F64h] BYREF
  int v291; // [rsp+3E8h] [rbp-F60h] BYREF
  void **v292; // [rsp+3F0h] [rbp-F58h] BYREF
  void ***v293; // [rsp+3F8h] [rbp-F50h]
  int v294; // [rsp+400h] [rbp-F48h]
  __int64 v295; // [rsp+408h] [rbp-F40h]
  __int64 v296; // [rsp+410h] [rbp-F38h]
  int v297; // [rsp+418h] [rbp-F30h]
  int v298; // [rsp+41Ch] [rbp-F2Ch]
  __int64 v299; // [rsp+420h] [rbp-F28h]
  char v300; // [rsp+428h] [rbp-F20h]
  __int64 v301; // [rsp+430h] [rbp-F18h]
  ErrMsgsBase *v302; // [rsp+438h] [rbp-F10h]
  char v303; // [rsp+440h] [rbp-F08h]
  __int64 v304; // [rsp+450h] [rbp-EF8h] BYREF
  int v305; // [rsp+458h] [rbp-EF0h]
  struct _GUID v306; // [rsp+460h] [rbp-EE8h] BYREF
  struct _GUID v307; // [rsp+470h] [rbp-ED8h] BYREF
  void *v308[2]; // [rsp+480h] [rbp-EC8h] BYREF
  __m128i v309; // [rsp+490h] [rbp-EB8h] BYREF
  int v310; // [rsp+4A0h] [rbp-EA8h]
  __int64 v311[3]; // [rsp+4A8h] [rbp-EA0h] BYREF
  bool v312; // [rsp+4C0h] [rbp-E88h]
  bool *v313; // [rsp+4C8h] [rbp-E80h]
  __int128 v314; // [rsp+4D0h] [rbp-E78h]
  _BYTE v315[16]; // [rsp+4E0h] [rbp-E68h] BYREF
  _BYTE v316[16]; // [rsp+4F0h] [rbp-E58h] BYREF
  _BYTE v317[16]; // [rsp+500h] [rbp-E48h] BYREF
  char v318[8]; // [rsp+510h] [rbp-E38h] BYREF
  int v319; // [rsp+518h] [rbp-E30h]
  int v320; // [rsp+520h] [rbp-E28h]
  _DWORD **v321; // [rsp+528h] [rbp-E20h]
  char *v322; // [rsp+530h] [rbp-E18h]
  __int64 v323; // [rsp+538h] [rbp-E10h]
  _DWORD *v324; // [rsp+540h] [rbp-E08h] BYREF
  int v325; // [rsp+548h] [rbp-E00h]
  int v326; // [rsp+54Ch] [rbp-DFCh]
  GUID *v327; // [rsp+550h] [rbp-DF8h]
  int v328; // [rsp+558h] [rbp-DF0h]
  int v329; // [rsp+55Ch] [rbp-DECh]
  const wchar_t *v330; // [rsp+560h] [rbp-DE8h]
  int v331; // [rsp+568h] [rbp-DE0h]
  int v332; // [rsp+56Ch] [rbp-DDCh]
  wchar_t *v333; // [rsp+570h] [rbp-DD8h]
  int v334; // [rsp+578h] [rbp-DD0h]
  int v335; // [rsp+57Ch] [rbp-DCCh]
  wchar_t *v336; // [rsp+580h] [rbp-DC8h]
  int v337; // [rsp+588h] [rbp-DC0h]
  int v338; // [rsp+58Ch] [rbp-DBCh]
  char v339; // [rsp+590h] [rbp-DB8h] BYREF
  __int64 v340; // [rsp+760h] [rbp-BE8h]
  __int64 v341; // [rsp+768h] [rbp-BE0h]
  _DWORD v342[2]; // [rsp+770h] [rbp-BD8h] BYREF
  bool v343; // [rsp+778h] [rbp-BD0h]
  bool v344; // [rsp+779h] [rbp-BCFh]
  char v345[8]; // [rsp+7A0h] [rbp-BA8h] BYREF
  int v346; // [rsp+7A8h] [rbp-BA0h]
  int v347; // [rsp+7B0h] [rbp-B98h]
  bool **v348; // [rsp+7B8h] [rbp-B90h]
  char *v349; // [rsp+7C0h] [rbp-B88h]
  __int64 v350; // [rsp+7C8h] [rbp-B80h]
  bool *v351; // [rsp+7D0h] [rbp-B78h] BYREF
  int v352; // [rsp+7D8h] [rbp-B70h]
  int v353; // [rsp+7DCh] [rbp-B6Ch]
  struct _GUID *v354; // [rsp+7E0h] [rbp-B68h]
  int v355; // [rsp+7E8h] [rbp-B60h]
  int v356; // [rsp+7ECh] [rbp-B5Ch]
  wchar_t *v357; // [rsp+7F0h] [rbp-B58h]
  int v358; // [rsp+7F8h] [rbp-B50h]
  int v359; // [rsp+7FCh] [rbp-B4Ch]
  wchar_t *v360; // [rsp+800h] [rbp-B48h]
  int v361; // [rsp+808h] [rbp-B40h]
  int v362; // [rsp+80Ch] [rbp-B3Ch]
  char *v363; // [rsp+810h] [rbp-B38h]
  unsigned int v364; // [rsp+818h] [rbp-B30h]
  int v365; // [rsp+81Ch] [rbp-B2Ch]
  char v366; // [rsp+820h] [rbp-B28h] BYREF
  __int64 v367; // [rsp+9F0h] [rbp-958h]
  __int64 v368; // [rsp+9F8h] [rbp-950h]
  bool v369; // [rsp+A00h] [rbp-948h] BYREF
  _BYTE v370[40]; // [rsp+A30h] [rbp-918h] BYREF
  _BYTE v371[40]; // [rsp+A58h] [rbp-8F0h] BYREF
  _BYTE v372[40]; // [rsp+A80h] [rbp-8C8h] BYREF
  _BYTE v373[24]; // [rsp+AA8h] [rbp-8A0h] BYREF
  _BYTE v374[24]; // [rsp+AC0h] [rbp-888h] BYREF
  _BYTE v375[24]; // [rsp+AD8h] [rbp-870h] BYREF
  _BYTE v376[48]; // [rsp+AF0h] [rbp-858h] BYREF
  _BYTE v377[24]; // [rsp+B20h] [rbp-828h] BYREF
  _QWORD *v378; // [rsp+B38h] [rbp-810h]
  int v379; // [rsp+D80h] [rbp-5C8h]
  int v380; // [rsp+D84h] [rbp-5C4h]
  char v381; // [rsp+D88h] [rbp-5C0h]
  bool v382; // [rsp+D89h] [rbp-5BFh]
  _OWORD Destination[5]; // [rsp+DB0h] [rbp-598h] BYREF
  int v384; // [rsp+E00h] [rbp-548h]
  char v385; // [rsp+E04h] [rbp-544h]
  wchar_t v386[8]; // [rsp+E10h] [rbp-538h] BYREF
  __int128 v387; // [rsp+E20h] [rbp-528h]
  __int128 v388; // [rsp+E30h] [rbp-518h]
  __int128 v389; // [rsp+E40h] [rbp-508h]
  __int64 v390; // [rsp+E50h] [rbp-4F8h]
  __int16 v391; // [rsp+E58h] [rbp-4F0h]
  wchar_t v392[72]; // [rsp+E60h] [rbp-4E8h] BYREF
  wchar_t v393[256]; // [rsp+EF0h] [rbp-458h] BYREF
  wchar_t Str[264]; // [rsp+10F0h] [rbp-258h] BYREF

  v260 = -2;
  *(_QWORD *)v226 = a4;
  v204 = a3;
  *(_QWORD *)v233 = a2;
  v215 = a1;
  v221 = a1;
  v232 = a2;
  v219 = a3;
  *(_QWORD *)v235 = a4;
  v207 = a8;
  v11 = (int *)a9;
  v212 = a9;
  *(_QWORD *)&v287[0].S_un.S_un_b.s_b1 = a9;
  v12 = (struct CNetConnection *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)a3 + 12) + 16LL))(*((_QWORD *)a3 + 12));
  v216 = v12;
  v13 = *((_QWORD *)a3 + 12);
  v283 = v13;
  v281 = *(struct _GUID *)((char *)a2 + 28);
  *a8 = 0;
  v286 = 0;
  if ( byte_102EDCC1E && (int)SNI_Conn::CmpTlsVersion(a2, dword_102EF3E14) < 0 )
  {
    log_unlocalized(L"x_elfInvalidTlsVersion 171");
    *(_DWORD *)a9 = 171;
    return 18456;
  }
  if ( *((_DWORD *)v12 + 270) )
  {
    if ( !byte_102EDCE2B || !HIBYTE(dword_102EF4364) )
    {
      *(_DWORD *)a9 = 183;
      return 40613;
    }
  }
  else if ( *((_DWORD *)v12 + 271) && (!byte_102EDCE2A || !HIBYTE(dword_102EF4364)) )
  {
    *(_DWORD *)a9 = 184;
    return 40613;
  }
  FSetContextInfoXdb(a3, &v281);
  *(_OWORD *)v222 = 0;
  XdbServerGlobals = GetXdbServerGlobals(v15);
  v17 = -1;
  do
    ++v17;
  while ( *(_WORD *)(XdbServerGlobals + 2 * v17) );
  v18 = 2 * v17;
  LOWORD(v222[1]) = v18;
  v222[0] = (wchar_t *)GetXdbServerGlobals(v18);
  v19 = *((_QWORD *)a3 + 24);
  if ( v19 )
  {
    v198 = 2 * *(unsigned __int16 *)(v19 + 70);
    v206 = (wchar_t *)(v19 + *(unsigned __int16 *)(v19 + 68));
  }
  else
  {
    v206 = 0;
  }
  if ( !*((_DWORD *)v12 + 243) )
  {
    log_unlocalized(L"x_elfRetrieveIpAddressFailed 81");
    *(_DWORD *)a9 = 81;
    return 42115;
  }
  v274 = 0;
  if ( v19 )
  {
    v274 = 2 * *(unsigned __int16 *)(v19 + 70);
    v279 = (wchar_t *)(v19 + *(unsigned __int16 *)(v19 + 68));
  }
  else
  {
    v279 = 0;
  }
  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  v21 = *(_QWORD *)(ThreadLocalStoragePointer[SystemThread_TlsIndex] + SystemThread_TlsOffset);
  LOBYTE(ThreadLocalStoragePointer) = 2;
  FeatureExtension = CPhysicalConnection::GetFeatureExtension(
                       *(_QWORD *)(*(_QWORD *)(v21 + 72) + 96LL),
                       ThreadLocalStoragePointer);
  v220 = FeatureExtension;
  v250 = FeatureExtension;
  v202 = FeatureExtension != 0;
  v23 = 0;
  v196 = 0;
  Login = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v240 = 0;
  memset(Destination, 0, sizeof(Destination));
  v384 = 0;
  v385 = 0;
  v267 = 0;
  v270 = 0x1000000;
  v203 = 0;
  v210 = 0;
  v282 = 0;
  v225 = 0;
  v307 = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
  v266[0] = 0;
  v192 = 0;
  v208 = *(_DWORD *)(GetXdbServerGlobals(v24) + 19628);
  v25 = 0;
  v197 = 0;
  v195 = byte_102EDCEE6;
  v277 = -1;
  v271 = 0;
  v200 = byte_102EDCF3B != 0;
  v275[0] = 0;
  v278 = 0;
  v273 = 0;
  v291 = 0;
  Source = *(void **)v226;
  LODWORD(DestinationSize) = a5;
  v238 = 0;
  v228 = 0;
  v269 = 1;
  v280[0] = 0;
  if ( IsFidoDWFrontEndSession() && byte_102EDCED7 )
  {
    v27 = GetXdbServerGlobals(v26);
    v28 = -1;
    do
      ++v28;
    while ( *(_WORD *)(v27 + 2 * v28 + 12538) );
    v29 = 2 * v28;
    v228 = v29;
    if ( (int)v29 <= 0 )
    {
      *(_DWORD *)a9 = 176;
      v23 = 40613;
      v196 = 40613;
      Login = 40613;
    }
    else
    {
      v238 = GetXdbServerGlobals(v29) + 12538;
    }
  }
  if ( !FeatureExtension )
  {
    if ( !a5 )
    {
      v23 = 18456;
      Login = 18456;
      *(_DWORD *)a9 = 122;
LABEL_34:
      v196 = 18456;
      goto LABEL_35;
    }
    if ( !*((_QWORD *)v204 + 26) )
    {
      v23 = 18456;
      Login = 18456;
      *(_DWORD *)a9 = 124;
      goto LABEL_34;
    }
  }
LABEL_35:
  v268 = 0;
  if ( a6 && (qword_102F21DB4 & 0x200) != 0 )
  {
    v346 = 327680;
    v347 = 0;
    v348 = &v351;
    v349 = &v366;
    v367 = 0;
    v350 = 0;
    v368 = 0;
    v351 = &v369;
    v352 = 33;
    v353 = 4;
    v369 = a7;
    v354 = &v281;
    v355 = 16;
    v356 = 1;
    v30 = *((_DWORD *)v216 + 244);
    v363 = (char *)v216 + 874;
    v364 = v30 & 0xFFFFFFFE;
    v365 = 4;
    v357 = v222[0];
    v358 = (__int64)v222[1] & 0xFFFE;
    v359 = 2;
    v360 = v206;
    v361 = 2 * ((unsigned __int64)v198 >> 1);
    v362 = 3;
    XeCloudPkg::re_login::Publish((XeCloudPkg::re_login *)v345);
  }
  v311[0] = (__int64)&CConnectionChecker::`vftable';
  v311[1] = (__int64)a2;
  v311[2] = (__int64)v204;
  v312 = a6;
  v313 = &v268;
  v314 = *(_OWORD *)v222;
  if ( !(unsigned __int8)CConnectionChecker::Check(v311, 0) )
  {
    *(_DWORD *)a9 = 0;
LABEL_185:
    operator delete[](v273);
    v76 = (void *)v278;
    if ( v278 )
    {
      operator delete[](*(void **)(v278 + 16));
      operator delete(v76, 0x18u);
    }
    return 26078;
  }
  v217 = 1295;
  v31 = (ErrMsgsBase *)operator new(0x20u, v215, 1, "sql\\ntdbms\\msql\\ods\\login.cpp", 1295, 3u);
  v32 = v31;
  v211 = v31;
  v251 = v31;
  if ( v31 )
  {
    ErrMsgsBase::ErrMsgsBase(v31, v215);
    *((_DWORD *)v32 + 6) = 0;
  }
  else
  {
    v32 = 0;
    v211 = 0;
  }
  v231 = v32;
  v261 = v32;
  if ( !v32 )
  {
    *(_DWORD *)a9 = 10;
LABEL_496:
    operator delete[](v273);
    v173 = (void *)v278;
    if ( v278 )
    {
      operator delete[](*(void **)(v278 + 16));
      operator delete(v173, 0x18u);
    }
    return 40613;
  }
  if ( v23 && !v208 )
  {
LABEL_413:
    if ( byte_102EDCF3D && BYTE1(v270) && v23 == 40914 )
    {
      v23 = 40532;
      v196 = 40532;
      goto LABEL_427;
    }
    if ( !*v207 )
    {
      if ( BYTE2(v270) )
      {
        if ( !v23 )
        {
          v23 = 18456;
          v196 = 18456;
          *v11 = 126;
          *(_OWORD *)v386 = 0;
          v387 = 0;
          v388 = 0;
          v389 = 0;
          v390 = 0;
          v391 = 0;
          GuidToString(&v281, v386, 0x4Au);
          v391 = 0;
          ex_callprint(4060, 11, 2, (unsigned int)v274, v279);
        }
        goto LABEL_427;
      }
      if ( !v23 || v23 == 40615 )
      {
        v23 = 40613;
        v196 = 40613;
        if ( HIBYTE(v270) )
          *v11 = 127;
        else
          *v11 = 134;
        goto LABEL_427;
      }
    }
    if ( !v23 )
      goto LABEL_448;
LABEL_427:
    if ( a6 )
      goto LABEL_448;
    if ( v195 )
      v149 = (v271 & 0x101) == 257;
    else
      v149 = v277 == 0;
    v150 = v149;
    v151 = v192 && v150;
    v152 = 0;
    if ( byte_102EDCBD5 )
      v152 = *v11 == 84;
    if ( v208 == 1 )
    {
      v153 = !v151;
    }
    else
    {
      if ( v208 != 2 )
      {
LABEL_447:
        CCloudExtensions::DosGuard::RegisterFailure(
          &v281,
          &v307,
          (char *)v216 + 776,
          *((unsigned int *)v216 + 243),
          v23,
          *v11);
        goto LABEL_448;
      }
      if ( v151 || v25 )
      {
LABEL_448:
        if ( (qword_102F21DB4 & 0x80u) != 0LL )
        {
          NextErrMsg = ErrMsgsBase::GetNextErrMsg(v32, 0);
          if ( NextErrMsg )
          {
            v155 = (__int64)v222[1] & 0xFFFE;
            v156 = v211;
            do
            {
              Msg = ErrMsg::GetMsg(NextErrMsg, &v274);
              v319 = 327680;
              v320 = 0;
              v321 = &v324;
              v322 = &v339;
              v340 = 0;
              v323 = 0;
              v341 = 0;
              v324 = v342;
              v325 = 42;
              v326 = 4;
              v327 = &Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
              v328 = 16;
              v329 = 4;
              v330 = 0;
              v331 = 0;
              v332 = 5;
              v333 = 0;
              v334 = 0;
              v335 = 6;
              v336 = 0;
              v337 = 0;
              v338 = 7;
              v342[0] = *(unsigned __int16 *)NextErrMsg;
              v342[1] = *((_DWORD *)NextErrMsg + 3);
              v343 = a6;
              v344 = v268;
              v327 = &v281;
              v330 = Msg;
              v331 = 2 * v274;
              v333 = v222[0];
              v334 = v155;
              v336 = v206;
              v337 = 2 * ((unsigned __int64)v198 >> 1);
              XeCloudPkg::login_substep_failure::Publish((XeCloudPkg::login_substep_failure *)v318);
              NextErrMsg = ErrMsgsBase::GetNextErrMsg(v156, NextErrMsg);
            }
            while ( NextErrMsg );
            v23 = v196;
            v11 = (int *)v212;
          }
        }
        v158 = a6;
        if ( v195 && !a6 )
        {
          XEventReportFirewallCategorizationEvent(v216, &v281, v206, (unsigned __int64)v198 >> 1, v271, v23);
          v158 = 0;
        }
        if ( v23 )
          goto LABEL_483;
        if ( v268 )
        {
LABEL_474:
          TickCount = GetTickCount();
          v169 = v204;
          *((_DWORD *)v204 + 238) = TickCount;
          goto LABEL_484;
        }
        LoginTokenFromSid = 0;
        v212 = 0;
        v160 = v266[0];
        if ( v266[0] || v273 && byte_102EDCC3D )
        {
          if ( v250 )
          {
            if ( !v158 )
            {
              v170 = v278;
              if ( v278 )
              {
                if ( !*(_QWORD *)(v250 + 128) )
                {
                  v278 = 0;
                  *(_QWORD *)(v250 + 128) = v170;
                  v160 = v266[0];
                }
              }
            }
          }
          LOBYTE(v185) = v160;
          LoginTokenFromSid = (struct ILoginToken *)CreateLoginTokenFromSid(
                                                      Destination,
                                                      v267,
                                                      7,
                                                      0,
                                                      1,
                                                      Source,
                                                      DestinationSize,
                                                      4,
                                                      0,
                                                      0,
                                                      v225,
                                                      (_DWORD)v185,
                                                      v273);
          v212 = LoginTokenFromSid;
        }
        else
        {
          v161 = (unsigned int)DestinationSize;
          v162 = 2 * ((unsigned __int64)(unsigned int)DestinationSize >> 1);
          if ( !is_mul_ok((unsigned __int64)(unsigned int)DestinationSize >> 1, 2u) )
            v162 = -1;
          v163 = (wchar_t *)operator new[](v162, v215, 1, "sql\\ntdbms\\msql\\ods\\login.cpp", 2451, 3u);
          v164 = v163;
          v222[0] = v163;
          if ( v163 )
          {
            v165 = Source;
            memcpy_s(v163, v161, Source, v161);
            if ( (_BYTE)v270 )
            {
              v166 = 1;
            }
            else
            {
              v166 = 3;
              if ( v203 )
                v166 = 5;
            }
            LoginTokenFromSid = CreateLoginTokenForImpersonation(
                                  0,
                                  *v207,
                                  v165,
                                  (unsigned int)DestinationSize,
                                  1u,
                                  5u,
                                  0,
                                  0,
                                  (void (__fastcall ****)(_QWORD, __int64))v164,
                                  DestinationSize,
                                  0,
                                  0,
                                  v166,
                                  0,
                                  Destination,
                                  v267,
                                  v225);
            v212 = LoginTokenFromSid;
          }
          else
          {
            *v11 = 10;
            v23 = 40613;
          }
          operator delete(v164, 2u);
          if ( v23 )
            goto LABEL_471;
        }
        if ( !LoginTokenFromSid )
        {
          *v11 = 54;
          goto LABEL_494;
        }
LABEL_471:
        OverwriteLoginTokenBySidForSDS(*v207, LoginTokenFromSid);
        if ( LoginTokenFromSid )
        {
          v167 = (char *)LoginTokenFromSid + *(int *)(*((_QWORD *)LoginTokenFromSid + 2) + 4LL) + 16;
          (*(void (__fastcall **)(char *))(*(_QWORD *)v167 + 8LL))(v167);
        }
        if ( !v23 )
          goto LABEL_474;
LABEL_483:
        v169 = v204;
LABEL_484:
        if ( !*((_DWORD *)v216 + 272)
          || (!v200
           || !*((_BYTE *)v216 + 1344)
           || *((_DWORD *)v216 + 334) != 1
           || *((_DWORD *)v216 + 335) == 2
           || (v271 & 0x10000) != 0
            ? (v171 = *((_DWORD *)v216 + 279))
            : (v171 = *((_DWORD *)v216 + 321)),
              LODWORD(v279) = v171,
              (v172 = CNetConnection::SetEffectivePeerIPAddress(v216, (unsigned __int8 *)&v279, 4u)) == 0) )
        {
          v174 = v207;
          if ( byte_102EDCAD7 && !byte_102EDCADA )
          {
            v306 = v281;
            AuditLoginXdb(v207, v23, (unsigned int)*v11, &v306);
          }
          if ( byte_102EDCEE8 && !byte_102EDCEE7 && v23 != 40613 && v23 != 40969 && *v11 != 165 )
          {
            v306 = v281;
            CheckIfTdAuditSessionExists(v169, v174, &v306);
          }
          if ( *((_BYTE *)qword_102EF3550 + 555) && !v23 && (*((_BYTE *)v169 + 402) & 0xF) == 0 )
          {
            v23 = 18456;
            *v11 = 7;
          }
          v66 = v211;
          goto LABEL_513;
        }
        *v11 = 160;
        XEventReportLoginSubstepFailureEvent(
          v172,
          160,
          a6,
          v268,
          &v281,
          v206,
          (unsigned __int64)v198 >> 1,
          &szPassword,
          0);
LABEL_494:
        v69 = v211;
LABEL_495:
        ErrMsgsBase::Release(v69);
        goto LABEL_496;
      }
      v153 = !v152;
    }
    if ( v153 )
      goto LABEL_447;
    goto LABEL_448;
  }
  v33 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                          + SystemThread_TlsOffset)
                              + 112LL)
                  + 24LL);
  v293 = 0;
  v294 = 0;
  v295 = 0;
  v296 = 0;
  v297 = 0;
  v298 = 1;
  v299 = 0;
  v300 = 1;
  v301 = v33;
  v292 = &CDeferMsgsConnOut::`vftable';
  v302 = v32;
  v303 = 0;
  v34 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                              + SystemThread_TlsOffset)
                  + 112LL);
  v213 = 0;
  v214 = 0;
  v35 = *(void ****)(v34 + 24);
  if ( v35 != &v292 )
  {
    *(_QWORD *)&v213 = v34;
    *((_QWORD *)&v213 + 1) = v35;
    *(_QWORD *)&v214 = v293;
    *((_QWORD *)&v214 + 1) = &v292;
    v293 = v35;
    *(_QWORD *)(v34 + 24) = &v292;
  }
  if ( !byte_102EDCE4A || (v201 = 1, !byte_10308E752) )
    v201 = 0;
  if ( v274 )
  {
    v36 = dword_102F1BB98;
    v37 = (CDefaultCollation *)CDefaultCollation::PDCServer();
    v38 = v274;
    if ( !CDefaultCollation::FEqIgnoreCaseW(v37, v279, v274, L"master", v36) )
    {
      v199 = 0;
      if ( !getdbid(v279, v38, v207, 0) || FSystemDatabase(v279, v38, *v207, 1) )
      {
        *v207 = 0;
        BYTE2(v270) = 1;
        if ( byte_102EDCB21 )
        {
          if ( !*(_DWORD *)(GetXdbServerGlobals(v39) + 11976)
            && !(unsigned int)IsVDWFrontendInstance()
            && !FSystemDBName(v279, v38) )
          {
            memset_0(Str, 0, 0x20Au);
            v229 = 0;
            if ( !getdbid(L"master", dword_102F1BB98, &v229, 0) )
            {
              *(_DWORD *)a9 = 126;
              v42 = v213;
              if ( (_QWORD)v213 )
              {
                *(_QWORD *)(*(_QWORD *)(v213 + 24) + 8LL) = v214;
                *(_QWORD *)(v42 + 24) = *((_QWORD *)&v213 + 1);
                v213 = 0;
                v214 = 0;
              }
              v292 = &CConnectionOutput::`vftable';
              goto LABEL_494;
            }
            if ( (int)GetRelativeWinfabServiceUri(v229, Str, 261) >= 0 )
            {
              v40 = -1;
              do
                ++v40;
              while ( Str[v40] );
              if ( (_DWORD)v40 && !wcsstr(Str, L"SQL.MasterDb") )
              {
                *(_DWORD *)a9 = 126;
                v41 = v213;
                if ( (_QWORD)v213 )
                {
                  *(_QWORD *)(*(_QWORD *)(v213 + 24) + 8LL) = v214;
                  *(_QWORD *)(v41 + 24) = *((_QWORD *)&v213 + 1);
                  v213 = 0;
                  v214 = 0;
                }
                v292 = &CConnectionOutput::`vftable';
                goto LABEL_494;
              }
            }
          }
        }
      }
      goto LABEL_76;
    }
  }
  v199 = 1;
  if ( getdbid(L"master", dword_102F1BB98, v207, 0) )
  {
LABEL_76:
    v23 = Login;
    goto LABEL_77;
  }
  *v207 = 0;
  v23 = Login;
  v196 = Login;
  if ( Login )
  {
    XEventReportLoginSubstepFailureEvent(40613, 83, 0, v268, &v281, v206, (unsigned __int64)v198 >> 1, &szPassword, 0);
    goto LABEL_78;
  }
  *(_DWORD *)a9 = 83;
  v23 = 40613;
  Login = 40613;
LABEL_77:
  v196 = v23;
LABEL_78:
  if ( a6 )
  {
    v46 = v233[0];
  }
  else
  {
    if ( v23 )
      goto LABEL_200;
    if ( Base_PublicGlobals::sm_invariantTscAvailable )
    {
      QueryPerformanceCounter(&PerformanceCount);
      QuadPart = (CSbTransportMgr *)PerformanceCount.QuadPart;
    }
    else
    {
      QuadPart = MEMORY[0x7FFE0008];
    }
    CNetConnection::GetLock(*(CNetConnection **)(v13 + 16));
    *(_QWORD *)(v13 + 864) = QuadPart;
    *(_DWORD *)(v13 + 880) = 1;
    v44 = *(_QWORD **)(*(_QWORD *)(v13 + 16) + 392LL);
    if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v45 = rand();
      if ( v45 == 5 * (v45 / 5) )
        Spinlock<114,16,258>::UpdateStatSnapshot();
    }
    *v44 = 0;
    try
    {
      ExcHandler::ExcHandler((ExcHandler *)v376, 0, 0, 0, (int (*)(int, int, int, int, char *))hdl_prntbackout, 0);
      Login = CCloudExtensions::DosGuard::CheckConnection(
                (const struct _GUID *)((char *)v216 + 776),
                *v207,
                &v307,
                v206,
                v198,
                (const wchar_t *)v216 + 388,
                *((_DWORD *)v216 + 243),
                a9);
      ExcHandler::~ExcHandler((ExcHandler *)v376);
    }
    catch ( SQLError v373 )
    {
      try
      {
        ExceptionBackout::ExceptionBackout((ExceptionBackout *)v315, (const struct SQLError *)v373);
        Login = 40613;
        *(_DWORD *)v212 = 115;
        ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v315);
      }
      catch ( ShortStackException )
      {
      }
      v13 = v283;
      v211 = v231;
      v204 = v219;
      *(_QWORD *)v226 = *(_QWORD *)v235;
      v46 = (int)v232;
      v215 = v221;
      FeatureExtension = v220;
      v11 = (int *)v212;
      goto LABEL_88;
    }
    v46 = v233[0];
LABEL_88:
    v47 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v48 = *(struct Worker **)(v47 + 256);
    if ( !v48 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v48 = *(struct Worker **)(v47 + 256);
    }
    if ( *((_DWORD *)v48 + 139) )
      ExceptionPostCatchActions(v48);
    if ( Base_PublicGlobals::sm_invariantTscAvailable )
    {
      QueryPerformanceCounter(&v249);
      v49 = (CSbTransportMgr *)v249.QuadPart;
    }
    else
    {
      v49 = MEMORY[0x7FFE0008];
    }
    CNetConnection::GetLock(*(CNetConnection **)(v13 + 16));
    if ( *(_DWORD *)(v13 + 880) )
    {
      v50 = *(_QWORD *)(v13 + 864);
      if ( (unsigned __int64)v49 > v50 )
        *(_QWORD *)(v13 + 872) += (char *)v49 - v50;
      *(_DWORD *)(v13 + 880) = 0;
    }
    v51 = *(_QWORD **)(*(_QWORD *)(v13 + 16) + 392LL);
    if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v52 = rand();
      if ( v52 == 5 * (v52 / 5) )
        Spinlock<114,16,258>::UpdateStatSnapshot();
    }
    *v51 = 0;
    v23 = Login;
    v196 = Login;
  }
  if ( v23 || !*v207 || !byte_102EDCB78 )
  {
LABEL_200:
    v80 = v216;
    if ( *(_BYTE *)(v13 + 1048) )
      goto LABEL_223;
    v81 = *((_DWORD *)v216 + 334);
    if ( *((_BYTE *)v216 + 1344) )
    {
      if ( v81 == 1 && *((_DWORD *)v216 + 335) == 2 )
        goto LABEL_223;
    }
    else if ( v81 == 1 )
    {
      goto LABEL_223;
    }
    v284 = 1;
    v272 = 1;
    v287[0] = SqlAzureIpAddress::ParseIpv4Address(
                (const wchar_t *)v216 + 388,
                (unsigned __int64)*((int *)v216 + 243) >> 1);
    v82 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v204 + 12) + 16LL))(*((_QWORD *)v204 + 12));
    v83 = v82;
    if ( (*(_BYTE *)(v82 + 512) & 1) == 0 )
    {
      v84 = *(_QWORD *)(v82 + 448);
      if ( v84 )
        SNI_Conn::AddEvent(v84, 80);
    }
    v86 = CCloudExtensions::CheckNetworkSecurityPerimeterAccess(
            *(const wchar_t **)(v13 + 1040),
            v287,
            &v281,
            v222[0],
            LOWORD(v222[1]),
            v206,
            v198,
            (const wchar_t *)v216 + 437,
            *((_DWORD *)v216 + 244),
            &v269,
            (enum ELoginFailedState *)&v284,
            v280,
            &v272);
    if ( (*(_BYTE *)(v83 + 512) & 1) == 0 )
    {
      v85 = *(_QWORD *)(v83 + 448);
      if ( v85 )
        SNI_Conn::AddEvent(v85, 81);
    }
    *(_BYTE *)(v13 + 1048) = 1;
    *(_DWORD *)(v13 + 1052) = v86;
    if ( v272 )
      *(_BYTE *)(v13 + 1056) = 1;
    v192 = !v269;
    if ( v280[0] )
    {
      if ( v269 )
        goto LABEL_223;
      if ( v23 )
        XEventReportLoginSubstepFailureEvent(
          v23,
          *v11,
          0,
          v268,
          &v281,
          v206,
          (unsigned __int64)v198 >> 1,
          &szPassword,
          0);
      v23 = v280[0];
      v196 = v280[0];
      Login = v280[0];
      *v11 = v284;
    }
    if ( !v269 )
    {
      v271 |= 0x1000000u;
      v87 = *(_QWORD *)(GetXdbServerGlobals(v85) + 20264);
      if ( v87 )
      {
        if ( (*(unsigned __int8 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v87 + 24LL))(v87, v287[0].S_un.S_addr) == 1 )
          v271 |= 0x10u;
      }
    }
LABEL_223:
    if ( v23 && !v208 || !v269 && v280[0] )
    {
      v25 = 0;
LABEL_410:
      v148 = v213;
      if ( (_QWORD)v213 )
      {
        *(_QWORD *)(*(_QWORD *)(v213 + 24) + 8LL) = v214;
        *(_QWORD *)(v148 + 24) = *((_QWORD *)&v213 + 1);
        v213 = 0;
        v214 = 0;
      }
      v292 = &CConnectionOutput::`vftable';
      v32 = v211;
      goto LABEL_413;
    }
    v217 = v23 != 0;
    SetSecuritySA(1);
    if ( *v207 && v269 )
    {
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&v245);
        v88 = (CSbTransportMgr *)v245.QuadPart;
      }
      else
      {
        v88 = MEMORY[0x7FFE0008];
      }
      CNetConnection::GetLock(*(CNetConnection **)(v13 + 16));
      *(_QWORD *)(v13 + 816) = v88;
      *(_DWORD *)(v13 + 832) = 1;
      v89 = *(_QWORD **)(*(_QWORD *)(v13 + 16) + 392LL);
      if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
      {
        v90 = rand();
        if ( v90 == 5 * (v90 / 5) )
          Spinlock<114,16,258>::UpdateStatSnapshot();
      }
      *v89 = 0;
      try
      {
        ExcHandler::ExcHandler((ExcHandler *)v371, 0, 0, 0, (int (*)(int, int, int, int, char *))hdl_prntbackout, 0);
        v224 = 1;
        v265 = NtCurrentTeb()->ThreadLocalStoragePointer;
        v91 = (_QWORD *)(v265[SystemThread_TlsIndex] + SystemThread_TlsOffset);
        v262 = v91;
        v263 = *v91;
        LOBYTE(v190) = *((_DWORD *)v80 + 272) != 0;
        LOBYTE(v189) = BYTE1(v270);
        LOBYTE(v183) = v268;
        LOBYTE(v91) = 1;
        v93 = CCloudExtensions::CheckFirewallRules(
                v263,
                v91,
                v222[0],
                LOWORD(v222[1]),
                v206,
                v198,
                (char *)v80 + 776,
                *((_DWORD *)v80 + 243),
                &v281,
                v183,
                &v224,
                &v277,
                &v271,
                (char *)v204 + 1188,
                (char *)v80 + 1096,
                v189,
                0,
                v190,
                *((_DWORD *)v80 + 271) != 0,
                *((_DWORD *)v80 + 270) != 0,
                1);
        v233[0] = v93;
        if ( v93 )
        {
          if ( *(_BYTE *)(GetXdbServerGlobals(v92) + 12005) )
          {
            v192 = 1;
          }
          else if ( v93 != 40615 )
          {
            if ( Login )
            {
              XEventReportLoginSubstepFailureEvent(
                v93,
                v224,
                0,
                v268,
                &v281,
                v206,
                (unsigned __int64)v198 >> 1,
                &szPassword,
                0);
            }
            else
            {
              Login = v93;
              *v11 = v224;
            }
          }
        }
        else
        {
          v192 = 1;
        }
        ExcHandler::~ExcHandler((ExcHandler *)v371);
      }
      catch ( SQLError v374 )
      {
        try
        {
          ExceptionBackout::ExceptionBackout((ExceptionBackout *)v317, (const struct SQLError *)v374);
          if ( Login )
          {
            XEventReportLoginSubstepFailureEvent(
              40613,
              128,
              0,
              v268,
              &v281,
              v206,
              (unsigned __int64)v198 >> 1,
              &szPassword,
              0);
          }
          else
          {
            *(_DWORD *)v212 = 128;
            Login = 40613;
          }
          ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v317);
        }
        catch ( ShortStackException )
        {
        }
        v13 = v283;
        v211 = v231;
        v204 = v219;
        v215 = v221;
        v11 = (int *)v212;
        v80 = v216;
      }
      v94 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v95 = *(struct Worker **)(v94 + 256);
      if ( !v95 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v95 = *(struct Worker **)(v94 + 256);
      }
      if ( *((_DWORD *)v95 + 139) )
        ExceptionPostCatchActions(v95);
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&v246);
        v96 = (CSbTransportMgr *)v246.QuadPart;
      }
      else
      {
        v96 = MEMORY[0x7FFE0008];
      }
      CNetConnection::GetLock(*(CNetConnection **)(v13 + 16));
      if ( *(_DWORD *)(v13 + 832) )
      {
        v97 = *(_QWORD *)(v13 + 816);
        if ( (unsigned __int64)v96 > v97 )
          *(_QWORD *)(v13 + 824) += (char *)v96 - v97;
        *(_DWORD *)(v13 + 832) = 0;
      }
      v98 = *(_QWORD **)(*(_QWORD *)(v13 + 16) + 392LL);
      if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
      {
        v99 = rand();
        if ( v99 == 5 * (v99 / 5) )
          Spinlock<114,16,258>::UpdateStatSnapshot();
      }
      *v98 = 0;
      v23 = Login;
      v196 = Login;
    }
    if ( !v23 && !(unsigned __int8)CConnectionChecker::Check(v311, 2) )
    {
      *v11 = 2;
      v23 = 26078;
      v196 = 26078;
      Login = 26078;
    }
    if ( v195 )
      v100 = (v271 & 0x101) == 257;
    else
      v100 = v277 == 0;
    v101 = v100;
    v209[1] = v101;
    v102 = v200 && *((_DWORD *)v80 + 272);
    if ( v23 && (v208 != 2 || !v102 && v192 && v101) || !v269 && v280[0] )
      goto LABEL_405;
    v103 = v23;
    LODWORD(v220) = v23;
    v226[0] = *v11;
    if ( !v199 && !v201 )
    {
      if ( v268 && v192 )
      {
        if ( !v23 )
        {
LABEL_405:
          v25 = v197;
LABEL_406:
          XDBDecodeRoleMemberships(v282, &v225, &v203, &v210, v273);
          if ( !v268 || v217 )
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)v204 + 13) + 264LL) + 216LL))(*(_QWORD *)(*((_QWORD *)v204 + 13) + 264LL));
          else
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)v204 + 13) + 264LL) + 304LL))(*(_QWORD *)(*((_QWORD *)v204 + 13) + 264LL));
          goto LABEL_410;
        }
      }
      else if ( !v23 )
      {
        goto LABEL_290;
      }
      v104 = *((_DWORD *)v80 + 243);
      v219 = 0;
      if ( !SqlAzureIpAddress::TryParse((const wchar_t *)v80 + 388, v104 >> 1, &v219) )
      {
        operator delete(v219, 0x18u);
        goto LABEL_290;
      }
      v109 = *(_QWORD *)(GetXdbServerGlobals(v105) + 19552);
      v255 = 4195473;
      v256 = 0;
      v258 = 0;
      v257 = 0;
      v259 = 0;
      v110 = v109 + 8;
      v236 = v109 + 8;
      v237 = 0;
      if ( (unsigned int)SOS_RWLock::GetLock(v109 + 8, 1, 1000, &v255) )
      {
        v112 = -2;
      }
      else
      {
        v237 = 1;
        v111 = SEHashTable<IPAddrInFirewallCache::IPAddrInFirewallCacheEntry,SqlAzureIpAddress,0,16,DefBaseAllocator>::Lookup(
                 v109 + 40,
                 v219);
        if ( v111
          && (!Base_PublicGlobals::sm_invariantTscAvailable
            ? (CSbTransportMgr *)(v113 = MEMORY[0x7FFE0008], v23 = Login, v196 = Login, v110 = v236)
            : (QueryPerformanceCounter(&v247), v113 = (CSbTransportMgr *)v247.QuadPart),
              (__int64)(*(_QWORD *)(v111 + 40) - (_QWORD)v113) >= 0) )
        {
          if ( *(_BYTE *)(v111 + 48) )
          {
            SOS_RWLock::ReleaseLock(v110, 1);
            v237 = 0;
            v112 = 1;
          }
          else
          {
            SOS_RWLock::ReleaseLock(v110, 1);
            v237 = 0;
            v112 = -1;
          }
        }
        else
        {
          SOS_RWLock::ReleaseLock(v110, 1);
          v237 = 0;
          v112 = 0;
        }
      }
      operator delete(v219, 0x18u);
      if ( v112 == -1 )
      {
        v25 = 0;
        v114 = v220;
      }
      else
      {
        if ( v112 != 1 )
        {
LABEL_290:
          v106 = 0;
          if ( *(_DWORD *)(qword_102ECFB00 + 14504)
            && (byte_102EDCC61 || (*((_BYTE *)qword_102ECFB10 + 1559) & 8) != 0)
            && CGlobalBabylonPolicyProvider::FRBACEnabled() )
          {
            v106 = ExternalCheckConnectSrvPerm(v215, v273, *v207);
            _InterlockedExchange((volatile __int32 *)v204 + 1271, v106);
            v23 = Login;
          }
          v107 = v273;
          LODWORD(v253) = 0;
          *((_QWORD *)&v253 + 1) = 0;
          LOWORD(v254) = 0;
          v308[1] = v215;
          v108 = (ErrMsgsBase *)operator new(0x28u, v215, "sql\\ntdbms\\include\\xodbcwrapper.h", 91, 3u);
          v251 = v108;
          if ( v108 )
          {
            *(_OWORD *)v108 = v253;
            *((_QWORD *)v108 + 2) = v254;
            *((_DWORD *)v108 + 6) = 0;
            *((_WORD *)v108 + 14) = 0;
          }
          else
          {
            v108 = 0;
          }
          v308[0] = v108;
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v248);
            v115 = (CSbTransportMgr *)v248.QuadPart;
          }
          else
          {
            v115 = MEMORY[0x7FFE0008];
            v23 = Login;
          }
          CNetConnection::GetLock(*(CNetConnection **)(v13 + 16));
          *(_QWORD *)(v13 + 888) = v115;
          *(_DWORD *)(v13 + 904) = 1;
          v116 = *(_QWORD **)(*(_QWORD *)(v13 + 16) + 392LL);
          if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
          {
            v117 = rand();
            if ( v117 == 5 * (v117 / 5) )
              Spinlock<114,16,258>::UpdateStatSnapshot();
          }
          *v116 = 0;
          v118 = v268 || v23;
          v191 = v106;
          LOBYTE(v190) = v192;
          LOBYTE(v187) = *((_DWORD *)v216 + 272) != 0;
          LOBYTE(v186) = v118;
          LOBYTE(v185) = a6;
          v119 = v204;
          v23 = CAutoOdbcConnectionWrapper::AuthenticateAgainstLogicalMasterOrAuthCache(
                  v308,
                  Source,
                  (unsigned int)DestinationSize,
                  *((_QWORD *)v204 + 26),
                  v222[0],
                  LOWORD(v222[1]),
                  v206,
                  v198,
                  (char *)v216 + 874,
                  (char *)v216 + 776,
                  *((_DWORD *)v216 + 243),
                  (_DWORD)v185,
                  v186,
                  v187,
                  &v307,
                  &v281,
                  (char *)&v270 + 2,
                  v190,
                  v311,
                  Destination,
                  &v267,
                  &v270,
                  &v282,
                  v11,
                  (char *)&v270 + 3,
                  &v277,
                  &v271,
                  &v286,
                  (char *)&v270 + 1,
                  v275,
                  (char *)v204 + 1188,
                  v202,
                  v266,
                  v238,
                  v228,
                  *((_DWORD *)v216 + 271) != 0,
                  *((_DWORD *)v216 + 270) != 0,
                  v191,
                  v107);
          v196 = v23;
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v234);
            v120 = (CSbTransportMgr *)v234.QuadPart;
          }
          else
          {
            v120 = MEMORY[0x7FFE0008];
            v196 = v23;
          }
          CNetConnection::GetLock(*(CNetConnection **)(v13 + 16));
          if ( *(_DWORD *)(v13 + 904) )
          {
            v121 = *(_QWORD *)(v13 + 888);
            if ( (unsigned __int64)v120 > v121 )
              *(_QWORD *)(v13 + 896) += (char *)v120 - v121;
            *(_DWORD *)(v13 + 904) = 0;
          }
          v122 = *(_QWORD **)(*(_QWORD *)(v13 + 16) + 392LL);
          if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
          {
            v123 = rand();
            if ( v123 == 5 * (v123 / 5) )
              Spinlock<114,16,258>::UpdateStatSnapshot();
          }
          *v122 = 0;
          if ( byte_102EDCE2D && (*((_BYTE *)qword_102ECFB10 + 1294) & 2) == 0 )
            *((_WORD *)v119 + 593) = v275[0];
          *((_DWORD *)v119 + 1272) = v286;
          v114 = v220;
          if ( !v23 && !(_DWORD)v220 && !(unsigned __int8)CConnectionChecker::Check(v311, 5) )
          {
            *v11 = 5;
            v23 = 26078;
            v196 = 26078;
          }
          if ( v195 )
          {
            if ( (v271 & 0x101) != 0x101 )
              goto LABEL_342;
          }
          else if ( v277 )
          {
LABEL_342:
            v124 = 0;
            goto LABEL_343;
          }
          v124 = 1;
LABEL_343:
          v25 = v23 != 40615 && v124;
          if ( v208 == 2 && (v114 || !v25) )
          {
            v125 = *((_DWORD *)v216 + 243);
            v221 = 0;
            if ( SqlAzureIpAddress::TryParse((const wchar_t *)v216 + 388, v125 >> 1, &v221) )
            {
              v127 = GetXdbServerGlobals(v126);
              IPAddrInFirewallCache::Update(*(IPAddrInFirewallCache **)(v127 + 19552), v221, v25);
            }
            operator delete(v221, 0x18u);
          }
          operator delete(v308[0], 0x28u);
          goto LABEL_356;
        }
        v25 = 1;
        v114 = v220;
      }
LABEL_356:
      if ( v114 )
      {
        v23 = v114;
        v196 = v114;
        *v11 = v226[0];
      }
      goto LABEL_406;
    }
    LODWORD(v283) = 0;
    v276[0] = 0;
    try
    {
      ExcHandler::ExcHandler((ExcHandler *)v372, 0, 0, 0, (int (*)(int, int, int, int, char *))hdl_prntbackout, 0);
      v128 = 0;
      v227 = 0;
      if ( *(_DWORD *)(qword_102ECFB00 + 14504)
        && (byte_102EDCC61 || (*((_BYTE *)qword_102ECFB10 + 1559) & 8) != 0 ? (v129 = 1) : (v129 = 0),
            v129 && CGlobalBabylonPolicyProvider::FRBACEnabled()) )
      {
        v130 = v273;
        v264 = v273;
        MasterDbId = GetMasterDbId();
        v227 = ExternalCheckConnectSrvPerm(v215, v130, MasterDbId);
        v132 = v204;
        _InterlockedExchange((volatile __int32 *)v204 + 1271, v227);
        v23 = Login;
        v128 = v227;
      }
      else
      {
        v132 = v204;
      }
      v133 = v268 || v23;
      v209[0] = v133;
      LOBYTE(v188) = v192;
      LOBYTE(v184) = a6;
      v134 = CCloudExtensions::AuthenticateLogin(
               Source,
               (unsigned int)DestinationSize,
               *((_QWORD *)v132 + 26),
               v222[0],
               LOWORD(v222[1]),
               &szPassword,
               0,
               (char *)v80 + 776,
               *((_DWORD *)v80 + 243),
               &v281,
               v184,
               v209,
               &v307,
               v276,
               v188,
               Destination,
               &v267,
               &v283,
               &v270,
               &v282,
               v11,
               (char *)&v270 + 3,
               &v277,
               &v271,
               *((_DWORD *)v80 + 272) != 0,
               (char *)&v270 + 1,
               v275,
               (char *)v132 + 1188,
               0,
               v202,
               v266,
               0,
               0,
               *((_DWORD *)v80 + 271) != 0,
               *((_DWORD *)v80 + 270) != 0,
               v128,
               v273);
      v194 = v134;
      if ( byte_102EDCE2D && (*((_BYTE *)qword_102ECFB10 + 1294) & 2) == 0 )
        *((_WORD *)v132 + 593) = v275[0];
      if ( v195 )
      {
        if ( (v271 & 0x101) != 0x101 )
          goto LABEL_380;
      }
      else if ( v277 )
      {
LABEL_380:
        v136 = 0;
        goto LABEL_381;
      }
      v136 = 1;
LABEL_381:
      v137 = v134 != 40615 && v136;
      v197 = v137;
      if ( v103 )
      {
        v194 = v103;
        *v11 = v226[0];
      }
      else if ( v134 )
      {
        if ( v134 != 40615 )
        {
          v234.QuadPart = 0x8000000001LL;
          if ( (qword_102F21DB4 & 0x80u) != 0LL )
          {
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v132 + 12) + 16LL))(*((_QWORD *)v132 + 12));
            XeCloudPkg::login_substep_failure::login_substep_failure((XeCloudPkg::login_substep_failure *)v377);
            v379 = v134;
            v380 = *v11;
            v381 = 0;
            v382 = v268;
            v138 = v378;
            v378[2] = &v281;
            *((_DWORD *)v138 + 6) = 16;
            *((_WORD *)v138 + 14) = 4;
            *((_WORD *)v138 + 15) = 0;
            v139 = v378;
            v378[4] = &szPassword;
            *((_DWORD *)v139 + 10) = 0;
            *((_WORD *)v139 + 22) = 5;
            *((_WORD *)v139 + 23) = 0;
            v140 = GetXdbServerGlobals(5);
            v142 = -1;
            do
              ++v142;
            while ( *(_WORD *)(v140 + 2 * v142) );
            v143 = GetXdbServerGlobals(v141);
            v144 = v378;
            v378[6] = v143;
            *((_DWORD *)v144 + 14) = 2 * v142;
            *((_WORD *)v144 + 30) = 6;
            *((_WORD *)v144 + 31) = 0;
            v145 = v378;
            v378[8] = v206;
            *((_DWORD *)v145 + 18) = 2 * ((unsigned __int64)v198 >> 1);
            *((_WORD *)v145 + 38) = 7;
            *((_WORD *)v145 + 39) = 0;
            XeCloudPkg::login_substep_failure::Publish((XeCloudPkg::login_substep_failure *)v377);
          }
        }
      }
      ExcHandler::~ExcHandler((ExcHandler *)v372);
    }
    catch ( SQLError v375 )
    {
      try
      {
        ExceptionBackout::ExceptionBackout((ExceptionBackout *)&v306, (const struct SQLError *)v375);
        if ( !(_DWORD)v220 )
        {
          v194 = 40613;
          *(_DWORD *)v212 = 115;
        }
        ExceptionBackout::~ExceptionBackout((ExceptionBackout *)&v306);
      }
      catch ( ShortStackException )
      {
      }
      v211 = v231;
      v204 = v219;
      v215 = v221;
      v11 = (int *)v212;
    }
    v146 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v147 = *(struct Worker **)(v146 + 256);
    if ( !v147 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v147 = *(struct Worker **)(v146 + 256);
    }
    if ( *((_DWORD *)v147 + 139) )
      ExceptionPostCatchActions(v147);
    v23 = v194;
    v196 = v194;
    if ( !v194 )
    {
      if ( v199 )
        *v207 = v283;
      if ( !(unsigned __int8)CConnectionChecker::Check(v311, 3) )
      {
        *v11 = 3;
        v23 = 26078;
        v196 = 26078;
      }
    }
    goto LABEL_405;
  }
  v288 = 0;
  v289 = 0;
  v290 = 0;
  if ( Base_PublicGlobals::sm_invariantTscAvailable )
  {
    QueryPerformanceCounter(&v244);
    v53 = (CSbTransportMgr *)v244.QuadPart;
  }
  else
  {
    v53 = MEMORY[0x7FFE0008];
    v23 = Login;
  }
  CNetConnection::GetLock(*(CNetConnection **)(v13 + 16));
  *(_QWORD *)(v13 + 912) = v53;
  *(_DWORD *)(v13 + 928) = 1;
  v54 = *(_QWORD **)(*(_QWORD *)(v13 + 16) + 392LL);
  if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
  {
    v55 = rand();
    if ( v55 == 5 * (v55 / 5) )
      Spinlock<114,16,258>::UpdateStatSnapshot();
  }
  *v54 = 0;
  try
  {
    ExcHandler::ExcHandler((ExcHandler *)v370, 0, 0, 0, (int (*)(int, int, int, int, char *))hdl_prntbackout, 0);
    if ( byte_102EDCD1A )
    {
      v304 = 0;
      v305 = 0;
      v56 = v207;
      AutoOpenDB::Open((AutoOpenDB *)&v304, 0, *v207, 0x4000u, 0);
      if ( !v304 )
      {
        LogSystemMetadata(
          L"login error - Open DB failed for DB name: %.*ls id: %u\n",
          (unsigned __int64)v198 >> 1,
          v206,
          *v207);
        v23 = 40613;
        Login = 40613;
        *v11 = 127;
      }
      if ( v304 )
        AutoOpenDB::CloseDB((AutoOpenDB *)&v304);
      if ( v23 )
        goto LABEL_123;
    }
    else
    {
      v56 = v207;
    }
    LOBYTE(v188) = *(_DWORD *)(v13 + 988) <= 1u;
    LODWORD(v185) = *v56;
    Login = FindLogin(
              v46,
              v226[0],
              a5,
              (int)&v288,
              (enum ELoginFailedState *)v11,
              (__int64)&v289,
              0,
              0,
              (__int64)&v289 + 4,
              0,
              (__int64)&v290,
              (__int64)v185,
              (__int64)&v270,
              (__int64)v311,
              v188,
              (__int64)&v278,
              (__int64)&v273,
              (__int64)&v291);
LABEL_123:
    ExcHandler::~ExcHandler((ExcHandler *)v370);
  }
  catch ( SQLError v309 )
  {
    try
    {
      ExceptionBackout::ExceptionBackout((ExceptionBackout *)v316, (const struct SQLError *)&v309);
      si128 = v309;
      v176 = v310;
      v240 = v310;
      v177 = v212;
      *(_DWORD *)v212 = 129;
      if ( v176 == 1 )
        v178 = v309.m128i_i32[0];
      else
        v178 = v309.m128i_u16[0];
      LODWORD(v232) = v178;
      if ( v178 != 40839 )
      {
        if ( v178 == 40863 )
        {
          *(_DWORD *)v177 = 137;
          v178 = 18456;
          v230 = 18456;
          goto LABEL_526;
        }
        if ( v178 != 40981 )
        {
          v178 = 40613;
          v230 = 40613;
LABEL_526:
          Login = v178;
          ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v316);
          goto LABEL_564;
        }
      }
      v230 = v178;
      goto LABEL_526;
    }
    catch ( ShortStackException )
    {
    }
LABEL_564:
    v13 = v283;
    v57 = v231;
    v211 = v231;
    v204 = v219;
    v215 = v221;
    FeatureExtension = v220;
    v11 = (int *)v212;
    goto LABEL_125;
  }
  v57 = v211;
LABEL_125:
  v58 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v59 = *(struct Worker **)(v58 + 256);
  if ( !v59 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v59 = *(struct Worker **)(v58 + 256);
  }
  if ( *((_DWORD *)v59 + 139) )
    ExceptionPostCatchActions(v59);
  if ( Base_PublicGlobals::sm_invariantTscAvailable )
  {
    QueryPerformanceCounter(&v242);
    v60 = (CSbTransportMgr *)v242.QuadPart;
  }
  else
  {
    v60 = MEMORY[0x7FFE0008];
  }
  CNetConnection::GetLock(*(CNetConnection **)(v13 + 16));
  if ( *(_DWORD *)(v13 + 928) )
  {
    v61 = *(_QWORD *)(v13 + 912);
    if ( (unsigned __int64)v60 > v61 )
      *(_QWORD *)(v13 + 920) += (char *)v60 - v61;
    *(_DWORD *)(v13 + 928) = 0;
  }
  v62 = *(_QWORD **)(*(_QWORD *)(v13 + 16) + 392LL);
  if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
  {
    v63 = rand();
    if ( v63 == 5 * (v63 / 5) )
      Spinlock<114,16,258>::UpdateStatSnapshot();
  }
  *v62 = 0;
  v23 = Login;
  v196 = Login;
  if ( !Login || (v64 = *v11, (unsigned int)(*v11 - 65) <= 1) || a7 )
  {
    v268 = 1;
    if ( *v11 != 138 )
    {
      if ( !Login )
      {
        if ( FeatureExtension )
        {
          if ( *v207 )
          {
            if ( FControlNodeDwShellDb() )
            {
              if ( byte_102EDCBDD )
              {
                v285 = 0;
                v77 = *((_QWORD *)v204 + 13);
                if ( v77 )
                {
                  v78 = *(_QWORD *)(v77 + 264);
                  if ( v78 )
                  {
                    v79 = (const unsigned __int8 *)(*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v78 + 408LL))(
                                                     v78,
                                                     &v285);
                    if ( v285 )
                    {
                      v235[0] = v285;
                      v192 = (unsigned int)CCloudExtensions::FIsLoginUserMemberOfDBRole(
                                             (const struct CCompExecCtxtBasic *)L"db_exporter",
                                             v79,
                                             v235,
                                             *v207,
                                             L"db_exporter",
                                             0x16u) != 0;
                    }
                  }
                }
              }
            }
          }
        }
      }
      goto LABEL_159;
    }
    v75 = v213;
    if ( (_QWORD)v213 )
    {
      *(_QWORD *)(*(_QWORD *)(v213 + 24) + 8LL) = v214;
      *(_QWORD *)(v75 + 24) = *((_QWORD *)&v213 + 1);
      v213 = 0;
      v214 = 0;
    }
    v292 = &CPassThroughConn::`vftable';
    goto LABEL_184;
  }
  if ( !byte_102EDCA60 || !*(_DWORD *)(qword_102ECFB00 + 14504) || v64 != 170 || Login != 47087 && Login != 18456 )
  {
    if ( !FeatureExtension )
    {
      if ( byte_102EDCD1A )
      {
        wcscpy(v392, L"Contained authentication failed with error: %d (major: %d, minor: %d)");
        memset_0(v393, 0, sizeof(v393));
        v243 = 0;
        v241 = 0;
        v71 = si128.m128i_i32[0];
        if ( v240 != 1 )
          v71 = si128.m128i_u16[0];
        LODWORD(v181) = si128.m128i_i32[0] % 100;
        LODWORD(v180) = si128.m128i_i32[0] / 100;
        v179[0] = v71;
        if ( (int)StringCchPrintfExW(v393, 0x100u, &v241, &v243, 0, v392, *(_QWORD *)v179, v180, v181) >= 0 )
        {
          v73 = -1;
          do
            ++v73;
          while ( v393[v73] );
          v182 = v73;
          v72 = v393;
        }
        else
        {
          v182 = 79;
          v72 = (wchar_t *)L"Contained authentication failed with error (failed to format inner error code)";
        }
        XEventReportLoginSubstepFailureEvent(
          Login,
          **(_DWORD **)&v287[0].S_un.S_un_b.s_b1,
          0,
          v268,
          &v281,
          v206,
          (unsigned __int64)v198 >> 1,
          v72,
          v182);
        if ( Login == 40613 )
        {
          v74 = v213;
          if ( (_QWORD)v213 )
          {
            *(_QWORD *)(*(_QWORD *)(v213 + 24) + 8LL) = v214;
            *(_QWORD *)(v74 + 24) = *((_QWORD *)&v213 + 1);
            v213 = 0;
            v214 = 0;
          }
          v292 = &CConnectionOutput::`vftable';
          v69 = v57;
          goto LABEL_495;
        }
      }
      goto LABEL_158;
    }
    v67 = v273;
    if ( v273 && Login == 18456 && (v64 == 62 || v64 == 189) && (byte_102EDCBFE || byte_102EDCC3D) )
    {
      v267 = *((_DWORD *)v273 + 5);
      memcpy_s(Destination, 0x55u, (char *)v273 + *((unsigned int *)v273 + 6), (int)v267);
      LODWORD(DestinationSize) = *((_DWORD *)v67 + 4);
      Source = (char *)v67 + *((unsigned int *)v67 + 3);
LABEL_158:
      v23 = 0;
      v196 = 0;
      Login = 0;
      goto LABEL_159;
    }
    v268 = 1;
    if ( v64 != 138 )
    {
LABEL_159:
      if ( byte_102EDCB21 && v23 == 40613 )
      {
        *v11 = 127;
        v68 = v213;
        if ( (_QWORD)v213 )
        {
          *(_QWORD *)(*(_QWORD *)(v213 + 24) + 8LL) = v214;
          *(_QWORD *)(v68 + 24) = *((_QWORD *)&v213 + 1);
          v213 = 0;
          v214 = 0;
        }
        v292 = &CConnectionOutput::`vftable';
        v69 = v57;
        goto LABEL_495;
      }
      if ( !v23 && !(unsigned __int8)CConnectionChecker::Check(v311, 1) )
      {
        *v11 = 1;
        v23 = 26078;
        v196 = 26078;
        Login = 26078;
      }
      goto LABEL_200;
    }
    v70 = v213;
    if ( (_QWORD)v213 )
    {
      *(_QWORD *)(*(_QWORD *)(v213 + 24) + 8LL) = v214;
      *(_QWORD *)(v70 + 24) = *((_QWORD *)&v213 + 1);
      v213 = 0;
      v214 = 0;
    }
    v292 = &CPassThroughConn::`vftable';
LABEL_184:
    v292 = &CConnectionOutput::`vftable';
    ErrMsgsBase::Release(v57);
    goto LABEL_185;
  }
  XEventReportLoginSubstepFailureEvent(Login, 170, 0, v268, &v281, v206, (unsigned __int64)v198 >> 1, &szPassword, 0);
  v65 = v213;
  if ( (_QWORD)v213 )
  {
    *(_QWORD *)(*(_QWORD *)(v213 + 24) + 8LL) = v214;
    *(_QWORD *)(v65 + 24) = *((_QWORD *)&v213 + 1);
    v213 = 0;
    v214 = 0;
  }
  v292 = &CConnectionOutput::`vftable';
  v66 = v57;
LABEL_513:
  ErrMsgsBase::Release(v66);
  operator delete[](v273);
  v175 = (void *)v278;
  if ( v278 )
  {
    operator delete[](*(void **)(v278 + 16));
    operator delete(v175, 0x18u);
  }
  return v23;
}

```

## disassembly

```asm
0x100f23ba0  push    rbx
0x100f23ba2  push    rsi
0x100f23ba3  push    rdi
0x100f23ba4  push    r12
0x100f23ba6  push    r13
0x100f23ba8  push    r14
0x100f23baa  push    r15
0x100f23bac  mov     eax, 1310h
0x100f23bb1  call    _alloca_probe
0x100f23bb6  sub     rsp, rax
0x100f23bb9  mov     [rsp+1348h+var_1028], 0FFFFFFFFFFFFFFFEh
0x100f23bc5  mov     rax, cs:__security_cookie
0x100f23bcc  xor     rax, rsp
0x100f23bcf  mov     [rsp+1348h+var_48], rax
0x100f23bd7  mov     rax, r9
0x100f23bda  mov     qword ptr [rsp+1348h+var_1138], rax
0x100f23be2  mov     r15, r8
0x100f23be5  mov     [rsp+1348h+var_11E8], r8
0x100f23bed  mov     rbx, rdx
0x100f23bf0  mov     qword ptr [rsp+1348h+var_1110], rdx
0x100f23bf8  mov     [rsp+1348h+var_1190], rcx
0x100f23c00  mov     [rsp+1348h+var_1160], rcx
0x100f23c08  mov     [rsp+1348h+var_1118], rdx
0x100f23c10  mov     [rsp+1348h+var_1170], r8
0x100f23c18  mov     qword ptr [rsp+1348h+var_1100], rax
0x100f23c20  mov     r12, [rsp+1348h+arg_38]
0x100f23c28  mov     [rsp+1348h+var_11D0], r12
0x100f23c30  mov     r13, [rsp+1348h+arg_40]
0x100f23c38  mov     [rsp+1348h+var_11B8], r13
0x100f23c40  mov     qword ptr [rsp+1348h+var_F78.S_un], r13
0x100f23c48  mov     rcx, [r8+60h]
0x100f23c4c  mov     rax, [rcx]
0x100f23c4f  call    qword ptr [rax+10h]
0x100f23c52  mov     rdi, rax
0x100f23c55  mov     [rsp+1348h+var_1188], rax
0x100f23c5d  mov     r14, [r15+60h]
0x100f23c61  mov     [rsp+1348h+var_F90], r14
0x100f23c69  movups  xmm0, xmmword ptr [rbx+1Ch]
0x100f23c6d  movaps  xmmword ptr [rsp+1348h+var_FA8.Data1], xmm0
0x100f23c75  xor     esi, esi
0x100f23c77  mov     [r12], esi
0x100f23c7b  mov     [rsp+1348h+var_F80], esi
0x100f23c82  cmp     cs:byte_102EDCC1E, sil
0x100f23c89  jz      short loc_100F23CBB
0x100f23c8b  mov     edx, cs:dword_102EF3E14; int
0x100f23c91  mov     rcx, rbx; this
0x100f23c94  call    ?CmpTlsVersion@SNI_Conn@@QEAAHH@Z; SNI_Conn::CmpTlsVersion(int)
0x100f23c99  test    eax, eax
0x100f23c9b  jns     short loc_100F23CBB
0x100f23c9d  lea     rcx, aXElfinvalidtls; "x_elfInvalidTlsVersion 171"
0x100f23ca4  call    ?log_unlocalized@@YAXPEB_WZZ; log_unlocalized(wchar_t const *,...)
0x100f23ca9  mov     dword ptr [r13+0], 0ABh
0x100f23cb1  mov     eax, 4818h
0x100f23cb6  jmp     loc_100F2739A
0x100f23cbb  cmp     [rdi+438h], esi
0x100f23cc1  jz      short loc_100F23CE7
0x100f23cc3  cmp     cs:byte_102EDCE2B, sil
0x100f23cca  jz      short loc_100F23CD5
0x100f23ccc  cmp     byte ptr cs:dword_102EF4364+3, sil
0x100f23cd3  jnz     short loc_100F23D13
0x100f23cd5  mov     dword ptr [r13+0], 0B7h
0x100f23cdd  mov     eax, 9EA5h
0x100f23ce2  jmp     loc_100F2739A
0x100f23ce7  cmp     [rdi+43Ch], esi
0x100f23ced  jz      short loc_100F23D13
0x100f23cef  cmp     cs:byte_102EDCE2A, sil
0x100f23cf6  jz      short loc_100F23D01
0x100f23cf8  cmp     byte ptr cs:dword_102EF4364+3, sil
0x100f23cff  jnz     short loc_100F23D13
0x100f23d01  mov     dword ptr [r13+0], 0B8h
0x100f23d09  mov     eax, 9EA5h
0x100f23d0e  jmp     loc_100F2739A
0x100f23d13  lea     rdx, [rsp+1348h+var_FA8]; struct _GUID *
0x100f23d1b  mov     rcx, r15; struct CSession *
0x100f23d1e  call    ?FSetContextInfoXdb@@YAXPEAVCSession@@PEBU_GUID@@@Z; FSetContextInfoXdb(CSession *,_GUID const *)
0x100f23d23  xorps   xmm0, xmm0
0x100f23d26  movups  xmmword ptr [rsp+1348h+var_1158], xmm0
0x100f23d2e  call    cs:__imp_GetXdbServerGlobals
0x100f23d34  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x100f23d3b  nop     dword ptr [rax+rax+00h]
0x100f23d40  inc     rcx
0x100f23d43  cmp     [rax+rcx*2], si
0x100f23d47  jnz     short loc_100F23D40
0x100f23d49  add     rcx, rcx
0x100f23d4c  mov     word ptr [rsp+1348h+var_1158+8], cx
0x100f23d54  call    cs:__imp_GetXdbServerGlobals
0x100f23d5a  mov     [rsp+1348h+var_1158], rax
0x100f23d62  mov     rax, [r15+0C0h]
0x100f23d69  test    rax, rax
0x100f23d6c  jz      short loc_100F23D8C
0x100f23d6e  movzx   edx, word ptr [rax+46h]
0x100f23d72  add     edx, edx
0x100f23d74  mov     [rsp+1348h+var_11F4], edx
0x100f23d7b  movzx   ecx, word ptr [rax+44h]
0x100f23d7f  add     rcx, rax
0x100f23d82  mov     [rsp+1348h+var_11D8], rcx
0x100f23d8a  jmp     short loc_100F23D94
0x100f23d8c  mov     [rsp+1348h+var_11D8], rsi
0x100f23d94  cmp     [rdi+3CCh], esi
0x100f23d9a  jnz     short loc_100F23DBA
0x100f23d9c  lea     rcx, aXElfretrieveip; "x_elfRetrieveIpAddressFailed 81"
0x100f23da3  call    ?log_unlocalized@@YAXPEB_WZZ; log_unlocalized(wchar_t const *,...)
0x100f23da8  mov     dword ptr [r13+0], 51h ; 'Q'
0x100f23db0  mov     eax, 0A483h
0x100f23db5  jmp     loc_100F2739A
0x100f23dba  mov     [rsp+1348h+var_FD8], esi
0x100f23dc1  test    rax, rax
0x100f23dc4  jz      short loc_100F23DE4
0x100f23dc6  movzx   ecx, word ptr [rax+46h]
0x100f23dca  add     ecx, ecx
0x100f23dcc  mov     [rsp+1348h+var_FD8], ecx
0x100f23dd3  movzx   ecx, word ptr [rax+44h]
0x100f23dd7  add     rcx, rax
0x100f23dda  mov     [rsp+1348h+var_FC0], rcx
0x100f23de2  jmp     short loc_100F23DEC
0x100f23de4  mov     [rsp+1348h+var_FC0], rsi
0x100f23dec  mov     rdx, gs:58h
0x100f23df5  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100f23dfc  mov     ecx, [rax]
0x100f23dfe  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100f23e05  mov     eax, [rax]
0x100f23e07  add     rax, [rdx+rcx*8]
0x100f23e0b  mov     rax, [rax]
0x100f23e0e  mov     rcx, [rax+48h]
0x100f23e12  mov     dl, 2
0x100f23e14  mov     rcx, [rcx+60h]
0x100f23e18  call    ?GetFeatureExtension@CPhysicalConnection@@QEBAPEAVCFeatureExtension@@W4EFeatureExtensionId@@@Z; CPhysicalConnection::GetFeatureExtension(EFeatureExtensionId)
0x100f23e1d  mov     r15, rax
0x100f23e20  mov     [rsp+1348h+var_1168], rax
0x100f23e28  mov     [rsp+1348h+var_1080], rax
0x100f23e30  test    rax, rax
0x100f23e33  setnz   [rsp+1348h+var_11ED]
0x100f23e3b  mov     edi, esi
0x100f23e3d  mov     [rsp+1348h+var_11FC], esi
0x100f23e44  mov     [rsp+1348h+var_1204], esi
0x100f23e4b  movdqa  xmm0, cs:__xmm@00000000ffffffffffffffff00000000
0x100f23e53  movdqu  [rsp+1348h+var_10E0], xmm0
0x100f23e5c  mov     [rsp+1348h+var_10D0], esi
0x100f23e63  xorps   xmm1, xmm1
0x100f23e66  xor     eax, eax
0x100f23e68  movups  [rsp+1348h+Destination], xmm1
0x100f23e70  movups  [rsp+1348h+var_588], xmm1
0x100f23e78  movups  [rsp+1348h+var_578], xmm1
0x100f23e80  movups  [rsp+1348h+var_568], xmm1
0x100f23e88  movups  [rsp+1348h+var_558], xmm1
0x100f23e90  mov     [rsp+1348h+var_548], eax
0x100f23e97  mov     [rsp+1348h+var_544], al
0x100f23e9e  mov     [rsp+1348h+var_FF4], esi
0x100f23ea5  mov     byte ptr [rsp+1348h+var_FEE], al
0x100f23eac  mov     [rsp+1348h+var_11EC], al
0x100f23eb3  mov     [rsp+1348h+var_11C2], al
0x100f23eba  mov     [rsp+1348h+var_F98], esi
0x100f23ec1  mov     [rsp+1348h+var_1140], esi
0x100f23ec8  movups  xmm0, xmmword ptr cs:?sm_val@?$Zero@ULocaleEntry@?$XE_StaticPackage@$0L@@@@@2ULocaleEntry@?$XE_StaticPackage@$0L@@@B.Data1; XE_StaticPackage<11>::LocaleEntry const Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val ...
0x100f23ecf  movups  xmmword ptr [rsp+1348h+var_ED8.Data1], xmm0
0x100f23ed7  mov     byte ptr [rsp+1348h+var_FEE+2], al
0x100f23ede  mov     byte ptr [rsp+1348h+var_FEE+3], 1
0x100f23ee6  mov     [rsp+1348h+var_FF8], al
0x100f23eed  mov     [rsp+1348h+var_1208], al
0x100f23ef4  call    cs:__imp_GetXdbServerGlobals
0x100f23efa  mov     eax, [rax+4CACh]
0x100f23f00  mov     [rsp+1348h+var_11C8], eax
0x100f23f07  xor     r12b, r12b
0x100f23f0a  mov     [rsp+1348h+var_11F8], r12b
0x100f23f12  movzx   eax, cs:byte_102EDCEE6
0x100f23f19  mov     [rsp+1348h+var_1200], al
0x100f23f20  mov     [rsp+1348h+var_FCC], 0FFFFFFFFh
0x100f23f2b  mov     dword ptr [rsp+1348h+var_FEE+6], esi
0x100f23f32  cmp     cs:byte_102EDCF3B, sil
0x100f23f39  setnz   [rsp+1348h+var_11EF]
0x100f23f41  mov     byte ptr [rsp+1348h+var_FEE+1], sil
0x100f23f49  mov     [rsp+1348h+var_FD4], si
0x100f23f51  mov     [rsp+1348h+var_FC8], rsi
0x100f23f59  mov     [rsp+1348h+var_FE0], rsi
0x100f23f61  mov     dword ptr [rsp+1348h+var_F64+4], esi
0x100f23f68  mov     rax, qword ptr [rsp+1348h+var_1138]
0x100f23f70  mov     [rsp+1348h+Source], rax
0x100f23f78  mov     eax, [rsp+1348h+arg_20]
0x100f23f7f  mov     dword ptr [rsp+1348h+DestinationSize], eax
0x100f23f86  mov     [rsp+1348h+var_10E8], rsi
0x100f23f8e  mov     [rsp+1348h+var_112C], esi
0x100f23f95  mov     [rsp+1348h+var_FEF], 1
0x100f23f9d  mov     [rsp+1348h+var_FB8], esi
0x100f23fa4  call    ?IsFidoDWFrontEndSession@@YA_NXZ; IsFidoDWFrontEndSession(void)
0x100f23fa9  test    al, al
0x100f23fab  jz      short loc_100F2401D
0x100f23fad  cmp     cs:byte_102EDCED7, r12b
0x100f23fb4  jz      short loc_100F2401D
0x100f23fb6  call    cs:__imp_GetXdbServerGlobals
0x100f23fbc  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x100f23fc3  nop     dword ptr [rax+00h]
0x100f23fc7  nop     word ptr [rax+rax+00000000h]
0x100f23fd0  inc     rcx
0x100f23fd3  cmp     word ptr [rax+rcx*2+30FAh], 0
0x100f23fdc  jnz     short loc_100F23FD0
0x100f23fde  add     rcx, rcx
0x100f23fe1  mov     [rsp+1348h+var_112C], ecx
0x100f23fe8  test    ecx, ecx
0x100f23fea  jle     short loc_100F24002
0x100f23fec  call    cs:__imp_GetXdbServerGlobals
0x100f23ff2  add     rax, 30FAh
0x100f23ff8  mov     [rsp+1348h+var_10E8], rax
0x100f24000  jmp     short loc_100F2401D
0x100f24002  mov     dword ptr [r13+0], 0B0h
0x100f2400a  mov     edi, 9EA5h
0x100f2400f  mov     [rsp+1348h+var_11FC], edi
0x100f24016  mov     [rsp+1348h+var_1204], edi
0x100f2401d  test    r15, r15
0x100f24020  jnz     short loc_100F2406F
0x100f24022  cmp     [rsp+1348h+arg_20], r15d
0x100f2402a  jnz     short loc_100F24042
0x100f2402c  mov     edi, 4818h
0x100f24031  mov     [rsp+1348h+var_1204], edi
0x100f24038  mov     dword ptr [r13+0], 7Ah ; 'z'
0x100f24040  jmp     short loc_100F24068
0x100f24042  mov     rax, [rsp+1348h+var_11E8]
0x100f2404a  cmp     qword ptr [rax+0D0h], 0
0x100f24052  jnz     short loc_100F2406F
0x100f24054  mov     edi, 4818h
0x100f24059  mov     [rsp+1348h+var_1204], edi
0x100f24060  mov     dword ptr [r13+0], 7Ch ; '|'
0x100f24068  mov     [rsp+1348h+var_11FC], edi
0x100f2406f  mov     [rsp+1348h+var_FF0], 0
0x100f24077  cmp     [rsp+1348h+arg_28], 0
0x100f2407f  jz      loc_100F241D4
0x100f24085  test    dword ptr cs:qword_102F21DB4, 200h
0x100f2408f  jz      loc_100F241D4
0x100f24095  mov     [rsp+1348h+var_BA0], 50000h
0x100f240a0  mov     [rsp+1348h+var_B98], esi
0x100f240a7  lea     rax, [rsp+1348h+var_B78]
0x100f240af  mov     [rsp+1348h+var_B90], rax
0x100f240b7  lea     rax, [rsp+1348h+var_B28]
0x100f240bf  mov     [rsp+1348h+var_B88], rax
0x100f240c7  mov     [rsp+1348h+var_958], rsi
0x100f240cf  mov     [rsp+1348h+var_B80], rsi
0x100f240d7  mov     [rsp+1348h+var_950], rsi
0x100f240df  lea     rax, [rsp+1348h+var_948]
0x100f240e7  mov     [rsp+1348h+var_B78], rax
0x100f240ef  mov     [rsp+1348h+var_B70], 21h ; '!'
0x100f240fa  mov     [rsp+1348h+var_B6C], 4
0x100f24105  movzx   eax, [rsp+1348h+arg_30]
0x100f2410d  mov     [rsp+1348h+var_948], al
0x100f24114  lea     rax, [rsp+1348h+var_FA8]
0x100f2411c  mov     [rsp+1348h+var_B68], rax
0x100f24124  mov     [rsp+1348h+var_B60], 10h
0x100f2412f  mov     [rsp+1348h+var_B5C], 1
0x100f2413a  mov     rax, [rsp+1348h+var_1188]
0x100f24142  mov     ecx, [rax+3D0h]
0x100f24148  add     rax, 36Ah
0x100f2414e  mov     [rsp+1348h+var_B38], rax
0x100f24156  and     ecx, 0FFFFFFFEh
0x100f24159  mov     [rsp+1348h+var_B30], ecx
0x100f24160  mov     [rsp+1348h+var_B2C], 4
0x100f2416b  movzx   ecx, word ptr [rsp+1348h+var_1158+8]
0x100f24173  mov     rax, [rsp+1348h+var_1158]
0x100f2417b  mov     [rsp+1348h+var_B58], rax
0x100f24183  and     ecx, 0FFFFFFFEh
0x100f24186  mov     [rsp+1348h+var_B50], ecx
0x100f2418d  mov     [rsp+1348h+var_B4C], 2
0x100f24198  movsxd  rax, [rsp+1348h+var_11F4]
0x100f241a0  shr     rax, 1
0x100f241a3  mov     rcx, [rsp+1348h+var_11D8]
0x100f241ab  mov     [rsp+1348h+var_B48], rcx
0x100f241b3  add     eax, eax
0x100f241b5  mov     [rsp+1348h+var_B40], eax
0x100f241bc  mov     [rsp+1348h+var_B3C], 3
0x100f241c7  lea     rcx, [rsp+1348h+var_BA8]; this
0x100f241cf  call    ?Publish@re_login@XeCloudPkg@@QEAAXXZ; XeCloudPkg::re_login::Publish(void)
0x100f241d4  lea     rax, ??_7CConnectionChecker@@6B@; const CConnectionChecker::`vftable'
0x100f241db  mov     [rsp+1348h+var_EA0], rax
0x100f241e3  mov     [rsp+1348h+var_E98], rbx
0x100f241eb  mov     rax, [rsp+1348h+var_11E8]
0x100f241f3  mov     [rsp+1348h+var_E90], rax
0x100f241fb  movzx   eax, [rsp+1348h+arg_28]
0x100f24203  mov     [rsp+1348h+var_E88], al
0x100f2420a  lea     rax, [rsp+1348h+var_FF0]
0x100f24212  mov     [rsp+1348h+var_E80], rax
0x100f2421a  movups  xmm0, xmmword ptr [rsp+1348h+var_1158]
0x100f24222  movups  [rsp+1348h+var_E78], xmm0
0x100f2422a  xor     edx, edx
0x100f2422c  lea     rcx, [rsp+1348h+var_EA0]
0x100f24234  call    ?Check@CConnectionChecker@@UEBA_NW4EClientDisconnectLoginPhase@@@Z; CConnectionChecker::Check(EClientDisconnectLoginPhase)
0x100f24239  test    al, al
0x100f2423b  jnz     short loc_100F24246
0x100f2423d  mov     [r13+0], esi
0x100f24241  jmp     loc_100F25321
0x100f24246  mov     [rsp+1348h+var_1180], 50Fh
0x100f24251  mov     byte ptr [rsp+1348h+var_1320], 3
0x100f24256  mov     dword ptr [rsp+1348h+var_1328], 50Fh
0x100f2425e  lea     r9, aSqlNtdbmsMsqlO_11; "sql\\ntdbms\\msql\\ods\\login.cpp"
0x100f24265  mov     r8d, 1
0x100f2426b  mov     rdx, [rsp+1348h+var_1190]
0x100f24273  lea     ecx, [r8+1Fh]
0x100f24277  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x100f2427d  mov     rbx, rax
0x100f24280  mov     [rsp+1348h+var_11C0], rax
0x100f24288  mov     [rsp+1348h+var_1078], rax
0x100f24290  test    rax, rax
0x100f24293  jz      short loc_100F242AC
0x100f24295  mov     rdx, [rsp+1348h+var_1190]
  ... truncated ...
```
