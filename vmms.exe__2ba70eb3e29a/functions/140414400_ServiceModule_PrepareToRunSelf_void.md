# ServiceModule::PrepareToRunSelf(void)

- ea: `0x140414400`
- end: `0x1404157f7`
- name: `?PrepareToRunSelf@ServiceModule@@QEAAXXZ`
- size: `5111`
- prototype: `void __fastcall(ServiceModule *__hidden this)`
- caller_count: `1`
- callee_count: `99`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x14048c184`

## callees

- `0x140022640`
- `0x140024af4`
- `0x1400342a0`
- `0x140034404`
- `0x140043d38`
- `0x140043d7c`
- `0x14005c630`
- `0x14006a594`
- `0x1400887bc`
- `0x140088814`
- `0x14008e064`
- `0x1400acf04`
- `0x1400b47d0`
- `0x1400b685c`
- `0x1400e1fb0`
- `0x1400e2a70`
- `0x1400e2f64`
- `0x1400e3320`
- `0x1400ea710`
- `0x1401156b8`
- `0x140117f50`
- `0x1401248b4`
- `0x140149058`
- `0x14016604c`
- `0x14017902c`
- `0x140188e18`
- `0x1401a72f8`
- `0x1401be65c`
- `0x140235e30`
- `0x1402435b4`
- `0x140248508`
- `0x140254478`
- `0x1402b62c4`
- `0x1402c041c`
- `0x1402ca818`
- `0x1402caba8`
- `0x1403c1b38`
- `0x140414400`
- `0x140415800`
- `0x1404158cc`
- `0x140415950`
- `0x1404374c4`
- `0x14046d3b8`
- `0x1404828e0`
- `0x140482bac`
- `0x1404835a0`
- `0x14048e308`
- `0x14048fc60`
- `0x140491c4c`
- `0x140492d24`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14041445c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14041445c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1404149c6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140414a76`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140414b47`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140414bb7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140414c0d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140414c87`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140414d04`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140414d50`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140414fc8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140415025`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1404150df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140415186`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14041520e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1404152b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14041535c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1404153db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14041545a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1404154d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14041556b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1404149c6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140414a76`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140414b47`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140414bb7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140414c0d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140414c87`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140414d04`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140414d50`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140414fc8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140415025`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1404150df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140415186`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14041520e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1404152b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14041535c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1404153db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14041545a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1404154d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14041556b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140414991`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140414a41`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140414b12`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140414b8c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140414bd8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140414c52`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140414cd9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140414d25`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140414f7b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140414ff0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140415097`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140415151`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1404151d9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140415280`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140415327`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1404153a6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140415425`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1404154a4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140415536`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140414991`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140414a41`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140414b12`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140414b8c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140414bd8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140414c52`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140414cd9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140414d25`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140414f7b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140414ff0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140415097`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140415151`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1404151d9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140415280`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140415327`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1404153a6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140415425`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1404154a4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140415536`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x1404157e9`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x1404157e9`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14041481f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14041481f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140414444`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1404147a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140414830`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140414444`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1404147a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140414830`

## string_xrefs

- `0x1404149e5`: `onecore\vm\vmms\registrar\vmcomponentregistrar.cpp`
- `0x140414ab3`: `onecore\vm\vmms\main\exe\servicemodule.cpp`
- `0x140414c2c`: `onecore\vm\vmms\main\exe\servicemodule.cpp`
- `0x140414cb3`: `onecore\vm\vmms\main\exe\servicemodule.cpp`
- `0x140414d85`: `onecore\vm\vmms\main\exe\servicemodule.cpp`
- `0x140414e12`: `onecore\vm\vmms\main\exe\servicemodule.cpp`
- `0x140414ef8`: `onecore\vm\vmms\main\exe\servicemodule.cpp`
- `0x140415049`: `onecore\vm\vmms\main\exe\servicemodule.cpp`
- `0x140415071`: `onecore\vm\vmms\main\exe\servicemodule.cpp`
- `0x140415103`: `onecore\vm\vmms\main\exe\servicemodule.cpp`
- `0x14041512b`: `onecore\vm\vmms\main\exe\servicemodule.cpp`
- `0x1404151aa`: `onecore\vm\vmms\main\exe\servicemodule.cpp`
- `0x140415232`: `onecore\vm\vmms\main\exe\servicemodule.cpp`
- `0x14041525a`: `onecore\vm\vmms\main\exe\servicemodule.cpp`
- `0x1404152d9`: `onecore\vm\vmms\main\exe\servicemodule.cpp`
- `0x140415301`: `onecore\vm\vmms\main\exe\servicemodule.cpp`
- `0x140415380`: `onecore\vm\vmms\main\exe\servicemodule.cpp`
- `0x1404153ff`: `onecore\vm\vmms\main\exe\servicemodule.cpp`
- `0x14041547e`: `onecore\vm\vmms\main\exe\servicemodule.cpp`
- `0x1404154fd`: `onecore\vm\vmms\main\exe\servicemodule.cpp`
- `0x14041558f`: `onecore\vm\vmms\main\exe\servicemodule.cpp`
- `0x140414479`: `onecore\vm\common\vml\VmModules.h`
- `0x14041449a`: `Create MI_Application singleton.`
- `0x1404144b7`: `Register SIDs`
- `0x140414708`: `Service set to running`
- `0x14041579d`: `Shutdown during wait for system `
- `0x1404148b9`: ` complete`
- `0x1404149f6`: `VmComponentRegistrar CreateInstance`
- `0x140414a97`: `ServiceModule::PrepareToRunSelf failed to initialize VmSwitchExtensionRegistrar.`
- `0x140414ac4`: `VmSwitchExtensionRegistrar CreateInstance`
- `0x140414ad7`: `VmIovStatusManager CreateInstance`
- `0x140414aea`: `VmVirtualFcProvider CreateInstance`
- `0x140414b77`: `VmMetricDefinitionManager CreateInstance`
- `0x140414bc3`: `VmmsWorkerManager OpenShared`
- `0x140414c3d`: `VmmsVirtualMachineManager OpenShared`
- `0x140414cc4`: `CCALFactory CreateClusterManagerInstance`
- `0x140414d10`: `CDPCoordinatorManager<HostCDPCoordinator> OpenShared`
- `0x140414d5c`: `CDPCoordinatorManager<CollectionCDPCoordinator> OpenShared`
- `0x140414f09`: `VmEthernetConnectionProvider CreateInstance`
- `0x140414f40`: `RemoteConnectionListener CreateInstance`
- `0x140414f53`: `SingleSettingsWatcher CreateInstance`
- `0x140414f66`: `VmmsMigrationManager CreateInstance`
- `0x140414fdb`: `VmVssWriter OpenShared`
- `0x14041526b`: `Initialize Undo Log Configuration Manager`
- `0x140415410`: `Initialize Failover Replication Broker Manager`
- `0x140415521`: `Initialize MountedStorageImageManager`
- `0x140415677`: `ServiceModule::PrepareToRunSelf`
- `0x1404156b2`: `Dispatch optional services registrar`
- `0x1404156db`: `Update the preshutdown timeout`
- `0x1404156ee`: `Update the root\interop namespace security`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall ServiceModule::PrepareToRunSelf(ServiceModule *this)
{
  ServiceModule *v1; // r14
  DWORD TickCount; // esi
  HANDLE EventW; // rax
  const char *v4; // r9
  ServiceModule *v5; // rcx
  ServiceModule *v6; // rcx
  ServiceModule *v7; // rcx
  ServiceModule *v8; // rcx
  ServiceModule *v9; // rcx
  void *v10; // rbx
  __int64 v11; // rax
  const struct type_info *v12; // rdx
  void *v13; // rbx
  __int64 v14; // rax
  const struct type_info *v15; // rdx
  void *v16; // rbx
  __int64 v17; // rax
  void *v18; // rbx
  __int64 v19; // rax
  const struct type_info *v20; // rdx
  void *v21; // rbx
  __int64 v22; // rax
  const struct type_info *v23; // rdx
  void *v24; // rbx
  __int64 v25; // rax
  const struct type_info *v26; // rdx
  void *v27; // rbx
  __int64 v28; // rax
  const struct type_info *v29; // rdx
  ServiceModule *v30; // rcx
  ServiceModule *v31; // rcx
  ServiceModule *v32; // rcx
  int IsSystemSetupInProgress; // r15d
  int v34; // eax
  int v35; // r12d
  const wchar_t *v36; // rdx
  DWORD v37; // ebx
  VmmsClusterManager *v38; // rax
  __int64 v39; // rax
  ServiceModule *v40; // rcx
  ServiceModule *v41; // rcx
  VmmsClusterManager *v42; // rax
  VmmsClusterManager *v43; // rax
  __int64 v44; // rax
  __int64 v45; // rax
  ServiceModule *v46; // rcx
  _QWORD *v47; // r15
  const unsigned __int16 *v48; // rdx
  ServiceModule *v49; // rcx
  __int64 v50; // rbx
  ServiceModule *v51; // rcx
  __int64 Instance; // rax
  ServiceModule *v53; // rcx
  __int64 v54; // rbx
  ServiceModule *v55; // rcx
  ServiceModule *v56; // rcx
  ServiceModule *v57; // rcx
  ServiceModule *v58; // rcx
  __int64 v59; // rbx
  ServiceModule *v60; // rcx
  ServiceModule *v61; // rcx
  __int64 v62; // rbx
  ServiceModule *v63; // rcx
  __int64 v64; // r15
  ServiceModule *v65; // rcx
  ServiceModule *v66; // rcx
  __int64 v67; // rax
  int v68; // eax
  ServiceModule *v69; // rcx
  unsigned int v70; // r15d
  unsigned int v71; // ebx
  const struct _GUID *v72; // r8
  int v73; // r15d
  ServiceModule *v74; // rcx
  const char *v75; // r9
  __int64 v76; // rdx
  void (__fastcall *v77)(__int64, __int64); // r10
  __int64 v78; // rax
  ServiceModule *v79; // rcx
  ServiceModule *v80; // rcx
  ServiceModule *v81; // rcx
  ServiceModule *v82; // rcx
  __int64 v83; // rbx
  ServiceModule *v84; // rcx
  VmmsClusterManager *v85; // rbx
  int v86; // eax
  VmmsSynthFcManager *v87; // rbx
  int v88; // eax
  __int64 v89; // rbx
  ServiceModule *v90; // rcx
  FrUndoLogConfigurationManager *v91; // rbx
  int v92; // eax
  VmmsFailoverReplicationManager *v93; // rbx
  int v94; // eax
  __int64 v95; // rbx
  ServiceModule *v96; // rcx
  __int64 v97; // rbx
  ServiceModule *v98; // rcx
  __int64 v99; // rbx
  ServiceModule *v100; // rcx
  __int64 v101; // rbx
  ServiceModule *v102; // rcx
  ServiceModule *v103; // rcx
  __int64 v104; // rbx
  ServiceModule *v105; // rcx
  _QWORD *v106; // rbx
  int v107; // ebx
  ServiceModule *v108; // rcx
  ServiceModule *v109; // rcx
  ServiceModule *v110; // rcx
  ServiceModule *v111; // rcx
  ServiceModule *v112; // rcx
  ServiceModule *v113; // rcx
  ServiceModule *v114; // rcx
  ServiceModule *v115; // rcx
  ServiceModule *v116; // rcx
  const struct _GUID *v117; // r8
  ServiceModule *v118; // rcx
  const struct _GUID *v119; // r8
  _QWORD *v120; // rax
  __int64 v121; // rax
  ServiceModule *v122; // rcx
  ServiceModule *v123; // rbx
  const char *v124; // r9
  const unsigned int *v125; // [rsp+28h] [rbp-C0h]
  int v126; // [rsp+20h] [rbp-C8h]
  int v127; // [rsp+20h] [rbp-C8h]
  const unsigned int *v128; // [rsp+28h] [rbp-C0h]
  VmmsClusterManager *v129; // [rsp+30h] [rbp-B8h] BYREF
  std::_Ref_count_base *v130; // [rsp+38h] [rbp-B0h]
  DWORD v131; // [rsp+50h] [rbp-98h]
  _QWORD *v132; // [rsp+58h] [rbp-90h]
  _DWORD *v133; // [rsp+60h] [rbp-88h]
  ServiceModule *v134; // [rsp+68h] [rbp-80h]
  _QWORD v135[3]; // [rsp+70h] [rbp-78h] BYREF
  unsigned __int64 v136; // [rsp+88h] [rbp-60h]
  __int64 v137[4]; // [rsp+90h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  v1 = this;
  v134 = this;
  v133 = (_DWORD *)((char *)this + 464);
  *((_DWORD *)this + 116) = 0;
  TickCount = GetTickCount();
  EventW = CreateEventW(0, 0, 0, 0);
  try
  {
    *((_QWORD *)v1 + 11) = EventW;
    if ( !EventW )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x744,
        (unsigned int)"onecore\\vm\\common\\vml\\VmModules.h",
        v4);
    v131 = TickCount;
    *((_QWORD *)v1 + 35) = Vml::VmMiApplication::OpenShared();
    ServiceModule::PreparePhaseTimeCheck(v5, TickCount, L"Create MI_Application singleton.");
    ServiceModule::RegisterVmGroupSids(v6);
    ServiceModule::GrantVmGroupSidSynchronizeAccessToSelf(v7);
    ServiceModule::AdjustVmGroupPrivileges(v8);
    ServiceModule::PreparePhaseTimeCheck(v9, TickCount, L"Register SIDs");
    v10 = operator new(0x140u);
    memset_0(v10, 0, 0x140u);
    v11 = Vml::VmOrderedThreadpoolDispatcher::VmOrderedThreadpoolDispatcher((Vml::VmOrderedThreadpoolDispatcher *)v10);
    *((_QWORD *)v1 + 39) = v11;
    v12 = (const struct type_info *)*(int *)(*(_QWORD *)(v11 + 8) + 4LL);
    Vml::VmSharableObject::AddUserInternal((const struct type_info *)((char *)v12 + v11 + 8), v12);
    v13 = operator new(0x140u);
    memset_0(v13, 0, 0x140u);
    v14 = Vml::VmOrderedThreadpoolDispatcher::VmOrderedThreadpoolDispatcher((Vml::VmOrderedThreadpoolDispatcher *)v13);
    *((_QWORD *)v1 + 40) = v14;
    v15 = (const struct type_info *)*(int *)(*(_QWORD *)(v14 + 8) + 4LL);
    Vml::VmSharableObject::AddUserInternal((const struct type_info *)((char *)v15 + v14 + 8), v15);
    v16 = operator new(0x78u);
    memset_0(v16, 0, 0x78u);
    v17 = Vml::VmMethodDelegate<ServiceModule,void,>::VmMethodDelegate<ServiceModule,void,>(v16);
    v132 = (_QWORD *)((char *)v1 + 296);
    *((_QWORD *)v1 + 37) = v17;
    *(_QWORD *)(v17 + 104) = v1;
    *(_QWORD *)(v17 + 112) = ServiceModule::RegisterOptionalServices;
    *(_QWORD *)(*((_QWORD *)v1 + 37) + 88LL) = *((_QWORD *)v1 + 40);
    Vml::VmSharableObject::AddUserInternal(*((Vml::VmSharableObject **)v1 + 37), (ServiceModule *)((char *)v1 + 296));
    v18 = operator new(0x78u);
    memset_0(v18, 0, 0x78u);
    v19 = Vml::VmMethodDelegate<ServiceModule,void,>::VmMethodDelegate<ServiceModule,void,>(v18);
    *((_QWORD *)v1 + 38) = v19;
    *(_QWORD *)(v19 + 104) = v1;
    *(_QWORD *)(v19 + 112) = ServiceModule::PerformStartupActions;
    *(_QWORD *)(*((_QWORD *)v1 + 38) + 88LL) = *((_QWORD *)v1 + 39);
    Vml::VmSharableObject::AddUserInternal(*((Vml::VmSharableObject **)v1 + 38), v20);
    v21 = operator new(0x78u);
    memset_0(v21, 0, 0x78u);
    v22 = Vml::VmMethodDelegate<ServiceModule,void,>::VmMethodDelegate<ServiceModule,void,>(v21);
    *((_QWORD *)v1 + 36) = v22;
    *(_QWORD *)(v22 + 104) = v1;
    *(_QWORD *)(v22 + 112) = ServiceModule::UnRegisterOptionalServices;
    *(_QWORD *)(*((_QWORD *)v1 + 36) + 88LL) = *((_QWORD *)v1 + 40);
    Vml::VmSharableObject::AddUserInternal(*((Vml::VmSharableObject **)v1 + 36), v23);
    v24 = operator new(0x78u);
    memset_0(v24, 0, 0x78u);
    v25 = Vml::VmMethodDelegate<ServiceModule,void,>::VmMethodDelegate<ServiceModule,void,>(v24);
    *((_QWORD *)v1 + 41) = v25;
    *(_QWORD *)(v25 + 104) = v1;
    *(_QWORD *)(v25 + 112) = ServiceModule::HandleServiceStop;
    *(_QWORD *)(*((_QWORD *)v1 + 41) + 88LL) = *((_QWORD *)v1 + 39);
    Vml::VmSharableObject::AddUserInternal(*((Vml::VmSharableObject **)v1 + 41), v26);
    v27 = operator new(0x78u);
    memset_0(v27, 0, 0x78u);
    v28 = Vml::VmMethodDelegate<ServiceModule,void,>::VmMethodDelegate<ServiceModule,void,>(v27);
    *((_QWORD *)v1 + 42) = v28;
    *(_QWORD *)(v28 + 104) = v1;
    *(_QWORD *)(v28 + 112) = ServiceModule::HandleServiceShutdown;
    *(_QWORD *)(*((_QWORD *)v1 + 42) + 88LL) = *((_QWORD *)v1 + 39);
    Vml::VmSharableObject::AddUserInternal(*((Vml::VmSharableObject **)v1 + 42), v29);
    ServiceModule::PreparePhaseTimeCheck(v30, TickCount, L"Delegate Init");
    Vml::VmServiceModule<ServiceModule>::SetServiceState(v1, 4, 0);
    ServiceModule::PreparePhaseTimeCheck(v31, TickCount, L"Service set to running");
    LODWORD(v27) = IsSystemUpgradeInProgress();
    IsSystemSetupInProgress = ServiceModule::IsSystemSetupInProgress(v32);
    v34 = IsServicingInProgress();
    v35 = v34;
    if ( (_DWORD)v27 )
    {
      v36 = L"upgrade";
    }
    else if ( IsSystemSetupInProgress )
    {
      v36 = L"setup";
    }
    else
    {
      if ( !v34 )
        goto LABEL_32;
      v36 = L"servicing";
    }
    std::wstring::wstring(v135, v36);
    v37 = 0;
    v38 = (VmmsClusterManager *)v135;
    if ( v136 > 7 )
      v38 = (VmmsClusterManager *)v135[0];
    v129 = v38;
    VmEventWrite<unsigned short const *>(&MSVM_VMMS_SCM_WAIT_FOR_SERVICING_OPERATION_INFO, 1u);
    if ( v35 )
      v37 = GetTickCount();
    v39 = std::operator+<unsigned short>(&v129, L"Waiting for system ", v135);
    if ( *(_QWORD *)(v39 + 24) > 7u )
      v39 = *(_QWORD *)v39;
    ServiceModule::PreparePhaseTimeCheck(v40, TickCount, (const unsigned __int16 *)v39);
    std::wstring::_Tidy_deallocate(&v129);
    while ( (unsigned int)ServiceModule::IsSystemSetupInProgress(v41)
         || (unsigned int)IsSystemUpgradeInProgress()
         || (unsigned int)IsServicingInProgress() )
    {
      if ( *((_DWORD *)v1 + 120) || *((_DWORD *)v1 + 121) )
      {
        v120 = v135;
        if ( v136 > 7 )
          v120 = (_QWORD *)v135[0];
        v133 = v120;
        VmEventWrite<unsigned short const *>(&MSVM_VMMS_SCM_SHUTDOWN_DURING_WAIT_FOR_SERVICING_OPERATION_INFO, 1u);
        v121 = std::operator+<unsigned short>(v137, L"Shutdown during wait for system ", v135);
        if ( *(_QWORD *)(v121 + 24) > 7u )
          v121 = *(_QWORD *)v121;
        ServiceModule::PreparePhaseTimeCheck(v122, TickCount, (const unsigned __int16 *)v121);
        std::wstring::_Tidy_deallocate(v137);
        *((_DWORD *)v1 + 117) = 1;
        Vml::VmServiceModule<ServiceModule>::SetServiceState(v1, 1, 0);
        ExitProcess(0);
      }
      Sleep(0x3E8u);
      if ( v35 && GetTickCount() - v37 > 0x927C0 )
      {
        v42 = (VmmsClusterManager *)v135;
        if ( v136 > 7 )
          v42 = (VmmsClusterManager *)v135[0];
        v129 = v42;
        VmEventWrite<unsigned short const *>(&MSVM_VMMS_SCM_SERVICING_OPERATION_TIMEOUT_INFO, 1u);
        break;
      }
    }
    v43 = (VmmsClusterManager *)v135;
    if ( v136 > 7 )
      v43 = (VmmsClusterManager *)v135[0];
    v129 = v43;
    VmEventWrite<unsigned short const *>(&MSVM_VMMS_SCM_SERVICING_OPERATION_COMPLETE_INFO, 1u);
    v44 = std::operator+<unsigned short>(v137, L"System ", v135);
    v45 = std::operator+<unsigned short>(&v129, v44, L" complete");
    if ( *(_QWORD *)(v45 + 24) > 7u )
      v45 = *(_QWORD *)v45;
    ServiceModule::PreparePhaseTimeCheck(v46, TickCount, (const unsigned __int16 *)v45);
    std::wstring::_Tidy_deallocate(&v129);
    std::wstring::_Tidy_deallocate(v137);
    std::wstring::_Tidy_deallocate(v135);
LABEL_32:
    v47 = operator new(0x228u);
    v129 = (VmmsClusterManager *)v47;
    memset_0(v47 + 1, 0, 0x220u);
    *v47 = -1;
    Vml::VmSlimReaderWriterLock::VmSlimReaderWriterLock((Vml::VmSlimReaderWriterLock *)(v47 + 1), v48);
    v47[3] = -1;
    v47[4] = 0;
    v47[5] = -1;
    v47[6] = 0;
    *((_DWORD *)v47 + 14) = 0;
    v47[8] = 0;
    v47[9] = 0;
    v47[10] = 0;
    v47[11] = 0;
    v47[12] = 0;
    v47[13] = 0;
    VmmsSwitchStatsPanel::VmmsSwitchStatsPanel((VmmsSwitchStatsPanel *)(v47 + 14));
    *((_QWORD *)v1 + 44) = v47;
    VmmsStatsPanel::Initialize((VmmsStatsPanel *)v47);
    ServiceModule::PreparePhaseTimeCheck(v49, TickCount, L"Initialize StatsPanel");
    EnterCriticalSection(&Vml::VmSingletonObject<VmComponentRegistrar,IVmComponentRegistrar>::gm_SingletonLock);
    v129 = 0;
    if ( (unsigned __int8)Vml::VmSingletonObject<VmComponentRegistrar,IVmComponentRegistrar>::TryOpenSharedInternal(&v129) )
      v50 = (__int64)v129;
    else
      v50 = Vml::VmSingletonObject<VmComponentRegistrar,IVmComponentRegistrar>::OpenSharedInternal();
    LeaveCriticalSection(&Vml::VmSingletonObject<VmComponentRegistrar,IVmComponentRegistrar>::gm_SingletonLock);
    if ( !v50 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2EF,
        (unsigned int)"onecore\\vm\\vmms\\registrar\\vmcomponentregistrar.cpp",
        (const char *)0x8007000ELL,
        v126);
    ServiceModule::PreparePhaseTimeCheck(v51, TickCount, L"VmComponentRegistrar CreateInstance");
    Instance = VmNetworkBridgeManager::GetInstance(&v129);
    std::shared_ptr<VmNetworkBridgeManager>::operator=(&g_VmNetworkBridgeManager, Instance);
    v53 = v130;
    if ( v130 )
      std::_Ref_count_base::_Decref(v130);
    ServiceModule::PreparePhaseTimeCheck(v53, TickCount, L"VmNetworkBridgeManager GetInstance");
    EnterCriticalSection(&Vml::VmSingletonObject<VmSwitchExtensionRegistrar,VmSwitchExtensionRegistrar>::gm_SingletonLock);
    v129 = 0;
    if ( (unsigned __int8)Vml::VmSingletonObject<VmSwitchExtensionRegistrar,VmSwitchExtensionRegistrar>::TryOpenSharedInternal(&v129) )
      v54 = (__int64)v129;
    else
      v54 = Vml::VmSingletonObject<VmSwitchExtensionRegistrar,VmSwitchExtensionRegistrar>::OpenSharedInternal();
    LeaveCriticalSection(&Vml::VmSingletonObject<VmSwitchExtensionRegistrar,VmSwitchExtensionRegistrar>::gm_SingletonLock);
    if ( !v54 )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(16480) )
        VmlDebugTrace(16480, L"ServiceModule::PrepareToRunSelf failed to initialize VmSwitchExtensionRegistrar.");
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4AE,
        (unsigned int)"onecore\\vm\\vmms\\main\\exe\\servicemodule.cpp",
        (const char *)0x8000FFFFLL,
        v126);
    }
    ServiceModule::PreparePhaseTimeCheck(v55, TickCount, L"VmSwitchExtensionRegistrar CreateInstance");
    VmIovStatusManager::CreateInstance();
    ServiceModule::PreparePhaseTimeCheck(v56, TickCount, L"VmIovStatusManager CreateInstance");
    VmVirtualFcProvider::CreateInstance();
    ServiceModule::PreparePhaseTimeCheck(v57, TickCount, L"VmVirtualFcProvider CreateInstance");
    CrmpResourcePoolManager::Initialize();
    ServiceModule::PreparePhaseTimeCheck(v58, TickCount, L"CrmResourcePoolManager Initialize");
    EnterCriticalSection(&Vml::VmSingletonObject<VmMetricDefinitionManager,VmMetricDefinitionManager>::gm_SingletonLock);
    v129 = 0;
    if ( (unsigned __int8)Vml::VmSingletonObject<VmMetricDefinitionManager,VmMetricDefinitionManager>::TryOpenSharedInternal(&v129) )
      v59 = (__int64)v129;
    else
      v59 = Vml::VmSingletonObject<VmMetricDefinitionManager,VmMetricDefinitionManager>::OpenSharedInternal();
    LeaveCriticalSection(&Vml::VmSingletonObject<VmMetricDefinitionManager,VmMetricDefinitionManager>::gm_SingletonLock);
    if ( !v59 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x25A,
        (unsigned int)"onecore\\vm\\vmms\\metrics\\vmmetricdefinitionmanager.cpp",
        (const char *)0x8007000ELL,
        v126);
    ServiceModule::PreparePhaseTimeCheck(v60, TickCount, L"VmMetricDefinitionManager CreateInstance");
    EnterCriticalSection(&Vml::VmSingletonObject<VmmsWorkerManager,IVmmsWorkerManager>::gm_SingletonLock);
    v129 = 0;
    if ( !(unsigned __int8)Vml::VmSingletonObject<VmmsWorkerManager,IVmmsWorkerManager>::TryOpenSharedInternal(&v129) )
      Vml::VmSingletonObject<VmmsWorkerManager,IVmmsWorkerManager>::OpenSharedInternal();
    LeaveCriticalSection(&Vml::VmSingletonObject<VmmsWorkerManager,IVmmsWorkerManager>::gm_SingletonLock);
    ServiceModule::PreparePhaseTimeCheck(v61, TickCount, L"VmmsWorkerManager OpenShared");
    EnterCriticalSection(&Vml::VmSingletonObject<VmmsVirtualMachineManager,IVmmsVirtualMachineManager>::gm_SingletonLock);
    v129 = 0;
    if ( (unsigned __int8)Vml::VmSingletonObject<VmmsVirtualMachineManager,IVmmsVirtualMachineManager>::TryOpenSharedInternal(&v129) )
      v62 = (__int64)v129;
    else
      v62 = Vml::VmSingletonObject<VmmsVirtualMachineManager,IVmmsVirtualMachineManager>::OpenSharedInternal();
    LeaveCriticalSection(&Vml::VmSingletonObject<VmmsVirtualMachineManager,IVmmsVirtualMachineManager>::gm_SingletonLock);
    if ( !v62 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4D7,
        (unsigned int)"onecore\\vm\\vmms\\main\\exe\\servicemodule.cpp",
        (const char *)0x8007000ELL,
        v126);
    ServiceModule::PreparePhaseTimeCheck(v63, TickCount, L"VmmsVirtualMachineManager OpenShared");
    EnterCriticalSection(&Vml::VmSingletonObject<VmmsCCALClusterManager,ICCALClusterManager>::gm_SingletonLock);
    v129 = 0;
    if ( (unsigned __int8)Vml::VmSingletonObject<VmmsCCALClusterManager,ICCALClusterManager>::TryOpenSharedInternal(&v129) )
      v64 = (__int64)v129;
    else
      v64 = Vml::VmSingletonObject<VmmsCCALClusterManager,ICCALClusterManager>::OpenSharedInternal();
    LeaveCriticalSection(&Vml::VmSingletonObject<VmmsCCALClusterManager,ICCALClusterManager>::gm_SingletonLock);
    if ( !v64 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4DE,
        (unsigned int)"onecore\\vm\\vmms\\main\\exe\\servicemodule.cpp",
        (const char *)0x8007000ELL,
        v126);
    ServiceModule::PreparePhaseTimeCheck(retaddr, TickCount, L"CCALFactory CreateClusterManagerInstance");
    EnterCriticalSection(&Vml::VmSingletonObject<CDPCoordinatorManager<HostCDPCoordinator>,CDPCoordinatorManager<HostCDPCoordinator>>::gm_SingletonLock);
    v129 = 0;
    if ( !(unsigned __int8)Vml::VmSingletonObject<CDPCoordinatorManager<HostCDPCoordinator>,CDPCoordinatorManager<HostCDPCoordinator>>::TryOpenSharedInternal(&v129) )
      Vml::VmSingletonObject<CDPCoordinatorManager<HostCDPCoordinator>,CDPCoordinatorManager<HostCDPCoordinator>>::OpenSharedInternal();
    LeaveCriticalSection(&Vml::VmSingletonObject<CDPCoordinatorManager<HostCDPCoordinator>,CDPCoordinatorManager<HostCDPCoordinator>>::gm_SingletonLock);
    ServiceModule::PreparePhaseTimeCheck(v65, TickCount, L"CDPCoordinatorManager<HostCDPCoordinator> OpenShared");
    EnterCriticalSection(&Vml::VmSingletonObject<CDPCoordinatorManager<CollectionCDPCoordinator>,CDPCoordinatorManager<CollectionCDPCoordinator>>::gm_SingletonLock);
    v129 = 0;
    if ( !(unsigned __int8)Vml::VmSingletonObject<CDPCoordinatorManager<CollectionCDPCoordinator>,CDPCoordinatorManager<CollectionCDPCoordinator>>::TryOpenSharedInternal(&v129) )
      Vml::VmSingletonObject<CDPCoordinatorManager<CollectionCDPCoordinator>,CDPCoordinatorManager<CollectionCDPCoordinator>>::OpenSharedInternal();
    LeaveCriticalSection(&Vml::VmSingletonObject<CDPCoordinatorManager<CollectionCDPCoordinator>,CDPCoordinatorManager<CollectionCDPCoordinator>>::gm_SingletonLock);
    ServiceModule::PreparePhaseTimeCheck(v66, TickCount, L"CDPCoordinatorManager<CollectionCDPCoordinator> OpenShared");
    v67 = Vml::VmSingletonObject<NumaPhysicalTopologyInfo,INumaPhysicalTopologyInfo>::OpenShared();
    if ( !v67 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4F3,
        (unsigned int)"onecore\\vm\\vmms\\main\\exe\\servicemodule.cpp",
        (const char *)0x8007000ELL,
        v126);
    v68 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v67 + 144LL))(v67);
    v70 = v68;
    if ( v68 < 0 )
    {
      v71 = v68 & 0xEFFFFFFF;
      _snwprintf_s<16>(v135, 16, L"%%%%%u", v68 & 0xEFFFFFFF);
      _snwprintf_s<16>(v137, 16, L"0x%08X", v71);
      VmEventWrite<unsigned short (&)[16],unsigned short (&)[16]>(
        &MSVM_VMMS_FAILED_TO_GET_PHYSICAL_TOPOLOGY,
        1u,
        (__int64)v137);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x502,
        (unsigned int)"onecore\\vm\\vmms\\main\\exe\\servicemodule.cpp",
        (const char *)v70,
        v127);
    }
    ServiceModule::PreparePhaseTimeCheck(v69, TickCount, L"Initialize Numa physical topology info");
    if ( (unsigned int)IsVIDRunning() )
    {
      v73 = 1;
    }
    else
    {
      VmEventWriteCommon(&MSVM_VMMS_VID_PROBLEM, 1u, v72, 0, 0, v128);
      v73 = 0;
    }
    if ( *((_DWORD *)v1 + 124) )
    {
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v62 + 336LL))(v62, 3);
      if ( v73 )
        goto LABEL_170;
    }
    else
    {
      if ( v73 )
      {
LABEL_170:
        try
        {
          *((_BYTE *)v1 + 476) = (unsigned int)VmmsVidUtilities::GetHypervisorSchedulerType() == 4;
        }
        catch ( ... )
        {
          wil::details::in1diag3::Log_CaughtException(
            retaddr,
            (void *)0x51F,
            (unsigned int)"onecore\\vm\\vmms\\main\\exe\\servicemodule.cpp",
            v75);
          TickCount = v131;
          v1 = v134;
          goto LABEL_79;
        }
        goto LABEL_79;
      }
      v76 = (unsigned int)((unsigned __int8)HviIsAnyHypervisorPresent() != 0) + 1;
      v77(v62, v76);
    }
LABEL_79:
    ServiceModule::PreparePhaseTimeCheck(v74, TickCount, L"Check for VID and Hypervisor");
    v78 = Vml::VmSingletonObject<VmEthernetConnectionProvider,VmEthernetConnectionProvider>::OpenShared();
    *((_QWORD *)v1 + 43) = v78;
    if ( !v78 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x52D,
        (unsigned int)"onecore\\vm\\vmms\\main\\exe\\servicemodule.cpp",
        (const char *)0x8007000ELL,
        v126);
    ServiceModule::PreparePhaseTimeCheck(v79, TickCount, L"VmEthernetConnectionProvider CreateInstance");
    if ( !Vml::VmSingletonObject<RemoteConnectionListener,RemoteConnectionListener>::OpenShared() )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x9F,
        (unsigned int)"onecore\\vm\\vmms\\remote\\singleportlistener.cpp",
        (const char *)0x8007000ELL,
        v126);
    ServiceModule::PreparePhaseTimeCheck(v80, TickCount, L"RemoteConnectionListener CreateInstance");
    SingleSettingsWatcher::CreateInstance();
    ServiceModule::PreparePhaseTimeCheck(v81, TickCount, L"SingleSettingsWatcher CreateInstance");
    VmmsMigrationManager::CreateInstance();
    ServiceModule::PreparePhaseTimeCheck(v82, TickCount, L"VmmsMigrationManager CreateInstance");
    EnterCriticalSection(&Vml::VmSingletonObject<VmVssWriter,VmVssWriter>::gm_SingletonLock);
    if ( (unsigned __int64)(Vml::VmSingletonObject<VmVssWriter,VmVssWriter>::gm_SingletonInstance - 1) <= 0xFFFFFFFFFFFFFFFDuLL
      && Vml::VmSharableObject::TryAddUser(
           (Vml::VmSharableObject *)(Vml::VmSingletonObject<VmVssWriter,VmVssWriter>::gm_SingletonInstance
                                   + 16
                                   + *(int *)(*(_QWORD *)(Vml::VmSingletonObject<VmVssWriter,VmVssWriter>::gm_SingletonInstance
                                                        + 16)
                                            + 4LL)),
           (unsigned int *)(Vml::VmSingletonObject<VmVssWriter,VmVssWriter>::gm_SingletonInstance + 16)) )
    {
      v83 = Vml::VmSingletonObject<VmVssWriter,VmVssWriter>::gm_SingletonInstance;
    }
    else
    {
      v83 = Vml::VmSingletonObject<VmVssWriter,VmVssWriter>::OpenSharedInternal();
    }
    LeaveCriticalSection(&Vml::VmSingletonObject<VmVssWriter,VmVssWriter>::gm_SingletonLock);
    *((_QWORD *)v1 + 55) = v83;
    ServiceModule::PreparePhaseTimeCheck(v84, TickCount, L"VmVssWriter OpenShared");
    EnterCriticalSection(&Vml::VmSingletonObject<VmmsClusterManager,VmmsClusterManager>::gm_SingletonLock);
    v129 = 0;
    if ( (unsigned __int8)Vml::VmSingletonObject<VmmsClusterManager,VmmsClusterManager>::TryOpenSharedInternal(&v129) )
      v85 = v129;
    else
      v85 = (VmmsClusterManager *)Vml::VmSingletonObject<VmmsClusterManager,VmmsClusterManager>::OpenSharedInternal();
    LeaveCriticalSection(&Vml::VmSingletonObject<VmmsClusterManager,VmmsClusterManager>::gm_SingletonLock);
    *((_QWORD *)v1 + 45) = v85;
    if ( !v85 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x553,
        (unsigned int)"onecore\\vm\\vmms\\main\\exe\\servicemodule.cpp",
        (const char *)0xE,
        v126);
    v86 = VmmsClusterManager::Initialize(v85);
    if ( v86 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x555,
        (unsigned int)"onecore\\vm\\vmms\\main\\exe\\servicemodule.cpp",
        (const char *)(unsigned int)v86,
        v126);
    ServiceModule::PreparePhaseTimeCheck(retaddr, TickCount, L"Initialize Cluster Manager");
    EnterCriticalSection(&Vml::VmSingletonObject<VmmsSynthFcManager,VmmsSynthFcManager>::gm_SingletonLock);
    if ( (unsigned __int64)Vml::VmSingletonObject<VmmsSynthFcManager,VmmsSynthFcManager>::gm_SingletonInstance - 1 <= 0xFFFFFFFFFFFFFFFDuLL
      && Vml::VmSharableObject::TryAddUser(
           (VmmsSynthFcManager *)((char *)Vml::VmSingletonObject<VmmsSynthFcManager,VmmsSynthFcManager>::gm_SingletonInstance
                                + *(int *)(*(_QWORD *)Vml::VmSingletonObject<VmmsSynthFcManager,VmmsSynthFcManager>::gm_SingletonInstance
                                         + 4LL)),
           (unsigned int *)Vml::VmSingletonObject<VmmsSynthFcManager,VmmsSynthFcManager>::gm_SingletonInstance) )
    {
      v87 = Vml::VmSingletonObject<VmmsSynthFcManager,VmmsSynthFcManager>::gm_SingletonInstance;
    }
    else
    {
      v87 = (VmmsSynthFcManager *)Vml::VmSingletonObject<VmmsSynthFcManager,VmmsSynthFcManager>::OpenSharedInternal();
    }
    LeaveCriticalSection(&Vml::VmSingletonObject<VmmsSynthFcManager,VmmsSynthFcManager>::gm_SingletonLock);
    *((_QWORD *)v1 + 46) = v87;
    if ( !v87 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x55F,
        (unsigned int)"onecore\\vm\\vmms\\main\\exe\\servicemodule.cpp",
        (const char *)0xE,
        v126);
    v88 = VmmsSynthFcManager::Initialize(v87);
    if ( v88 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x561,
        (unsigned int)"onecore\\vm\\vmms\\main\\exe\\servicemodule.cpp",
        (const char *)(unsigned int)v88,
        v126);
    ServiceModule::PreparePhaseTimeCheck(retaddr, TickCount, L"Initialize synthetic FC manager");
    EnterCriticalSection(&Vml::VmSingletonObject<FrCtSmartBitmapManager,FrCtSmartBitmapManager>::gm_SingletonLock);
    v129 = 0;
    if ( (unsigned __int8)Vml::VmSingletonObject<FrCtSmartBitmapManager,FrCtSmartBitmapManager>::TryOpenSharedInternal(&v129) )
      v89 = (__int64)v129;
    else
      v89 = Vml::VmSingletonObject<FrCtSmartBitmapManager,FrCtSmartBitmapManager>::OpenSharedInternal();
    LeaveCriticalSection(&Vml::VmSingletonObject<FrCtSmartBitmapManager,FrCtSmartBitmapManager>::gm_SingletonLock);
    *((_QWORD *)v1 + 48) = v89;
    if ( !v89 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x56B,
        (unsigned int)"onecore\\vm\\vmms\\main\\exe\\servicemodule.cpp",
        (const char *)0xE,
        v126);
    std::_Tree<std::_Tmap_traits<Vml::VmGuid,Vml::VmReferencePtr<IVmmsReferencePointGroup,Vml::VmUserReferenceTraits>,std::less<Vml::VmGuid>,std::allocator<std::pair<Vml::VmGuid const,Vml::VmReferencePtr<IVmmsReferencePointGroup,Vml::VmUserReferenceTraits>>>,0>>::clear(v89 + 8);
    ServiceModule::PreparePhaseTimeCheck(v90, TickCount, L"Initialize FR smart bitmap manager");
    EnterCriticalSection(&Vml::VmSingletonObject<FrUndoLogConfigurationManager,FrUndoLogConfigurationManager>::gm_SingletonLock);
    v129 = 0;
    if ( (unsigned __int8)Vml::VmSingletonObject<FrUndoLogConfigurationManager,FrUndoLogConfigurationManager>::TryOpenSharedInternal(&v129) )
      v91 = v129;
    else
      v91 = (FrUndoLogConfigurationManager *)Vml::VmSingletonObject<FrUndoLogConfigurationManager,FrUndoLogConfigurationManager>::OpenSharedInternal();
    LeaveCriticalSection(&Vml::VmSingletonObject<FrUndoLogConfigurationManager,FrUndoLogConfigurationManager>::gm_SingletonLock);
    *((_QWORD *)v1 + 47) = v91;
    if ( !v91 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x578,
        (unsigned int)"onecore\\vm\\vmms\\main\\exe\\servicemodule.cpp",
        (const char *)0xE,
        v126);
    v92 = FrUndoLogConfigurationManager::Initialize(v91);
    if ( v92 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x57B,
        (unsigned int)"onecore\\vm\\vmms\\main\\exe\\servicemodule.cpp",
        (const char *)(unsigned int)v92,
        v126);
    ServiceModule::PreparePhaseTimeCheck(retaddr, TickCount, L"Initialize Undo Log Configuration Manager");
    EnterCriticalSection(&Vml::VmSingletonObject<VmmsFailoverReplicationManager,VmmsFailoverReplicationManager>::gm_SingletonLock);
    v129 = 0;
    if ( (unsigned __int8)Vml::VmSingletonObject<VmmsFailoverReplicationManager,VmmsFailoverReplicationManager>::TryOpenSharedInternal(&v129) )
      v93 = v129;
    else
      v93 = (VmmsFailoverReplicationManager *)Vml::VmSingletonObject<VmmsFailoverReplicationManager,VmmsFailoverReplicationManager>::OpenSharedInternal();
    LeaveCriticalSection(&Vml::VmSingletonObject<VmmsFailoverReplicationManager,VmmsFailoverReplicationManager>::gm_SingletonLock);
    *((_QWORD *)v1 + 49) = v93;
    if ( !v93 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x585,
        (unsigned int)"onecore\\vm\\vmms\\main\\exe\\servicemodule.cpp",
        (const char *)0xE,
        v126);
    v94 = VmmsFailoverReplicationManager::Initialize(v93);
    if ( v94 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x587,
        (unsigned int)"onecore\\vm\\vmms\\main\\exe\\servicemodule.cpp",
        (const char *)(unsigned int)v94,
        v126);
    ServiceModule::PreparePhaseTimeCheck(retaddr, TickCount, L"Initialize Failover Replication manager");
    EnterCriticalSection(&Vml::VmSingletonObject<VmmsFailoverReplicationNetworkManager,VmmsFailoverReplicationNetworkManager>::gm_SingletonLock);
    v129 = 0;
    if ( (unsigned __int8)Vml::VmSingletonObject<VmmsFailoverReplicationNetworkManager,VmmsFailoverReplicationNetworkManager>::TryOpenSharedInternal(&v129) )
      v95 = (__int64)v129;
    else
      v95 = Vml::VmSingletonObject<VmmsFailoverReplicationNetworkManager,VmmsFailoverReplicationNetworkManager>::OpenSharedInternal();
    LeaveCriticalSection(&Vml::VmSingletonObject<VmmsFailoverReplicationNetworkManager,VmmsFailoverReplicationNetworkManager>::gm_SingletonLock);
    *((_QWORD *)v1 + 50) = v95;
    if ( !v95 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x591,
        (unsigned int)"onecore\\vm\\vmms\\main\\exe\\servicemodule.cpp",
        (const char *)0xE,
        v126);
    ServiceModule::PreparePhaseTimeCheck(v96, TickCount, L"Initialize Failover Replication Network manager");
    EnterCriticalSection(&Vml::VmSingletonObject<VmmsFailoverReplicationBrokerManager,IVmmsFailoverReplicationBrokerManager>::gm_SingletonLock);
    v129 = 0;
    if ( (unsigned __int8)Vml::VmSingletonObject<VmmsFailoverReplicationBrokerManager,IVmmsFailoverReplicationBrokerManager>::TryOpenSharedInternal(&v129) )
      v97 = (__int64)v129;
    else
      v97 = Vml::VmSingletonObject<VmmsFailoverReplicationBrokerManager,IVmmsFailoverReplicationBrokerManager>::OpenSharedInternal();
    LeaveCriticalSection(&Vml::VmSingletonObject<VmmsFailoverReplicationBrokerManager,IVmmsFailoverReplicationBrokerManager>::gm_SingletonLock);
    *((_QWORD *)v1 + 51) = v97;
    if ( !v97 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x59C,
        (unsigned int)"onecore\\vm\\vmms\\main\\exe\\servicemodule.cpp",
        (const char *)0xE,
        v126);
    ServiceModule::PreparePhaseTimeCheck(v98, TickCount, L"Initialize Failover Replication Broker Manager");
    EnterCriticalSection(&Vml::VmSingletonObject<VmmsFailoverReplicationEndpointProviderManager,VmmsFailoverReplicationEndpointProviderManager>::gm_SingletonLock);
    v129 = 0;
    if ( (unsigned __int8)Vml::VmSingletonObject<VmmsFailoverReplicationEndpointProviderManager,VmmsFailoverReplicationEndpointProviderManager>::TryOpenSharedInternal(&v129) )
      v99 = (__int64)v129;
    else
      v99 = Vml::VmSingletonObject<VmmsFailoverReplicationEndpointProviderManager,VmmsFailoverReplicationEndpointProviderManager>::OpenSharedInternal();
    LeaveCriticalSection(&Vml::VmSingletonObject<VmmsFailoverReplicationEndpointProviderManager,VmmsFailoverReplicationEndpointProviderManager>::gm_SingletonLock);
    *((_QWORD *)v1 + 52) = v99;
    if ( !v99 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x5A7,
        (unsigned int)"onecore\\vm\\vmms\\main\\exe\\servicemodule.cpp",
        (const char *)0xE,
        v126);
    ServiceModule::PreparePhaseTimeCheck(v100, TickCount, L"Initialize Failover Replication Endpoint Provider Manager");
    EnterCriticalSection(&Vml::VmSingletonObject<ReplicationCoordinatorManager,ReplicationCoordinatorManager>::gm_SingletonLock);
    v129 = 0;
    if ( (unsigned __int8)Vml::VmSingletonObject<ReplicationCoordinatorManager,ReplicationCoordinatorManager>::TryOpenSharedInternal(&v129) )
      v101 = (__int64)v129;
    else
      v101 = Vml::VmSingletonObject<ReplicationCoordinatorManager,ReplicationCoordinatorManager>::OpenSharedInternal();
    LeaveCriticalSection(&Vml::VmSingletonObject<ReplicationCoordinatorManager,ReplicationCoordinatorManager>::gm_SingletonLock);
    *((_QWORD *)v1 + 53) = v101;
    if ( !v101 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x5B2,
        (unsigned int)"onecore\\vm\\vmms\\main\\exe\\servicemodule.cpp",
        (const char *)0xE,
        v126);
    ServiceModule::PreparePhaseTimeCheck(v102, TickCount, L"Initialize Replication Coordinator Manager");
    MountedStorageImageManager::CreateInstance();
    ServiceModule::PreparePhaseTimeCheck(v103, TickCount, L"Initialize MountedStorageImageManager");
    EnterCriticalSection(&Vml::VmSingletonObject<VmmsVmPhuManager,VmmsVmPhuManager>::gm_SingletonLock);
    v129 = 0;
    if ( (unsigned __int8)Vml::VmSingletonObject<VmmsVmPhuManager,VmmsVmPhuManager>::TryOpenSharedInternal(&v129) )
      v104 = (__int64)v129;
    else
      v104 = Vml::VmSingletonObject<VmmsVmPhuManager,VmmsVmPhuManager>::OpenSharedInternal();
    LeaveCriticalSection(&Vml::VmSingletonObject<VmmsVmPhuManager,VmmsVmPhuManager>::gm_SingletonLock);
    *((_QWORD *)v1 + 56) = v104;
    if ( !v104 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x5C3,
        (unsigned int)"onecore\\vm\\vmms\\main\\exe\\servicemodule.cpp",
        (const char *)0xE,
        v126);
    ServiceModule::PreparePhaseTimeCheck(v105, TickCount, L"Initialize VM-PHU Manager");
    v106 = operator new(0x194408u);
    memset_0(v106, 0, 0x194408u);
    Vml::VmSharableObject::VmSharableObject((Vml::VmSharableObject *)v106);
    *v106 = &ProcessorStatisticsBase::`vftable';
    *((_DWORD *)v106 + 20) = 0;
    v106[11] = 0;
    v106[12] = 0;
    *((_DWORD *)v106 + 26) = 0;
    *v106 = &LpStatistics::`vftable';
    *((_OWORD *)v106 + 7) = 0;
    *((_OWORD *)v106 + 8) = 0;
    *((_OWORD *)v106 + 9) = 0;
    v106[20] = 0;
    *((_BYTE *)v106 + 1655760) = 0;
    *((_BYTE *)v106 + 1655808) = 0;
    memset_0(v106 + 21, 0, 0x194328u);
    Vml::VmReferencePtr<VmmsMigratedVm,Vml::VmUserReferenceTraits>::Reset((char *)v1 + 456, v106);
    v107 = LpStatistics::Initialize(*((PVOID *)v1 + 57));
    if ( v107 >= 0 )
    {
      ProcessorStatisticsBase::Start(*((ProcessorStatisticsBase **)v1 + 57));
    }
    else
    {
      Vml::VmReferencePtr<VmmsMigratedVm,Vml::VmUserReferenceTraits>::Reset((char *)v1 + 456, 0);
      if ( (unsigned int)VmlIsDebugTraceEnabled(16481) )
        VmlDebugTrace(
          16481,
          L"%hs: Failed to initialize LpStatistics with HRESULT: %08X",
          "ServiceModule::PrepareToRunSelf",
          (unsigned int)v107);
    }
    ServiceModule::PreparePhaseTimeCheck(v108, TickCount, L"Initialize Logical Processor statistics");
    Vml::VmDelegateInterface<void,>::Dispatch(*v132);
    ServiceModule::PreparePhaseTimeCheck(v109, TickCount, L"Dispatch optional services registrar");
    ServiceModule::InitializeMacAddressRange(v110);
    ServiceModule::PreparePhaseTimeCheck(v111, TickCount, L"Initialize the MAC address range");
    ServiceModule::UpdatePreshutdownTimeout(v1);
    ServiceModule::PreparePhaseTimeCheck(v112, TickCount, L"Update the preshutdown timeout");
    ServiceModule::AdjustInteropNamespaceSecurity(v113);
    ServiceModule::PreparePhaseTimeCheck(v114, TickCount, L"Update the root\\interop namespace security");
    ServiceModule::EnableProcessMitigations(v115);
    ServiceModule::PreparePhaseTimeCheck(v116, TickCount, L"Enable process mitigation");
    *v133 = 1;
    VmEventWriteCommon(&MSVM_VMMS_SCM_STARTUP_INFORMATION, 1u, v117, 0, 0, v128);
    ServiceModule::PreparePhaseTimeCheck(v118, TickCount, L"Startup Finished");
  }
  catch ( ... )
  {
    VmEventWriteCommon(&MSVM_VMMS_SCM_STARTUP_ERROR, 1u, v119, 0, 0, v125);
    v123 = v134;
    try
    {
      ServiceModule::CleanUpFromRunSelf(v134);
      *((_DWORD *)v123 + 117) = 1;
    }
    catch ( ... )
    {
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x611,
        (unsigned int)"onecore\\vm\\vmms\\main\\exe\\servicemodule.cpp",
        v124);
    }
    throw;
  }
}

```

## disassembly

```asm
0x140414400  mov     [rsp+arg_8], rbx
0x140414405  mov     [rsp+arg_10], rsi
0x14041440a  push    rdi
0x14041440b  push    r12
0x14041440d  push    r13
0x14041440f  push    r14
0x140414411  push    r15
0x140414413  sub     rsp, 0C0h
0x14041441a  mov     rax, cs:__security_cookie
0x140414421  xor     rax, rsp
0x140414424  mov     [rsp+0E8h+var_38], rax
0x14041442c  mov     r14, rcx
0x14041442f  mov     [rsp+0E8h+var_80], rcx
0x140414434  lea     rax, [rcx+1D0h]
0x14041443b  mov     [rsp+0E8h+var_88], rax
0x140414440  xor     edi, edi
0x140414442  mov     [rax], edi
0x140414444  call    cs:__imp_GetTickCount
0x14041444b  nop     dword ptr [rax+rax+00h]
0x140414450  mov     esi, eax
0x140414452  xor     r9d, r9d; lpName
0x140414455  xor     r8d, r8d; bInitialState
0x140414458  xor     edx, edx; bManualReset
0x14041445a  xor     ecx, ecx; lpEventAttributes
0x14041445c  call    cs:__imp_CreateEventW
0x140414463  nop     dword ptr [rax+rax+00h]
0x140414468  mov     [r14+58h], rax
0x14041446c  test    rax, rax
0x14041446f  jnz     short loc_14041448A
0x140414471  mov     rcx, [rsp+0E8h]; this
0x140414479  lea     r8, aOnecoreVmCommo_10; "onecore\\vm\\common\\vml\\VmModules.h"
0x140414480  mov     edx, 744h; void *
0x140414485  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14041448a  mov     [rsp+0E8h+var_98], esi
0x14041448e  call    ?OpenShared@VmMiApplication@Vml@@SAPEAV12@XZ; Vml::VmMiApplication::OpenShared(void)
0x140414493  mov     [r14+118h], rax
0x14041449a  lea     r8, aCreateMiApplic; "Create MI_Application singleton."
0x1404144a1  mov     edx, esi; unsigned int
0x1404144a3  call    ?PreparePhaseTimeCheck@ServiceModule@@AEAAXKPEBG@Z; ServiceModule::PreparePhaseTimeCheck(ulong,ushort const *)
0x1404144a8  call    ?RegisterVmGroupSids@ServiceModule@@AEAAXXZ; ServiceModule::RegisterVmGroupSids(void)
0x1404144ad  call    ?GrantVmGroupSidSynchronizeAccessToSelf@ServiceModule@@AEAAXXZ; ServiceModule::GrantVmGroupSidSynchronizeAccessToSelf(void)
0x1404144b2  call    ?AdjustVmGroupPrivileges@ServiceModule@@AEAAXXZ; ServiceModule::AdjustVmGroupPrivileges(void)
0x1404144b7  lea     r8, aRegisterSids; "Register SIDs"
0x1404144be  mov     edx, esi; unsigned int
0x1404144c0  call    ?PreparePhaseTimeCheck@ServiceModule@@AEAAXKPEBG@Z; ServiceModule::PreparePhaseTimeCheck(ulong,ushort const *)
0x1404144c5  mov     r15d, 140h
0x1404144cb  mov     ecx, r15d; Size
0x1404144ce  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1404144d3  mov     rbx, rax
0x1404144d6  mov     r8d, r15d; Size
0x1404144d9  xor     edx, edx; Val
0x1404144db  mov     rcx, rax; void *
0x1404144de  call    memset_0
0x1404144e3  mov     rcx, rbx; this
0x1404144e6  call    ??0VmOrderedThreadpoolDispatcher@Vml@@QEAA@XZ; Vml::VmOrderedThreadpoolDispatcher::VmOrderedThreadpoolDispatcher(void)
0x1404144eb  mov     [r14+138h], rax
0x1404144f2  mov     rcx, [rax+8]
0x1404144f6  movsxd  rdx, dword ptr [rcx+4]; struct type_info *
0x1404144fa  lea     rcx, [rax+8]
0x1404144fe  add     rcx, rdx; this
0x140414501  call    ?AddUserInternal@VmSharableObject@Vml@@AEAAKAEBVtype_info@@@Z; Vml::VmSharableObject::AddUserInternal(type_info const &)
0x140414506  mov     ecx, r15d; Size
0x140414509  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14041450e  mov     rbx, rax
0x140414511  mov     r8d, r15d; Size
0x140414514  xor     edx, edx; Val
0x140414516  mov     rcx, rax; void *
0x140414519  call    memset_0
0x14041451e  mov     rcx, rbx; this
0x140414521  call    ??0VmOrderedThreadpoolDispatcher@Vml@@QEAA@XZ; Vml::VmOrderedThreadpoolDispatcher::VmOrderedThreadpoolDispatcher(void)
0x140414526  mov     [r14+140h], rax
0x14041452d  mov     rcx, [rax+8]
0x140414531  movsxd  rdx, dword ptr [rcx+4]; struct type_info *
0x140414535  lea     rcx, [rax+8]
0x140414539  add     rcx, rdx; this
0x14041453c  call    ?AddUserInternal@VmSharableObject@Vml@@AEAAKAEBVtype_info@@@Z; Vml::VmSharableObject::AddUserInternal(type_info const &)
0x140414541  mov     r15d, 78h ; 'x'
0x140414547  mov     ecx, r15d; Size
0x14041454a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14041454f  mov     rbx, rax
0x140414552  mov     r8d, r15d; Size
0x140414555  xor     edx, edx; Val
0x140414557  mov     rcx, rax; void *
0x14041455a  call    memset_0
0x14041455f  mov     rcx, rbx
0x140414562  call    ??0?$VmMethodDelegate@VServiceModule@@X$$V@Vml@@QEAA@XZ; Vml::VmMethodDelegate<ServiceModule,void,>::VmMethodDelegate<ServiceModule,void,>(void)
0x140414567  lea     rdx, [r14+128h]; struct type_info *
0x14041456e  mov     [rsp+0E8h+var_90], rdx
0x140414573  mov     [rdx], rax
0x140414576  mov     [rax+68h], r14
0x14041457a  lea     rcx, ?RegisterOptionalServices@ServiceModule@@AEAAXXZ; ServiceModule::RegisterOptionalServices(void)
0x140414581  mov     [rax+70h], rcx
0x140414585  mov     rcx, [rdx]
0x140414588  mov     rax, [r14+140h]
0x14041458f  mov     [rcx+58h], rax
0x140414593  mov     rcx, [rdx]; this
0x140414596  call    ?AddUserInternal@VmSharableObject@Vml@@AEAAKAEBVtype_info@@@Z; Vml::VmSharableObject::AddUserInternal(type_info const &)
0x14041459b  mov     ecx, r15d; Size
0x14041459e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1404145a3  mov     rbx, rax
0x1404145a6  mov     r8d, r15d; Size
0x1404145a9  xor     edx, edx; Val
0x1404145ab  mov     rcx, rax; void *
0x1404145ae  call    memset_0
0x1404145b3  mov     rcx, rbx
0x1404145b6  call    ??0?$VmMethodDelegate@VServiceModule@@X$$V@Vml@@QEAA@XZ; Vml::VmMethodDelegate<ServiceModule,void,>::VmMethodDelegate<ServiceModule,void,>(void)
0x1404145bb  mov     [r14+130h], rax
0x1404145c2  mov     [rax+68h], r14
0x1404145c6  lea     rcx, ?PerformStartupActions@ServiceModule@@AEAAXXZ; ServiceModule::PerformStartupActions(void)
0x1404145cd  mov     [rax+70h], rcx
0x1404145d1  mov     rcx, [r14+130h]
0x1404145d8  mov     rax, [r14+138h]
0x1404145df  mov     [rcx+58h], rax
0x1404145e3  mov     rcx, [r14+130h]; this
0x1404145ea  call    ?AddUserInternal@VmSharableObject@Vml@@AEAAKAEBVtype_info@@@Z; Vml::VmSharableObject::AddUserInternal(type_info const &)
0x1404145ef  mov     ecx, r15d; Size
0x1404145f2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1404145f7  mov     rbx, rax
0x1404145fa  mov     r8d, r15d; Size
0x1404145fd  xor     edx, edx; Val
0x1404145ff  mov     rcx, rax; void *
0x140414602  call    memset_0
0x140414607  mov     rcx, rbx
0x14041460a  call    ??0?$VmMethodDelegate@VServiceModule@@X$$V@Vml@@QEAA@XZ; Vml::VmMethodDelegate<ServiceModule,void,>::VmMethodDelegate<ServiceModule,void,>(void)
0x14041460f  mov     [r14+120h], rax
0x140414616  mov     [rax+68h], r14
0x14041461a  lea     rcx, ?UnRegisterOptionalServices@ServiceModule@@AEAAXXZ; ServiceModule::UnRegisterOptionalServices(void)
0x140414621  mov     [rax+70h], rcx
0x140414625  mov     rcx, [r14+120h]
0x14041462c  mov     rax, [r14+140h]
0x140414633  mov     [rcx+58h], rax
0x140414637  mov     rcx, [r14+120h]; this
0x14041463e  call    ?AddUserInternal@VmSharableObject@Vml@@AEAAKAEBVtype_info@@@Z; Vml::VmSharableObject::AddUserInternal(type_info const &)
0x140414643  mov     ecx, r15d; Size
0x140414646  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14041464b  mov     rbx, rax
0x14041464e  mov     r8d, r15d; Size
0x140414651  xor     edx, edx; Val
0x140414653  mov     rcx, rax; void *
0x140414656  call    memset_0
0x14041465b  mov     rcx, rbx
0x14041465e  call    ??0?$VmMethodDelegate@VServiceModule@@X$$V@Vml@@QEAA@XZ; Vml::VmMethodDelegate<ServiceModule,void,>::VmMethodDelegate<ServiceModule,void,>(void)
0x140414663  mov     [r14+148h], rax
0x14041466a  mov     [rax+68h], r14
0x14041466e  lea     rcx, ?HandleServiceStop@ServiceModule@@AEAAXXZ; ServiceModule::HandleServiceStop(void)
0x140414675  mov     [rax+70h], rcx
0x140414679  mov     rcx, [r14+148h]
0x140414680  mov     rax, [r14+138h]
0x140414687  mov     [rcx+58h], rax
0x14041468b  mov     rcx, [r14+148h]; this
0x140414692  call    ?AddUserInternal@VmSharableObject@Vml@@AEAAKAEBVtype_info@@@Z; Vml::VmSharableObject::AddUserInternal(type_info const &)
0x140414697  mov     ecx, r15d; Size
0x14041469a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14041469f  mov     rbx, rax
0x1404146a2  mov     r8d, r15d; Size
0x1404146a5  xor     edx, edx; Val
0x1404146a7  mov     rcx, rax; void *
0x1404146aa  call    memset_0
0x1404146af  mov     rcx, rbx
0x1404146b2  call    ??0?$VmMethodDelegate@VServiceModule@@X$$V@Vml@@QEAA@XZ; Vml::VmMethodDelegate<ServiceModule,void,>::VmMethodDelegate<ServiceModule,void,>(void)
0x1404146b7  mov     [r14+150h], rax
0x1404146be  mov     [rax+68h], r14
0x1404146c2  lea     rcx, ?HandleServiceShutdown@ServiceModule@@AEAAXXZ; ServiceModule::HandleServiceShutdown(void)
0x1404146c9  mov     [rax+70h], rcx
0x1404146cd  mov     rcx, [r14+150h]
0x1404146d4  mov     rax, [r14+138h]
0x1404146db  mov     [rcx+58h], rax
0x1404146df  mov     rcx, [r14+150h]; this
0x1404146e6  call    ?AddUserInternal@VmSharableObject@Vml@@AEAAKAEBVtype_info@@@Z; Vml::VmSharableObject::AddUserInternal(type_info const &)
0x1404146eb  lea     r8, aDelegateInit; "Delegate Init"
0x1404146f2  mov     edx, esi; unsigned int
0x1404146f4  call    ?PreparePhaseTimeCheck@ServiceModule@@AEAAXKPEBG@Z; ServiceModule::PreparePhaseTimeCheck(ulong,ushort const *)
0x1404146f9  xor     r8d, r8d
0x1404146fc  lea     edx, [r15-74h]
0x140414700  mov     rcx, r14
0x140414703  call    ?SetServiceState@?$VmServiceModule@VServiceModule@@@Vml@@QEAAXII@Z; Vml::VmServiceModule<ServiceModule>::SetServiceState(uint,uint)
0x140414708  lea     r8, aServiceSetToRu; "Service set to running"
0x14041470f  mov     edx, esi; unsigned int
0x140414711  call    ?PreparePhaseTimeCheck@ServiceModule@@AEAAXKPEBG@Z; ServiceModule::PreparePhaseTimeCheck(ulong,ushort const *)
0x140414716  call    IsSystemUpgradeInProgress
0x14041471b  mov     ebx, eax
0x14041471d  call    ?IsSystemSetupInProgress@ServiceModule@@AEAAHXZ; ServiceModule::IsSystemSetupInProgress(void)
0x140414722  mov     r15d, eax
0x140414725  call    IsServicingInProgress
0x14041472a  mov     r12d, eax
0x14041472d  test    ebx, ebx
0x14041472f  jnz     short loc_140414757
0x140414731  test    r15d, r15d
0x140414734  jnz     short loc_14041474E
0x140414736  test    eax, eax
0x140414738  jz      short loc_140414743
0x14041473a  lea     rdx, aServicing; "servicing"
0x140414741  jmp     short loc_14041475E
0x140414743  mov     r13d, 1
0x140414749  jmp     loc_140414904
0x14041474e  lea     rdx, aSetup; "setup"
0x140414755  jmp     short loc_14041475E
0x140414757  lea     rdx, aUpgrade_0; "upgrade"
0x14041475e  lea     rcx, [rsp+0E8h+var_78]
0x140414763  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140414768  nop
0x140414769  mov     ebx, edi
0x14041476b  lea     rax, [rsp+0E8h+var_78]
0x140414770  cmp     [rsp+0E8h+var_60], 7
0x140414779  cmova   rax, [rsp+0E8h+var_78]
0x14041477f  mov     [rsp+0E8h+var_B8], rax
0x140414784  lea     r9, [rsp+0E8h+var_B8]
0x140414789  mov     r13d, 1
0x14041478f  mov     edx, r13d; unsigned int
0x140414792  lea     rcx, MSVM_VMMS_SCM_WAIT_FOR_SERVICING_OPERATION_INFO; EventDescriptor
0x140414799  call    ??$VmEventWrite@PEBG@@YAXPEBU_EVENT_DESCRIPTOR@@IAEBU_GUID@@$$QEAPEBG@Z; VmEventWrite<ushort const *>(_EVENT_DESCRIPTOR const *,uint,_GUID const &,ushort const * &&)
0x14041479e  test    r12d, r12d
0x1404147a1  jz      short loc_1404147B1
0x1404147a3  call    cs:__imp_GetTickCount
0x1404147aa  nop     dword ptr [rax+rax+00h]
0x1404147af  mov     ebx, eax
0x1404147b1  lea     r8, [rsp+0E8h+var_78]
0x1404147b6  lea     rdx, aWaitingForSyst; "Waiting for system "
0x1404147bd  lea     rcx, [rsp+0E8h+var_B8]
0x1404147c2  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBGAEBV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring const &)
0x1404147c7  cmp     qword ptr [rax+18h], 7
0x1404147cc  jbe     short loc_1404147D1
0x1404147ce  mov     rax, [rax]
0x1404147d1  mov     r8, rax; unsigned __int16 *
0x1404147d4  mov     edx, esi; unsigned int
0x1404147d6  call    ?PreparePhaseTimeCheck@ServiceModule@@AEAAXKPEBG@Z; ServiceModule::PreparePhaseTimeCheck(ulong,ushort const *)
0x1404147db  lea     rcx, [rsp+0E8h+var_B8]
0x1404147e0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1404147e5  call    ?IsSystemSetupInProgress@ServiceModule@@AEAAHXZ; ServiceModule::IsSystemSetupInProgress(void)
0x1404147ea  test    eax, eax
0x1404147ec  jnz     short loc_140414800
0x1404147ee  call    IsSystemUpgradeInProgress
0x1404147f3  test    eax, eax
0x1404147f5  jnz     short loc_140414800
0x1404147f7  call    IsServicingInProgress
0x1404147fc  test    eax, eax
0x1404147fe  jz      short loc_140414872
0x140414800  cmp     [r14+1E0h], edi
0x140414807  jnz     loc_14041576B
0x14041480d  cmp     [r14+1E4h], edi
0x140414814  jnz     loc_14041576B
0x14041481a  mov     ecx, 3E8h; dwMilliseconds
0x14041481f  call    cs:__imp_Sleep
0x140414826  nop     dword ptr [rax+rax+00h]
0x14041482b  test    r12d, r12d
0x14041482e  jz      short loc_1404147E5
0x140414830  call    cs:__imp_GetTickCount
0x140414837  nop     dword ptr [rax+rax+00h]
0x14041483c  sub     eax, ebx
0x14041483e  cmp     eax, 927C0h
0x140414843  jbe     short loc_1404147E5
0x140414845  lea     rax, [rsp+0E8h+var_78]
0x14041484a  cmp     [rsp+0E8h+var_60], 7
0x140414853  cmova   rax, [rsp+0E8h+var_78]
0x140414859  mov     [rsp+0E8h+var_B8], rax
0x14041485e  lea     r9, [rsp+0E8h+var_B8]
0x140414863  mov     edx, r13d; unsigned int
0x140414866  lea     rcx, MSVM_VMMS_SCM_SERVICING_OPERATION_TIMEOUT_INFO; EventDescriptor
0x14041486d  call    ??$VmEventWrite@PEBG@@YAXPEBU_EVENT_DESCRIPTOR@@IAEBU_GUID@@$$QEAPEBG@Z; VmEventWrite<ushort const *>(_EVENT_DESCRIPTOR const *,uint,_GUID const &,ushort const * &&)
0x140414872  lea     rax, [rsp+0E8h+var_78]
0x140414877  cmp     [rsp+0E8h+var_60], 7
0x140414880  cmova   rax, [rsp+0E8h+var_78]
0x140414886  mov     [rsp+0E8h+var_B8], rax
0x14041488b  lea     r9, [rsp+0E8h+var_B8]
0x140414890  mov     edx, r13d; unsigned int
0x140414893  lea     rcx, MSVM_VMMS_SCM_SERVICING_OPERATION_COMPLETE_INFO; EventDescriptor
0x14041489a  call    ??$VmEventWrite@PEBG@@YAXPEBU_EVENT_DESCRIPTOR@@IAEBU_GUID@@$$QEAPEBG@Z; VmEventWrite<ushort const *>(_EVENT_DESCRIPTOR const *,uint,_GUID const &,ushort const * &&)
0x14041489f  lea     r8, [rsp+0E8h+var_78]
0x1404148a4  lea     rdx, aSystem_0; "System "
0x1404148ab  lea     rcx, [rsp+0E8h+var_58]
0x1404148b3  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBGAEBV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring const &)
0x1404148b8  nop
0x1404148b9  lea     r8, aComplete; " complete"
0x1404148c0  mov     rdx, rax
0x1404148c3  lea     rcx, [rsp+0E8h+var_B8]
0x1404148c8  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1404148cd  cmp     qword ptr [rax+18h], 7
0x1404148d2  jbe     short loc_1404148D7
0x1404148d4  mov     rax, [rax]
0x1404148d7  mov     r8, rax; unsigned __int16 *
0x1404148da  mov     edx, esi; unsigned int
0x1404148dc  call    ?PreparePhaseTimeCheck@ServiceModule@@AEAAXKPEBG@Z; ServiceModule::PreparePhaseTimeCheck(ulong,ushort const *)
0x1404148e1  lea     rcx, [rsp+0E8h+var_B8]
0x1404148e6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1404148eb  nop
0x1404148ec  lea     rcx, [rsp+0E8h+var_58]
0x1404148f4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1404148f9  nop
0x1404148fa  lea     rcx, [rsp+0E8h+var_78]
0x1404148ff  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140414904  mov     ecx, 228h; Size
0x140414909  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14041490e  mov     r15, rax
0x140414911  mov     [rsp+0E8h+var_B8], rax
0x140414916  lea     rcx, [rax+8]; void *
0x14041491a  xor     edx, edx; Val
0x14041491c  mov     r8d, 220h; Size
0x140414922  call    memset_0
0x140414927  or      r12, 0FFFFFFFFFFFFFFFFh
0x14041492b  mov     [r15], r12
  ... truncated ...
```
