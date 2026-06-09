# VirtualMachine::Teardown(void)

- ea: `0x14003f2cc`
- end: `0x14003f8e7`
- name: `?Teardown@VirtualMachine@@QEAAXXZ`
- size: `1563`
- prototype: `void __fastcall(VirtualMachine *__hidden this)`
- caller_count: `1`
- callee_count: `37`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14003ee00`

## callees

- `0x140022548`
- `0x14003d674`
- `0x14003f2cc`
- `0x14003f8f0`
- `0x1400557e0`
- `0x140055af4`
- `0x14005e660`
- `0x14007f388`
- `0x140083434`
- `0x1400834e4`
- `0x140084528`
- `0x1400b6a48`
- `0x1400b6aec`
- `0x1400b6b44`
- `0x1400c174c`
- `0x1400c5f04`
- `0x1400d8c3c`
- `0x1400f2b10`
- `0x14011ea40`
- `0x14011f6fc`
- `0x1401433e0`
- `0x14014343c`
- `0x140143498`
- `0x1401434f4`
- `0x140143550`
- `0x1401435ac`
- `0x140143608`
- `0x140143664`
- `0x1401436c0`
- `0x14014371c`
- `0x140143778`
- `0x1401437d4`
- `0x140143830`
- `0x140159968`
- `0x14016a6bc`
- `0x14016af74`
- `0x1402cb010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14003f4b6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14003f4b6`
- `WS2_32!__imp_WSACleanup` at `0x14003f4cb`
- `WS2_32!__imp_WSACleanup` at `0x14003f4cb`
- `vid!VidSchedulerAssistReset` at `0x14003f419`
- `vid!VidSchedulerAssistReset` at `0x14003f419`
- `vid!VidEpfReset` at `0x14003f3e3`
- `vid!VidEpfReset` at `0x14003f3e3`

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
        (void *)0x9A3,
        (unsigned int)"onecore\\vm\\worker\\wpcore\\virtualmachine.cpp",
        v6);
    if ( (v5 & 0x100000) != 0 && !(unsigned int)VidSchedulerAssistReset(*((_QWORD *)this + 122)) )
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0x9A8,
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
0x14003f2cc  push    rbp
0x14003f2ce  push    rbx
0x14003f2cf  push    rsi
0x14003f2d0  push    rdi
0x14003f2d1  push    r12
0x14003f2d3  push    r13
0x14003f2d5  push    r14
0x14003f2d7  push    r15
0x14003f2d9  lea     rbp, [rsp-0A8h]
0x14003f2e1  sub     rsp, 1A8h
0x14003f2e8  mov     rax, cs:__security_cookie
0x14003f2ef  xor     rax, rsp
0x14003f2f2  mov     [rbp+0E0h+var_50], rax
0x14003f2f9  mov     rbx, rcx
0x14003f2fc  movups  xmm0, xmmword ptr [rcx+470h]
0x14003f303  movdqu  [rsp+1E0h+var_1B8], xmm0
0x14003f309  xor     edx, edx; Val
0x14003f30b  mov     r8d, 150h; Size
0x14003f311  lea     rcx, [rsp+1E0h+var_1A0]; void *
0x14003f316  call    memset_0
0x14003f31b  lea     rdx, aVmteardown; "VmTeardown"
0x14003f322  lea     rcx, [rsp+1E0h+var_1A0]; struct wil::details::IFailureCallback *
0x14003f327  call    ??0?$ActivityBase@VVmWorkerTrace@@$0A@$0BA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<VmWorkerTrace,0,16,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<VmWorkerTrace,0,16,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x14003f32c  lea     r13, ??_7VmTeardown@VmWorkerTrace@@6B@; const VmWorkerTrace::VmTeardown::`vftable'
0x14003f333  mov     [rsp+1E0h+var_1A0], r13
0x14003f338  lea     rcx, [rsp+1E0h+var_1A0]; this
0x14003f33d  call    ?StartActivity@VmTeardown@VmWorkerTrace@@QEAAXXZ; VmWorkerTrace::VmTeardown::StartActivity(void)
0x14003f342  nop
0x14003f343  mov     rax, [rbp+0E0h+var_90]
0x14003f347  lea     r15, [rbx+0A40h]
0x14003f34e  xor     r12d, r12d
0x14003f351  add     rax, 8
0x14003f355  jz      short loc_14003F35C
0x14003f357  movups  xmm0, xmmword ptr [rax]
0x14003f35a  jmp     short loc_14003F35F
0x14003f35c  xorps   xmm0, xmm0
0x14003f35f  movdqu  xmmword ptr [r15], xmm0
0x14003f364  mov     [rsp+1E0h+var_1C0], r15
0x14003f369  lea     rcx, [rbx+6B0h]; this
0x14003f370  call    ?DisableAndWait@AsyncTimer@@QEAAHXZ; AsyncTimer::DisableAndWait(void)
0x14003f375  lea     rdx, [rsp+1E0h+var_1B8]
0x14003f37a  lea     rcx, [rsp+1E0h+var_1A0]
0x14003f37f  call    ??$TeardownTimerWait@AEAU_GUID@@@VmTeardown@VmWorkerTrace@@QEAAXAEAU_GUID@@@Z; VmWorkerTrace::VmTeardown::TeardownTimerWait<_GUID &>(_GUID &)
0x14003f384  xor     edx, edx; int
0x14003f386  mov     rcx, rbx; this
0x14003f389  call    ?TeardownPartition@VirtualMachine@@AEAAXH@Z; VirtualMachine::TeardownPartition(int)
0x14003f38e  lea     rdx, [rsp+1E0h+var_1B8]
0x14003f393  lea     rcx, [rsp+1E0h+var_1A0]
0x14003f398  call    ??$TeardownPartition@AEAU_GUID@@@VmTeardown@VmWorkerTrace@@QEAAXAEAU_GUID@@@Z; VmWorkerTrace::VmTeardown::TeardownPartition<_GUID &>(_GUID &)
0x14003f39d  lea     r14, [rbx+400h]
0x14003f3a4  mov     rcx, [r14]
0x14003f3a7  test    rcx, rcx
0x14003f3aa  jz      loc_14003F484
0x14003f3b0  add     rcx, 8
0x14003f3b4  mov     rax, [rcx]
0x14003f3b7  mov     rax, [rax+58h]
0x14003f3bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003f3c0  mov     rcx, [r14]
0x14003f3c3  mov     rax, [rcx]
0x14003f3c6  mov     rax, [rax+140h]
0x14003f3cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003f3d2  mov     rdi, rax
0x14003f3d5  bt      rax, 11h
0x14003f3da  jnb     short loc_14003F40B
0x14003f3dc  mov     rcx, [rbx+3D0h]
0x14003f3e3  call    cs:__imp_VidEpfReset
0x14003f3ea  nop     dword ptr [rax+rax+00h]
0x14003f3ef  mov     rcx, [rbp+0E8h]; this
0x14003f3f6  test    eax, eax
0x14003f3f8  jnz     short loc_14003F40B
0x14003f3fa  lea     r8, aOnecoreVmWorke_77; "onecore\\vm\\worker\\wpcore\\virtualmac"...
0x14003f401  mov     edx, 9A3h; void *
0x14003f406  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x14003f40b  bt      rdi, 14h
0x14003f410  jnb     short loc_14003F441
0x14003f412  mov     rcx, [rbx+3D0h]
0x14003f419  call    cs:__imp_VidSchedulerAssistReset
0x14003f420  nop     dword ptr [rax+rax+00h]
0x14003f425  mov     rcx, [rbp+0E8h]; this
0x14003f42c  test    eax, eax
0x14003f42e  jnz     short loc_14003F441
0x14003f430  lea     r8, aOnecoreVmWorke_77; "onecore\\vm\\worker\\wpcore\\virtualmac"...
0x14003f437  mov     edx, 9A8h; void *
0x14003f43c  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x14003f441  mov     rcx, [rbx+410h]
0x14003f448  test    rcx, rcx
0x14003f44b  jz      short loc_14003F484
0x14003f44d  mov     rax, [rcx]
0x14003f450  mov     rax, [rax+0B8h]
0x14003f457  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003f45c  test    eax, eax
0x14003f45e  jz      short loc_14003F484
0x14003f460  cmp     dword ptr [rbx+4F4h], 3
0x14003f467  jz      short loc_14003F484
0x14003f469  mov     rcx, [r14]
0x14003f46c  add     rcx, 18h
0x14003f470  mov     rax, [rcx]
0x14003f473  xor     r8d, r8d
0x14003f476  mov     edx, 80100h
0x14003f47b  mov     rax, [rax+18h]
0x14003f47f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003f484  mov     rcx, rbx; this
0x14003f487  call    ?TeardownMotherboard@VirtualMachine@@QEAAXXZ; VirtualMachine::TeardownMotherboard(void)
0x14003f48c  lea     rdx, [rsp+1E0h+var_1B8]
0x14003f491  lea     rcx, [rsp+1E0h+var_1A0]
0x14003f496  call    ??$TeardownMotherboard@AEAU_GUID@@@VmTeardown@VmWorkerTrace@@QEAAXAEAU_GUID@@@Z; VmWorkerTrace::VmTeardown::TeardownMotherboard<_GUID &>(_GUID &)
0x14003f49b  lea     rsi, [rbx+418h]
0x14003f4a2  mov     rdi, [rsi]
0x14003f4a5  test    rdi, rdi
0x14003f4a8  jz      short loc_14003F4E1
0x14003f4aa  mov     rcx, [rdi+0E0h]; pwa
0x14003f4b1  test    rcx, rcx
0x14003f4b4  jz      short loc_14003F4C2
0x14003f4b6  call    cs:__imp_CloseThreadpoolWait
0x14003f4bd  nop     dword ptr [rax+rax+00h]
0x14003f4c2  cmp     [rdi+0D0h], r12d
0x14003f4c9  jz      short loc_14003F4D7
0x14003f4cb  call    cs:__imp_WSACleanup
0x14003f4d2  nop     dword ptr [rax+rax+00h]
0x14003f4d7  xor     edx, edx
0x14003f4d9  mov     rcx, rsi
0x14003f4dc  call    ?Reset@?$VmReferencePtr@VWorkerConfiguration@@VVmUserReferenceTraits@Vml@@@Vml@@QEAAXPEAVWorkerConfiguration@@@Z; Vml::VmReferencePtr<WorkerConfiguration,Vml::VmUserReferenceTraits>::Reset(WorkerConfiguration *)
0x14003f4e1  lea     rdx, [rsp+1E0h+var_1B8]
0x14003f4e6  lea     rcx, [rsp+1E0h+var_1A0]
0x14003f4eb  call    ??$TeardownMigrationManager@AEAU_GUID@@@VmTeardown@VmWorkerTrace@@QEAAXAEAU_GUID@@@Z; VmWorkerTrace::VmTeardown::TeardownMigrationManager<_GUID &>(_GUID &)
0x14003f4f0  mov     rdx, [rbx+0A18h]
0x14003f4f7  mov     [rbx+0A18h], r12
0x14003f4fe  test    rdx, rdx
0x14003f501  jz      short loc_14003F517
0x14003f503  mov     rax, [rdx+8]
0x14003f507  movsxd  rcx, dword ptr [rax+4]
0x14003f50b  add     rdx, 8
0x14003f50f  add     rcx, rdx; this
0x14003f512  call    ?DecrementUserCount@VmSharableObject@Vml@@AEAAKXZ; Vml::VmSharableObject::DecrementUserCount(void)
0x14003f517  mov     [rbx+598h], r12
0x14003f51e  mov     rcx, [rbx+590h]
0x14003f525  mov     [rbx+590h], r12
0x14003f52c  test    rcx, rcx
0x14003f52f  jz      short loc_14003F53A
0x14003f531  add     rcx, 8; this
0x14003f535  call    ?DecrementUserCount@VmSharableObject@Vml@@AEAAKXZ; Vml::VmSharableObject::DecrementUserCount(void)
0x14003f53a  mov     rdx, [rbx+3E8h]
0x14003f541  test    rdx, rdx
0x14003f544  jz      short loc_14003F586
0x14003f546  mov     rcx, [rdx+98h]
0x14003f54d  add     rcx, 8
0x14003f551  mov     rax, [rcx]
0x14003f554  mov     rdx, [rdx+0C0h]
0x14003f55b  mov     rax, [rax+40h]
0x14003f55f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003f564  mov     rdx, [rbx+3E8h]
0x14003f56b  mov     rax, [rdx+8]
0x14003f56f  movsxd  rcx, dword ptr [rax+4]
0x14003f573  add     rdx, 8
0x14003f577  add     rcx, rdx; this
0x14003f57a  call    ?DecrementUserCount@VmSharableObject@Vml@@AEAAKXZ; Vml::VmSharableObject::DecrementUserCount(void)
0x14003f57f  mov     [rbx+3E8h], r12
0x14003f586  mov     rcx, [rbx+3F0h]; this
0x14003f58d  test    rcx, rcx
0x14003f590  jz      short loc_14003F5B9
0x14003f592  call    ?TeardownRegisteredResults@WorkerCpuidHandler@@AEAAXXZ; WorkerCpuidHandler::TeardownRegisteredResults(void)
0x14003f597  mov     rdx, [rbx+3F0h]
0x14003f59e  mov     rax, [rdx+8]
0x14003f5a2  movsxd  rcx, dword ptr [rax+4]
0x14003f5a6  add     rdx, 8
0x14003f5aa  add     rcx, rdx; this
0x14003f5ad  call    ?DecrementUserCount@VmSharableObject@Vml@@AEAAKXZ; Vml::VmSharableObject::DecrementUserCount(void)
0x14003f5b2  mov     [rbx+3F0h], r12
0x14003f5b9  mov     rcx, [rbx+3F8h]; this
0x14003f5c0  test    rcx, rcx
0x14003f5c3  jz      short loc_14003F5EC
0x14003f5c5  call    ?Teardown@WorkerExceptionHandler@@QEAAXXZ; WorkerExceptionHandler::Teardown(void)
0x14003f5ca  mov     rdx, [rbx+3F8h]
0x14003f5d1  mov     rax, [rdx+8]
0x14003f5d5  movsxd  rcx, dword ptr [rax+4]
0x14003f5d9  add     rdx, 8
0x14003f5dd  add     rcx, rdx; this
0x14003f5e0  call    ?DecrementUserCount@VmSharableObject@Vml@@AEAAKXZ; Vml::VmSharableObject::DecrementUserCount(void)
0x14003f5e5  mov     [rbx+3F8h], r12
0x14003f5ec  lea     rdx, [rsp+1E0h+var_1B8]
0x14003f5f1  lea     rcx, [rsp+1E0h+var_1A0]
0x14003f5f6  call    ??$TeardownInternalInterceptHandler@AEAU_GUID@@@VmTeardown@VmWorkerTrace@@QEAAXAEAU_GUID@@@Z; VmWorkerTrace::VmTeardown::TeardownInternalInterceptHandler<_GUID &>(_GUID &)
0x14003f5fb  mov     rcx, [rbx+3E0h]; this
0x14003f602  test    rcx, rcx
0x14003f605  jz      short loc_14003F613
0x14003f607  call    ?Teardown@MemoryManager@@QEAAXXZ; MemoryManager::Teardown(void)
0x14003f60c  mov     [rbx+3E0h], r12
0x14003f613  lea     rdi, [rbx+410h]
0x14003f61a  mov     rcx, [rdi]
0x14003f61d  test    rcx, rcx
0x14003f620  jz      short loc_14003F63B
0x14003f622  mov     rax, [rcx]
0x14003f625  mov     rax, [rax+108h]
0x14003f62c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003f631  xor     edx, edx
0x14003f633  mov     rcx, rdi
0x14003f636  call    ?Reset@?$VmReferencePtr@VVndCompletionThread@@VVmUserReferenceTraits@Vml@@@Vml@@QEAAXPEAVVndCompletionThread@@@Z; Vml::VmReferencePtr<VndCompletionThread,Vml::VmUserReferenceTraits>::Reset(VndCompletionThread *)
0x14003f63b  lea     rdx, [rsp+1E0h+var_1B8]
0x14003f640  lea     rcx, [rsp+1E0h+var_1A0]
0x14003f645  call    ??$TeardownProcessorManager@AEAU_GUID@@@VmTeardown@VmWorkerTrace@@QEAAXAEAU_GUID@@@Z; VmWorkerTrace::VmTeardown::TeardownProcessorManager<_GUID &>(_GUID &)
0x14003f64a  mov     rcx, [r14]
0x14003f64d  test    rcx, rcx
0x14003f650  jz      short loc_14003F668
0x14003f652  mov     rax, [rcx]
0x14003f655  mov     rax, [rax+58h]
0x14003f659  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003f65e  xor     edx, edx
0x14003f660  mov     rcx, r14
0x14003f663  call    ?Reset@?$VmReferencePtr@UIVidPartitionManager@@VVmUserReferenceTraits@Vml@@@Vml@@QEAAXPEAUIVidPartitionManager@@@Z; Vml::VmReferencePtr<IVidPartitionManager,Vml::VmUserReferenceTraits>::Reset(IVidPartitionManager *)
0x14003f668  mov     rcx, [rbx+420h]
0x14003f66f  test    rcx, rcx
0x14003f672  jz      short loc_14003F6D8
0x14003f674  mov     rax, [rbx+588h]
0x14003f67b  cmp     [rax+17Ch], r12d
0x14003f682  jnz     short loc_14003F6A2
0x14003f684  mov     edx, 1
0x14003f689  cmp     [rbx+4F4h], edx
0x14003f68f  jnz     short loc_14003F6A2
0x14003f691  cmp     [rbx+4F0h], edx
0x14003f697  jz      short loc_14003F6A5
0x14003f699  cmp     [rbx+4F8h], r12d
0x14003f6a0  jz      short loc_14003F6A5
0x14003f6a2  mov     edx, r12d
0x14003f6a5  mov     rax, [rcx]
0x14003f6a8  mov     rax, [rax+20h]
0x14003f6ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003f6b1  mov     rdx, [rbx+420h]
0x14003f6b8  mov     [rbx+420h], r12
0x14003f6bf  test    rdx, rdx
0x14003f6c2  jz      short loc_14003F6D8
0x14003f6c4  mov     rax, [rdx+8]
0x14003f6c8  movsxd  rcx, dword ptr [rax+4]
0x14003f6cc  add     rdx, 8
0x14003f6d0  add     rcx, rdx; this
0x14003f6d3  call    ?DecrementUserCount@VmSharableObject@Vml@@AEAAKXZ; Vml::VmSharableObject::DecrementUserCount(void)
0x14003f6d8  lea     rdx, [rsp+1E0h+var_1B8]
0x14003f6dd  lea     rcx, [rsp+1E0h+var_1A0]
0x14003f6e2  call    ??$TeardownSavedStateFileManager@AEAU_GUID@@@VmTeardown@VmWorkerTrace@@QEAAXAEAU_GUID@@@Z; VmWorkerTrace::VmTeardown::TeardownSavedStateFileManager<_GUID &>(_GUID &)
0x14003f6e7  lea     rcx, [rbx+428h]
0x14003f6ee  call    ?Reset@?$VmReferencePtr@UIMetricManager@@VVmUserReferenceTraits@Vml@@@Vml@@QEAAXPEAUIMetricManager@@@Z; Vml::VmReferencePtr<IMetricManager,Vml::VmUserReferenceTraits>::Reset(IMetricManager *)
0x14003f6f3  lea     rdx, [rsp+1E0h+var_1B8]
0x14003f6f8  lea     rcx, [rsp+1E0h+var_1A0]
0x14003f6fd  call    ??$TeardownMetricManager@AEAU_GUID@@@VmTeardown@VmWorkerTrace@@QEAAXAEAU_GUID@@@Z; VmWorkerTrace::VmTeardown::TeardownMetricManager<_GUID &>(_GUID &)
0x14003f702  mov     rdx, [rbx+408h]
0x14003f709  mov     [rbx+408h], r12
0x14003f710  test    rdx, rdx
0x14003f713  jz      short loc_14003F729
0x14003f715  mov     rax, [rdx+8]
0x14003f719  movsxd  rcx, dword ptr [rax+4]
0x14003f71d  add     rdx, 8
0x14003f721  add     rcx, rdx; this
0x14003f724  call    ?DecrementUserCount@VmSharableObject@Vml@@AEAAKXZ; Vml::VmSharableObject::DecrementUserCount(void)
0x14003f729  lea     rdx, [rsp+1E0h+var_1B8]
0x14003f72e  lea     rcx, [rsp+1E0h+var_1A0]
0x14003f733  call    ??$TeardownNumaManager@AEAU_GUID@@@VmTeardown@VmWorkerTrace@@QEAAXAEAU_GUID@@@Z; VmWorkerTrace::VmTeardown::TeardownNumaManager<_GUID &>(_GUID &)
0x14003f738  mov     rcx, [rbx+430h]
0x14003f73f  mov     [rbx+430h], r12
0x14003f746  test    rcx, rcx
0x14003f749  jz      short loc_14003F757
0x14003f74b  mov     rax, [rcx]
0x14003f74e  mov     rax, [rax+10h]
0x14003f752  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003f757  lea     rdx, [rsp+1E0h+var_1B8]
0x14003f75c  lea     rcx, [rsp+1E0h+var_1A0]
0x14003f761  call    ??$TeardownSecurityManager@AEAU_GUID@@@VmTeardown@VmWorkerTrace@@QEAAXAEAU_GUID@@@Z; VmWorkerTrace::VmTeardown::TeardownSecurityManager<_GUID &>(_GUID &)
0x14003f766  mov     rcx, [rbx+5A8h]
0x14003f76d  mov     [rbx+5A8h], r12
0x14003f774  test    rcx, rcx
0x14003f777  jz      short loc_14003F785
0x14003f779  mov     rax, [rcx]
0x14003f77c  mov     rax, [rax+10h]
0x14003f780  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003f785  mov     rcx, [rbx+910h]
0x14003f78c  mov     [rbx+910h], r12
0x14003f793  test    rcx, rcx
0x14003f796  jz      short loc_14003F7A4
0x14003f798  mov     rax, [rcx]
0x14003f79b  mov     rax, [rax+10h]
0x14003f79f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003f7a4  mov     rcx, [rbx+918h]
0x14003f7ab  mov     [rbx+918h], r12
0x14003f7b2  test    rcx, rcx
0x14003f7b5  jz      short loc_14003F7C3
0x14003f7b7  mov     rax, [rcx]
0x14003f7ba  mov     rax, [rax+10h]
0x14003f7be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003f7c3  mov     rcx, [rbx+5B8h]
0x14003f7ca  mov     [rbx+5B8h], r12
0x14003f7d1  test    rcx, rcx
0x14003f7d4  jz      short loc_14003F7E2
0x14003f7d6  mov     rax, [rcx]
0x14003f7d9  mov     rax, [rax+10h]
0x14003f7dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003f7e2  mov     rcx, [rbx+5C0h]
0x14003f7e9  mov     [rbx+5C0h], r12
0x14003f7f0  test    rcx, rcx
0x14003f7f3  jz      short loc_14003F801
0x14003f7f5  mov     rax, [rcx]
0x14003f7f8  mov     rax, [rax+10h]
0x14003f7fc  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
