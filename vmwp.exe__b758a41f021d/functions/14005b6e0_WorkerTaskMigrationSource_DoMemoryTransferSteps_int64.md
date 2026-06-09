# WorkerTaskMigrationSource::DoMemoryTransferSteps(__int64 &)

- ea: `0x14005b6e0`
- end: `0x14005ba57`
- name: `?DoMemoryTransferSteps@WorkerTaskMigrationSource@@AEAAJAEA_J@Z`
- size: `887`
- prototype: `__int64 __fastcall(WorkerTaskMigrationSource *__hidden this, __int64 *)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x140059d50`

## callees

- `0x1400012e0`
- `0x14001ec28`
- `0x14003b720`
- `0x14005b6e0`
- `0x14005ba60`
- `0x14005bac0`
- `0x14005c320`
- `0x14005c420`
- `0x140078628`
- `0x14007e850`
- `0x1400835ec`
- `0x1400bc420`
- `0x1400f1e50`
- `0x1400fece0`
- `0x14011ea40`
- `0x1401f28d4`
- `0x14020cf58`
- `0x14021df24`
- `0x140225f38`
- `0x1402cb010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005b88e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005b88e`
- `vid!VidMemXferConnectOpen` at `0x14005b87a`
- `vid!VidMemXferConnectOpen` at `0x14005b87a`

## string_xrefs

- `0x14005b79e`: `onecore\vm\worker\migration\workertaskmigrationsource.cpp`
- `0x14005b7e7`: `onecore\vm\worker\migration\workertaskmigrationsource.cpp`
- `0x14005b813`: `onecore\vm\worker\migration\workertaskmigrationsource.cpp`
- `0x14005b847`: `onecore\vm\worker\migration\workertaskmigrationsource.cpp`
- `0x14005b94d`: `onecore\vm\worker\migration\workertaskmigrationsource.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall WorkerTaskMigrationSource::DoMemoryTransferSteps(
        WorkerTaskMigrationSource *this,
        __int64 *a2,
        __int64 a3)
{
  __int64 v5; // r9
  __int64 v6; // rax
  __int64 v7; // rdx
  __int64 v8; // r9
  int v9; // eax
  MigrationManager *v10; // rbx
  int started; // eax
  int v12; // eax
  __int64 (__fastcall ***v13)(_QWORD); // rcx
  __int64 v14; // rax
  signed int LastError; // eax
  unsigned int v16; // r14d
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 *v19; // rcx
  __int64 v20; // rax
  int v22; // [rsp+20h] [rbp-A8h]
  int v23; // [rsp+20h] [rbp-A8h]
  void *v24; // [rsp+40h] [rbp-88h] BYREF
  __int64 v25; // [rsp+48h] [rbp-80h] BYREF
  __int64 VmName; // [rsp+50h] [rbp-78h] BYREF
  __int64 v27; // [rsp+58h] [rbp-70h] BYREF
  __int64 (__fastcall *v28)(); // [rsp+60h] [rbp-68h]
  __int64 v29; // [rsp+68h] [rbp-60h]
  WorkerTaskMigrationSource *v30; // [rsp+70h] [rbp-58h]
  __int64 *v31; // [rsp+90h] [rbp-38h]
  __int64 v32[4]; // [rsp+98h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  if ( (*((_DWORD *)this + 257) & 0x200) != 0 )
  {
    v5 = *((_QWORD *)this + 159);
    v24 =  IVmLiveMigrationTargetEvents::`vcall'{40,{flat}};
    v6 = std::bind<long (IVirtualDeviceMigration::*)(void),std::_Ph<1> const &>(v32, &v24, a3, v5);
    v31 = 0;
    v27 = (__int64)&std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,long (IVirtualDeviceMigration::*)(void),std::_Ph<1> const &>,long,IVirtualDeviceMigration *>::`vftable';
    v28 = *(__int64 (__fastcall **)())v6;
    LOBYTE(v29) = *(_BYTE *)(v6 + 8);
    v31 = &v27;
    VirtualDeviceMigrationCollection<VmWorkerTrace::SourceMigrationTask>::Invoke<VmWorkerTrace::PrepareForMigrationBrownoutTransferAtSource,VmWorkerTrace::PrepareForMigrationBrownoutTransferAtSourcePerVdev,>(
      v8,
      v7,
      &v27);
  }
  if ( *((_DWORD *)this + 230) )
  {
    v9 = GmoMigration::EnableAccessTracking(*((GmoMigration **)this + 58));
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x57A,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
        (const char *)(unsigned int)v9,
        v22);
  }
  v24 = 0;
  v10 = (MigrationManager *)*((_QWORD *)this + 54);
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &v24,
    0);
  started = MigrationManager::WaitForStartTransfer(v10, &v24);
  if ( started < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x57E,
      (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
      (const char *)(unsigned int)started,
      v22);
  v12 = WorkerTaskMigrationSource::CheckCancel((WorkerTaskMigrationSource *)((char *)this + 400));
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x580,
      (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
      (const char *)(unsigned int)v12,
      v22);
  if ( (*((_BYTE *)this + 1028) & 8) != 0 )
  {
    if ( !v24 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x584,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
        (const char *)0x80070006LL,
        v22);
    v13 = (__int64 (__fastcall ***)(_QWORD))(*(_QWORD *)(*((_QWORD *)this + 2) + 1024LL) + 24LL);
    v14 = (**v13)(v13);
    if ( !(unsigned int)VidMemXferConnectOpen(v14, v24) )
    {
      LastError = GetLastError();
      v16 = LastError;
      if ( LastError > 0 )
        v16 = (unsigned __int16)LastError | 0x80070000;
      _snwprintf_s<16>(&v27, 16, L"%%%%%u", v16 & 0xEFFFFFFF);
      _snwprintf_s<16>(v32, 16, L"0x%08X", v16 & 0xEFFFFFFF);
      v17 = *((_QWORD *)this + 2);
      v25 = v17 + 1152;
      VmName = (__int64)VirtualMachine::GetVmName((VirtualMachine *)(v17 + 16));
      VmEventWriteAndReport<unsigned short const *,unsigned short const *,unsigned short (&)[16],unsigned short (&)[16]>(
        (struct _EVENT_DESCRIPTOR *)&MSVM_WORKER_MIGRATION_SOURCE_SMB_SHARE_OPEN_FAILED,
        5u,
        (__int64)&VmName,
        (__int64)&v25,
        (__int64)&v27,
        (__int64)v32);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x595,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
        (const char *)v16,
        v23);
    }
    *((_DWORD *)this + 118) = 1;
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &v24,
    0);
  WorkerTaskMigrationSource::StartStateTransferProgressToSourceVmmsTimer((struct _TP_TIMER **)this);
  wil::details::lambda_call__lambda_429a5c1df7b22a965c642a91f03ef627___::__autoclassinit2(v32);
  v18 = _tlgWrapSz<unsigned short>::_tlgWrapSz<unsigned short>(&VmName, this);
  wil::scope_exit__lambda_b9f70fa37eb8ffe11aaa181db9f48d0d___(v32, v18);
  v19 = (__int64 *)*((_QWORD *)this + 165);
  v20 = *v19;
  v27 = (__int64)&std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,long (WorkerTaskMigrationSource::*)(void),WorkerTaskMigrationSource *>,long,>::`vftable';
  v28 =  WorkerTaskMigrationSource::`vcall'{0,{flat}};
  v29 = 400;
  v30 = this;
  v31 = &v27;
  (*(void (__fastcall **)(__int64 *, __int64 *, __int64 *))(v20 + 16))(v19, &v27, a2);
  LODWORD(v25) = 0;
  WorkerAsyncTaskBase::UpdateStatusProgress(this, 0x5Au, (int *)&v25);
  wil::details::lambda_call__lambda_b9f70fa37eb8ffe11aaa181db9f48d0d___::_lambda_call__lambda_b9f70fa37eb8ffe11aaa181db9f48d0d___(v32);
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v24);
  return 0;
}

```

## disassembly

```asm
0x14005b6e0  mov     r11, rsp
0x14005b6e3  mov     [r11+18h], rbx
0x14005b6e7  mov     [r11+20h], rdi
0x14005b6eb  push    r14
0x14005b6ed  sub     rsp, 0C0h
0x14005b6f4  mov     rax, cs:__security_cookie
0x14005b6fb  xor     rax, rsp
0x14005b6fe  mov     [rsp+0C8h+var_10], rax
0x14005b706  mov     r14, rdx
0x14005b709  mov     rdi, rcx
0x14005b70c  test    dword ptr [rcx+404h], 200h
0x14005b716  jz      short loc_14005B77A
0x14005b718  mov     r9, [rcx+4F8h]
0x14005b71f  lea     rax, ??_9IVmLiveMigrationTargetEvents@@$BCI@AA; [thunk]: IVmLiveMigrationTargetEvents::`vcall'{40,{flat}}
0x14005b726  mov     [rsp+0C8h+var_88], rax
0x14005b72b  lea     rdx, [rsp+0C8h+var_88]
0x14005b730  lea     rcx, [r11-30h]
0x14005b734  call    ??$bind@P8IVirtualDeviceMigration@@EAAJXZAEBU?$_Ph@$00@std@@@std@@YA?AV?$_Binder@U_Unforced@std@@P8IVirtualDeviceMigration@@EAAJXZAEBU?$_Ph@$00@2@@0@$$QEAP8IVirtualDeviceMigration@@EAAJXZAEBU?$_Ph@$00@0@@Z; std::bind<long (IVirtualDeviceMigration::*)(void),std::_Ph<1> const &>(long (IVirtualDeviceMigration::*&&)(void),std::_Ph<1> const &)
0x14005b739  mov     [rsp+0C8h+var_38], 0
0x14005b745  lea     rcx, ??_7?$_Func_impl_no_alloc@V?$_Binder@U_Unforced@std@@P8IVirtualDeviceMigration@@EAAJXZAEBU?$_Ph@$00@2@@std@@JPEAUIVirtualDeviceMigration@@@std@@6B@; const std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,long (IVirtualDeviceMigration::*)(void),std::_Ph<1> const &>,long,IVirtualDeviceMigration *>::`vftable'
0x14005b74c  mov     [rsp+0C8h+var_70], rcx
0x14005b751  mov     rcx, [rax]
0x14005b754  mov     [rsp+0C8h+var_68], rcx
0x14005b759  mov     al, [rax+8]
0x14005b75c  mov     byte ptr [rsp+0C8h+var_60], al
0x14005b760  lea     rax, [rsp+0C8h+var_70]
0x14005b765  mov     [rsp+0C8h+var_38], rax
0x14005b76d  lea     r8, [rsp+0C8h+var_70]
0x14005b772  mov     rcx, r9
0x14005b775  call    ??$Invoke@VPrepareForMigrationBrownoutTransferAtSource@VmWorkerTrace@@VPrepareForMigrationBrownoutTransferAtSourcePerVdev@2@$$V@?$VirtualDeviceMigrationCollection@VSourceMigrationTask@VmWorkerTrace@@@@IEAAXW4IVirtualDeviceMigration@Methods@VmMigrationVDevOperationSettings@@V?$function@$$A6AJPEAUIVirtualDeviceMigration@@@Z@std@@@Z; VirtualDeviceMigrationCollection<VmWorkerTrace::SourceMigrationTask>::Invoke<VmWorkerTrace::PrepareForMigrationBrownoutTransferAtSource,VmWorkerTrace::PrepareForMigrationBrownoutTransferAtSourcePerVdev,>(VmMigrationVDevOperationSettings::Methods::IVirtualDeviceMigration,std::function<long (IVirtualDeviceMigration *)>)
0x14005b77a  cmp     dword ptr [rdi+398h], 0
0x14005b781  jz      short loc_14005B7AF
0x14005b783  mov     rcx, [rdi+1D0h]; this
0x14005b78a  call    ?EnableAccessTracking@GmoMigration@@QEAAJXZ; GmoMigration::EnableAccessTracking(void)
0x14005b78f  mov     rcx, [rsp+0C8h]; this
0x14005b797  test    eax, eax
0x14005b799  jns     short loc_14005B7AF
0x14005b79b  mov     r9d, eax; char *
0x14005b79e  lea     r8, aOnecoreVmWorke_0; "onecore\\vm\\worker\\migration\\workert"...
0x14005b7a5  mov     edx, 57Ah; void *
0x14005b7aa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14005b7af  mov     [rsp+0C8h+var_88], 0
0x14005b7b8  mov     rbx, [rdi+1B0h]
0x14005b7bf  xor     edx, edx
0x14005b7c1  lea     rcx, [rsp+0C8h+var_88]
0x14005b7c6  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?NtClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x14005b7cb  lea     rdx, [rsp+0C8h+var_88]; void **
0x14005b7d0  mov     rcx, rbx; this
0x14005b7d3  call    ?WaitForStartTransfer@MigrationManager@@QEAAJPEAPEAX@Z; MigrationManager::WaitForStartTransfer(void * *)
0x14005b7d8  mov     rcx, [rsp+0C8h]; this
0x14005b7e0  test    eax, eax
0x14005b7e2  jns     short loc_14005B7F8
0x14005b7e4  mov     r9d, eax; char *
0x14005b7e7  lea     r8, aOnecoreVmWorke_0; "onecore\\vm\\worker\\migration\\workert"...
0x14005b7ee  mov     edx, 57Eh; void *
0x14005b7f3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14005b7f8  lea     rcx, [rdi+190h]; this
0x14005b7ff  call    ?CheckCancel@WorkerTaskMigrationSource@@UEAAJXZ; WorkerTaskMigrationSource::CheckCancel(void)
0x14005b804  mov     rcx, [rsp+0C8h]; this
0x14005b80c  test    eax, eax
0x14005b80e  jns     short loc_14005B824
0x14005b810  mov     r9d, eax; char *
0x14005b813  lea     r8, aOnecoreVmWorke_0; "onecore\\vm\\worker\\migration\\workert"...
0x14005b81a  mov     edx, 580h; void *
0x14005b81f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14005b824  test    byte ptr [rdi+404h], 8
0x14005b82b  jz      loc_14005B968
0x14005b831  mov     rcx, [rsp+0C8h]; this
0x14005b839  cmp     [rsp+0C8h+var_88], 0
0x14005b83f  jnz     short loc_14005B858
0x14005b841  mov     r9d, 80070006h; char *
0x14005b847  lea     r8, aOnecoreVmWorke_0; "onecore\\vm\\worker\\migration\\workert"...
0x14005b84e  mov     edx, 584h; void *
0x14005b853  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14005b858  mov     rax, [rdi+10h]
0x14005b85c  mov     rcx, [rax+400h]
0x14005b863  add     rcx, 18h
0x14005b867  mov     rax, [rcx]
0x14005b86a  mov     rax, [rax]
0x14005b86d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005b872  mov     rdx, [rsp+0C8h+var_88]
0x14005b877  mov     rcx, rax
0x14005b87a  call    cs:__imp_VidMemXferConnectOpen
0x14005b881  nop     dword ptr [rax+rax+00h]
0x14005b886  test    eax, eax
0x14005b888  jnz     loc_14005B95E
0x14005b88e  call    cs:__imp_GetLastError
0x14005b895  nop     dword ptr [rax+rax+00h]
0x14005b89a  mov     r14d, eax
0x14005b89d  test    eax, eax
0x14005b89f  jle     short loc_14005B8AC
0x14005b8a1  movzx   r14d, ax
0x14005b8a5  or      r14d, 80070000h
0x14005b8ac  mov     ebx, r14d
0x14005b8af  btr     ebx, 1Ch
0x14005b8b3  mov     r9d, ebx
0x14005b8b6  lea     r8, aU_0; "%%%%%u"
0x14005b8bd  mov     edx, 10h
0x14005b8c2  lea     rcx, [rsp+0C8h+var_70]
0x14005b8c7  call    ??$_snwprintf_s@$0BA@@@YAHAEAY0BA@G_KPEBGZZ; _snwprintf_s<16>(ushort (&)[16],unsigned __int64,ushort const *,...)
0x14005b8cc  mov     r9d, ebx
0x14005b8cf  lea     r8, a0x08x; "0x%08X"
0x14005b8d6  mov     edx, 10h
0x14005b8db  lea     rcx, [rsp+0C8h+var_30]
0x14005b8e3  call    ??$_snwprintf_s@$0BA@@@YAHAEAY0BA@G_KPEBGZZ; _snwprintf_s<16>(ushort (&)[16],unsigned __int64,ushort const *,...)
0x14005b8e8  mov     rcx, [rdi+10h]
0x14005b8ec  lea     rax, [rcx+480h]
0x14005b8f3  mov     [rsp+0C8h+var_80], rax
0x14005b8f8  add     rcx, 10h; this
0x14005b8fc  call    ?GetVmName@VirtualMachine@@UEBAPEBGXZ; VirtualMachine::GetVmName(void)
0x14005b901  mov     [rsp+0C8h+var_78], rax
0x14005b906  lea     rax, [rsp+0C8h+var_30]
0x14005b90e  mov     [rsp+0C8h+var_90], rax; __int64
0x14005b913  lea     rax, [rsp+0C8h+var_70]
0x14005b918  mov     [rsp+0C8h+var_98], rax; __int64
0x14005b91d  lea     rax, [rsp+0C8h+var_80]
0x14005b922  mov     [rsp+0C8h+var_A0], rax; __int64
0x14005b927  lea     rax, [rsp+0C8h+var_78]
0x14005b92c  mov     [rsp+0C8h+var_A8], rax; int
0x14005b931  mov     edx, 5; unsigned int
0x14005b936  lea     rcx, MSVM_WORKER_MIGRATION_SOURCE_SMB_SHARE_OPEN_FAILED; struct _EVENT_DESCRIPTOR *
0x14005b93d  call    ??$VmEventWriteAndReport@PEBGPEBGAEAY0BA@GAEAY0BA@G@@YAXPEBU_EVENT_DESCRIPTOR@@IAEBU_GUID@@PEBG$$QEAPEBG3AEAY0BA@G4@Z; VmEventWriteAndReport<ushort const *,ushort const *,ushort (&)[16],ushort (&)[16]>(_EVENT_DESCRIPTOR const *,uint,_GUID const &,ushort const *,ushort const * &&,ushort const * &&,ushort (&)[16],ushort (&)[16])
0x14005b942  mov     rcx, [rsp+0C8h]; this
0x14005b94a  mov     r9d, r14d; char *
0x14005b94d  lea     r8, aOnecoreVmWorke_0; "onecore\\vm\\worker\\migration\\workert"...
0x14005b954  mov     edx, 595h; void *
0x14005b959  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14005b95e  mov     dword ptr [rdi+1D8h], 1
0x14005b968  xor     edx, edx
0x14005b96a  lea     rcx, [rsp+0C8h+var_88]
0x14005b96f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?NtClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x14005b974  mov     rcx, rdi; pv
0x14005b977  call    ?StartStateTransferProgressToSourceVmmsTimer@WorkerTaskMigrationSource@@AEAAXXZ; WorkerTaskMigrationSource::StartStateTransferProgressToSourceVmmsTimer(void)
0x14005b97c  lea     rcx, [rsp+0C8h+var_30]
0x14005b984  call    wil__details__lambda_call__lambda_429a5c1df7b22a965c642a91f03ef627_______autoclassinit2
0x14005b989  mov     rdx, rdi
0x14005b98c  lea     rcx, [rsp+0C8h+var_78]
0x14005b991  call    ??0?$_tlgWrapSz@G@@QEAA@PEBG@Z; _tlgWrapSz<ushort>::_tlgWrapSz<ushort>(ushort const *)
0x14005b996  mov     rdx, rax
0x14005b999  lea     rcx, [rsp+0C8h+var_30]
0x14005b9a1  call    wil__scope_exit__lambda_b9f70fa37eb8ffe11aaa181db9f48d0d___
0x14005b9a6  nop
0x14005b9a7  mov     rcx, [rdi+528h]
0x14005b9ae  mov     rax, [rcx]
0x14005b9b1  lea     rdx, ??_7?$_Func_impl_no_alloc@V?$_Binder@U_Unforced@std@@P8WorkerTaskMigrationSource@@EAAJXZPEAV3@@std@@J$$V@std@@6B@; const std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,long (WorkerTaskMigrationSource::*)(void),WorkerTaskMigrationSource *>,long,>::`vftable'
0x14005b9b8  mov     [rsp+0C8h+var_70], rdx
0x14005b9bd  lea     rdx, ??_9WorkerTaskMigrationSource@@$BA@AA; [thunk]: WorkerTaskMigrationSource::`vcall'{0,{flat}}
0x14005b9c4  mov     [rsp+0C8h+var_68], rdx
0x14005b9c9  mov     [rsp+0C8h+var_60], 190h
0x14005b9d2  mov     [rsp+0C8h+var_58], rdi
0x14005b9d7  lea     rdx, [rsp+0C8h+var_70]
0x14005b9dc  mov     [rsp+0C8h+var_38], rdx
0x14005b9e4  mov     r8, r14
0x14005b9e7  lea     rdx, [rsp+0C8h+var_70]
0x14005b9ec  mov     rax, [rax+10h]
0x14005b9f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005b9f5  mov     dword ptr [rsp+0C8h+var_80], 0
0x14005b9fd  lea     r8, [rsp+0C8h+var_80]; int *
0x14005ba02  mov     edx, 5Ah ; 'Z'; unsigned int
0x14005ba07  mov     rcx, rdi; this
0x14005ba0a  call    ?UpdateStatusProgress@WorkerAsyncTaskBase@@MEAAXIAEAH@Z; WorkerAsyncTaskBase::UpdateStatusProgress(uint,int &)
0x14005ba0f  nop
0x14005ba10  lea     rcx, [rsp+0C8h+var_30]
0x14005ba18  call    wil__details__lambda_call__lambda_b9f70fa37eb8ffe11aaa181db9f48d0d______lambda_call__lambda_b9f70fa37eb8ffe11aaa181db9f48d0d___
0x14005ba1d  nop
0x14005ba1e  lea     rcx, [rsp+0C8h+var_88]
0x14005ba23  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?NtClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14005ba28  xor     eax, eax
0x14005ba2a  jmp     short loc_14005BA30
0x14005ba2c  mov     eax, dword ptr [rsp+0C8h+var_80]
0x14005ba30  mov     rcx, [rsp+0C8h+var_10]
0x14005ba38  xor     rcx, rsp; StackCookie
0x14005ba3b  call    __security_check_cookie
0x14005ba40  lea     r11, [rsp+0C8h+var_8]
0x14005ba48  mov     rbx, [r11+20h]
0x14005ba4c  mov     rdi, [r11+28h]
0x14005ba50  mov     rsp, r11
0x14005ba53  pop     r14
0x14005ba55  retn
```
