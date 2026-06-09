# ComputeService::Management::UtilityVmTemplateOrchestrator::Destruct(std::shared_ptr<ComputeService::Management::ComputeSystem> const &,ComputeService::Management::DestructInfo const &)

- ea: `0x14008b3d0`
- end: `0x14008b6dc`
- name: `?Destruct@UtilityVmTemplateOrchestrator@Management@ComputeService@@UEAA_NAEBV?$shared_ptr@VComputeSystem@Management@ComputeService@@@std@@AEBUDestructInfo@23@@Z`
- size: `780`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140017040`
- `0x140020890`
- `0x140021de0`
- `0x140021ea4`
- `0x14002f9e8`
- `0x14007f588`
- `0x140080124`
- `0x14008a83c`
- `0x14008a94c`
- `0x14008a978`
- `0x14008b3d0`
- `0x14008b6e4`
- `0x14008b6f0`
- `0x14008b790`
- `0x14008b8b4`
- `0x14008c800`
- `0x140104510`
- `0x1401332f0`
- `0x140134048`
- `0x14017e5d0`
- `0x1402373c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14008b55f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14008b55f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x14008b50f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x14008b50f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14008b4fb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14008b4fb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14008b5a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14008b5a3`

## string_xrefs

- `0x14008b434`: `UtilityVmTemplate_Destruct`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall ComputeService::Management::UtilityVmTemplateOrchestrator::Destruct(__int64 a1, _QWORD *a2, DWORD *a3)
{
  _QWORD *v5; // rcx
  __int64 v6; // rbx
  __int64 v7; // rdx
  char v8; // di
  __int64 v9; // rdx
  const struct ComputeService::Vmwp::WorkerProcessContext *v10; // rdx
  enum ResourceType v11; // r8d
  struct _TP_WAIT *v12; // rcx
  __int64 v13; // rcx
  const struct ComputeService::Vmwp::WorkerProcessContext *v14; // rdx
  const unsigned __int16 *v15; // rdx
  ComputeService::RecoveryStore *v16; // rcx
  const struct _FILETIME *v17; // rdx
  const struct _FILETIME *v18; // rax
  unsigned __int64 v19; // rax
  __int64 v20; // rdx
  ComputeService::Telemetry *v21; // rcx
  unsigned __int64 v22; // rdx
  void *v23; // rax
  int v24; // r8d
  int v25; // r9d
  struct _FILETIME v27; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v28[32]; // [rsp+38h] [rbp-C8h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v30[42]; // [rsp+60h] [rbp-A0h] BYREF

  memset_0(v30, 0, sizeof(v30));
  SystemTimeAsFileTime.dwLowDateTime = *a3;
  v5 = (_QWORD *)(*(_QWORD *)*a2 + 8LL);
  if ( *(_QWORD *)(*(_QWORD *)*a2 + 32LL) > 7u )
    v5 = (_QWORD *)*v5;
  v27 = (struct _FILETIME)v5;
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v30,
    "UtilityVmTemplate_Destruct");
  v30[0] = &ComputeService::Diagnostics::TraceProvider::UtilityVmTemplate_Destruct::`vftable';
  ComputeService::Diagnostics::TraceProvider::UtilityVmTemplate_Destruct::StartActivity<unsigned short const *,unsigned int,int const &>(
    v30,
    &v27,
    &SystemTimeAsFileTime,
    a3 + 2);
  v6 = ComputeService::Management::ComputeSystem::GetStateAs<ComputeService::Management::TemplateVmSystemState>(*a2);
  v7 = *(_QWORD *)(v6 + 432);
  if ( v7 )
  {
    v8 = 0;
    SystemTimeAsFileTime = 0;
    wil::AcquireSRWLockExclusive(&SystemTimeAsFileTime, v7 + 160);
    v9 = *(_QWORD *)(v6 + 432);
    if ( *(_DWORD *)(v9 + 152) != 3 && (unsigned int)(*(_DWORD *)(v9 + 152) - 4) >= 2 )
    {
      *(_DWORD *)(v9 + 152) = 3;
      v8 = 1;
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&SystemTimeAsFileTime);
    if ( v8 )
    {
      v12 = *(struct _TP_WAIT **)(v6 + 472);
      if ( v12 )
      {
        if ( (*a3 & 0x1000) == 0 )
        {
          SetThreadpoolWait(v12, 0, 0);
          WaitForThreadpoolWaitCallbacks(*(PTP_WAIT *)(v6 + 472), 1);
        }
        wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&void CloseThreadpoolWait(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(
          v6 + 472,
          0);
      }
      v13 = *(_QWORD *)(v6 + 464);
      if ( v13 && ComputeService::Vmwp::IsWorkerProcessRunning((ComputeService::Vmwp *)(v13 + 112), v10) )
      {
        ComputeService::Vmwp::TerminateWorkerProcess((ComputeService::Vmwp *)(*(_QWORD *)(v6 + 464) + 112LL), v14);
        WaitForSingleObject(*(HANDLE *)(*(_QWORD *)(v6 + 464) + 136LL), 0xFFFFFFFF);
      }
      ComputeService::Resource::FreeResourceType(
        (ComputeService::Resource *)(v6 + 480),
        (const struct ComputeService::Resource::ResourceState *)2,
        v11);
      v16 = (ComputeService::RecoveryStore *)(*(_QWORD *)*a2 + 8LL);
      if ( *(_QWORD *)(*(_QWORD *)*a2 + 32LL) > 7u )
        v16 = *(ComputeService::RecoveryStore **)v16;
      ComputeService::RecoveryStore::RemoveSystem(v16, v15);
      SystemTimeAsFileTime = 0;
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      v27 = SystemTimeAsFileTime;
      v18 = (const struct _FILETIME *)wil::FileTime::ToInt64((wil::FileTime *)(v6 + 496), v17);
      v19 = wil::FileTime::ToInt64((wil::FileTime *)&v27, v18);
      v21 = (ComputeService::Telemetry *)(*(_QWORD *)*a2 + 8LL);
      if ( *(_QWORD *)(*(_QWORD *)*a2 + 32LL) > 7u )
        v21 = *(ComputeService::Telemetry **)v21;
      v22 = (__int64)((unsigned __int128)((__int64)(v19 - v20) * (__int128)0x346DC5D63886594BLL) >> 64) >> 11;
      ComputeService::Telemetry::LogUtilityVmTemplateDestructedEvent(
        v21,
        *(const unsigned __int16 **)(*(_QWORD *)(v6 + 432) + 144LL),
        v22 + (v22 >> 63),
        *(_QWORD *)(*(_QWORD *)(v6 + 432) + 144LL));
      SystemTimeAsFileTime = 0;
      wil::AcquireSRWLockExclusive(&SystemTimeAsFileTime, *(_QWORD *)(v6 + 432) + 160LL);
      *(_DWORD *)(*(_QWORD *)(v6 + 432) + 152LL) = 4;
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&SystemTimeAsFileTime);
      ComputeService::Management::UtilityVmTemplateOrchestrator::CleanupTemplate(*(_QWORD *)*a2 + 8LL);
      v23 = (void *)Marshal::ToJson<Schema::Responses::System::SystemExitStatus const &,>(v28, a3 + 2);
      ComputeService::ComputeSystemUtilities::NotifyComputeSystem(*a2, 1, v24, v25, 0, v23);
      Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v28);
    }
  }
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v30,
    0);
  ComputeService::Diagnostics::TraceProvider::UtilityVmTemplate_Destruct::~UtilityVmTemplate_Destruct((ComputeService::Diagnostics::TraceProvider::UtilityVmTemplate_Destruct *)v30);
  return 0;
}

```

## disassembly

```asm
0x14008b3d0  mov     [rsp-8+arg_0], rbx
0x14008b3d5  push    rbp
0x14008b3d6  push    rsi
0x14008b3d7  push    rdi
0x14008b3d8  push    r14
0x14008b3da  push    r15
0x14008b3dc  lea     rbp, [rsp-0C0h]
0x14008b3e4  sub     rsp, 1C0h
0x14008b3eb  mov     rax, cs:__security_cookie
0x14008b3f2  xor     rax, rsp
0x14008b3f5  mov     [rbp+0E0h+var_30], rax
0x14008b3fc  mov     r14, r8
0x14008b3ff  mov     rsi, rdx
0x14008b402  xor     edx, edx; Val
0x14008b404  mov     r8d, 150h; Size
0x14008b40a  lea     rcx, [rsp+1E0h+var_180]; void *
0x14008b40f  call    memset_0
0x14008b414  mov     eax, [r14]
0x14008b417  mov     [rsp+1E0h+SystemTimeAsFileTime.dwLowDateTime], eax
0x14008b41b  mov     rax, [rsi]
0x14008b41e  mov     rcx, [rax]
0x14008b421  add     rcx, 8
0x14008b425  cmp     qword ptr [rcx+18h], 7
0x14008b42a  jbe     short loc_14008B42F
0x14008b42c  mov     rcx, [rcx]
0x14008b42f  mov     [rsp+1E0h+var_1B0], rcx
0x14008b434  lea     rdx, aUtilityvmtempl_0; "UtilityVmTemplate_Destruct"
0x14008b43b  lea     rcx, [rsp+1E0h+var_180]
0x14008b440  call    ??0?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x14008b445  lea     rax, ??_7UtilityVmTemplate_Destruct@TraceProvider@Diagnostics@ComputeService@@6B@; const ComputeService::Diagnostics::TraceProvider::UtilityVmTemplate_Destruct::`vftable'
0x14008b44c  mov     [rsp+1E0h+var_180], rax
0x14008b451  lea     r9, [r14+8]
0x14008b455  lea     r8, [rsp+1E0h+SystemTimeAsFileTime]
0x14008b45a  lea     rdx, [rsp+1E0h+var_1B0]
0x14008b45f  lea     rcx, [rsp+1E0h+var_180]
0x14008b464  call    ??$StartActivity@PEBGIAEBH@UtilityVmTemplate_Destruct@TraceProvider@Diagnostics@ComputeService@@QEAAX$$QEAPEBG$$QEAIAEBH@Z; ComputeService::Diagnostics::TraceProvider::UtilityVmTemplate_Destruct::StartActivity<ushort const *,uint,int const &>(ushort const * &&,uint &&,int const &)
0x14008b469  nop
0x14008b46a  mov     rcx, [rsi]
0x14008b46d  call    ??$GetStateAs@UTemplateVmSystemState@Management@ComputeService@@@ComputeSystem@Management@ComputeService@@QEAAPEAUTemplateVmSystemState@12@XZ; ComputeService::Management::ComputeSystem::GetStateAs<ComputeService::Management::TemplateVmSystemState>(void)
0x14008b472  mov     rbx, rax
0x14008b475  mov     rdx, [rax+1B0h]
0x14008b47c  test    rdx, rdx
0x14008b47f  jz      loc_14008B69C
0x14008b485  xor     dil, dil
0x14008b488  mov     qword ptr [rsp+1E0h+SystemTimeAsFileTime.dwLowDateTime], 0
0x14008b491  add     rdx, 0A0h
0x14008b498  lea     rcx, [rsp+1E0h+SystemTimeAsFileTime]
0x14008b49d  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x14008b4a2  mov     rdx, [rbx+1B0h]
0x14008b4a9  mov     eax, [rdx+98h]
0x14008b4af  sub     eax, 3
0x14008b4b2  jz      short loc_14008B4CB
0x14008b4b4  sub     eax, 1
0x14008b4b7  jz      short loc_14008B4CB
0x14008b4b9  cmp     eax, 1
0x14008b4bc  jz      short loc_14008B4CB
0x14008b4be  mov     dword ptr [rdx+98h], 3
0x14008b4c8  mov     dil, 1
0x14008b4cb  lea     rcx, [rsp+1E0h+SystemTimeAsFileTime]
0x14008b4d0  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x14008b4d5  test    dil, dil
0x14008b4d8  jz      loc_14008B69C
0x14008b4de  lea     rdi, [rbx+1D8h]
0x14008b4e5  mov     rcx, [rdi]; pwa
0x14008b4e8  test    rcx, rcx
0x14008b4eb  jz      short loc_14008B525
0x14008b4ed  test    dword ptr [r14], 1000h
0x14008b4f4  jnz     short loc_14008B51B
0x14008b4f6  xor     r8d, r8d; pftTimeout
0x14008b4f9  xor     edx, edx; h
0x14008b4fb  call    cs:__imp_SetThreadpoolWait
0x14008b502  nop     dword ptr [rax+rax+00h]
0x14008b507  mov     edx, 1; fCancelPendingCallbacks
0x14008b50c  mov     rcx, [rdi]; pwa
0x14008b50f  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x14008b516  nop     dword ptr [rax+rax+00h]
0x14008b51b  xor     edx, edx
0x14008b51d  mov     rcx, rdi
0x14008b520  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?CloseThreadpoolWait@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&CloseThreadpoolWait(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x14008b525  mov     rcx, [rbx+1D0h]
0x14008b52c  test    rcx, rcx
0x14008b52f  jz      short loc_14008B56B
0x14008b531  add     rcx, 70h ; 'p'; this
0x14008b535  call    ?IsWorkerProcessRunning@Vmwp@ComputeService@@YA_NAEBUWorkerProcessContext@12@@Z; ComputeService::Vmwp::IsWorkerProcessRunning(ComputeService::Vmwp::WorkerProcessContext const &)
0x14008b53a  test    al, al
0x14008b53c  jz      short loc_14008B56B
0x14008b53e  mov     rcx, [rbx+1D0h]
0x14008b545  add     rcx, 70h ; 'p'; this
0x14008b549  call    ?TerminateWorkerProcess@Vmwp@ComputeService@@YAXAEBUWorkerProcessContext@12@@Z; ComputeService::Vmwp::TerminateWorkerProcess(ComputeService::Vmwp::WorkerProcessContext const &)
0x14008b54e  mov     rcx, [rbx+1D0h]
0x14008b555  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14008b558  mov     rcx, [rcx+88h]; hHandle
0x14008b55f  call    cs:__imp_WaitForSingleObject
0x14008b566  nop     dword ptr [rax+rax+00h]
0x14008b56b  lea     rcx, [rbx+1E0h]; this
0x14008b572  mov     edx, 2; struct ComputeService::Resource::ResourceState *
0x14008b577  call    ?FreeResourceType@Resource@ComputeService@@YAXAEBUResourceState@12@W4ResourceType@12@@Z; ComputeService::Resource::FreeResourceType(ComputeService::Resource::ResourceState const &,ComputeService::Resource::ResourceType)
0x14008b57c  mov     rax, [rsi]
0x14008b57f  mov     rcx, [rax]
0x14008b582  add     rcx, 8
0x14008b586  cmp     qword ptr [rcx+18h], 7
0x14008b58b  jbe     short loc_14008B590
0x14008b58d  mov     rcx, [rcx]; this
0x14008b590  call    ?RemoveSystem@RecoveryStore@ComputeService@@YAXPEBG@Z; ComputeService::RecoveryStore::RemoveSystem(ushort const *)
0x14008b595  mov     qword ptr [rsp+1E0h+SystemTimeAsFileTime.dwLowDateTime], 0
0x14008b59e  lea     rcx, [rsp+1E0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14008b5a3  call    cs:__imp_GetSystemTimeAsFileTime
0x14008b5aa  nop     dword ptr [rax+rax+00h]
0x14008b5af  mov     rax, qword ptr [rsp+1E0h+SystemTimeAsFileTime.dwLowDateTime]
0x14008b5b4  mov     [rsp+1E0h+var_1B0], rax
0x14008b5b9  lea     rcx, [rbx+1F0h]; this
0x14008b5c0  call    ?ToInt64@FileTime@wil@@YA_KAEBU_FILETIME@@@Z; wil::FileTime::ToInt64(_FILETIME const &)
0x14008b5c5  mov     rdx, rax; struct _FILETIME *
0x14008b5c8  lea     rcx, [rsp+1E0h+var_1B0]; this
0x14008b5cd  call    ?ToInt64@FileTime@wil@@YA_KAEBU_FILETIME@@@Z; wil::FileTime::ToInt64(_FILETIME const &)
0x14008b5d2  mov     r8, rax
0x14008b5d5  sub     r8, rdx
0x14008b5d8  mov     rcx, [rbx+1B0h]
0x14008b5df  mov     r9, [rcx+90h]; unsigned __int64
0x14008b5e6  mov     rcx, [rsi]
0x14008b5e9  mov     rcx, [rcx]
0x14008b5ec  add     rcx, 8
0x14008b5f0  cmp     qword ptr [rcx+18h], 7
0x14008b5f5  jbe     short loc_14008B5FA
0x14008b5f7  mov     rcx, [rcx]; this
0x14008b5fa  mov     rax, 346DC5D63886594Bh
0x14008b604  imul    r8
0x14008b607  sar     rdx, 0Bh
0x14008b60b  mov     r8, rdx
0x14008b60e  shr     r8, 3Fh
0x14008b612  add     r8, rdx; unsigned __int64
0x14008b615  mov     rdx, r9; unsigned __int16 *
0x14008b618  call    ?LogUtilityVmTemplateDestructedEvent@Telemetry@ComputeService@@YAXPEBG_K1@Z; ComputeService::Telemetry::LogUtilityVmTemplateDestructedEvent(ushort const *,unsigned __int64,unsigned __int64)
0x14008b61d  mov     qword ptr [rsp+1E0h+SystemTimeAsFileTime.dwLowDateTime], 0
0x14008b626  mov     rdx, [rbx+1B0h]
0x14008b62d  add     rdx, 0A0h
0x14008b634  lea     rcx, [rsp+1E0h+SystemTimeAsFileTime]
0x14008b639  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x14008b63e  mov     rax, [rbx+1B0h]
0x14008b645  mov     dword ptr [rax+98h], 4
0x14008b64f  lea     rcx, [rsp+1E0h+SystemTimeAsFileTime]
0x14008b654  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x14008b659  mov     rax, [rsi]
0x14008b65c  mov     rcx, [rax]
0x14008b65f  add     rcx, 8
0x14008b663  call    ?CleanupTemplate@UtilityVmTemplateOrchestrator@Management@ComputeService@@CAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ComputeService::Management::UtilityVmTemplateOrchestrator::CleanupTemplate(std::wstring const &)
0x14008b668  lea     rdx, [r14+8]
0x14008b66c  lea     rcx, [rsp+1E0h+var_1A8]
0x14008b671  call    ??$ToJson@AEBUSystemExitStatus@System@Responses@Schema@@$$V@Marshal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBUSystemExitStatus@System@Responses@Schema@@W4MarshalFlags@0@@Z; Marshal::ToJson<Schema::Responses::System::SystemExitStatus const &,>(Schema::Responses::System::SystemExitStatus const &,Marshal::MarshalFlags)
0x14008b676  nop
0x14008b677  mov     [rsp+1E0h+var_1B8], rax; void *
0x14008b67c  mov     [rsp+1E0h+var_1C0], 0; int
0x14008b684  mov     edx, 1; int
0x14008b689  mov     rcx, [rsi]; int
0x14008b68c  call    ?NotifyComputeSystem@ComputeSystemUtilities@ComputeService@@YAXPEAVComputeSystem@Management@2@W4NotificationType@System@Compute@@W4ActiveOperation@67@_KJ$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ComputeService::ComputeSystemUtilities::NotifyComputeSystem(ComputeService::Management::ComputeSystem *,Compute::System::NotificationType,Compute::System::ActiveOperation,unsigned __int64,long,std::wstring &&)
0x14008b691  nop
0x14008b692  lea     rcx, [rsp+1E0h+var_1A8]; this
0x14008b697  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x14008b69c  xor     edx, edx
0x14008b69e  lea     rcx, [rsp+1E0h+var_180]
0x14008b6a3  call    ?Stop@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x14008b6a8  nop
0x14008b6a9  lea     rcx, [rsp+1E0h+var_180]; this
0x14008b6ae  call    ??1UtilityVmTemplate_Destruct@TraceProvider@Diagnostics@ComputeService@@QEAA@XZ; ComputeService::Diagnostics::TraceProvider::UtilityVmTemplate_Destruct::~UtilityVmTemplate_Destruct(void)
0x14008b6b3  xor     al, al
0x14008b6b5  mov     rcx, [rbp+0E0h+var_30]
0x14008b6bc  xor     rcx, rsp; StackCookie
0x14008b6bf  call    __security_check_cookie
0x14008b6c4  mov     rbx, [rsp+1E0h+arg_0]
0x14008b6cc  add     rsp, 1C0h
0x14008b6d3  pop     r15
0x14008b6d5  pop     r14
0x14008b6d7  pop     rdi
0x14008b6d8  pop     rsi
0x14008b6d9  pop     rbp
0x14008b6da  retn
```
