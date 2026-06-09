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
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 XdbServerGlobals; // rax
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rax
  _QWORD *ThreadLocalStoragePointer; // rdx
  __int64 v23; // rax
  __int64 FeatureExtension; // r15
  unsigned int v25; // edi
  __int64 v26; // rdx
  __int64 v27; // rcx
  bool v28; // r12
  __int64 v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // rax
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // rcx
  int v35; // ecx
  ErrMsgsBase *v36; // rax
  ErrMsgsBase *v37; // rbx
  __int64 v38; // rax
  __int64 v39; // rcx
  void ***v40; // rdx
  unsigned int v41; // ebx
  CDefaultCollation *v42; // rax
  int v43; // edi
  __int64 v44; // rdx
  __int64 v45; // rcx
  __int64 v46; // rax
  __int64 v47; // rdx
  __int64 v48; // rdx
  CSbTransportMgr *QuadPart; // rbx
  _QWORD *v50; // rbx
  int v51; // r8d
  int v52; // r12d
  __int64 v53; // rbx
  struct Worker *v54; // rcx
  CSbTransportMgr *v55; // rbx
  unsigned __int64 v56; // rax
  _QWORD *v57; // rbx
  int v58; // r8d
  CSbTransportMgr *v59; // rbx
  _QWORD *v60; // rbx
  int v61; // r8d
  unsigned int *v62; // rbx
  ErrMsgsBase *v63; // r12
  __int64 v64; // rbx
  struct Worker *v65; // rcx
  CSbTransportMgr *v66; // rbx
  unsigned __int64 v67; // rax
  _QWORD *v68; // rbx
  int v69; // r8d
  int v70; // ecx
  __int64 v71; // rdx
  ErrMsgsBase *v72; // rcx
  struct FederatedContext *v73; // rbx
  __int64 v74; // rdx
  ErrMsgsBase *v75; // rcx
  __int64 v76; // rdx
  __int32 v77; // ecx
  wchar_t *v78; // rax
  __int64 v79; // rax
  __int64 v80; // rdx
  __int64 v81; // rdx
  void *v82; // rbx
  __int64 v83; // rcx
  __int64 v84; // rcx
  const unsigned __int8 *v85; // rax
  struct CNetConnection *v86; // r12
  int v87; // eax
  __int64 v88; // rax
  __int64 v89; // rbx
  __int64 v90; // rcx
  __int64 v91; // rdx
  __int64 v92; // rcx
  int v93; // r15d
  __int64 v94; // rcx
  CSbTransportMgr *v95; // rbx
  _QWORD *v96; // rbx
  int v97; // r8d
  _QWORD *v98; // rdx
  __int64 v99; // rdx
  __int64 v100; // rcx
  int v101; // ebx
  __int64 v102; // rbx
  struct Worker *v103; // rcx
  CSbTransportMgr *v104; // rbx
  unsigned __int64 v105; // rax
  _QWORD *v106; // rbx
  int v107; // r8d
  bool v108; // zf
  char v109; // al
  bool v110; // cl
  unsigned int v111; // r15d
  unsigned int v112; // edx
  __int64 v113; // rdx
  __int64 v114; // rcx
  __int32 v115; // r15d
  struct FederatedContext *v116; // r12
  ErrMsgsBase *v117; // rax
  __int64 v118; // r15
  __int64 v119; // rbx
  __int64 v120; // r15
  int v121; // ebx
  CSbTransportMgr *v122; // rax
  unsigned int v123; // r14d
  CSbTransportMgr *v124; // rbx
  _QWORD *v125; // rbx
  int v126; // r8d
  bool v127; // r11
  struct CSession *v128; // r15
  CSbTransportMgr *v129; // rbx
  unsigned __int64 v130; // rax
  _QWORD *v131; // rbx
  int v132; // r8d
  char v133; // al
  unsigned int v134; // edx
  __int64 v135; // rdx
  __int64 v136; // rcx
  __int64 v137; // rax
  __int32 v138; // ebx
  char v139; // al
  struct FederatedContext *v140; // rbx
  unsigned __int16 MasterDbId; // ax
  struct CSession *v142; // r14
  bool v143; // al
  int v144; // ebx
  char v146; // al
  bool v147; // al
  _QWORD *v148; // rax
  _QWORD *v149; // rax
  __int64 v150; // rdx
  __int64 v151; // rax
  __int64 v152; // rdx
  __int64 v153; // rcx
  __int64 v154; // rbx
  __int64 v155; // rax
  _QWORD *v156; // rcx
  _QWORD *v157; // rcx
  __int64 v158; // rbx
  struct Worker *v159; // rcx
  __int64 v160; // rdx
  bool v161; // zf
  char v162; // al
  bool v163; // al
  bool v164; // cl
  bool v165; // zf
  const struct ErrMsg *NextErrMsg; // rbx
  int v167; // r12d
  ErrMsgsBase *v168; // rdi
  const wchar_t *Msg; // rax
  bool v170; // al
  struct ILoginToken *LoginTokenFromSid; // rbx
  char v172; // cl
  rsize_t v173; // r12
  unsigned __int64 v174; // rax
  wchar_t *v175; // rax
  wchar_t *v176; // r14
  void *v177; // rbx
  unsigned int v178; // ecx
  char *v179; // rcx
  DWORD TickCount; // eax
  struct CSession *v181; // rbx
  __int64 v182; // rax
  int v183; // eax
  int v184; // eax
  void *v185; // rbx
  unsigned int *v186; // rsi
  void *v187; // rbx
  int v188; // eax
  enum ELoginFailedState *v189; // r8
  int v190; // ecx
  int v191[2]; // [rsp+30h] [rbp-1318h]
  wchar_t *v192; // [rsp+38h] [rbp-1310h]
  __int64 v193; // [rsp+40h] [rbp-1308h]
  int v194; // [rsp+40h] [rbp-1308h]
  int v195; // [rsp+48h] [rbp-1300h]
  int v196; // [rsp+50h] [rbp-12F8h]
  unsigned int *v197; // [rsp+58h] [rbp-12F0h]
  int v198; // [rsp+60h] [rbp-12E8h]
  int v199; // [rsp+68h] [rbp-12E0h]
  __int64 v200; // [rsp+70h] [rbp-12D8h]
  int v201; // [rsp+78h] [rbp-12D0h]
  int v202; // [rsp+88h] [rbp-12C0h]
  __int32 v203; // [rsp+128h] [rbp-1220h]
  bool v204; // [rsp+140h] [rbp-1208h]
  unsigned int Login; // [rsp+144h] [rbp-1204h]
  int v206; // [rsp+144h] [rbp-1204h]
  char v207; // [rsp+148h] [rbp-1200h]
  unsigned int v208; // [rsp+14Ch] [rbp-11FCh]
  bool v209; // [rsp+150h] [rbp-11F8h]
  int v210; // [rsp+154h] [rbp-11F4h]
  char v211; // [rsp+158h] [rbp-11F0h]
  bool v212; // [rsp+159h] [rbp-11EFh]
  char v213; // [rsp+15Ah] [rbp-11EEh]
  bool v214; // [rsp+15Bh] [rbp-11EDh]
  bool v215; // [rsp+15Ch] [rbp-11ECh] BYREF
  struct CSession *v216; // [rsp+160h] [rbp-11E8h]
  rsize_t DestinationSize; // [rsp+168h] [rbp-11E0h]
  wchar_t *v218; // [rsp+170h] [rbp-11D8h]
  unsigned int *v219; // [rsp+178h] [rbp-11D0h]
  int v220; // [rsp+180h] [rbp-11C8h]
  _BYTE v221[2]; // [rsp+184h] [rbp-11C4h] BYREF
  bool v222; // [rsp+186h] [rbp-11C2h] BYREF
  ErrMsgsBase *v223; // [rsp+188h] [rbp-11C0h]
  enum ELoginFailedState *v224; // [rsp+190h] [rbp-11B8h]
  __int128 v225; // [rsp+198h] [rbp-11B0h]
  __int128 v226; // [rsp+1A8h] [rbp-11A0h]
  struct IMemObj *v227; // [rsp+1B8h] [rbp-1190h]
  struct CNetConnection *v228; // [rsp+1C0h] [rbp-1188h]
  int v229; // [rsp+1C8h] [rbp-1180h]
  void *Source; // [rsp+1D0h] [rbp-1178h]
  struct SqlAzureIpAddress *v231; // [rsp+1D8h] [rbp-1170h] BYREF
  __int64 v232; // [rsp+1E0h] [rbp-1168h]
  struct SqlAzureIpAddress *v233; // [rsp+1E8h] [rbp-1160h] BYREF
  wchar_t *v234[2]; // [rsp+1F0h] [rbp-1158h]
  int v236; // [rsp+204h] [rbp-1144h] BYREF
  int v237; // [rsp+208h] [rbp-1140h] BYREF
  int v238[2]; // [rsp+210h] [rbp-1138h]
  __int32 v239; // [rsp+218h] [rbp-1130h]
  int v240; // [rsp+21Ch] [rbp-112Ch]
  unsigned int v241; // [rsp+220h] [rbp-1128h] BYREF
  int v242; // [rsp+224h] [rbp-1124h]
  ErrMsgsBase *v243; // [rsp+228h] [rbp-1120h]
  struct SNI_Conn *v244; // [rsp+230h] [rbp-1118h]
  int v245[2]; // [rsp+238h] [rbp-1110h]
  LARGE_INTEGER v246; // [rsp+240h] [rbp-1108h] BYREF
  int v247[2]; // [rsp+248h] [rbp-1100h] BYREF
  __int64 v248; // [rsp+250h] [rbp-10F8h]
  int v249; // [rsp+258h] [rbp-10F0h]
  __int64 v250; // [rsp+260h] [rbp-10E8h]
  __m128i si128; // [rsp+268h] [rbp-10E0h]
  int v252; // [rsp+278h] [rbp-10D0h]
  wchar_t *v253; // [rsp+280h] [rbp-10C8h] BYREF
  LARGE_INTEGER v254; // [rsp+288h] [rbp-10C0h] BYREF
  unsigned __int64 v255; // [rsp+290h] [rbp-10B8h] BYREF
  LARGE_INTEGER v256; // [rsp+298h] [rbp-10B0h] BYREF
  LARGE_INTEGER v257; // [rsp+2A0h] [rbp-10A8h] BYREF
  LARGE_INTEGER v258; // [rsp+2A8h] [rbp-10A0h] BYREF
  LARGE_INTEGER v259; // [rsp+2B0h] [rbp-1098h] BYREF
  LARGE_INTEGER v260; // [rsp+2B8h] [rbp-1090h] BYREF
  LARGE_INTEGER v261; // [rsp+2C0h] [rbp-1088h] BYREF
  __int64 v262; // [rsp+2C8h] [rbp-1080h]
  ErrMsgsBase *v263; // [rsp+2D0h] [rbp-1078h]
  LARGE_INTEGER PerformanceCount; // [rsp+2D8h] [rbp-1070h] BYREF
  __int128 v265; // [rsp+2E0h] [rbp-1068h]
  __int64 v266; // [rsp+2F0h] [rbp-1058h]
  int v267; // [rsp+2F8h] [rbp-1050h] BYREF
  __int64 v268; // [rsp+300h] [rbp-1048h]
  __int64 v269; // [rsp+308h] [rbp-1040h]
  __int64 v270; // [rsp+310h] [rbp-1038h]
  __int64 v271; // [rsp+318h] [rbp-1030h]
  __int64 v272; // [rsp+320h] [rbp-1028h]
  ErrMsgsBase *v273; // [rsp+328h] [rbp-1020h]
  _QWORD *v274; // [rsp+330h] [rbp-1018h]
  __int64 v275; // [rsp+338h] [rbp-1010h]
  struct FederatedContext *v276; // [rsp+340h] [rbp-1008h]
  _QWORD *v277; // [rsp+348h] [rbp-1000h]
  _BYTE v278[4]; // [rsp+350h] [rbp-FF8h] BYREF
  unsigned int v279; // [rsp+354h] [rbp-FF4h] BYREF
  bool v280; // [rsp+358h] [rbp-FF0h] BYREF
  bool v281; // [rsp+359h] [rbp-FEFh] BYREF
  int v282; // [rsp+35Ah] [rbp-FEEh] BYREF
  int v283; // [rsp+360h] [rbp-FE8h] BYREF
  bool v284; // [rsp+364h] [rbp-FE4h] BYREF
  struct FederatedContext *v285; // [rsp+368h] [rbp-FE0h] BYREF
  int v286; // [rsp+370h] [rbp-FD8h] BYREF
  _WORD v287[2]; // [rsp+374h] [rbp-FD4h] BYREF
  char v288[4]; // [rsp+378h] [rbp-FD0h] BYREF
  int v289; // [rsp+37Ch] [rbp-FCCh] BYREF
  __int64 v290; // [rsp+380h] [rbp-FC8h] BYREF
  wchar_t *v291; // [rsp+388h] [rbp-FC0h] BYREF
  unsigned int v292[4]; // [rsp+390h] [rbp-FB8h] BYREF
  struct _GUID v293; // [rsp+3A0h] [rbp-FA8h] BYREF
  int v294; // [rsp+3B0h] [rbp-F98h] BYREF
  __int64 v295; // [rsp+3B8h] [rbp-F90h] BYREF
  int v296; // [rsp+3C0h] [rbp-F88h] BYREF
  int v297; // [rsp+3C4h] [rbp-F84h] BYREF
  int v298; // [rsp+3C8h] [rbp-F80h] BYREF
  struct in_addr v299[2]; // [rsp+3D0h] [rbp-F78h] BYREF
  int v300; // [rsp+3D8h] [rbp-F70h] BYREF
  __int64 v301; // [rsp+3DCh] [rbp-F6Ch] BYREF
  int v302; // [rsp+3E4h] [rbp-F64h] BYREF
  int v303; // [rsp+3E8h] [rbp-F60h] BYREF
  void **v304; // [rsp+3F0h] [rbp-F58h] BYREF
  void ***v305; // [rsp+3F8h] [rbp-F50h]
  int v306; // [rsp+400h] [rbp-F48h]
  __int64 v307; // [rsp+408h] [rbp-F40h]
  __int64 v308; // [rsp+410h] [rbp-F38h]
  int v309; // [rsp+418h] [rbp-F30h]
  int v310; // [rsp+41Ch] [rbp-F2Ch]
  __int64 v311; // [rsp+420h] [rbp-F28h]
  char v312; // [rsp+428h] [rbp-F20h]
  __int64 v313; // [rsp+430h] [rbp-F18h]
  ErrMsgsBase *v314; // [rsp+438h] [rbp-F10h]
  char v315; // [rsp+440h] [rbp-F08h]
  __int64 v316; // [rsp+450h] [rbp-EF8h] BYREF
  int v317; // [rsp+458h] [rbp-EF0h]
  struct _GUID v318; // [rsp+460h] [rbp-EE8h] BYREF
  struct _GUID v319; // [rsp+470h] [rbp-ED8h] BYREF
  void *v320[2]; // [rsp+480h] [rbp-EC8h] BYREF
  __m128i v321; // [rsp+490h] [rbp-EB8h] BYREF
  int v322; // [rsp+4A0h] [rbp-EA8h]
  __int64 v323[3]; // [rsp+4A8h] [rbp-EA0h] BYREF
  bool v324; // [rsp+4C0h] [rbp-E88h]
  bool *v325; // [rsp+4C8h] [rbp-E80h]
  __int128 v326; // [rsp+4D0h] [rbp-E78h]
  _BYTE v327[16]; // [rsp+4E0h] [rbp-E68h] BYREF
  _BYTE v328[16]; // [rsp+4F0h] [rbp-E58h] BYREF
  _BYTE v329[16]; // [rsp+500h] [rbp-E48h] BYREF
  char v330[8]; // [rsp+510h] [rbp-E38h] BYREF
  int v331; // [rsp+518h] [rbp-E30h]
  int v332; // [rsp+520h] [rbp-E28h]
  _DWORD **v333; // [rsp+528h] [rbp-E20h]
  char *v334; // [rsp+530h] [rbp-E18h]
  __int64 v335; // [rsp+538h] [rbp-E10h]
  _DWORD *v336; // [rsp+540h] [rbp-E08h] BYREF
  int v337; // [rsp+548h] [rbp-E00h]
  int v338; // [rsp+54Ch] [rbp-DFCh]
  GUID *v339; // [rsp+550h] [rbp-DF8h]
  int v340; // [rsp+558h] [rbp-DF0h]
  int v341; // [rsp+55Ch] [rbp-DECh]
  const wchar_t *v342; // [rsp+560h] [rbp-DE8h]
  int v343; // [rsp+568h] [rbp-DE0h]
  int v344; // [rsp+56Ch] [rbp-DDCh]
  wchar_t *v345; // [rsp+570h] [rbp-DD8h]
  int v346; // [rsp+578h] [rbp-DD0h]
  int v347; // [rsp+57Ch] [rbp-DCCh]
  wchar_t *v348; // [rsp+580h] [rbp-DC8h]
  int v349; // [rsp+588h] [rbp-DC0h]
  int v350; // [rsp+58Ch] [rbp-DBCh]
  char v351; // [rsp+590h] [rbp-DB8h] BYREF
  __int64 v352; // [rsp+760h] [rbp-BE8h]
  __int64 v353; // [rsp+768h] [rbp-BE0h]
  _DWORD v354[2]; // [rsp+770h] [rbp-BD8h] BYREF
  bool v355; // [rsp+778h] [rbp-BD0h]
  bool v356; // [rsp+779h] [rbp-BCFh]
  char v357[8]; // [rsp+7A0h] [rbp-BA8h] BYREF
  int v358; // [rsp+7A8h] [rbp-BA0h]
  int v359; // [rsp+7B0h] [rbp-B98h]
  bool **v360; // [rsp+7B8h] [rbp-B90h]
  char *v361; // [rsp+7C0h] [rbp-B88h]
  __int64 v362; // [rsp+7C8h] [rbp-B80h]
  bool *v363; // [rsp+7D0h] [rbp-B78h] BYREF
  int v364; // [rsp+7D8h] [rbp-B70h]
  int v365; // [rsp+7DCh] [rbp-B6Ch]
  struct _GUID *v366; // [rsp+7E0h] [rbp-B68h]
  int v367; // [rsp+7E8h] [rbp-B60h]
  int v368; // [rsp+7ECh] [rbp-B5Ch]
  wchar_t *v369; // [rsp+7F0h] [rbp-B58h]
  int v370; // [rsp+7F8h] [rbp-B50h]
  int v371; // [rsp+7FCh] [rbp-B4Ch]
  wchar_t *v372; // [rsp+800h] [rbp-B48h]
  int v373; // [rsp+808h] [rbp-B40h]
  int v374; // [rsp+80Ch] [rbp-B3Ch]
  char *v375; // [rsp+810h] [rbp-B38h]
  unsigned int v376; // [rsp+818h] [rbp-B30h]
  int v377; // [rsp+81Ch] [rbp-B2Ch]
  char v378; // [rsp+820h] [rbp-B28h] BYREF
  __int64 v379; // [rsp+9F0h] [rbp-958h]
  __int64 v380; // [rsp+9F8h] [rbp-950h]
  bool v381; // [rsp+A00h] [rbp-948h] BYREF
  _BYTE v382[40]; // [rsp+A30h] [rbp-918h] BYREF
  _BYTE v383[40]; // [rsp+A58h] [rbp-8F0h] BYREF
  _BYTE v384[40]; // [rsp+A80h] [rbp-8C8h] BYREF
  _BYTE v385[24]; // [rsp+AA8h] [rbp-8A0h] BYREF
  _BYTE v386[24]; // [rsp+AC0h] [rbp-888h] BYREF
  _BYTE v387[24]; // [rsp+AD8h] [rbp-870h] BYREF
  _BYTE v388[48]; // [rsp+AF0h] [rbp-858h] BYREF
  _BYTE v389[24]; // [rsp+B20h] [rbp-828h] BYREF
  _QWORD *v390; // [rsp+B38h] [rbp-810h]
  int v391; // [rsp+D80h] [rbp-5C8h]
  int v392; // [rsp+D84h] [rbp-5C4h]
  char v393; // [rsp+D88h] [rbp-5C0h]
  bool v394; // [rsp+D89h] [rbp-5BFh]
  _OWORD Destination[5]; // [rsp+DB0h] [rbp-598h] BYREF
  int v396; // [rsp+E00h] [rbp-548h]
  char v397; // [rsp+E04h] [rbp-544h]
  wchar_t v398[8]; // [rsp+E10h] [rbp-538h] BYREF
  __int128 v399; // [rsp+E20h] [rbp-528h]
  __int128 v400; // [rsp+E30h] [rbp-518h]
  __int128 v401; // [rsp+E40h] [rbp-508h]
  __int64 v402; // [rsp+E50h] [rbp-4F8h]
  __int16 v403; // [rsp+E58h] [rbp-4F0h]
  wchar_t v404[72]; // [rsp+E60h] [rbp-4E8h] BYREF
  wchar_t v405[256]; // [rsp+EF0h] [rbp-458h] BYREF
  wchar_t Str[264]; // [rsp+10F0h] [rbp-258h] BYREF

  v272 = -2;
  *(_QWORD *)v238 = a4;
  v216 = a3;
  *(_QWORD *)v245 = a2;
  v227 = a1;
  v233 = a1;
  v244 = a2;
  v231 = a3;
  *(_QWORD *)v247 = a4;
  v219 = a8;
  v11 = (int *)a9;
  v224 = a9;
  *(_QWORD *)&v299[0].S_un.S_un_b.s_b1 = a9;
  v12 = (struct CNetConnection *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)a3 + 12) + 16LL))(*((_QWORD *)a3 + 12));
  v228 = v12;
  v13 = *((_QWORD *)a3 + 12);
  v295 = v13;
  v293 = *(struct _GUID *)((char *)a2 + 28);
  *a8 = 0;
  v298 = 0;
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
  FSetContextInfoXdb(a3, &v293);
  *(_OWORD *)v234 = 0;
  XdbServerGlobals = GetXdbServerGlobals(v16, v15);
  v19 = -1;
  do
    ++v19;
  while ( *(_WORD *)(XdbServerGlobals + 2 * v19) );
  v20 = 2 * v19;
  LOWORD(v234[1]) = v20;
  v234[0] = (wchar_t *)GetXdbServerGlobals(v20, v18);
  v21 = *((_QWORD *)a3 + 24);
  if ( v21 )
  {
    v210 = 2 * *(unsigned __int16 *)(v21 + 70);
    v218 = (wchar_t *)(v21 + *(unsigned __int16 *)(v21 + 68));
  }
  else
  {
    v218 = 0;
  }
  if ( !*((_DWORD *)v12 + 243) )
  {
    log_unlocalized(L"x_elfRetrieveIpAddressFailed 81");
    *(_DWORD *)a9 = 81;
    return 42115;
  }
  v286 = 0;
  if ( v21 )
  {
    v286 = 2 * *(unsigned __int16 *)(v21 + 70);
    v291 = (wchar_t *)(v21 + *(unsigned __int16 *)(v21 + 68));
  }
  else
  {
    v291 = 0;
  }
  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  v23 = *(_QWORD *)(ThreadLocalStoragePointer[SystemThread_TlsIndex] + SystemThread_TlsOffset);
  LOBYTE(ThreadLocalStoragePointer) = 2;
  FeatureExtension = CPhysicalConnection::GetFeatureExtension(
                       *(_QWORD *)(*(_QWORD *)(v23 + 72) + 96LL),
                       ThreadLocalStoragePointer);
  v232 = FeatureExtension;
  v262 = FeatureExtension;
  v214 = FeatureExtension != 0;
  v25 = 0;
  v208 = 0;
  Login = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v252 = 0;
  memset(Destination, 0, sizeof(Destination));
  v396 = 0;
  v397 = 0;
  v279 = 0;
  v282 = 0x1000000;
  v215 = 0;
  v222 = 0;
  v294 = 0;
  v237 = 0;
  v319 = Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
  v278[0] = 0;
  v204 = 0;
  v220 = *(_DWORD *)(GetXdbServerGlobals(v27, v26) + 19628);
  v28 = 0;
  v209 = 0;
  v207 = byte_102EDCEE6;
  v289 = -1;
  v283 = 0;
  v212 = byte_102EDCF3B != 0;
  v287[0] = 0;
  v290 = 0;
  v285 = 0;
  v303 = 0;
  Source = *(void **)v238;
  LODWORD(DestinationSize) = a5;
  v250 = 0;
  v240 = 0;
  v281 = 1;
  v292[0] = 0;
  if ( IsFidoDWFrontEndSession() && byte_102EDCED7 )
  {
    v31 = GetXdbServerGlobals(v30, v29);
    v33 = -1;
    do
      ++v33;
    while ( *(_WORD *)(v31 + 2 * v33 + 12538) );
    v34 = 2 * v33;
    v240 = v34;
    if ( (int)v34 <= 0 )
    {
      *(_DWORD *)a9 = 176;
      v25 = 40613;
      v208 = 40613;
      Login = 40613;
    }
    else
    {
      v250 = GetXdbServerGlobals(v34, v32) + 12538;
    }
  }
  if ( !FeatureExtension )
  {
    if ( !a5 )
    {
      v25 = 18456;
      Login = 18456;
      *(_DWORD *)a9 = 122;
LABEL_34:
      v208 = 18456;
      goto LABEL_35;
    }
    if ( !*((_QWORD *)v216 + 26) )
    {
      v25 = 18456;
      Login = 18456;
      *(_DWORD *)a9 = 124;
      goto LABEL_34;
    }
  }
LABEL_35:
  v280 = 0;
  if ( a6 && (qword_102F21DB4 & 0x200) != 0 )
  {
    v358 = 327680;
    v359 = 0;
    v360 = &v363;
    v361 = &v378;
    v379 = 0;
    v362 = 0;
    v380 = 0;
    v363 = &v381;
    v364 = 33;
    v365 = 4;
    v381 = a7;
    v366 = &v293;
    v367 = 16;
    v368 = 1;
    v35 = *((_DWORD *)v228 + 244);
    v375 = (char *)v228 + 874;
    v376 = v35 & 0xFFFFFFFE;
    v377 = 4;
    v369 = v234[0];
    v370 = (__int64)v234[1] & 0xFFFE;
    v371 = 2;
    v372 = v218;
    v373 = 2 * ((unsigned __int64)v210 >> 1);
    v374 = 3;
    XeCloudPkg::re_login::Publish((XeCloudPkg::re_login *)v357);
  }
  v323[0] = (__int64)&CConnectionChecker::`vftable';
  v323[1] = (__int64)a2;
  v323[2] = (__int64)v216;
  v324 = a6;
  v325 = &v280;
  v326 = *(_OWORD *)v234;
  if ( !(unsigned __int8)CConnectionChecker::Check(v323, 0) )
  {
    *(_DWORD *)a9 = 0;
LABEL_185:
    operator delete[](v285);
    v82 = (void *)v290;
    if ( v290 )
    {
      operator delete[](*(void **)(v290 + 16));
      operator delete(v82, 0x18u);
    }
    return 26078;
  }
  v229 = 1295;
  v36 = (ErrMsgsBase *)operator new(0x20u, v227, 1, "sql\\ntdbms\\msql\\ods\\login.cpp", 1295, 3u);
  v37 = v36;
  v223 = v36;
  v263 = v36;
  if ( v36 )
  {
    ErrMsgsBase::ErrMsgsBase(v36, v227);
    *((_DWORD *)v37 + 6) = 0;
  }
  else
  {
    v37 = 0;
    v223 = 0;
  }
  v243 = v37;
  v273 = v37;
  if ( !v37 )
  {
    *(_DWORD *)a9 = 10;
LABEL_496:
    operator delete[](v285);
    v185 = (void *)v290;
    if ( v290 )
    {
      operator delete[](*(void **)(v290 + 16));
      operator delete(v185, 0x18u);
    }
    return 40613;
  }
  if ( v25 && !v220 )
  {
LABEL_413:
    if ( byte_102EDCF3D && BYTE1(v282) && v25 == 40914 )
    {
      v25 = 40532;
      v208 = 40532;
      goto LABEL_427;
    }
    if ( !*v219 )
    {
      if ( BYTE2(v282) )
      {
        if ( !v25 )
        {
          v25 = 18456;
          v208 = 18456;
          *v11 = 126;
          *(_OWORD *)v398 = 0;
          v399 = 0;
          v400 = 0;
          v401 = 0;
          v402 = 0;
          v403 = 0;
          GuidToString(&v293, v398, 0x4Au);
          v403 = 0;
          ex_callprint(4060, 11, 2, (unsigned int)v286, v291);
        }
        goto LABEL_427;
      }
      if ( !v25 || v25 == 40615 )
      {
        v25 = 40613;
        v208 = 40613;
        if ( HIBYTE(v282) )
          *v11 = 127;
        else
          *v11 = 134;
        goto LABEL_427;
      }
    }
    if ( !v25 )
      goto LABEL_448;
LABEL_427:
    if ( a6 )
      goto LABEL_448;
    if ( v207 )
      v161 = (v283 & 0x101) == 257;
    else
      v161 = v289 == 0;
    v162 = v161;
    v163 = v204 && v162;
    v164 = 0;
    if ( byte_102EDCBD5 )
      v164 = *v11 == 84;
    if ( v220 == 1 )
    {
      v165 = !v163;
    }
    else
    {
      if ( v220 != 2 )
      {
LABEL_447:
        CCloudExtensions::DosGuard::RegisterFailure(
          &v293,
          &v319,
          (char *)v228 + 776,
          *((unsigned int *)v228 + 243),
          v25,
          *v11);
        goto LABEL_448;
      }
      if ( v163 || v28 )
      {
LABEL_448:
        if ( (qword_102F21DB4 & 0x80u) != 0LL )
        {
          NextErrMsg = ErrMsgsBase::GetNextErrMsg(v37, 0);
          if ( NextErrMsg )
          {
            v167 = (__int64)v234[1] & 0xFFFE;
            v168 = v223;
            do
            {
              Msg = ErrMsg::GetMsg(NextErrMsg, &v286);
              v331 = 327680;
              v332 = 0;
              v333 = &v336;
              v334 = &v351;
              v352 = 0;
              v335 = 0;
              v353 = 0;
              v336 = v354;
              v337 = 42;
              v338 = 4;
              v339 = &Zero<XE_StaticPackage<11>::LocaleEntry>::sm_val;
              v340 = 16;
              v341 = 4;
              v342 = 0;
              v343 = 0;
              v344 = 5;
              v345 = 0;
              v346 = 0;
              v347 = 6;
              v348 = 0;
              v349 = 0;
              v350 = 7;
              v354[0] = *(unsigned __int16 *)NextErrMsg;
              v354[1] = *((_DWORD *)NextErrMsg + 3);
              v355 = a6;
              v356 = v280;
              v339 = &v293;
              v342 = Msg;
              v343 = 2 * v286;
              v345 = v234[0];
              v346 = v167;
              v348 = v218;
              v349 = 2 * ((unsigned __int64)v210 >> 1);
              XeCloudPkg::login_substep_failure::Publish((XeCloudPkg::login_substep_failure *)v330);
              NextErrMsg = ErrMsgsBase::GetNextErrMsg(v168, NextErrMsg);
            }
            while ( NextErrMsg );
            v25 = v208;
            v11 = (int *)v224;
          }
        }
        v170 = a6;
        if ( v207 && !a6 )
        {
          XEventReportFirewallCategorizationEvent(v228, &v293, v218, (unsigned __int64)v210 >> 1, v283, v25);
          v170 = 0;
        }
        if ( v25 )
          goto LABEL_483;
        if ( v280 )
        {
LABEL_474:
          TickCount = GetTickCount();
          v181 = v216;
          *((_DWORD *)v216 + 238) = TickCount;
          goto LABEL_484;
        }
        LoginTokenFromSid = 0;
        v224 = 0;
        v172 = v278[0];
        if ( v278[0] || v285 && byte_102EDCC3D )
        {
          if ( v262 )
          {
            if ( !v170 )
            {
              v182 = v290;
              if ( v290 )
              {
                if ( !*(_QWORD *)(v262 + 128) )
                {
                  v290 = 0;
                  *(_QWORD *)(v262 + 128) = v182;
                  v172 = v278[0];
                }
              }
            }
          }
          LOBYTE(v197) = v172;
          LoginTokenFromSid = (struct ILoginToken *)CreateLoginTokenFromSid(
                                                      Destination,
                                                      v279,
                                                      7,
                                                      0,
                                                      1,
                                                      Source,
                                                      DestinationSize,
                                                      4,
                                                      0,
                                                      0,
                                                      v237,
                                                      (_DWORD)v197,
                                                      v285);
          v224 = LoginTokenFromSid;
        }
        else
        {
          v173 = (unsigned int)DestinationSize;
          v174 = 2 * ((unsigned __int64)(unsigned int)DestinationSize >> 1);
          if ( !is_mul_ok((unsigned __int64)(unsigned int)DestinationSize >> 1, 2u) )
            v174 = -1;
          v175 = (wchar_t *)operator new[](v174, v227, 1, "sql\\ntdbms\\msql\\ods\\login.cpp", 2451, 3u);
          v176 = v175;
          v234[0] = v175;
          if ( v175 )
          {
            v177 = Source;
            memcpy_s(v175, v173, Source, v173);
            if ( (_BYTE)v282 )
            {
              v178 = 1;
            }
            else
            {
              v178 = 3;
              if ( v215 )
                v178 = 5;
            }
            LoginTokenFromSid = CreateLoginTokenForImpersonation(
                                  0,
                                  *v219,
                                  v177,
                                  (unsigned int)DestinationSize,
                                  1u,
                                  5u,
                                  0,
                                  0,
                                  (void (__fastcall ****)(_QWORD, __int64))v176,
                                  DestinationSize,
                                  0,
                                  0,
                                  v178,
                                  0,
                                  Destination,
                                  v279,
                                  v237);
            v224 = LoginTokenFromSid;
          }
          else
          {
            *v11 = 10;
            v25 = 40613;
          }
          operator delete(v176, 2u);
          if ( v25 )
            goto LABEL_471;
        }
        if ( !LoginTokenFromSid )
        {
          *v11 = 54;
          goto LABEL_494;
        }
LABEL_471:
        OverwriteLoginTokenBySidForSDS(*v219, LoginTokenFromSid);
        if ( LoginTokenFromSid )
        {
          v179 = (char *)LoginTokenFromSid + *(int *)(*((_QWORD *)LoginTokenFromSid + 2) + 4LL) + 16;
          (*(void (__fastcall **)(char *))(*(_QWORD *)v179 + 8LL))(v179);
        }
        if ( !v25 )
          goto LABEL_474;
LABEL_483:
        v181 = v216;
LABEL_484:
        if ( !*((_DWORD *)v228 + 272)
          || (!v212
           || !*((_BYTE *)v228 + 1344)
           || *((_DWORD *)v228 + 334) != 1
           || *((_DWORD *)v228 + 335) == 2
           || (v283 & 0x10000) != 0
            ? (v183 = *((_DWORD *)v228 + 279))
            : (v183 = *((_DWORD *)v228 + 321)),
              LODWORD(v291) = v183,
              (v184 = CNetConnection::SetEffectivePeerIPAddress(v228, (unsigned __int8 *)&v291, 4u)) == 0) )
        {
          v186 = v219;
          if ( byte_102EDCAD7 && !byte_102EDCADA )
          {
            v318 = v293;
            AuditLoginXdb(v219, v25, (unsigned int)*v11, &v318);
          }
          if ( byte_102EDCEE8 && !byte_102EDCEE7 && v25 != 40613 && v25 != 40969 && *v11 != 165 )
          {
            v318 = v293;
            CheckIfTdAuditSessionExists(v181, v186, &v318);
          }
          if ( *((_BYTE *)qword_102EF3550 + 555) && !v25 && (*((_BYTE *)v181 + 402) & 0xF) == 0 )
          {
            v25 = 18456;
            *v11 = 7;
          }
          v72 = v223;
          goto LABEL_513;
        }
        *v11 = 160;
        XEventReportLoginSubstepFailureEvent(
          v184,
          160,
          a6,
          v280,
          &v293,
          v218,
          (unsigned __int64)v210 >> 1,
          &szPassword,
          0);
LABEL_494:
        v75 = v223;
LABEL_495:
        ErrMsgsBase::Release(v75);
        goto LABEL_496;
      }
      v165 = !v164;
    }
    if ( v165 )
      goto LABEL_447;
    goto LABEL_448;
  }
  v38 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                          + SystemThread_TlsOffset)
                              + 112LL)
                  + 24LL);
  v305 = 0;
  v306 = 0;
  v307 = 0;
  v308 = 0;
  v309 = 0;
  v310 = 1;
  v311 = 0;
  v312 = 1;
  v313 = v38;
  v304 = &CDeferMsgsConnOut::`vftable';
  v314 = v37;
  v315 = 0;
  v39 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                              + SystemThread_TlsOffset)
                  + 112LL);
  v225 = 0;
  v226 = 0;
  v40 = *(void ****)(v39 + 24);
  if ( v40 != &v304 )
  {
    *(_QWORD *)&v225 = v39;
    *((_QWORD *)&v225 + 1) = v40;
    *(_QWORD *)&v226 = v305;
    *((_QWORD *)&v226 + 1) = &v304;
    v305 = v40;
    *(_QWORD *)(v39 + 24) = &v304;
  }
  if ( !byte_102EDCE4A || (v213 = 1, !byte_10308E752) )
    v213 = 0;
  if ( v286 )
  {
    v41 = dword_102F1BB98;
    v42 = (CDefaultCollation *)CDefaultCollation::PDCServer(v39);
    v43 = v286;
    if ( !CDefaultCollation::FEqIgnoreCaseW(v42, v291, v286, L"master", v41) )
    {
      v211 = 0;
      if ( !getdbid(v291, v43, v219, 0) || FSystemDatabase(v291, v43, *v219, 1) )
      {
        *v219 = 0;
        BYTE2(v282) = 1;
        if ( byte_102EDCB21 )
        {
          if ( !*(_DWORD *)(GetXdbServerGlobals(v45, v44) + 11976)
            && !(unsigned int)IsVDWFrontendInstance()
            && !FSystemDBName(v291, v43) )
          {
            memset_0(Str, 0, 0x20Au);
            v241 = 0;
            if ( !getdbid(L"master", dword_102F1BB98, &v241, 0) )
            {
              *(_DWORD *)a9 = 126;
              v48 = v225;
              if ( (_QWORD)v225 )
              {
                *(_QWORD *)(*(_QWORD *)(v225 + 24) + 8LL) = v226;
                *(_QWORD *)(v48 + 24) = *((_QWORD *)&v225 + 1);
                v225 = 0;
                v226 = 0;
              }
              v304 = &CConnectionOutput::`vftable';
              goto LABEL_494;
            }
            if ( (int)GetRelativeWinfabServiceUri(v241, Str, 261) >= 0 )
            {
              v46 = -1;
              do
                ++v46;
              while ( Str[v46] );
              if ( (_DWORD)v46 && !wcsstr(Str, L"SQL.MasterDb") )
              {
                *(_DWORD *)a9 = 126;
                v47 = v225;
                if ( (_QWORD)v225 )
                {
                  *(_QWORD *)(*(_QWORD *)(v225 + 24) + 8LL) = v226;
                  *(_QWORD *)(v47 + 24) = *((_QWORD *)&v225 + 1);
                  v225 = 0;
                  v226 = 0;
                }
                v304 = &CConnectionOutput::`vftable';
                goto LABEL_494;
              }
            }
          }
        }
      }
      goto LABEL_76;
    }
  }
  v211 = 1;
  if ( getdbid(L"master", dword_102F1BB98, v219, 0) )
  {
LABEL_76:
    v25 = Login;
    goto LABEL_77;
  }
  *v219 = 0;
  v25 = Login;
  v208 = Login;
  if ( Login )
  {
    XEventReportLoginSubstepFailureEvent(40613, 83, 0, v280, &v293, v218, (unsigned __int64)v210 >> 1, &szPassword, 0);
    goto LABEL_78;
  }
  *(_DWORD *)a9 = 83;
  v25 = 40613;
  Login = 40613;
LABEL_77:
  v208 = v25;
LABEL_78:
  if ( a6 )
  {
    v52 = v245[0];
  }
  else
  {
    if ( v25 )
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
    v50 = *(_QWORD **)(*(_QWORD *)(v13 + 16) + 392LL);
    if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v51 = rand();
      if ( v51 == 5 * (v51 / 5) )
        Spinlock<114,16,258>::UpdateStatSnapshot();
    }
    *v50 = 0;
    try
    {
      ExcHandler::ExcHandler((ExcHandler *)v388, 0, 0, 0, (int (*)(int, int, int, int, char *))hdl_prntbackout, 0);
      Login = CCloudExtensions::DosGuard::CheckConnection(
                (const struct _GUID *)((char *)v228 + 776),
                *v219,
                &v319,
                v218,
                v210,
                (const wchar_t *)v228 + 388,
                *((_DWORD *)v228 + 243),
                a9);
      ExcHandler::~ExcHandler((ExcHandler *)v388);
    }
    catch ( SQLError v385 )
    {
      try
      {
        ExceptionBackout::ExceptionBackout((ExceptionBackout *)v327, (const struct SQLError *)v385);
        Login = 40613;
        *(_DWORD *)v224 = 115;
        ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v327);
      }
      catch ( ShortStackException )
      {
      }
      v13 = v295;
      v223 = v243;
      v216 = v231;
      *(_QWORD *)v238 = *(_QWORD *)v247;
      v52 = (int)v244;
      v227 = v233;
      FeatureExtension = v232;
      v11 = (int *)v224;
      goto LABEL_88;
    }
    v52 = v245[0];
LABEL_88:
    v53 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v54 = *(struct Worker **)(v53 + 256);
    if ( !v54 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v54 = *(struct Worker **)(v53 + 256);
    }
    if ( *((_DWORD *)v54 + 139) )
      ExceptionPostCatchActions(v54);
    if ( Base_PublicGlobals::sm_invariantTscAvailable )
    {
      QueryPerformanceCounter(&v261);
      v55 = (CSbTransportMgr *)v261.QuadPart;
    }
    else
    {
      v55 = MEMORY[0x7FFE0008];
    }
    CNetConnection::GetLock(*(CNetConnection **)(v13 + 16));
    if ( *(_DWORD *)(v13 + 880) )
    {
      v56 = *(_QWORD *)(v13 + 864);
      if ( (unsigned __int64)v55 > v56 )
        *(_QWORD *)(v13 + 872) += (char *)v55 - v56;
      *(_DWORD *)(v13 + 880) = 0;
    }
    v57 = *(_QWORD **)(*(_QWORD *)(v13 + 16) + 392LL);
    if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
    {
      v58 = rand();
      if ( v58 == 5 * (v58 / 5) )
        Spinlock<114,16,258>::UpdateStatSnapshot();
    }
    *v57 = 0;
    v25 = Login;
    v208 = Login;
  }
  if ( v25 || !*v219 || !byte_102EDCB78 )
  {
LABEL_200:
    v86 = v228;
    if ( *(_BYTE *)(v13 + 1048) )
      goto LABEL_223;
    v87 = *((_DWORD *)v228 + 334);
    if ( *((_BYTE *)v228 + 1344) )
    {
      if ( v87 == 1 && *((_DWORD *)v228 + 335) == 2 )
        goto LABEL_223;
    }
    else if ( v87 == 1 )
    {
      goto LABEL_223;
    }
    v296 = 1;
    v284 = 1;
    v299[0] = SqlAzureIpAddress::ParseIpv4Address(
                (const wchar_t *)v228 + 388,
                (unsigned __int64)*((int *)v228 + 243) >> 1);
    v88 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v216 + 12) + 16LL))(*((_QWORD *)v216 + 12));
    v89 = v88;
    if ( (*(_BYTE *)(v88 + 512) & 1) == 0 )
    {
      v90 = *(_QWORD *)(v88 + 448);
      if ( v90 )
        SNI_Conn::AddEvent(v90, 80);
    }
    v93 = CCloudExtensions::CheckNetworkSecurityPerimeterAccess(
            *(const wchar_t **)(v13 + 1040),
            v299,
            &v293,
            v234[0],
            LOWORD(v234[1]),
            v218,
            v210,
            (const wchar_t *)v228 + 437,
            *((_DWORD *)v228 + 244),
            &v281,
            (enum ELoginFailedState *)&v296,
            v292,
            &v284);
    if ( (*(_BYTE *)(v89 + 512) & 1) == 0 )
    {
      v92 = *(_QWORD *)(v89 + 448);
      if ( v92 )
        SNI_Conn::AddEvent(v92, 81);
    }
    *(_BYTE *)(v13 + 1048) = 1;
    *(_DWORD *)(v13 + 1052) = v93;
    if ( v284 )
      *(_BYTE *)(v13 + 1056) = 1;
    v204 = !v281;
    if ( v292[0] )
    {
      if ( v281 )
        goto LABEL_223;
      if ( v25 )
        XEventReportLoginSubstepFailureEvent(
          v25,
          *v11,
          0,
          v280,
          &v293,
          v218,
          (unsigned __int64)v210 >> 1,
          &szPassword,
          0);
      v25 = v292[0];
      v208 = v292[0];
      Login = v292[0];
      *v11 = v296;
    }
    if ( !v281 )
    {
      v283 |= 0x1000000u;
      v94 = *(_QWORD *)(GetXdbServerGlobals(v92, v91) + 20264);
      if ( v94 )
      {
        if ( (*(unsigned __int8 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v94 + 24LL))(v94, v299[0].S_un.S_addr) == 1 )
          v283 |= 0x10u;
      }
    }
LABEL_223:
    if ( v25 && !v220 || !v281 && v292[0] )
    {
      v28 = 0;
LABEL_410:
      v160 = v225;
      if ( (_QWORD)v225 )
      {
        *(_QWORD *)(*(_QWORD *)(v225 + 24) + 8LL) = v226;
        *(_QWORD *)(v160 + 24) = *((_QWORD *)&v225 + 1);
        v225 = 0;
        v226 = 0;
      }
      v304 = &CConnectionOutput::`vftable';
      v37 = v223;
      goto LABEL_413;
    }
    v229 = v25 != 0;
    SetSecuritySA(1);
    if ( *v219 && v281 )
    {
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&v257);
        v95 = (CSbTransportMgr *)v257.QuadPart;
      }
      else
      {
        v95 = MEMORY[0x7FFE0008];
      }
      CNetConnection::GetLock(*(CNetConnection **)(v13 + 16));
      *(_QWORD *)(v13 + 816) = v95;
      *(_DWORD *)(v13 + 832) = 1;
      v96 = *(_QWORD **)(*(_QWORD *)(v13 + 16) + 392LL);
      if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
      {
        v97 = rand();
        if ( v97 == 5 * (v97 / 5) )
          Spinlock<114,16,258>::UpdateStatSnapshot();
      }
      *v96 = 0;
      try
      {
        ExcHandler::ExcHandler((ExcHandler *)v383, 0, 0, 0, (int (*)(int, int, int, int, char *))hdl_prntbackout, 0);
        v236 = 1;
        v277 = NtCurrentTeb()->ThreadLocalStoragePointer;
        v98 = (_QWORD *)(v277[SystemThread_TlsIndex] + SystemThread_TlsOffset);
        v274 = v98;
        v275 = *v98;
        LOBYTE(v202) = *((_DWORD *)v86 + 272) != 0;
        LOBYTE(v201) = BYTE1(v282);
        LOBYTE(v195) = v280;
        LOBYTE(v98) = 1;
        v101 = CCloudExtensions::CheckFirewallRules(
                 v275,
                 v98,
                 v234[0],
                 LOWORD(v234[1]),
                 v218,
                 v210,
                 (char *)v86 + 776,
                 *((_DWORD *)v86 + 243),
                 &v293,
                 v195,
                 &v236,
                 &v289,
                 &v283,
                 (char *)v216 + 1188,
                 (char *)v86 + 1096,
                 v201,
                 0,
                 v202,
                 *((_DWORD *)v86 + 271) != 0,
                 *((_DWORD *)v86 + 270) != 0,
                 1);
        v245[0] = v101;
        if ( v101 )
        {
          if ( *(_BYTE *)(GetXdbServerGlobals(v100, v99) + 12005) )
          {
            v204 = 1;
          }
          else if ( v101 != 40615 )
          {
            if ( Login )
            {
              XEventReportLoginSubstepFailureEvent(
                v101,
                v236,
                0,
                v280,
                &v293,
                v218,
                (unsigned __int64)v210 >> 1,
                &szPassword,
                0);
            }
            else
            {
              Login = v101;
              *v11 = v236;
            }
          }
        }
        else
        {
          v204 = 1;
        }
        ExcHandler::~ExcHandler((ExcHandler *)v383);
      }
      catch ( SQLError v386 )
      {
        try
        {
          ExceptionBackout::ExceptionBackout((ExceptionBackout *)v329, (const struct SQLError *)v386);
          if ( Login )
          {
            XEventReportLoginSubstepFailureEvent(
              40613,
              128,
              0,
              v280,
              &v293,
              v218,
              (unsigned __int64)v210 >> 1,
              &szPassword,
              0);
          }
          else
          {
            *(_DWORD *)v224 = 128;
            Login = 40613;
          }
          ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v329);
        }
        catch ( ShortStackException )
        {
        }
        v13 = v295;
        v223 = v243;
        v216 = v231;
        v227 = v233;
        v11 = (int *)v224;
        v86 = v228;
      }
      v102 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v103 = *(struct Worker **)(v102 + 256);
      if ( !v103 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v103 = *(struct Worker **)(v102 + 256);
      }
      if ( *((_DWORD *)v103 + 139) )
        ExceptionPostCatchActions(v103);
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&v258);
        v104 = (CSbTransportMgr *)v258.QuadPart;
      }
      else
      {
        v104 = MEMORY[0x7FFE0008];
      }
      CNetConnection::GetLock(*(CNetConnection **)(v13 + 16));
      if ( *(_DWORD *)(v13 + 832) )
      {
        v105 = *(_QWORD *)(v13 + 816);
        if ( (unsigned __int64)v104 > v105 )
          *(_QWORD *)(v13 + 824) += (char *)v104 - v105;
        *(_DWORD *)(v13 + 832) = 0;
      }
      v106 = *(_QWORD **)(*(_QWORD *)(v13 + 16) + 392LL);
      if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
      {
        v107 = rand();
        if ( v107 == 5 * (v107 / 5) )
          Spinlock<114,16,258>::UpdateStatSnapshot();
      }
      *v106 = 0;
      v25 = Login;
      v208 = Login;
    }
    if ( !v25 && !(unsigned __int8)CConnectionChecker::Check(v323, 2) )
    {
      *v11 = 2;
      v25 = 26078;
      v208 = 26078;
      Login = 26078;
    }
    if ( v207 )
      v108 = (v283 & 0x101) == 257;
    else
      v108 = v289 == 0;
    v109 = v108;
    v221[1] = v109;
    v110 = v212 && *((_DWORD *)v86 + 272);
    if ( v25 && (v220 != 2 || !v110 && v204 && v109) || !v281 && v292[0] )
      goto LABEL_405;
    v111 = v25;
    LODWORD(v232) = v25;
    v238[0] = *v11;
    if ( !v211 && !v213 )
    {
      if ( v280 && v204 )
      {
        if ( !v25 )
        {
LABEL_405:
          v28 = v209;
LABEL_406:
          XDBDecodeRoleMemberships(v294, &v237, &v215, &v222, v285);
          if ( !v280 || v229 )
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)v216 + 13) + 264LL) + 216LL))(*(_QWORD *)(*((_QWORD *)v216 + 13) + 264LL));
          else
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)v216 + 13) + 264LL) + 304LL))(*(_QWORD *)(*((_QWORD *)v216 + 13) + 264LL));
          goto LABEL_410;
        }
      }
      else if ( !v25 )
      {
        goto LABEL_290;
      }
      v112 = *((_DWORD *)v86 + 243);
      v231 = 0;
      if ( !SqlAzureIpAddress::TryParse((const wchar_t *)v86 + 388, v112 >> 1, &v231) )
      {
        operator delete(v231, 0x18u);
        goto LABEL_290;
      }
      v118 = *(_QWORD *)(GetXdbServerGlobals(v114, v113) + 19552);
      v267 = 4195473;
      v268 = 0;
      v270 = 0;
      v269 = 0;
      v271 = 0;
      v119 = v118 + 8;
      v248 = v118 + 8;
      v249 = 0;
      if ( (unsigned int)SOS_RWLock::GetLock(v118 + 8, 1, 1000, &v267) )
      {
        v121 = -2;
      }
      else
      {
        v249 = 1;
        v120 = SEHashTable<IPAddrInFirewallCache::IPAddrInFirewallCacheEntry,SqlAzureIpAddress,0,16,DefBaseAllocator>::Lookup(
                 v118 + 40,
                 v231);
        if ( v120
          && (!Base_PublicGlobals::sm_invariantTscAvailable
            ? (CSbTransportMgr *)(v122 = MEMORY[0x7FFE0008], v25 = Login, v208 = Login, v119 = v248)
            : (QueryPerformanceCounter(&v259), v122 = (CSbTransportMgr *)v259.QuadPart),
              (__int64)(*(_QWORD *)(v120 + 40) - (_QWORD)v122) >= 0) )
        {
          if ( *(_BYTE *)(v120 + 48) )
          {
            SOS_RWLock::ReleaseLock(v119, 1);
            v249 = 0;
            v121 = 1;
          }
          else
          {
            SOS_RWLock::ReleaseLock(v119, 1);
            v249 = 0;
            v121 = -1;
          }
        }
        else
        {
          SOS_RWLock::ReleaseLock(v119, 1);
          v249 = 0;
          v121 = 0;
        }
      }
      operator delete(v231, 0x18u);
      if ( v121 == -1 )
      {
        v28 = 0;
        v123 = v232;
      }
      else
      {
        if ( v121 != 1 )
        {
LABEL_290:
          v115 = 0;
          if ( *(_DWORD *)(qword_102ECFB00 + 14504)
            && (byte_102EDCC61 || (*((_BYTE *)qword_102ECFB10 + 1559) & 8) != 0)
            && CGlobalBabylonPolicyProvider::FRBACEnabled() )
          {
            v115 = ExternalCheckConnectSrvPerm(v227, v285, *v219);
            _InterlockedExchange((volatile __int32 *)v216 + 1271, v115);
            v25 = Login;
          }
          v116 = v285;
          LODWORD(v265) = 0;
          *((_QWORD *)&v265 + 1) = 0;
          LOWORD(v266) = 0;
          v320[1] = v227;
          v117 = (ErrMsgsBase *)operator new(0x28u, v227, "sql\\ntdbms\\include\\xodbcwrapper.h", 91, 3u);
          v263 = v117;
          if ( v117 )
          {
            *(_OWORD *)v117 = v265;
            *((_QWORD *)v117 + 2) = v266;
            *((_DWORD *)v117 + 6) = 0;
            *((_WORD *)v117 + 14) = 0;
          }
          else
          {
            v117 = 0;
          }
          v320[0] = v117;
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v260);
            v124 = (CSbTransportMgr *)v260.QuadPart;
          }
          else
          {
            v124 = MEMORY[0x7FFE0008];
            v25 = Login;
          }
          CNetConnection::GetLock(*(CNetConnection **)(v13 + 16));
          *(_QWORD *)(v13 + 888) = v124;
          *(_DWORD *)(v13 + 904) = 1;
          v125 = *(_QWORD **)(*(_QWORD *)(v13 + 16) + 392LL);
          if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
          {
            v126 = rand();
            if ( v126 == 5 * (v126 / 5) )
              Spinlock<114,16,258>::UpdateStatSnapshot();
          }
          *v125 = 0;
          v127 = v280 || v25;
          v203 = v115;
          LOBYTE(v202) = v204;
          LOBYTE(v199) = *((_DWORD *)v228 + 272) != 0;
          LOBYTE(v198) = v127;
          LOBYTE(v197) = a6;
          v128 = v216;
          v25 = CAutoOdbcConnectionWrapper::AuthenticateAgainstLogicalMasterOrAuthCache(
                  v320,
                  Source,
                  (unsigned int)DestinationSize,
                  *((_QWORD *)v216 + 26),
                  v234[0],
                  LOWORD(v234[1]),
                  v218,
                  v210,
                  (char *)v228 + 874,
                  (char *)v228 + 776,
                  *((_DWORD *)v228 + 243),
                  (_DWORD)v197,
                  v198,
                  v199,
                  &v319,
                  &v293,
                  (char *)&v282 + 2,
                  v202,
                  v323,
                  Destination,
                  &v279,
                  &v282,
                  &v294,
                  v11,
                  (char *)&v282 + 3,
                  &v289,
                  &v283,
                  &v298,
                  (char *)&v282 + 1,
                  v287,
                  (char *)v216 + 1188,
                  v214,
                  v278,
                  v250,
                  v240,
                  *((_DWORD *)v228 + 271) != 0,
                  *((_DWORD *)v228 + 270) != 0,
                  v203,
                  v116);
          v208 = v25;
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v246);
            v129 = (CSbTransportMgr *)v246.QuadPart;
          }
          else
          {
            v129 = MEMORY[0x7FFE0008];
            v208 = v25;
          }
          CNetConnection::GetLock(*(CNetConnection **)(v13 + 16));
          if ( *(_DWORD *)(v13 + 904) )
          {
            v130 = *(_QWORD *)(v13 + 888);
            if ( (unsigned __int64)v129 > v130 )
              *(_QWORD *)(v13 + 896) += (char *)v129 - v130;
            *(_DWORD *)(v13 + 904) = 0;
          }
          v131 = *(_QWORD **)(*(_QWORD *)(v13 + 16) + 392LL);
          if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
          {
            v132 = rand();
            if ( v132 == 5 * (v132 / 5) )
              Spinlock<114,16,258>::UpdateStatSnapshot();
          }
          *v131 = 0;
          if ( byte_102EDCE2D && (*((_BYTE *)qword_102ECFB10 + 1294) & 2) == 0 )
            *((_WORD *)v128 + 593) = v287[0];
          *((_DWORD *)v128 + 1272) = v298;
          v123 = v232;
          if ( !v25 && !(_DWORD)v232 && !(unsigned __int8)CConnectionChecker::Check(v323, 5) )
          {
            *v11 = 5;
            v25 = 26078;
            v208 = 26078;
          }
          if ( v207 )
          {
            if ( (v283 & 0x101) != 0x101 )
              goto LABEL_342;
          }
          else if ( v289 )
          {
LABEL_342:
            v133 = 0;
            goto LABEL_343;
          }
          v133 = 1;
LABEL_343:
          v28 = v25 != 40615 && v133;
          if ( v220 == 2 && (v123 || !v28) )
          {
            v134 = *((_DWORD *)v228 + 243);
            v233 = 0;
            if ( SqlAzureIpAddress::TryParse((const wchar_t *)v228 + 388, v134 >> 1, &v233) )
            {
              v137 = GetXdbServerGlobals(v136, v135);
              IPAddrInFirewallCache::Update(*(IPAddrInFirewallCache **)(v137 + 19552), v233, v28);
            }
            operator delete(v233, 0x18u);
          }
          operator delete(v320[0], 0x28u);
          goto LABEL_356;
        }
        v28 = 1;
        v123 = v232;
      }
LABEL_356:
      if ( v123 )
      {
        v25 = v123;
        v208 = v123;
        *v11 = v238[0];
      }
      goto LABEL_406;
    }
    LODWORD(v295) = 0;
    v288[0] = 0;
    try
    {
      ExcHandler::ExcHandler((ExcHandler *)v384, 0, 0, 0, (int (*)(int, int, int, int, char *))hdl_prntbackout, 0);
      v138 = 0;
      v239 = 0;
      if ( *(_DWORD *)(qword_102ECFB00 + 14504)
        && (byte_102EDCC61 || (*((_BYTE *)qword_102ECFB10 + 1559) & 8) != 0 ? (v139 = 1) : (v139 = 0),
            v139 && CGlobalBabylonPolicyProvider::FRBACEnabled()) )
      {
        v140 = v285;
        v276 = v285;
        MasterDbId = GetMasterDbId();
        v239 = ExternalCheckConnectSrvPerm(v227, v140, MasterDbId);
        v142 = v216;
        _InterlockedExchange((volatile __int32 *)v216 + 1271, v239);
        v25 = Login;
        v138 = v239;
      }
      else
      {
        v142 = v216;
      }
      v143 = v280 || v25;
      v221[0] = v143;
      LOBYTE(v200) = v204;
      LOBYTE(v196) = a6;
      v144 = CCloudExtensions::AuthenticateLogin(
               Source,
               (unsigned int)DestinationSize,
               *((_QWORD *)v142 + 26),
               v234[0],
               LOWORD(v234[1]),
               &szPassword,
               0,
               (char *)v86 + 776,
               *((_DWORD *)v86 + 243),
               &v293,
               v196,
               v221,
               &v319,
               v288,
               v200,
               Destination,
               &v279,
               &v295,
               &v282,
               &v294,
               v11,
               (char *)&v282 + 3,
               &v289,
               &v283,
               *((_DWORD *)v86 + 272) != 0,
               (char *)&v282 + 1,
               v287,
               (char *)v142 + 1188,
               0,
               v214,
               v278,
               0,
               0,
               *((_DWORD *)v86 + 271) != 0,
               *((_DWORD *)v86 + 270) != 0,
               v138,
               v285);
      v206 = v144;
      if ( byte_102EDCE2D && (*((_BYTE *)qword_102ECFB10 + 1294) & 2) == 0 )
        *((_WORD *)v142 + 593) = v287[0];
      if ( v207 )
      {
        if ( (v283 & 0x101) != 0x101 )
          goto LABEL_380;
      }
      else if ( v289 )
      {
LABEL_380:
        v146 = 0;
        goto LABEL_381;
      }
      v146 = 1;
LABEL_381:
      v147 = v144 != 40615 && v146;
      v209 = v147;
      if ( v111 )
      {
        v206 = v111;
        *v11 = v238[0];
      }
      else if ( v144 )
      {
        if ( v144 != 40615 )
        {
          v246.QuadPart = 0x8000000001LL;
          if ( (qword_102F21DB4 & 0x80u) != 0LL )
          {
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v142 + 12) + 16LL))(*((_QWORD *)v142 + 12));
            XeCloudPkg::login_substep_failure::login_substep_failure((XeCloudPkg::login_substep_failure *)v389);
            v391 = v144;
            v392 = *v11;
            v393 = 0;
            v394 = v280;
            v148 = v390;
            v390[2] = &v293;
            *((_DWORD *)v148 + 6) = 16;
            *((_WORD *)v148 + 14) = 4;
            *((_WORD *)v148 + 15) = 0;
            v149 = v390;
            v390[4] = &szPassword;
            *((_DWORD *)v149 + 10) = 0;
            *((_WORD *)v149 + 22) = 5;
            *((_WORD *)v149 + 23) = 0;
            v151 = GetXdbServerGlobals(5, v150);
            v154 = -1;
            do
              ++v154;
            while ( *(_WORD *)(v151 + 2 * v154) );
            v155 = GetXdbServerGlobals(v153, v152);
            v156 = v390;
            v390[6] = v155;
            *((_DWORD *)v156 + 14) = 2 * v154;
            *((_WORD *)v156 + 30) = 6;
            *((_WORD *)v156 + 31) = 0;
            v157 = v390;
            v390[8] = v218;
            *((_DWORD *)v157 + 18) = 2 * ((unsigned __int64)v210 >> 1);
            *((_WORD *)v157 + 38) = 7;
            *((_WORD *)v157 + 39) = 0;
            XeCloudPkg::login_substep_failure::Publish((XeCloudPkg::login_substep_failure *)v389);
          }
        }
      }
      ExcHandler::~ExcHandler((ExcHandler *)v384);
    }
    catch ( SQLError v387 )
    {
      try
      {
        ExceptionBackout::ExceptionBackout((ExceptionBackout *)&v318, (const struct SQLError *)v387);
        if ( !(_DWORD)v232 )
        {
          v206 = 40613;
          *(_DWORD *)v224 = 115;
        }
        ExceptionBackout::~ExceptionBackout((ExceptionBackout *)&v318);
      }
      catch ( ShortStackException )
      {
      }
      v223 = v243;
      v216 = v231;
      v227 = v233;
      v11 = (int *)v224;
    }
    v158 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v159 = *(struct Worker **)(v158 + 256);
    if ( !v159 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v159 = *(struct Worker **)(v158 + 256);
    }
    if ( *((_DWORD *)v159 + 139) )
      ExceptionPostCatchActions(v159);
    v25 = v206;
    v208 = v206;
    if ( !v206 )
    {
      if ( v211 )
        *v219 = v295;
      if ( !(unsigned __int8)CConnectionChecker::Check(v323, 3) )
      {
        *v11 = 3;
        v25 = 26078;
        v208 = 26078;
      }
    }
    goto LABEL_405;
  }
  v300 = 0;
  v301 = 0;
  v302 = 0;
  if ( Base_PublicGlobals::sm_invariantTscAvailable )
  {
    QueryPerformanceCounter(&v256);
    v59 = (CSbTransportMgr *)v256.QuadPart;
  }
  else
  {
    v59 = MEMORY[0x7FFE0008];
    v25 = Login;
  }
  CNetConnection::GetLock(*(CNetConnection **)(v13 + 16));
  *(_QWORD *)(v13 + 912) = v59;
  *(_DWORD *)(v13 + 928) = 1;
  v60 = *(_QWORD **)(*(_QWORD *)(v13 + 16) + 392LL);
  if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
  {
    v61 = rand();
    if ( v61 == 5 * (v61 / 5) )
      Spinlock<114,16,258>::UpdateStatSnapshot();
  }
  *v60 = 0;
  try
  {
    ExcHandler::ExcHandler((ExcHandler *)v382, 0, 0, 0, (int (*)(int, int, int, int, char *))hdl_prntbackout, 0);
    if ( byte_102EDCD1A )
    {
      v316 = 0;
      v317 = 0;
      v62 = v219;
      AutoOpenDB::Open((AutoOpenDB *)&v316, 0, *v219, 0x4000u, 0);
      if ( !v316 )
      {
        LogSystemMetadata(
          L"login error - Open DB failed for DB name: %.*ls id: %u\n",
          (unsigned __int64)v210 >> 1,
          v218,
          *v219);
        v25 = 40613;
        Login = 40613;
        *v11 = 127;
      }
      if ( v316 )
        AutoOpenDB::CloseDB((AutoOpenDB *)&v316);
      if ( v25 )
        goto LABEL_123;
    }
    else
    {
      v62 = v219;
    }
    LOBYTE(v200) = *(_DWORD *)(v13 + 988) <= 1u;
    LODWORD(v197) = *v62;
    Login = FindLogin(
              v52,
              v238[0],
              a5,
              (int)&v300,
              (enum ELoginFailedState *)v11,
              (__int64)&v301,
              0,
              0,
              (__int64)&v301 + 4,
              0,
              (__int64)&v302,
              (__int64)v197,
              (__int64)&v282,
              (__int64)v323,
              v200,
              (__int64)&v290,
              (__int64)&v285,
              (__int64)&v303);
LABEL_123:
    ExcHandler::~ExcHandler((ExcHandler *)v382);
  }
  catch ( SQLError v321 )
  {
    try
    {
      ExceptionBackout::ExceptionBackout((ExceptionBackout *)v328, (const struct SQLError *)&v321);
      si128 = v321;
      v188 = v322;
      v252 = v322;
      v189 = v224;
      *(_DWORD *)v224 = 129;
      if ( v188 == 1 )
        v190 = v321.m128i_i32[0];
      else
        v190 = v321.m128i_u16[0];
      LODWORD(v244) = v190;
      if ( v190 != 40839 )
      {
        if ( v190 == 40863 )
        {
          *(_DWORD *)v189 = 137;
          v190 = 18456;
          v242 = 18456;
          goto LABEL_526;
        }
        if ( v190 != 40981 )
        {
          v190 = 40613;
          v242 = 40613;
LABEL_526:
          Login = v190;
          ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v328);
          goto LABEL_564;
        }
      }
      v242 = v190;
      goto LABEL_526;
    }
    catch ( ShortStackException )
    {
    }
LABEL_564:
    v13 = v295;
    v63 = v243;
    v223 = v243;
    v216 = v231;
    v227 = v233;
    FeatureExtension = v232;
    v11 = (int *)v224;
    goto LABEL_125;
  }
  v63 = v223;
LABEL_125:
  v64 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v65 = *(struct Worker **)(v64 + 256);
  if ( !v65 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v65 = *(struct Worker **)(v64 + 256);
  }
  if ( *((_DWORD *)v65 + 139) )
    ExceptionPostCatchActions(v65);
  if ( Base_PublicGlobals::sm_invariantTscAvailable )
  {
    QueryPerformanceCounter(&v254);
    v66 = (CSbTransportMgr *)v254.QuadPart;
  }
  else
  {
    v66 = MEMORY[0x7FFE0008];
  }
  CNetConnection::GetLock(*(CNetConnection **)(v13 + 16));
  if ( *(_DWORD *)(v13 + 928) )
  {
    v67 = *(_QWORD *)(v13 + 912);
    if ( (unsigned __int64)v66 > v67 )
      *(_QWORD *)(v13 + 920) += (char *)v66 - v67;
    *(_DWORD *)(v13 + 928) = 0;
  }
  v68 = *(_QWORD **)(*(_QWORD *)(v13 + 16) + 392LL);
  if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
  {
    v69 = rand();
    if ( v69 == 5 * (v69 / 5) )
      Spinlock<114,16,258>::UpdateStatSnapshot();
  }
  *v68 = 0;
  v25 = Login;
  v208 = Login;
  if ( !Login || (v70 = *v11, (unsigned int)(*v11 - 65) <= 1) || a7 )
  {
    v280 = 1;
    if ( *v11 != 138 )
    {
      if ( !Login )
      {
        if ( FeatureExtension )
        {
          if ( *v219 )
          {
            if ( FControlNodeDwShellDb() )
            {
              if ( byte_102EDCBDD )
              {
                v297 = 0;
                v83 = *((_QWORD *)v216 + 13);
                if ( v83 )
                {
                  v84 = *(_QWORD *)(v83 + 264);
                  if ( v84 )
                  {
                    v85 = (const unsigned __int8 *)(*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v84 + 408LL))(
                                                     v84,
                                                     &v297);
                    if ( v297 )
                    {
                      v247[0] = v297;
                      v204 = (unsigned int)CCloudExtensions::FIsLoginUserMemberOfDBRole(
                                             (const struct CCompExecCtxtBasic *)L"db_exporter",
                                             v85,
                                             v247,
                                             *v219,
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
    v81 = v225;
    if ( (_QWORD)v225 )
    {
      *(_QWORD *)(*(_QWORD *)(v225 + 24) + 8LL) = v226;
      *(_QWORD *)(v81 + 24) = *((_QWORD *)&v225 + 1);
      v225 = 0;
      v226 = 0;
    }
    v304 = &CPassThroughConn::`vftable';
    goto LABEL_184;
  }
  if ( !byte_102EDCA60 || !*(_DWORD *)(qword_102ECFB00 + 14504) || v70 != 170 || Login != 47087 && Login != 18456 )
  {
    if ( !FeatureExtension )
    {
      if ( byte_102EDCD1A )
      {
        wcscpy(v404, L"Contained authentication failed with error: %d (major: %d, minor: %d)");
        memset_0(v405, 0, sizeof(v405));
        v255 = 0;
        v253 = 0;
        v77 = si128.m128i_i32[0];
        if ( v252 != 1 )
          v77 = si128.m128i_u16[0];
        LODWORD(v193) = si128.m128i_i32[0] % 100;
        LODWORD(v192) = si128.m128i_i32[0] / 100;
        v191[0] = v77;
        if ( (int)StringCchPrintfExW(v405, 0x100u, &v253, &v255, 0, v404, *(_QWORD *)v191, v192, v193) >= 0 )
        {
          v79 = -1;
          do
            ++v79;
          while ( v405[v79] );
          v194 = v79;
          v78 = v405;
        }
        else
        {
          v194 = 79;
          v78 = (wchar_t *)L"Contained authentication failed with error (failed to format inner error code)";
        }
        XEventReportLoginSubstepFailureEvent(
          Login,
          **(_DWORD **)&v299[0].S_un.S_un_b.s_b1,
          0,
          v280,
          &v293,
          v218,
          (unsigned __int64)v210 >> 1,
          v78,
          v194);
        if ( Login == 40613 )
        {
          v80 = v225;
          if ( (_QWORD)v225 )
          {
            *(_QWORD *)(*(_QWORD *)(v225 + 24) + 8LL) = v226;
            *(_QWORD *)(v80 + 24) = *((_QWORD *)&v225 + 1);
            v225 = 0;
            v226 = 0;
          }
          v304 = &CConnectionOutput::`vftable';
          v75 = v63;
          goto LABEL_495;
        }
      }
      goto LABEL_158;
    }
    v73 = v285;
    if ( v285 && Login == 18456 && (v70 == 62 || v70 == 189) && (byte_102EDCBFE || byte_102EDCC3D) )
    {
      v279 = *((_DWORD *)v285 + 5);
      memcpy_s(Destination, 0x55u, (char *)v285 + *((unsigned int *)v285 + 6), (int)v279);
      LODWORD(DestinationSize) = *((_DWORD *)v73 + 4);
      Source = (char *)v73 + *((unsigned int *)v73 + 3);
LABEL_158:
      v25 = 0;
      v208 = 0;
      Login = 0;
      goto LABEL_159;
    }
    v280 = 1;
    if ( v70 != 138 )
    {
LABEL_159:
      if ( byte_102EDCB21 && v25 == 40613 )
      {
        *v11 = 127;
        v74 = v225;
        if ( (_QWORD)v225 )
        {
          *(_QWORD *)(*(_QWORD *)(v225 + 24) + 8LL) = v226;
          *(_QWORD *)(v74 + 24) = *((_QWORD *)&v225 + 1);
          v225 = 0;
          v226 = 0;
        }
        v304 = &CConnectionOutput::`vftable';
        v75 = v63;
        goto LABEL_495;
      }
      if ( !v25 && !(unsigned __int8)CConnectionChecker::Check(v323, 1) )
      {
        *v11 = 1;
        v25 = 26078;
        v208 = 26078;
        Login = 26078;
      }
      goto LABEL_200;
    }
    v76 = v225;
    if ( (_QWORD)v225 )
    {
      *(_QWORD *)(*(_QWORD *)(v225 + 24) + 8LL) = v226;
      *(_QWORD *)(v76 + 24) = *((_QWORD *)&v225 + 1);
      v225 = 0;
      v226 = 0;
    }
    v304 = &CPassThroughConn::`vftable';
LABEL_184:
    v304 = &CConnectionOutput::`vftable';
    ErrMsgsBase::Release(v63);
    goto LABEL_185;
  }
  XEventReportLoginSubstepFailureEvent(Login, 170, 0, v280, &v293, v218, (unsigned __int64)v210 >> 1, &szPassword, 0);
  v71 = v225;
  if ( (_QWORD)v225 )
  {
    *(_QWORD *)(*(_QWORD *)(v225 + 24) + 8LL) = v226;
    *(_QWORD *)(v71 + 24) = *((_QWORD *)&v225 + 1);
    v225 = 0;
    v226 = 0;
  }
  v304 = &CConnectionOutput::`vftable';
  v72 = v63;
LABEL_513:
  ErrMsgsBase::Release(v72);
  operator delete[](v285);
  v187 = (void *)v290;
  if ( v290 )
  {
    operator delete[](*(void **)(v290 + 16));
    operator delete(v187, 0x18u);
  }
  return v25;
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
