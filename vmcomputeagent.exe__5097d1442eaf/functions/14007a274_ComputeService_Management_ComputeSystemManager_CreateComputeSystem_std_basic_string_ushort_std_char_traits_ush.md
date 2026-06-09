# ComputeService::Management::ComputeSystemManager::CreateComputeSystem(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,IVmHandleBrokerManager *,void *,ComputeService::Management::ServerOperationProperties)

- ea: `0x14007a274`
- end: `0x14007b049`
- name: `?CreateComputeSystem@ComputeSystemManager@Management@ComputeService@@QEAA?AUCreateSystemResult@23@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0PEAUIVmHandleBrokerManager@@PEAXUServerOperationProperties@23@@Z`
- size: `3541`
- prototype: ``
- caller_count: `1`
- callee_count: `31`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140051428`

## callees

- `0x1400024b0`
- `0x140005360`
- `0x1400056fc`
- `0x140006098`
- `0x140008760`
- `0x14000aeec`
- `0x14000ea60`
- `0x140027858`
- `0x14002c6cc`
- `0x14004199c`
- `0x14004ea24`
- `0x14004eda8`
- `0x1400651ac`
- `0x140066c08`
- `0x1400727b0`
- `0x140073078`
- `0x1400730a8`
- `0x140073708`
- `0x1400746c0`
- `0x1400750f8`
- `0x14007a274`
- `0x14007b050`
- `0x14007b16c`
- `0x14007bed8`
- `0x14007c054`
- `0x14007d038`
- `0x1400dc6e8`
- `0x1400dd2fc`
- `0x1400f4e40`
- `0x1400f4eb8`
- `0x1400fe010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x14007a669`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x14007a669`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14007a429`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14007a429`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14007a445`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14007a445`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14007a3ea`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14007a3ea`

## string_xrefs

- `0x14007afbb`: `onecore\vm\compute\management\orchestration\shared\OrchestratorRegistry.h`
- `0x14007a316`: `ComputeSystemManager_Create`
- `0x14007a729`: `onecore\vm\compute\management\computesystem\computesystemmanager.cpp`
- `0x14007af8b`: `onecore\vm\compute\management\computesystem\computesystemmanager.cpp`
- `0x14007afa3`: `onecore\vm\compute\management\computesystem\computesystemmanager.cpp`
- `0x14007afd3`: `onecore\vm\compute/management/orchestration/shared/OrchestratorRegistry.h`
- `0x14007b034`: `onecore\vm\compute/management/orchestration/shared/OrchestratorRegistry.h`
- `0x14007afee`: `onecore\vm\compute\management\computesystem\ComputeSystem.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall ComputeService::Management::ComputeSystemManager::CreateComputeSystem(
        RTL_SRWLOCK *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        __int64 a7)
{
  const unsigned __int16 *v11; // rdi
  const unsigned __int16 *v12; // r12
  PVOID v13; // rdi
  _QWORD *v14; // rdx
  __int64 v15; // rcx
  char v16; // di
  PSRWLOCK *Ptr; // r12
  __int64 *v18; // rbx
  char *v19; // rdi
  PSRWLOCK *v20; // r13
  __int64 v21; // rdx
  __int64 v22; // r8
  PSRWLOCK v23; // rax
  PSRWLOCK v24; // rcx
  volatile signed __int32 *v25; // rbx
  _DWORD *v26; // r12
  volatile signed __int32 *v27; // rbx
  _QWORD *v28; // r12
  __int64 v29; // rcx
  _QWORD *v30; // rdx
  __int64 *v31; // rbx
  __int64 v32; // rcx
  __int64 v33; // rax
  __int64 v34; // rcx
  __int64 v35; // r9
  __int128 *v36; // rax
  __int64 v37; // rcx
  volatile signed __int32 *v38; // rbx
  __int128 *v39; // rcx
  __int64 v40; // rax
  __int64 v41; // rbx
  __int64 v42; // r8
  _QWORD *v43; // rax
  char v44; // cl
  char v45; // cl
  __int64 v46; // rcx
  volatile signed __int32 *v47; // rbx
  __int64 (__fastcall *v48)(__int64, __int128 *, _OWORD *, _QWORD, _QWORD *); // rbx
  _QWORD *v49; // r15
  __int64 v50; // rdx
  __int64 v51; // rcx
  __int64 v52; // rax
  char v53; // si
  volatile signed __int32 *v54; // rbx
  __int64 v55; // rcx
  volatile signed __int32 *v56; // rbx
  volatile signed __int32 *v57; // rbx
  volatile signed __int32 *v58; // rbx
  int v60; // [rsp+20h] [rbp-E0h]
  int *v61; // [rsp+20h] [rbp-E0h]
  __int128 v62; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v63; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v64; // [rsp+60h] [rbp-A0h]
  __int64 v65; // [rsp+70h] [rbp-90h]
  __int64 v66; // [rsp+78h] [rbp-88h]
  _OWORD v67[3]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v68; // [rsp+B8h] [rbp-48h]
  _QWORD v69[7]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD *v70; // [rsp+F8h] [rbp-8h]
  _BYTE v71[64]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v72[2]; // [rsp+140h] [rbp+40h] BYREF
  __int64 v73; // [rsp+150h] [rbp+50h] BYREF
  int v74[4]; // [rsp+158h] [rbp+58h] BYREF
  __int64 v75; // [rsp+168h] [rbp+68h]
  __int64 v76; // [rsp+170h] [rbp+70h]
  __int128 v77; // [rsp+178h] [rbp+78h] BYREF
  __int128 v78; // [rsp+188h] [rbp+88h] BYREF
  _QWORD v79[2]; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v80; // [rsp+1B0h] [rbp+B0h]
  int v81; // [rsp+1B8h] [rbp+B8h]
  int v82; // [rsp+1BCh] [rbp+BCh]
  _QWORD v83[2]; // [rsp+1C0h] [rbp+C0h] BYREF
  __int64 v84; // [rsp+1D0h] [rbp+D0h]
  __int64 v85; // [rsp+1D8h] [rbp+D8h]
  _QWORD v86[2]; // [rsp+1E0h] [rbp+E0h] BYREF
  __int64 v87; // [rsp+1F0h] [rbp+F0h]
  unsigned __int64 v88; // [rsp+1F8h] [rbp+F8h]
  int v89; // [rsp+200h] [rbp+100h]
  char v90; // [rsp+208h] [rbp+108h]
  void **v91; // [rsp+210h] [rbp+110h] BYREF
  int v92; // [rsp+218h] [rbp+118h] BYREF
  char v93; // [rsp+21Ch] [rbp+11Ch]
  int v94; // [rsp+240h] [rbp+140h] BYREF
  const char *v95; // [rsp+248h] [rbp+148h]
  __int64 v96; // [rsp+250h] [rbp+150h]
  char v97; // [rsp+258h] [rbp+158h]
  int v98; // [rsp+260h] [rbp+160h]
  char v99[152]; // [rsp+268h] [rbp+168h] BYREF
  __int64 v100; // [rsp+300h] [rbp+200h]
  __int64 v101; // [rsp+308h] [rbp+208h]
  int v102; // [rsp+310h] [rbp+210h]
  __int64 v103; // [rsp+318h] [rbp+218h]
  int *v104; // [rsp+320h] [rbp+220h]
  __int64 v105; // [rsp+328h] [rbp+228h]
  __int64 v106; // [rsp+330h] [rbp+230h]
  void ***v107; // [rsp+338h] [rbp+238h]
  __int64 v108; // [rsp+340h] [rbp+240h]
  int v109; // [rsp+348h] [rbp+248h]
  int *v110; // [rsp+350h] [rbp+250h]
  char v111; // [rsp+358h] [rbp+258h]
  __int128 v112; // [rsp+360h] [rbp+260h] BYREF
  __int64 v113; // [rsp+370h] [rbp+270h]
  __int64 v114; // [rsp+378h] [rbp+278h]
  __int64 v115; // [rsp+380h] [rbp+280h]
  __int128 v116; // [rsp+388h] [rbp+288h] BYREF
  __int64 v117; // [rsp+398h] [rbp+298h]
  unsigned __int64 v118; // [rsp+3A0h] [rbp+2A0h]
  __int64 v119; // [rsp+3A8h] [rbp+2A8h] BYREF
  __int128 v120; // [rsp+3B0h] [rbp+2B0h]
  __int128 v121; // [rsp+3C0h] [rbp+2C0h]
  __int128 v122; // [rsp+3D0h] [rbp+2D0h]
  int v123; // [rsp+3E0h] [rbp+2E0h]
  _BYTE v124[776]; // [rsp+3E8h] [rbp+2E8h] BYREF
  _BYTE v125[3248]; // [rsp+6F0h] [rbp+5F0h] BYREF
  __int128 v126; // [rsp+13A0h] [rbp+12A0h] BYREF
  __int64 v127; // [rsp+13B0h] [rbp+12B0h]
  __int64 v128; // [rsp+13B8h] [rbp+12B8h]
  wil::details::in1diag3 *retaddr; // [rsp+1418h] [rbp+1318h]

  v72[0] = (__int64)a1;
  v66 = a7;
  v76 = a7;
  memset_0(&v91, 0, 0x150u);
  if ( *(_QWORD *)(a4 + 24) <= 7u )
    v11 = (const unsigned __int16 *)a4;
  else
    v11 = *(const unsigned __int16 **)a4;
  v12 = (const unsigned __int16 *)a3;
  if ( *(_QWORD *)(a3 + 24) > 7u )
    v12 = *(const unsigned __int16 **)a3;
  v92 = 0;
  v93 = 0;
  v97 = 0;
  v94 = 0;
  v95 = "ComputeSystemManager_Create";
  v96 = 0;
  v98 = 0;
  v100 = 0;
  v101 = 0;
  memset_0(v99, 0, sizeof(v99));
  v102 = 1;
  v103 = 0;
  v104 = &v92;
  v105 = 0;
  v106 = 0;
  v107 = &v91;
  v108 = 0;
  v109 = 0;
  v110 = &v94;
  v111 = 0;
  v91 = &ComputeService::Diagnostics::TraceProvider::ComputeSystemManager_Create::`vftable';
  ComputeService::Diagnostics::TraceProvider::ComputeSystemManager_Create::StartActivity(
    (ComputeService::Diagnostics::TraceProvider::ComputeSystemManager_Create *)&v91,
    v12,
    v11);
  if ( *(_DWORD *)(a7 + 24) != 1 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0xCB,
      (unsigned int)"onecore\\vm\\compute\\management\\computesystem\\computesystemmanager.cpp",
      (const char *)0x80070057LL,
      v60);
  AcquireSRWLockShared(a1 + 11);
  std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,Vml::CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_lower_bound<std::wstring>(
    &a1[9],
    &v62,
    a3);
  v13 = (PVOID)v63;
  if ( *(_BYTE *)(v63 + 25) )
    goto LABEL_16;
  v14 = (_QWORD *)(v63 + 32);
  if ( *(_QWORD *)(v63 + 56) > 7u )
    v14 = (_QWORD *)*v14;
  v15 = *(_QWORD *)(a3 + 24) <= 7u ? a3 : *(_QWORD *)a3;
  if ( (int)_o__wcsicmp(v15, v14) < 0 || v13 == a1[9].Ptr )
LABEL_16:
    v16 = 0;
  else
    v16 = 1;
  ReleaseSRWLockShared(a1 + 11);
  if ( v16 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD2,
      (unsigned int)"onecore\\vm\\compute\\management\\computesystem\\computesystemmanager.cpp",
      (const char *)0xC037010FLL,
      v60);
  *(_OWORD *)v74 = 0;
  v75 = 0;
  Ptr = (PSRWLOCK *)a1[15].Ptr;
  v18 = (__int64 *)ComputeService::Diagnostics::DiagnosticCacheInner::AddSystem(*Ptr);
  v19 = (char *)operator new(0x30u);
  *(_QWORD *)&v77 = v19;
  *(_OWORD *)v19 = 0;
  *((_DWORD *)v19 + 2) = 1;
  *((_DWORD *)v19 + 3) = 1;
  *(_QWORD *)v19 = &std::_Ref_count_obj2<ComputeService::Diagnostics::SystemEntry>::`vftable';
  v20 = (PSRWLOCK *)(v19 + 16);
  v21 = *v18;
  v22 = v18[1];
  *v18 = 0;
  v18[1] = 0;
  v23 = Ptr[1];
  if ( v23 )
    _InterlockedIncrement((volatile signed __int32 *)&v23[1]);
  v24 = Ptr[1];
  *v20 = *Ptr;
  *((_QWORD *)v19 + 3) = v24;
  *((_QWORD *)v19 + 4) = v21;
  *((_QWORD *)v19 + 5) = v22;
  *(_QWORD *)&v77 = v19 + 16;
  *((_QWORD *)&v77 + 1) = v19;
  v25 = (volatile signed __int32 *)*((_QWORD *)&v62 + 1);
  if ( *((_QWORD *)&v62 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v62 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
      if ( _InterlockedExchangeAdd(v25 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
    }
  }
  v26 = operator new(0x40u);
  *(_QWORD *)&v77 = v26;
  *(_OWORD *)v26 = 0;
  v26[2] = 1;
  v26[3] = 1;
  *(_QWORD *)v26 = &std::_Ref_count_obj2<ComputeService::Management::ServerOperationTracker>::`vftable';
  *((_QWORD *)v26 + 2) = 0;
  *((_QWORD *)v26 + 3) = 0;
  *((_QWORD *)v26 + 4) = 0;
  *((_QWORD *)v26 + 5) = 0;
  *((_QWORD *)v26 + 6) = 0;
  *((_QWORD *)v26 + 7) = 0;
  _InterlockedIncrement((volatile signed __int32 *)v19 + 2);
  *((_QWORD *)v26 + 6) = v20;
  *((_QWORD *)v26 + 7) = v19;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v19 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(void *))v19)(v19);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v19 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(char *))(*(_QWORD *)v19 + 8LL))(v19);
  }
  *(_QWORD *)v74 = v26 + 4;
  v27 = *(volatile signed __int32 **)&v74[2];
  *(_QWORD *)&v74[2] = v26;
  if ( v27 )
  {
    if ( _InterlockedExchangeAdd(v27 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v27)(v27);
      if ( _InterlockedExchangeAdd(v27 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 8LL))(v27);
    }
  }
  v75 = 0;
  v78 = 0;
  v69[0] = &std::_Func_impl_no_alloc<_lambda_7ff8c2eaf54bbf08262be3efa113d168_,void,std::wstring const &,ComputeService::Management::ComputeSystemNotificationInfo_2 const &>::`vftable';
  v28 = (_QWORD *)v72[0];
  v69[1] = v72[0];
  v70 = v69;
  *(_QWORD *)&v77 = v69;
  if ( *(_QWORD *)(a3 + 24) > 7u )
    a3 = *(_QWORD *)a3;
  v72[0] = a3;
  v29 = v28[8];
  if ( !v29 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  v61 = v74;
  (*(void (__fastcall **)(__int64, __int128 *, __int64 *, __int64))(*(_QWORD *)v29 + 16LL))(v29, &v78, v72, a4);
  if ( v70 )
  {
    v30 = v69;
    LOBYTE(v30) = v70 != v69;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v70 + 32LL))(v70, v30);
    v70 = 0;
  }
  v31 = (__int64 *)v78;
  if ( !ComputeService::Management::OrchestratorRegistrar<ComputeService::Management::IComputeSystemOrchestrator>::Orchestrators[2 * *(int *)(*(_QWORD *)v78 + 40LL)] )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3F,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\OrchestratorRegistry.h",
      (const char *)0x80070032LL,
      (int)v74);
  v73 = ComputeService::Management::OrchestratorRegistrar<ComputeService::Management::IComputeSystemOrchestrator>::Orchestrators[2 * *(int *)(*(_QWORD *)v78 + 40LL)];
  memset_0(v71, 0, sizeof(v71));
  *(_QWORD *)&v77 = &v73;
  *((_QWORD *)&v77 + 1) = &v78;
  *(_QWORD *)&v62 = retaddr;
  *((_QWORD *)&v62 + 1) = "onecore\\vm\\compute\\management\\computesystem\\computesystemmanager.cpp";
  *(_QWORD *)&v63 = 0;
  WORD4(v63) = 229;
  wil::scope_exit_log__lambda_0b41060d77d9fb66fe986d0a09b0876a___(v71, &v62, &v77);
  v32 = *v31;
  if ( *(_DWORD *)(*v31 + 40) == 9 )
  {
    v112 = 0;
    v113 = 0;
    v114 = 7;
    LOWORD(v112) = 0;
    v115 = 0;
    v116 = 0;
    v117 = 0;
    v118 = 7;
    LOWORD(v116) = 0;
    memset_0(&v119, 0, 0x40u);
    v119 = 0;
    v120 = 0;
    v121 = 0;
    v122 = 0;
    v123 = 0;
    memset_0(v124, 0, sizeof(v124));
    vmstd::optional<Schema::Container>::optional<Schema::Container>(v124);
    memset_0(v125, 0, 0xCA8u);
    vmstd::optional<Schema::VirtualMachine>::optional<Schema::VirtualMachine>(v125);
    v125[3240] = 0;
    v126 = 0;
    v127 = 0;
    v128 = 7;
    LOWORD(v126) = 0;
    if ( *(_QWORD *)(a4 + 24) <= 7u )
      v33 = a4;
    else
      v33 = *(_QWORD *)a4;
    v72[0] = v33;
    v72[1] = *(_QWORD *)(a4 + 16);
    ComputeService::MarshalUtilities::FromJsonStrictThrow<Schema::ComputeSystem,>(v72, &v112);
    v34 = *((_QWORD *)ComputeService::Diagnostics::TraceProvider::Instance() + 1);
    if ( *(_DWORD *)v34 > 4u
      && (*(_QWORD *)(v34 + 16) & 1) != 0
      && (*(_QWORD *)(v34 + 24) & 1LL) == *(_QWORD *)(v34 + 24) )
    {
      v36 = &v116;
      if ( v118 > 7 )
        v36 = (__int128 *)v116;
      v72[0] = (__int64)v36;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,unsigned __int64,unsigned long,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteEx_EventWriteEx(_tlgProvider_t const *,void const *,unsigned __int64,unsigned long,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),unsigned __int64,unsigned long,_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        v34,
        (int)v74,
        (LPCGUID)(v104 + 2),
        (__int64)v72);
    }
    v77 = 0;
    ComputeService::Management::ComputeSystemManager::FindComputeSystem(v28, &v77, &v116, v35);
    v37 = ComputeService::Management::OrchestratorRegistrar<ComputeService::Management::IProxyComputeSystemOrchestrator>::Orchestrators[2 * *(int *)(*(_QWORD *)v78 + 40LL)];
    if ( !v37 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3F,
        (unsigned int)"onecore\\vm\\compute/management/orchestration/shared/OrchestratorRegistry.h",
        (const char *)0x80070032LL,
        (int)v61);
    (*(void (__fastcall **)(__int64, __int128 *, __int128 *))(*(_QWORD *)v37 + 8LL))(v37, &v78, &v77);
    v38 = (volatile signed __int32 *)*((_QWORD *)&v77 + 1);
    if ( *((_QWORD *)&v77 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v77 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v38)(v38);
        if ( _InterlockedExchangeAdd(v38 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v38 + 8LL))(v38);
      }
    }
    std::wstring::~wstring(&v126);
    Schema::VirtualMachine::~VirtualMachine((Schema::VirtualMachine *)v125);
    Schema::Container::~Container((Schema::Container *)v124);
    Marshal::DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>::~DelayedBase<Schema::Responses::System::MemoryTopology,Marshal::Details::DelayedJsonTraits>(&v119);
    std::wstring::~wstring(&v116);
    v39 = &v112;
LABEL_85:
    std::wstring::~wstring(v39);
    goto LABEL_86;
  }
  if ( *(_DWORD *)(v32 + 40) == 2 )
  {
    LODWORD(v61) = 0;
    v40 = _RTDynamicCast_0(
            v32,
            0,
            &ComputeService::Management::ComputeSystemConfiguration `RTTI Type Descriptor',
            &ComputeService::Management::VirtualMachineConfiguration `RTTI Type Descriptor');
    if ( !v40 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5D,
        (unsigned int)"onecore\\vm\\compute\\management\\computesystem\\ComputeSystem.h",
        (const char *)0x80004001LL,
        0);
    if ( *(_BYTE *)(v40 + 4296) && *(_BYTE *)(v40 + 3280) )
    {
      v41 = v40 + 3176;
      *(_QWORD *)&v77 = v79;
      std::wstring::wstring(v79, v40 + 3176);
      std::wstring::wstring(v83, v41 + 32);
      std::wstring::wstring(v86, v41 + 64);
      v89 = *(_DWORD *)(v41 + 96);
      v90 = *(_BYTE *)(v41 + 104);
      v42 = *((_QWORD *)ComputeService::Diagnostics::TraceProvider::Instance() + 1);
      if ( *(_DWORD *)v42 > 4u
        && (*(_QWORD *)(v42 + 16) & 1) != 0
        && (*(_QWORD *)(v42 + 24) & 1LL) == *(_QWORD *)(v42 + 24) )
      {
        if ( !v90 )
          __fastfail(5u);
        v43 = v86;
        if ( v88 > 7 )
          v43 = (_QWORD *)v86[0];
        v72[0] = (__int64)v43;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,unsigned __int64,unsigned long,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteEx_EventWriteEx(_tlgProvider_t const *,void const *,unsigned __int64,unsigned long,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),unsigned __int64,unsigned long,_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          v42,
          0,
          (LPCGUID)(v104 + 2),
          (__int64)v72);
      }
      if ( !v90 )
        __fastfail(5u);
      if ( !v80 && !v84 || (v44 = 1, !v87) )
        v44 = 0;
      if ( v44 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x111,
          (unsigned int)"onecore\\vm\\compute\\management\\computesystem\\computesystemmanager.cpp",
          (const char *)0x8007000DLL,
          (int)v61);
      if ( v80 || v84 || (v45 = 1, v87) )
        v45 = 0;
      if ( v45 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x113,
          (unsigned int)"onecore\\vm\\compute\\management\\computesystem\\computesystemmanager.cpp",
          (const char *)0x8007000DLL,
          (int)v61);
      if ( v87 )
      {
        v77 = 0;
        ComputeService::Management::ComputeSystemManager::FindComputeSystem(v28, &v77, v86, v84);
        v46 = ComputeService::Management::OrchestratorRegistrar<ComputeService::Management::ICloneOrchestrator>::Orchestrators[2 * *(int *)(*(_QWORD *)v78 + 40LL)];
        if ( !v46 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x3F,
            (unsigned int)"onecore\\vm\\compute/management/orchestration/shared/OrchestratorRegistry.h",
            (const char *)0x80070032LL,
            (int)v61);
        (*(void (__fastcall **)(__int64, __int128 *, __int128 *))(*(_QWORD *)v46 + 8LL))(v46, &v78, &v77);
        v47 = (volatile signed __int32 *)*((_QWORD *)&v77 + 1);
        if ( *((_QWORD *)&v77 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v77 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v47)(v47);
            if ( _InterlockedExchangeAdd(v47 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v47 + 8LL))(v47);
          }
        }
      }
      std::wstring::~wstring(v86);
      std::wstring::~wstring(v83);
      v39 = (__int128 *)v79;
      goto LABEL_85;
    }
  }
LABEL_86:
  if ( !(*(unsigned __int8 (__fastcall **)(_QWORD *, __int128 *))(*v28 + 8LL))(v28, &v78) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x121,
      (unsigned int)"onecore\\vm\\compute\\management\\computesystem\\computesystemmanager.cpp",
      (const char *)0xC037010FLL,
      (int)v61);
  v48 = *(__int64 (__fastcall **)(__int64, __int128 *, _OWORD *, _QWORD, _QWORD *))(*(_QWORD *)v73 + 8LL);
  v49 = (_QWORD *)v66;
  v79[0] = *(_QWORD *)v66;
  v79[1] = *(_QWORD *)(v66 + 8);
  v80 = *(_QWORD *)(v66 + 16);
  v81 = *(_DWORD *)(v66 + 24);
  v82 = *(_DWORD *)(v66 + 28);
  v83[0] = *(_QWORD *)(v66 + 32);
  v83[1] = *(_QWORD *)(v66 + 40);
  *(_QWORD *)(v66 + 32) = 0;
  v49[5] = 0;
  v50 = v49[8];
  v49[8] = 0;
  v51 = v49[7];
  v49[7] = 0;
  v52 = v49[6];
  v49[6] = 0;
  v84 = v52;
  v85 = v51;
  v86[0] = v50;
  ComputeService::Management::MakeActiveServerOperation(&v62, &v78, v79);
  v65 = 0;
  v67[0] = v62;
  v62 = 0;
  v67[1] = v63;
  v63 = 0;
  v67[2] = v64;
  v64 = 0;
  v68 = 0;
  v53 = v48(v73, &v78, v67, 0, v28);
  ComputeService::Management::RetireServerOperation::~RetireServerOperation((ComputeService::Management::RetireServerOperation *)&v63);
  v54 = (volatile signed __int32 *)*((_QWORD *)&v62 + 1);
  if ( *((_QWORD *)&v62 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v62 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v54)(v54);
      if ( !_InterlockedDecrement(v54 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v54 + 8LL))(v54);
    }
  }
  v71[56] = 0;
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,1,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v91);
  *(_BYTE *)a2 = v53;
  *(_DWORD *)(a2 + 1) = 0;
  *(_WORD *)(a2 + 5) = 0;
  *(_BYTE *)(a2 + 7) = 0;
  *(_QWORD *)(a2 + 8) = 0;
  *(_QWORD *)(a2 + 16) = 0;
  v55 = *((_QWORD *)&v78 + 1);
  if ( *((_QWORD *)&v78 + 1) )
  {
    _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v78 + 1) + 8LL));
    v55 = *((_QWORD *)&v78 + 1);
  }
  *(_QWORD *)(a2 + 8) = v78;
  *(_QWORD *)(a2 + 16) = v55;
  wil::details::lambda_call_log__lambda_0b41060d77d9fb66fe986d0a09b0876a___::reset(v71);
  v56 = (volatile signed __int32 *)*((_QWORD *)&v78 + 1);
  if ( *((_QWORD *)&v78 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v78 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v56)(v56);
      if ( _InterlockedExchangeAdd(v56 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v56 + 8LL))(v56);
    }
  }
  v57 = *(volatile signed __int32 **)&v74[2];
  if ( *(_QWORD *)&v74[2] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v74[2] + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v57)(v57);
      if ( _InterlockedExchangeAdd(v57 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v57 + 8LL))(v57);
    }
  }
  v91 = &ComputeService::Diagnostics::TraceProvider::ComputeSystemManager_Create::`vftable';
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,1,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v91);
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,1,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeService::Diagnostics::TraceProvider,0,1,4,0,_TlgReflectorTag_Param0IsProviderType>(&v91);
  std::vector<ComputeService::Resources::ServerResource>::~vector<ComputeService::Resources::ServerResource>(v49 + 6);
  v58 = (volatile signed __int32 *)v49[5];
  if ( v58 )
  {
    if ( _InterlockedExchangeAdd(v58 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v58)(v58);
      if ( _InterlockedExchangeAdd(v58 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v58 + 8LL))(v58);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x14007a274  push    rbp
0x14007a276  push    rbx
0x14007a277  push    rsi
0x14007a278  push    rdi
0x14007a279  push    r12
0x14007a27b  push    r13
0x14007a27d  push    r14
0x14007a27f  push    r15
0x14007a281  lea     rbp, [rsp-12D8h]
0x14007a289  mov     eax, 13D8h
0x14007a28e  call    _alloca_probe
0x14007a293  sub     rsp, rax
0x14007a296  mov     rax, cs:__security_cookie
0x14007a29d  xor     rax, rsp
0x14007a2a0  mov     [rbp+1310h+var_50], rax
0x14007a2a7  mov     r15, r9
0x14007a2aa  mov     rsi, r8
0x14007a2ad  mov     r14, rdx
0x14007a2b0  mov     rbx, rcx
0x14007a2b3  mov     [rbp+1310h+var_12D0], rcx
0x14007a2b7  mov     [rsp+1410h+var_1398], rdx
0x14007a2bc  mov     r13, [rbp+1310h+arg_30]
0x14007a2c3  mov     [rsp+1410h+var_1398], r13
0x14007a2c8  mov     [rbp+1310h+var_12A0], r13
0x14007a2cc  xor     edx, edx; Val
0x14007a2ce  mov     r8d, 150h; Size
0x14007a2d4  lea     rcx, [rbp+1310h+var_1200]; void *
0x14007a2db  call    memset_0
0x14007a2e0  cmp     qword ptr [r15+18h], 7
0x14007a2e5  jbe     short loc_14007A2EC
0x14007a2e7  mov     rdi, [r15]
0x14007a2ea  jmp     short loc_14007A2EF
0x14007a2ec  mov     rdi, r15
0x14007a2ef  mov     r12, rsi
0x14007a2f2  cmp     qword ptr [rsi+18h], 7
0x14007a2f7  jbe     short loc_14007A2FC
0x14007a2f9  mov     r12, [rsi]
0x14007a2fc  xor     ecx, ecx
0x14007a2fe  mov     [rbp+1310h+var_11F8], ecx
0x14007a304  mov     [rbp+1310h+var_11F4], cl
0x14007a30a  mov     [rbp+1310h+var_11B8], cl
0x14007a310  mov     [rbp+1310h+var_11D0], ecx
0x14007a316  lea     rax, aComputesystemm_1; "ComputeSystemManager_Create"
0x14007a31d  mov     [rbp+1310h+var_11C8], rax
0x14007a324  mov     [rbp+1310h+var_11C0], rcx
0x14007a32b  mov     [rbp+1310h+var_11B0], ecx
0x14007a331  mov     [rbp+1310h+var_1110], rcx
0x14007a338  mov     [rbp+1310h+var_1108], rcx
0x14007a33f  xor     edx, edx; Val
0x14007a341  mov     r8d, 98h; Size
0x14007a347  lea     rcx, [rbp+1310h+var_11A8]; void *
0x14007a34e  call    memset_0
0x14007a353  mov     [rbp+1310h+var_1100], 1
0x14007a35d  xor     eax, eax
0x14007a35f  mov     [rbp+1310h+var_10F8], rax
0x14007a366  lea     rax, [rbp+1310h+var_11F8]
0x14007a36d  mov     [rbp+1310h+var_10F0], rax
0x14007a374  xor     ecx, ecx
0x14007a376  mov     [rbp+1310h+var_10E8], rcx
0x14007a37d  mov     [rbp+1310h+var_10E0], rcx
0x14007a384  lea     rax, [rbp+1310h+var_1200]
0x14007a38b  mov     [rbp+1310h+var_10D8], rax
0x14007a392  mov     [rbp+1310h+var_10D0], rcx
0x14007a399  mov     [rbp+1310h+var_10C8], ecx
0x14007a39f  lea     rax, [rbp+1310h+var_11D0]
0x14007a3a6  mov     [rbp+1310h+var_10C0], rax
0x14007a3ad  mov     [rbp+1310h+var_10B8], cl
0x14007a3b3  lea     rax, ??_7ComputeSystemManager_Create@TraceProvider@Diagnostics@ComputeService@@6B@; const ComputeService::Diagnostics::TraceProvider::ComputeSystemManager_Create::`vftable'
0x14007a3ba  mov     [rbp+1310h+var_1200], rax
0x14007a3c1  mov     r8, rdi; unsigned __int16 *
0x14007a3c4  mov     rdx, r12; unsigned __int16 *
0x14007a3c7  lea     rcx, [rbp+1310h+var_1200]; this
0x14007a3ce  call    ?StartActivity@ComputeSystemManager_Create@TraceProvider@Diagnostics@ComputeService@@QEAAXPEBG0@Z; ComputeService::Diagnostics::TraceProvider::ComputeSystemManager_Create::StartActivity(ushort const *,ushort const *)
0x14007a3d3  nop
0x14007a3d4  mov     rcx, [rbp+1318h]; this
0x14007a3db  cmp     dword ptr [r13+18h], 1
0x14007a3e0  jnz     loc_14007AF85
0x14007a3e6  lea     rcx, [rbx+58h]; SRWLock
0x14007a3ea  call    cs:__imp_AcquireSRWLockShared
0x14007a3f0  mov     r8, rsi
0x14007a3f3  lea     rdx, [rsp+1410h+var_13D0]
0x14007a3f8  lea     rcx, [rbx+48h]
0x14007a3fc  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@UCaseInsensitiveLess@Vml@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,Vml::CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x14007a401  mov     rdi, qword ptr [rsp+1410h+var_13C0]
0x14007a406  cmp     byte ptr [rdi+19h], 0
0x14007a40a  jnz     short loc_14007A43E
0x14007a40c  lea     rdx, [rdi+20h]
0x14007a410  cmp     qword ptr [rdx+18h], 7
0x14007a415  jbe     short loc_14007A41A
0x14007a417  mov     rdx, [rdx]
0x14007a41a  cmp     qword ptr [rsi+18h], 7
0x14007a41f  jbe     short loc_14007A426
0x14007a421  mov     rcx, [rsi]
0x14007a424  jmp     short loc_14007A429
0x14007a426  mov     rcx, rsi
0x14007a429  call    cs:__imp__o__wcsicmp
0x14007a42f  test    eax, eax
0x14007a431  js      short loc_14007A43E
0x14007a433  cmp     rdi, [rbx+48h]
0x14007a437  jz      short loc_14007A43E
0x14007a439  mov     dil, 1
0x14007a43c  jmp     short loc_14007A441
0x14007a43e  xor     dil, dil
0x14007a441  lea     rcx, [rbx+58h]; SRWLock
0x14007a445  call    cs:__imp_ReleaseSRWLockShared
0x14007a44b  mov     rcx, [rbp+1318h]; this
0x14007a452  test    dil, dil
0x14007a455  jnz     loc_14007AF9D
0x14007a45b  xorps   xmm1, xmm1
0x14007a45e  movdqu  xmmword ptr [rbp+1310h+var_12B8], xmm1
0x14007a463  xor     eax, eax
0x14007a465  mov     [rbp+1310h+var_12A8], rax
0x14007a469  mov     r12, [rbx+78h]
0x14007a46d  lea     rdx, [rsp+1410h+var_13D0]
0x14007a472  mov     rcx, [r12]; SRWLock
0x14007a476  call    ?AddSystem@DiagnosticCacheInner@Diagnostics@ComputeService@@QEAA?AV?$shared_ptr@VSystemEntryInner@Diagnostics@ComputeService@@@std@@XZ; ComputeService::Diagnostics::DiagnosticCacheInner::AddSystem(void)
0x14007a47b  mov     rbx, rax
0x14007a47e  mov     ecx, 30h ; '0'; Size
0x14007a483  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14007a488  mov     rdi, rax
0x14007a48b  mov     qword ptr [rbp+1310h+var_1298], rax
0x14007a48f  xorps   xmm0, xmm0
0x14007a492  movups  xmmword ptr [rax], xmm0
0x14007a495  mov     dword ptr [rax+8], 1
0x14007a49c  mov     dword ptr [rax+0Ch], 1
0x14007a4a3  lea     rax, ??_7?$_Ref_count_obj2@VSystemEntry@Diagnostics@ComputeService@@@std@@6B@; const std::_Ref_count_obj2<ComputeService::Diagnostics::SystemEntry>::`vftable'
0x14007a4aa  mov     [rdi], rax
0x14007a4ad  lea     r13, [rdi+10h]
0x14007a4b1  mov     rdx, [rbx]
0x14007a4b4  mov     r8, [rbx+8]
0x14007a4b8  mov     qword ptr [rbx], 0
0x14007a4bf  mov     qword ptr [rbx+8], 0
0x14007a4c7  mov     rax, [r12+8]
0x14007a4cc  test    rax, rax
0x14007a4cf  jz      short loc_14007A4D5
0x14007a4d1  lock inc dword ptr [rax+8]
0x14007a4d5  mov     rcx, [r12+8]
0x14007a4da  mov     rax, [r12]
0x14007a4de  mov     [r13+0], rax
0x14007a4e2  mov     [r13+8], rcx
0x14007a4e6  mov     [r13+10h], rdx
0x14007a4ea  mov     [r13+18h], r8
0x14007a4ee  movups  [rbp+1310h+var_1298], xmm0
0x14007a4f2  mov     qword ptr [rbp+1310h+var_1298], r13
0x14007a4f6  mov     qword ptr [rbp+1310h+var_1298+8], rdi
0x14007a4fd  or      r12d, 0FFFFFFFFh
0x14007a501  mov     rbx, qword ptr [rsp+1410h+var_13D0+8]
0x14007a506  test    rbx, rbx
0x14007a509  jz      short loc_14007A543
0x14007a50b  mov     eax, r12d
0x14007a50e  lock xadd [rbx+8], eax
0x14007a513  add     eax, r12d
0x14007a516  jnz     short loc_14007A543
0x14007a518  mov     rax, [rbx]
0x14007a51b  mov     rcx, rbx
0x14007a51e  mov     rax, [rax]
0x14007a521  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a526  mov     eax, r12d
0x14007a529  lock xadd [rbx+0Ch], eax
0x14007a52e  add     eax, r12d
0x14007a531  jnz     short loc_14007A543
0x14007a533  mov     rax, [rbx]
0x14007a536  mov     rcx, rbx
0x14007a539  mov     rax, [rax+8]
0x14007a53d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a542  nop
0x14007a543  mov     ecx, 40h ; '@'; Size
0x14007a548  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14007a54d  mov     r12, rax
0x14007a550  mov     qword ptr [rbp+1310h+var_1298], rax
0x14007a554  xorps   xmm0, xmm0
0x14007a557  movups  xmmword ptr [rax], xmm0
0x14007a55a  mov     dword ptr [rax+8], 1
0x14007a561  mov     dword ptr [rax+0Ch], 1
0x14007a568  lea     rax, ??_7?$_Ref_count_obj2@VServerOperationTracker@Management@ComputeService@@@std@@6B@; const std::_Ref_count_obj2<ComputeService::Management::ServerOperationTracker>::`vftable'
0x14007a56f  mov     [r12], rax
0x14007a573  lea     rbx, [r12+10h]
0x14007a578  xor     eax, eax
0x14007a57a  mov     [rbx], rax
0x14007a57d  mov     [rbx+8], rax
0x14007a581  mov     [rbx+10h], rax
0x14007a585  mov     [rbx+18h], rax
0x14007a589  mov     [rbx+20h], rax
0x14007a58d  mov     [rbx+28h], rax
0x14007a591  lock inc dword ptr [rdi+8]
0x14007a595  mov     [rbx+20h], r13
0x14007a599  mov     [rbx+28h], rdi
0x14007a59d  or      eax, 0FFFFFFFFh
0x14007a5a0  lock xadd [rdi+8], eax
0x14007a5a5  cmp     eax, 1
0x14007a5a8  jnz     short loc_14007A5D4
0x14007a5aa  mov     rax, [rdi]
0x14007a5ad  mov     rcx, rdi
0x14007a5b0  mov     rax, [rax]
0x14007a5b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a5b8  or      eax, 0FFFFFFFFh
0x14007a5bb  lock xadd [rdi+0Ch], eax
0x14007a5c0  cmp     eax, 1
0x14007a5c3  jnz     short loc_14007A5D4
0x14007a5c5  mov     rax, [rdi]
0x14007a5c8  mov     rcx, rdi
0x14007a5cb  mov     rax, [rax+8]
0x14007a5cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a5d4  mov     qword ptr [rbp+1310h+var_12B8], rbx
0x14007a5d8  mov     rbx, qword ptr [rbp+1310h+var_12B8+8]
0x14007a5dc  mov     qword ptr [rbp+1310h+var_12B8+8], r12
0x14007a5e0  xor     r13d, r13d
0x14007a5e3  test    rbx, rbx
0x14007a5e6  jz      short loc_14007A620
0x14007a5e8  or      eax, 0FFFFFFFFh
0x14007a5eb  lock xadd [rbx+8], eax
0x14007a5f0  cmp     eax, 1
0x14007a5f3  jnz     short loc_14007A620
0x14007a5f5  mov     rax, [rbx]
0x14007a5f8  mov     rcx, rbx
0x14007a5fb  mov     rax, [rax]
0x14007a5fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a603  or      eax, 0FFFFFFFFh
0x14007a606  lock xadd [rbx+0Ch], eax
0x14007a60b  cmp     eax, 1
0x14007a60e  jnz     short loc_14007A620
0x14007a610  mov     rax, [rbx]
0x14007a613  mov     rcx, rbx
0x14007a616  mov     rax, [rax+8]
0x14007a61a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a61f  nop
0x14007a620  mov     [rbp+1310h+var_12A8], r13
0x14007a624  xorps   xmm0, xmm0
0x14007a627  movups  [rbp+1310h+var_1288], xmm0
0x14007a62e  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_7ff8c2eaf54bbf08262be3efa113d168_@@XAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBUComputeSystemNotificationInfo_2@Management@ComputeService@@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_7ff8c2eaf54bbf08262be3efa113d168_,void,std::wstring const &,ComputeService::Management::ComputeSystemNotificationInfo_2 const &>::`vftable'
0x14007a635  mov     [rbp+1310h+var_1350], rax
0x14007a639  mov     r12, [rbp+1310h+var_12D0]
0x14007a63d  mov     [rbp+1310h+var_1348], r12
0x14007a641  lea     rax, [rbp+1310h+var_1350]
0x14007a645  mov     [rbp+1310h+var_1318], rax
0x14007a649  lea     rax, [rbp+1310h+var_1350]
0x14007a64d  mov     qword ptr [rbp+1310h+var_1298], rax
0x14007a651  cmp     qword ptr [rsi+18h], 7
0x14007a656  jbe     short loc_14007A65B
0x14007a658  mov     rsi, [rsi]
0x14007a65b  mov     [rbp+1310h+var_12D0], rsi
0x14007a65f  mov     rcx, [r12+40h]
0x14007a664  test    rcx, rcx
0x14007a667  jnz     short loc_14007A670
0x14007a669  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x14007a66f  int     3; Trap to Debugger
0x14007a670  mov     rax, [rcx]
0x14007a673  lea     rdx, [rbp+1310h+var_1350]
0x14007a677  mov     [rsp+1410h+var_13E8], rdx
0x14007a67c  lea     rdx, [rbp+1310h+var_12B8]
0x14007a680  mov     qword ptr [rsp+1410h+var_13F0], rdx; int
0x14007a685  mov     r9, r15
0x14007a688  lea     r8, [rbp+1310h+var_12D0]
0x14007a68c  lea     rdx, [rbp+1310h+var_1288]
0x14007a693  mov     rax, [rax+10h]
0x14007a697  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a69c  nop
0x14007a69d  mov     rcx, [rbp+1310h+var_1318]
0x14007a6a1  test    rcx, rcx
0x14007a6a4  jz      short loc_14007A6C0
0x14007a6a6  mov     rax, [rcx]
0x14007a6a9  lea     rdx, [rbp+1310h+var_1350]
0x14007a6ad  cmp     rcx, rdx
0x14007a6b0  setnz   dl
0x14007a6b3  mov     rax, [rax+20h]
0x14007a6b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a6bc  mov     [rbp+1310h+var_1318], r13
0x14007a6c0  mov     rbx, qword ptr [rbp+1310h+var_1288]
0x14007a6c7  mov     rax, [rbx]
0x14007a6ca  movsxd  rcx, dword ptr [rax+28h]
0x14007a6ce  add     rcx, rcx
0x14007a6d1  lea     rax, __ImageBase
0x14007a6d8  mov     rax, rva ?Orchestrators@?$OrchestratorRegistrar@VIComputeSystemOrchestrator@Management@ComputeService@@@Management@ComputeService@@0V?$array@V?$shared_ptr@VIComputeSystemOrchestrator@Management@ComputeService@@@std@@$09@std@@A[rax+rcx*8]; std::array<std::shared_ptr<ComputeService::Management::IComputeSystemOrchestrator>,10> ComputeService::Management::OrchestratorRegistrar<ComputeService::Management::IComputeSystemOrchestrator>::Orchestrators ...
0x14007a6e0  mov     rcx, [rbp+1318h]; this
0x14007a6e7  test    rax, rax
0x14007a6ea  jz      loc_14007AFB5
0x14007a6f0  mov     [rbp+1310h+var_12C0], rax
0x14007a6f4  mov     esi, 40h ; '@'
0x14007a6f9  mov     r8d, esi; Size
0x14007a6fc  xor     edx, edx; Val
0x14007a6fe  lea     rcx, [rbp+1310h+var_1310]; void *
0x14007a702  call    memset_0
0x14007a707  lea     rax, [rbp+1310h+var_12C0]
0x14007a70b  mov     qword ptr [rbp+1310h+var_1298], rax
0x14007a70f  lea     rax, [rbp+1310h+var_1288]
0x14007a716  mov     qword ptr [rbp+1310h+var_1298+8], rax
0x14007a71d  mov     rax, [rbp+1318h]
0x14007a724  mov     qword ptr [rsp+1410h+var_13D0], rax
0x14007a729  lea     rdi, aOnecoreVmCompu_44; "onecore\\vm\\compute\\management\\compu"...
0x14007a730  mov     qword ptr [rsp+1410h+var_13D0+8], rdi
0x14007a735  mov     qword ptr [rsp+1410h+var_13C0], r13
0x14007a73a  mov     eax, 0E5h
0x14007a73f  mov     word ptr [rsp+1410h+var_13C0+8], ax
0x14007a744  lea     r8, [rbp+1310h+var_1298]
0x14007a748  lea     rdx, [rsp+1410h+var_13D0]
0x14007a74d  lea     rcx, [rbp+1310h+var_1310]
0x14007a751  call    wil__scope_exit_log__lambda_0b41060d77d9fb66fe986d0a09b0876a___
0x14007a756  nop
0x14007a757  mov     rcx, [rbx]
0x14007a75a  cmp     dword ptr [rcx+28h], 9
  ... truncated ...
```
