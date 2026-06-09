# VirtualMachine::Teardown(void)

- ea: `0x14004f8cc`
- end: `0x14004fee7`
- name: `?Teardown@VirtualMachine@@QEAAXXZ`
- size: `1563`
- prototype: `void __fastcall(VirtualMachine *__hidden this)`
- caller_count: `1`
- callee_count: `37`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14004f468`

## callees

- `0x140021fd8`
- `0x140031af8`
- `0x14004f8cc`
- `0x14004fef0`
- `0x140055a90`
- `0x140055d80`
- `0x14008707c`
- `0x140094aec`
- `0x140094b9c`
- `0x140099814`
- `0x1400c6e7c`
- `0x1400c6f20`
- `0x1400c6f78`
- `0x1400d438c`
- `0x1400d6da4`
- `0x1400e795c`
- `0x1400e9040`
- `0x140132960`
- `0x14013361c`
- `0x140156c80`
- `0x140156cdc`
- `0x140156d38`
- `0x140156d94`
- `0x140156df0`
- `0x140156e4c`
- `0x140156ea8`
- `0x140156f04`
- `0x140156f60`
- `0x140156fbc`
- `0x140157018`
- `0x140157074`
- `0x1401570d0`
- `0x14016b758`
- `0x14017297c`
- `0x14017c07c`
- `0x14017c934`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14004fab6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14004fab6`
- `WS2_32!__imp_WSACleanup` at `0x14004facb`
- `WS2_32!__imp_WSACleanup` at `0x14004facb`
- `vid!VidSchedulerAssistReset` at `0x14004fa19`
- `vid!VidSchedulerAssistReset` at `0x14004fa19`
- `vid!VidEpfReset` at `0x14004f9e3`
- `vid!VidEpfReset` at `0x14004f9e3`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall VirtualMachine::Teardown(VirtualMachine *this)
{
  __int128 v2; // xmm0
  _QWORD *v3; // r14
  __int64 v4; // rcx
  __int64 v5; // rdi
  const char *v6; // r9
  const char *v7; // r9
  __int64 v8; // rcx
  __int64 v9; // rdi
  struct _TP_WAIT *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rdx
  WorkerCpuidHandler *v14; // rcx
  WorkerExceptionHandler *v15; // rcx
  MemoryManager *v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  Vml::VmSharableObject *v28; // rcx
  Vml::VmSharableObject *v29; // rcx
  __int128 v30; // [rsp+28h] [rbp-D8h] BYREF
  void **v31; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v32[264]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v33; // [rsp+150h] [rbp+50h]
  _BYTE v34[8]; // [rsp+158h] [rbp+58h] BYREF
  _BYTE v35[48]; // [rsp+160h] [rbp+60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+E8h]

  v30 = *((_OWORD *)this + 71);
  memset_0(&v31, 0, 0x150u);
  wil::ActivityBase<VmWorkerTrace,0,16,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VmWorkerTrace,0,16,4,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)&v31);
  v31 = &VmWorkerTrace::VmTeardown::`vftable';
  VmWorkerTrace::VmTeardown::StartActivity((VmWorkerTrace::VmTeardown *)&v31);
  if ( v33 == -8 )
    v2 = 0;
  else
    v2 = *(_OWORD *)(v33 + 8);
  *((_OWORD *)this + 164) = v2;
  AsyncTimer::DisableAndWait((VirtualMachine *)((char *)this + 1712));
  VmWorkerTrace::VmTeardown::TeardownTimerWait<_GUID &>(&v31, &v30);
  VirtualMachine::TeardownPartition(this, 0);
  VmWorkerTrace::VmTeardown::TeardownPartition<_GUID &>(&v31, &v30);
  v3 = (_QWORD *)((char *)this + 1024);
  v4 = *((_QWORD *)this + 128);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v4 + 8) + 88LL))(v4 + 8);
    v5 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v3 + 320LL))(*v3);
    if ( (v5 & 0x20000) != 0 && !(unsigned int)VidEpfReset(*((_QWORD *)this + 122)) )
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0x972,
        (unsigned int)"onecore\\vm\\worker\\wpcore\\virtualmachine.cpp",
        v6);
    if ( (v5 & 0x100000) != 0 && !(unsigned int)VidSchedulerAssistReset(*((_QWORD *)this + 122)) )
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0x977,
        (unsigned int)"onecore\\vm\\worker\\wpcore\\virtualmachine.cpp",
        v7);
    v8 = *((_QWORD *)this + 130);
    if ( v8 && (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v8 + 184LL))(v8) && *((_DWORD *)this + 317) != 3 )
      (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)(*v3 + 24LL) + 24LL))(*v3 + 24LL, 524544, 0);
  }
  VirtualMachine::TeardownMotherboard(this);
  VmWorkerTrace::VmTeardown::TeardownMotherboard<_GUID &>(&v31, &v30);
  v9 = *((_QWORD *)this + 131);
  if ( v9 )
  {
    v10 = *(struct _TP_WAIT **)(v9 + 224);
    if ( v10 )
      CloseThreadpoolWait(v10);
    if ( *(_DWORD *)(v9 + 208) )
      WSACleanup();
    Vml::VmReferencePtr<WorkerConfiguration,Vml::VmUserReferenceTraits>::Reset((char *)this + 1048, 0);
  }
  VmWorkerTrace::VmTeardown::TeardownMigrationManager<_GUID &>(&v31, &v30);
  v11 = *((_QWORD *)this + 323);
  *((_QWORD *)this + 323) = 0;
  if ( v11 )
    Vml::VmSharableObject::DecrementUserCount((Vml::VmSharableObject *)(v11 + 8 + *(int *)(*(_QWORD *)(v11 + 8) + 4LL)));
  *((_QWORD *)this + 179) = 0;
  v12 = *((_QWORD *)this + 178);
  *((_QWORD *)this + 178) = 0;
  if ( v12 )
    Vml::VmSharableObject::DecrementUserCount((Vml::VmSharableObject *)(v12 + 8));
  v13 = *((_QWORD *)this + 125);
  if ( v13 )
  {
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(*(_QWORD *)(v13 + 152) + 8LL) + 64LL))(
      *(_QWORD *)(v13 + 152) + 8LL,
      *(_QWORD *)(v13 + 192));
    Vml::VmSharableObject::DecrementUserCount((Vml::VmSharableObject *)(*((_QWORD *)this + 125)
                                                                      + 8LL
                                                                      + *(int *)(*(_QWORD *)(*((_QWORD *)this + 125)
                                                                                           + 8LL)
                                                                               + 4LL)));
    *((_QWORD *)this + 125) = 0;
  }
  v14 = (WorkerCpuidHandler *)*((_QWORD *)this + 126);
  if ( v14 )
  {
    WorkerCpuidHandler::TeardownRegisteredResults(v14);
    Vml::VmSharableObject::DecrementUserCount((Vml::VmSharableObject *)(*((_QWORD *)this + 126)
                                                                      + 8LL
                                                                      + *(int *)(*(_QWORD *)(*((_QWORD *)this + 126)
                                                                                           + 8LL)
                                                                               + 4LL)));
    *((_QWORD *)this + 126) = 0;
  }
  v15 = (WorkerExceptionHandler *)*((_QWORD *)this + 127);
  if ( v15 )
  {
    WorkerExceptionHandler::Teardown(v15);
    Vml::VmSharableObject::DecrementUserCount((Vml::VmSharableObject *)(*((_QWORD *)this + 127)
                                                                      + 8LL
                                                                      + *(int *)(*(_QWORD *)(*((_QWORD *)this + 127)
                                                                                           + 8LL)
                                                                               + 4LL)));
    *((_QWORD *)this + 127) = 0;
  }
  VmWorkerTrace::VmTeardown::TeardownInternalInterceptHandler<_GUID &>(&v31, &v30);
  v16 = (MemoryManager *)*((_QWORD *)this + 124);
  if ( v16 )
  {
    MemoryManager::Teardown(v16);
    *((_QWORD *)this + 124) = 0;
  }
  v17 = *((_QWORD *)this + 130);
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 264LL))(v17);
    Vml::VmReferencePtr<VndCompletionThread,Vml::VmUserReferenceTraits>::Reset((char *)this + 1040, 0);
  }
  VmWorkerTrace::VmTeardown::TeardownProcessorManager<_GUID &>(&v31, &v30);
  if ( *v3 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v3 + 88LL))(*v3);
    Vml::VmReferencePtr<IVidPartitionManager,Vml::VmUserReferenceTraits>::Reset((char *)this + 1024, 0);
  }
  v18 = *((_QWORD *)this + 132);
  if ( v18 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 32LL))(v18);
    v19 = *((_QWORD *)this + 132);
    *((_QWORD *)this + 132) = 0;
    if ( v19 )
      Vml::VmSharableObject::DecrementUserCount((Vml::VmSharableObject *)(v19 + 8 + *(int *)(*(_QWORD *)(v19 + 8) + 4LL)));
  }
  VmWorkerTrace::VmTeardown::TeardownSavedStateFileManager<_GUID &>(&v31, &v30);
  Vml::VmReferencePtr<IMetricManager,Vml::VmUserReferenceTraits>::Reset((char *)this + 1064);
  VmWorkerTrace::VmTeardown::TeardownMetricManager<_GUID &>(&v31, &v30);
  v20 = *((_QWORD *)this + 129);
  *((_QWORD *)this + 129) = 0;
  if ( v20 )
    Vml::VmSharableObject::DecrementUserCount((Vml::VmSharableObject *)(v20 + 8 + *(int *)(*(_QWORD *)(v20 + 8) + 4LL)));
  VmWorkerTrace::VmTeardown::TeardownNumaManager<_GUID &>(&v31, &v30);
  v21 = *((_QWORD *)this + 134);
  *((_QWORD *)this + 134) = 0;
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  VmWorkerTrace::VmTeardown::TeardownSecurityManager<_GUID &>(&v31, &v30);
  v22 = *((_QWORD *)this + 181);
  *((_QWORD *)this + 181) = 0;
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  v23 = *((_QWORD *)this + 290);
  *((_QWORD *)this + 290) = 0;
  if ( v23 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  v24 = *((_QWORD *)this + 291);
  *((_QWORD *)this + 291) = 0;
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  v25 = *((_QWORD *)this + 183);
  *((_QWORD *)this + 183) = 0;
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  v26 = *((_QWORD *)this + 184);
  *((_QWORD *)this + 184) = 0;
  if ( v26 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  v27 = *((_QWORD *)this + 185);
  *((_QWORD *)this + 185) = 0;
  if ( v27 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  VmWorkerTrace::VmTeardown::TeardownRdpAndMonitorDevice<_GUID &>(&v31, &v30);
  v28 = (Vml::VmSharableObject *)*((_QWORD *)this + 180);
  if ( v28 )
  {
    Vml::VmSharableObject::DecrementUserCount(v28);
    *((_QWORD *)this + 180) = 0;
  }
  VmWorkerTrace::VmTeardown::TeardownAsyncTimerlist<_GUID &>(&v31, &v30);
  v29 = (Vml::VmSharableObject *)*((_QWORD *)this + 177);
  *((_QWORD *)this + 177) = 0;
  if ( v29 )
    Vml::VmSharableObject::DecrementUserCount(v29);
  VmWorkerTrace::VmTeardown::TeardownWorkerConfig<_GUID &>(&v31, &v30);
  wil::ActivityBase<VmWorkerTrace,0,16,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v31, 0);
  if ( this != (VirtualMachine *)-2624LL )
    VirtualMachine::ResetActivityId((struct _GUID *)this + 164);
  v31 = &VmWorkerTrace::VmTeardown::`vftable';
  wil::ActivityBase<VmWorkerTrace,0,16,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v31);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v35);
  wil::details::shared_object<wil::ActivityBase<VmWorkerTrace,0,16,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<VmWorkerTrace,_TlgReflectorTag_Param0IsProviderType>>::reset(v34);
  wil::ActivityBase<VmWorkerTrace,0,16,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<VmWorkerTrace,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<VmWorkerTrace,_TlgReflectorTag_Param0IsProviderType>(v32);
}

```

## disassembly

```asm
0x14004f8cc  push    rbp
0x14004f8ce  push    rbx
0x14004f8cf  push    rsi
0x14004f8d0  push    rdi
0x14004f8d1  push    r12
0x14004f8d3  push    r13
0x14004f8d5  push    r14
0x14004f8d7  push    r15
0x14004f8d9  lea     rbp, [rsp-0A8h]
0x14004f8e1  sub     rsp, 1A8h
0x14004f8e8  mov     rax, cs:__security_cookie
0x14004f8ef  xor     rax, rsp
0x14004f8f2  mov     [rbp+0E0h+var_50], rax
0x14004f8f9  mov     rbx, rcx
0x14004f8fc  movups  xmm0, xmmword ptr [rcx+470h]
0x14004f903  movdqu  [rsp+1E0h+var_1B8], xmm0
0x14004f909  xor     edx, edx; Val
0x14004f90b  mov     r8d, 150h; Size
0x14004f911  lea     rcx, [rsp+1E0h+var_1A0]; void *
0x14004f916  call    memset_0
0x14004f91b  lea     rdx, aVmteardown; "VmTeardown"
0x14004f922  lea     rcx, [rsp+1E0h+var_1A0]; struct wil::details::IFailureCallback *
0x14004f927  call    ??0?$ActivityBase@VVmWorkerTrace@@$0A@$0BA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<VmWorkerTrace,0,16,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VmWorkerTrace,0,16,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x14004f92c  lea     r13, ??_7VmTeardown@VmWorkerTrace@@6B@; const VmWorkerTrace::VmTeardown::`vftable'
0x14004f933  mov     [rsp+1E0h+var_1A0], r13
0x14004f938  lea     rcx, [rsp+1E0h+var_1A0]; this
0x14004f93d  call    ?StartActivity@VmTeardown@VmWorkerTrace@@QEAAXXZ; VmWorkerTrace::VmTeardown::StartActivity(void)
0x14004f942  nop
0x14004f943  mov     rax, [rbp+0E0h+var_90]
0x14004f947  lea     r15, [rbx+0A40h]
0x14004f94e  xor     r12d, r12d
0x14004f951  add     rax, 8
0x14004f955  jz      short loc_14004F95C
0x14004f957  movups  xmm0, xmmword ptr [rax]
0x14004f95a  jmp     short loc_14004F95F
0x14004f95c  xorps   xmm0, xmm0
0x14004f95f  movdqu  xmmword ptr [r15], xmm0
0x14004f964  mov     [rsp+1E0h+var_1C0], r15
0x14004f969  lea     rcx, [rbx+6B0h]; this
0x14004f970  call    ?DisableAndWait@AsyncTimer@@QEAAHXZ; AsyncTimer::DisableAndWait(void)
0x14004f975  lea     rdx, [rsp+1E0h+var_1B8]
0x14004f97a  lea     rcx, [rsp+1E0h+var_1A0]
0x14004f97f  call    ??$TeardownTimerWait@AEAU_GUID@@@VmTeardown@VmWorkerTrace@@QEAAXAEAU_GUID@@@Z; VmWorkerTrace::VmTeardown::TeardownTimerWait<_GUID &>(_GUID &)
0x14004f984  xor     edx, edx; int
0x14004f986  mov     rcx, rbx; this
0x14004f989  call    ?TeardownPartition@VirtualMachine@@AEAAXH@Z; VirtualMachine::TeardownPartition(int)
0x14004f98e  lea     rdx, [rsp+1E0h+var_1B8]
0x14004f993  lea     rcx, [rsp+1E0h+var_1A0]
0x14004f998  call    ??$TeardownPartition@AEAU_GUID@@@VmTeardown@VmWorkerTrace@@QEAAXAEAU_GUID@@@Z; VmWorkerTrace::VmTeardown::TeardownPartition<_GUID &>(_GUID &)
0x14004f99d  lea     r14, [rbx+400h]
0x14004f9a4  mov     rcx, [r14]
0x14004f9a7  test    rcx, rcx
0x14004f9aa  jz      loc_14004FA84
0x14004f9b0  add     rcx, 8
0x14004f9b4  mov     rax, [rcx]
0x14004f9b7  mov     rax, [rax+58h]
0x14004f9bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f9c0  mov     rcx, [r14]
0x14004f9c3  mov     rax, [rcx]
0x14004f9c6  mov     rax, [rax+140h]
0x14004f9cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f9d2  mov     rdi, rax
0x14004f9d5  bt      rax, 11h
0x14004f9da  jnb     short loc_14004FA0B
0x14004f9dc  mov     rcx, [rbx+3D0h]
0x14004f9e3  call    cs:__imp_VidEpfReset
0x14004f9ea  nop     dword ptr [rax+rax+00h]
0x14004f9ef  mov     rcx, [rbp+0E8h]; this
0x14004f9f6  test    eax, eax
0x14004f9f8  jnz     short loc_14004FA0B
0x14004f9fa  lea     r8, aOnecoreVmWorke_77; "onecore\\vm\\worker\\wpcore\\virtualmac"...
0x14004fa01  mov     edx, 972h; void *
0x14004fa06  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x14004fa0b  bt      rdi, 14h
0x14004fa10  jnb     short loc_14004FA41
0x14004fa12  mov     rcx, [rbx+3D0h]
0x14004fa19  call    cs:__imp_VidSchedulerAssistReset
0x14004fa20  nop     dword ptr [rax+rax+00h]
0x14004fa25  mov     rcx, [rbp+0E8h]; this
0x14004fa2c  test    eax, eax
0x14004fa2e  jnz     short loc_14004FA41
0x14004fa30  lea     r8, aOnecoreVmWorke_77; "onecore\\vm\\worker\\wpcore\\virtualmac"...
0x14004fa37  mov     edx, 977h; void *
0x14004fa3c  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x14004fa41  mov     rcx, [rbx+410h]
0x14004fa48  test    rcx, rcx
0x14004fa4b  jz      short loc_14004FA84
0x14004fa4d  mov     rax, [rcx]
0x14004fa50  mov     rax, [rax+0B8h]
0x14004fa57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004fa5c  test    eax, eax
0x14004fa5e  jz      short loc_14004FA84
0x14004fa60  cmp     dword ptr [rbx+4F4h], 3
0x14004fa67  jz      short loc_14004FA84
0x14004fa69  mov     rcx, [r14]
0x14004fa6c  add     rcx, 18h
0x14004fa70  mov     rax, [rcx]
0x14004fa73  xor     r8d, r8d
0x14004fa76  mov     edx, 80100h
0x14004fa7b  mov     rax, [rax+18h]
0x14004fa7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004fa84  mov     rcx, rbx; this
0x14004fa87  call    ?TeardownMotherboard@VirtualMachine@@QEAAXXZ; VirtualMachine::TeardownMotherboard(void)
0x14004fa8c  lea     rdx, [rsp+1E0h+var_1B8]
0x14004fa91  lea     rcx, [rsp+1E0h+var_1A0]
0x14004fa96  call    ??$TeardownMotherboard@AEAU_GUID@@@VmTeardown@VmWorkerTrace@@QEAAXAEAU_GUID@@@Z; VmWorkerTrace::VmTeardown::TeardownMotherboard<_GUID &>(_GUID &)
0x14004fa9b  lea     rsi, [rbx+418h]
0x14004faa2  mov     rdi, [rsi]
0x14004faa5  test    rdi, rdi
0x14004faa8  jz      short loc_14004FAE1
0x14004faaa  mov     rcx, [rdi+0E0h]; pwa
0x14004fab1  test    rcx, rcx
0x14004fab4  jz      short loc_14004FAC2
0x14004fab6  call    cs:__imp_CloseThreadpoolWait
0x14004fabd  nop     dword ptr [rax+rax+00h]
0x14004fac2  cmp     [rdi+0D0h], r12d
0x14004fac9  jz      short loc_14004FAD7
0x14004facb  call    cs:__imp_WSACleanup
0x14004fad2  nop     dword ptr [rax+rax+00h]
0x14004fad7  xor     edx, edx
0x14004fad9  mov     rcx, rsi
0x14004fadc  call    ?Reset@?$VmReferencePtr@VWorkerConfiguration@@VVmUserReferenceTraits@Vml@@@Vml@@QEAAXPEAVWorkerConfiguration@@@Z; Vml::VmReferencePtr<WorkerConfiguration,Vml::VmUserReferenceTraits>::Reset(WorkerConfiguration *)
0x14004fae1  lea     rdx, [rsp+1E0h+var_1B8]
0x14004fae6  lea     rcx, [rsp+1E0h+var_1A0]
0x14004faeb  call    ??$TeardownMigrationManager@AEAU_GUID@@@VmTeardown@VmWorkerTrace@@QEAAXAEAU_GUID@@@Z; VmWorkerTrace::VmTeardown::TeardownMigrationManager<_GUID &>(_GUID &)
0x14004faf0  mov     rdx, [rbx+0A18h]
0x14004faf7  mov     [rbx+0A18h], r12
0x14004fafe  test    rdx, rdx
0x14004fb01  jz      short loc_14004FB17
0x14004fb03  mov     rax, [rdx+8]
0x14004fb07  movsxd  rcx, dword ptr [rax+4]
0x14004fb0b  add     rdx, 8
0x14004fb0f  add     rcx, rdx; this
0x14004fb12  call    ?DecrementUserCount@VmSharableObject@Vml@@AEAAKXZ; Vml::VmSharableObject::DecrementUserCount(void)
0x14004fb17  mov     [rbx+598h], r12
0x14004fb1e  mov     rcx, [rbx+590h]
0x14004fb25  mov     [rbx+590h], r12
0x14004fb2c  test    rcx, rcx
0x14004fb2f  jz      short loc_14004FB3A
0x14004fb31  add     rcx, 8; this
0x14004fb35  call    ?DecrementUserCount@VmSharableObject@Vml@@AEAAKXZ; Vml::VmSharableObject::DecrementUserCount(void)
0x14004fb3a  mov     rdx, [rbx+3E8h]
0x14004fb41  test    rdx, rdx
0x14004fb44  jz      short loc_14004FB86
0x14004fb46  mov     rcx, [rdx+98h]
0x14004fb4d  add     rcx, 8
0x14004fb51  mov     rax, [rcx]
0x14004fb54  mov     rdx, [rdx+0C0h]
0x14004fb5b  mov     rax, [rax+40h]
0x14004fb5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004fb64  mov     rdx, [rbx+3E8h]
0x14004fb6b  mov     rax, [rdx+8]
0x14004fb6f  movsxd  rcx, dword ptr [rax+4]
0x14004fb73  add     rdx, 8
0x14004fb77  add     rcx, rdx; this
0x14004fb7a  call    ?DecrementUserCount@VmSharableObject@Vml@@AEAAKXZ; Vml::VmSharableObject::DecrementUserCount(void)
0x14004fb7f  mov     [rbx+3E8h], r12
0x14004fb86  mov     rcx, [rbx+3F0h]; this
0x14004fb8d  test    rcx, rcx
0x14004fb90  jz      short loc_14004FBB9
0x14004fb92  call    ?TeardownRegisteredResults@WorkerCpuidHandler@@AEAAXXZ; WorkerCpuidHandler::TeardownRegisteredResults(void)
0x14004fb97  mov     rdx, [rbx+3F0h]
0x14004fb9e  mov     rax, [rdx+8]
0x14004fba2  movsxd  rcx, dword ptr [rax+4]
0x14004fba6  add     rdx, 8
0x14004fbaa  add     rcx, rdx; this
0x14004fbad  call    ?DecrementUserCount@VmSharableObject@Vml@@AEAAKXZ; Vml::VmSharableObject::DecrementUserCount(void)
0x14004fbb2  mov     [rbx+3F0h], r12
0x14004fbb9  mov     rcx, [rbx+3F8h]; this
0x14004fbc0  test    rcx, rcx
0x14004fbc3  jz      short loc_14004FBEC
0x14004fbc5  call    ?Teardown@WorkerExceptionHandler@@QEAAXXZ; WorkerExceptionHandler::Teardown(void)
0x14004fbca  mov     rdx, [rbx+3F8h]
0x14004fbd1  mov     rax, [rdx+8]
0x14004fbd5  movsxd  rcx, dword ptr [rax+4]
0x14004fbd9  add     rdx, 8
0x14004fbdd  add     rcx, rdx; this
0x14004fbe0  call    ?DecrementUserCount@VmSharableObject@Vml@@AEAAKXZ; Vml::VmSharableObject::DecrementUserCount(void)
0x14004fbe5  mov     [rbx+3F8h], r12
0x14004fbec  lea     rdx, [rsp+1E0h+var_1B8]
0x14004fbf1  lea     rcx, [rsp+1E0h+var_1A0]
0x14004fbf6  call    ??$TeardownInternalInterceptHandler@AEAU_GUID@@@VmTeardown@VmWorkerTrace@@QEAAXAEAU_GUID@@@Z; VmWorkerTrace::VmTeardown::TeardownInternalInterceptHandler<_GUID &>(_GUID &)
0x14004fbfb  mov     rcx, [rbx+3E0h]; this
0x14004fc02  test    rcx, rcx
0x14004fc05  jz      short loc_14004FC13
0x14004fc07  call    ?Teardown@MemoryManager@@QEAAXXZ; MemoryManager::Teardown(void)
0x14004fc0c  mov     [rbx+3E0h], r12
0x14004fc13  lea     rdi, [rbx+410h]
0x14004fc1a  mov     rcx, [rdi]
0x14004fc1d  test    rcx, rcx
0x14004fc20  jz      short loc_14004FC3B
0x14004fc22  mov     rax, [rcx]
0x14004fc25  mov     rax, [rax+108h]
0x14004fc2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004fc31  xor     edx, edx
0x14004fc33  mov     rcx, rdi
0x14004fc36  call    ?Reset@?$VmReferencePtr@VVndCompletionThread@@VVmUserReferenceTraits@Vml@@@Vml@@QEAAXPEAVVndCompletionThread@@@Z; Vml::VmReferencePtr<VndCompletionThread,Vml::VmUserReferenceTraits>::Reset(VndCompletionThread *)
0x14004fc3b  lea     rdx, [rsp+1E0h+var_1B8]
0x14004fc40  lea     rcx, [rsp+1E0h+var_1A0]
0x14004fc45  call    ??$TeardownProcessorManager@AEAU_GUID@@@VmTeardown@VmWorkerTrace@@QEAAXAEAU_GUID@@@Z; VmWorkerTrace::VmTeardown::TeardownProcessorManager<_GUID &>(_GUID &)
0x14004fc4a  mov     rcx, [r14]
0x14004fc4d  test    rcx, rcx
0x14004fc50  jz      short loc_14004FC68
0x14004fc52  mov     rax, [rcx]
0x14004fc55  mov     rax, [rax+58h]
0x14004fc59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004fc5e  xor     edx, edx
0x14004fc60  mov     rcx, r14
0x14004fc63  call    ?Reset@?$VmReferencePtr@UIVidPartitionManager@@VVmUserReferenceTraits@Vml@@@Vml@@QEAAXPEAUIVidPartitionManager@@@Z; Vml::VmReferencePtr<IVidPartitionManager,Vml::VmUserReferenceTraits>::Reset(IVidPartitionManager *)
0x14004fc68  mov     rcx, [rbx+420h]
0x14004fc6f  test    rcx, rcx
0x14004fc72  jz      short loc_14004FCD8
0x14004fc74  mov     rax, [rbx+588h]
0x14004fc7b  cmp     [rax+17Ch], r12d
0x14004fc82  jnz     short loc_14004FCA2
0x14004fc84  mov     edx, 1
0x14004fc89  cmp     [rbx+4F4h], edx
0x14004fc8f  jnz     short loc_14004FCA2
0x14004fc91  cmp     [rbx+4F0h], edx
0x14004fc97  jz      short loc_14004FCA5
0x14004fc99  cmp     [rbx+4F8h], r12d
0x14004fca0  jz      short loc_14004FCA5
0x14004fca2  mov     edx, r12d
0x14004fca5  mov     rax, [rcx]
0x14004fca8  mov     rax, [rax+20h]
0x14004fcac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004fcb1  mov     rdx, [rbx+420h]
0x14004fcb8  mov     [rbx+420h], r12
0x14004fcbf  test    rdx, rdx
0x14004fcc2  jz      short loc_14004FCD8
0x14004fcc4  mov     rax, [rdx+8]
0x14004fcc8  movsxd  rcx, dword ptr [rax+4]
0x14004fccc  add     rdx, 8
0x14004fcd0  add     rcx, rdx; this
0x14004fcd3  call    ?DecrementUserCount@VmSharableObject@Vml@@AEAAKXZ; Vml::VmSharableObject::DecrementUserCount(void)
0x14004fcd8  lea     rdx, [rsp+1E0h+var_1B8]
0x14004fcdd  lea     rcx, [rsp+1E0h+var_1A0]
0x14004fce2  call    ??$TeardownSavedStateFileManager@AEAU_GUID@@@VmTeardown@VmWorkerTrace@@QEAAXAEAU_GUID@@@Z; VmWorkerTrace::VmTeardown::TeardownSavedStateFileManager<_GUID &>(_GUID &)
0x14004fce7  lea     rcx, [rbx+428h]
0x14004fcee  call    ?Reset@?$VmReferencePtr@UIMetricManager@@VVmUserReferenceTraits@Vml@@@Vml@@QEAAXPEAUIMetricManager@@@Z; Vml::VmReferencePtr<IMetricManager,Vml::VmUserReferenceTraits>::Reset(IMetricManager *)
0x14004fcf3  lea     rdx, [rsp+1E0h+var_1B8]
0x14004fcf8  lea     rcx, [rsp+1E0h+var_1A0]
0x14004fcfd  call    ??$TeardownMetricManager@AEAU_GUID@@@VmTeardown@VmWorkerTrace@@QEAAXAEAU_GUID@@@Z; VmWorkerTrace::VmTeardown::TeardownMetricManager<_GUID &>(_GUID &)
0x14004fd02  mov     rdx, [rbx+408h]
0x14004fd09  mov     [rbx+408h], r12
0x14004fd10  test    rdx, rdx
0x14004fd13  jz      short loc_14004FD29
0x14004fd15  mov     rax, [rdx+8]
0x14004fd19  movsxd  rcx, dword ptr [rax+4]
0x14004fd1d  add     rdx, 8
0x14004fd21  add     rcx, rdx; this
0x14004fd24  call    ?DecrementUserCount@VmSharableObject@Vml@@AEAAKXZ; Vml::VmSharableObject::DecrementUserCount(void)
0x14004fd29  lea     rdx, [rsp+1E0h+var_1B8]
0x14004fd2e  lea     rcx, [rsp+1E0h+var_1A0]
0x14004fd33  call    ??$TeardownNumaManager@AEAU_GUID@@@VmTeardown@VmWorkerTrace@@QEAAXAEAU_GUID@@@Z; VmWorkerTrace::VmTeardown::TeardownNumaManager<_GUID &>(_GUID &)
0x14004fd38  mov     rcx, [rbx+430h]
0x14004fd3f  mov     [rbx+430h], r12
0x14004fd46  test    rcx, rcx
0x14004fd49  jz      short loc_14004FD57
0x14004fd4b  mov     rax, [rcx]
0x14004fd4e  mov     rax, [rax+10h]
0x14004fd52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004fd57  lea     rdx, [rsp+1E0h+var_1B8]
0x14004fd5c  lea     rcx, [rsp+1E0h+var_1A0]
0x14004fd61  call    ??$TeardownSecurityManager@AEAU_GUID@@@VmTeardown@VmWorkerTrace@@QEAAXAEAU_GUID@@@Z; VmWorkerTrace::VmTeardown::TeardownSecurityManager<_GUID &>(_GUID &)
0x14004fd66  mov     rcx, [rbx+5A8h]
0x14004fd6d  mov     [rbx+5A8h], r12
0x14004fd74  test    rcx, rcx
0x14004fd77  jz      short loc_14004FD85
0x14004fd79  mov     rax, [rcx]
0x14004fd7c  mov     rax, [rax+10h]
0x14004fd80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004fd85  mov     rcx, [rbx+910h]
0x14004fd8c  mov     [rbx+910h], r12
0x14004fd93  test    rcx, rcx
0x14004fd96  jz      short loc_14004FDA4
0x14004fd98  mov     rax, [rcx]
0x14004fd9b  mov     rax, [rax+10h]
0x14004fd9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004fda4  mov     rcx, [rbx+918h]
0x14004fdab  mov     [rbx+918h], r12
0x14004fdb2  test    rcx, rcx
0x14004fdb5  jz      short loc_14004FDC3
0x14004fdb7  mov     rax, [rcx]
0x14004fdba  mov     rax, [rax+10h]
0x14004fdbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004fdc3  mov     rcx, [rbx+5B8h]
0x14004fdca  mov     [rbx+5B8h], r12
0x14004fdd1  test    rcx, rcx
0x14004fdd4  jz      short loc_14004FDE2
0x14004fdd6  mov     rax, [rcx]
0x14004fdd9  mov     rax, [rax+10h]
0x14004fddd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004fde2  mov     rcx, [rbx+5C0h]
0x14004fde9  mov     [rbx+5C0h], r12
0x14004fdf0  test    rcx, rcx
0x14004fdf3  jz      short loc_14004FE01
0x14004fdf5  mov     rax, [rcx]
0x14004fdf8  mov     rax, [rax+10h]
0x14004fdfc  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
