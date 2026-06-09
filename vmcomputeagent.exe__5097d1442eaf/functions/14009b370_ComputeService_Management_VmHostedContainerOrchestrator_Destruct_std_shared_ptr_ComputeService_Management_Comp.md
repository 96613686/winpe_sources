# ComputeService::Management::VmHostedContainerOrchestrator::Destruct(std::shared_ptr<ComputeService::Management::ComputeSystem> const &,ComputeService::Management::DestructInfo const &)

- ea: `0x14009b370`
- end: `0x14009b8c7`
- name: `?Destruct@VmHostedContainerOrchestrator@Management@ComputeService@@UEAA_NAEBV?$shared_ptr@VComputeSystem@Management@ComputeService@@@std@@AEBUDestructInfo@23@@Z`
- size: `1367`
- prototype: ``
- caller_count: `0`
- callee_count: `28`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140005360`
- `0x140006098`
- `0x140008760`
- `0x14000ea60`
- `0x14001e4f4`
- `0x14003f374`
- `0x14003f698`
- `0x14003f850`
- `0x14003fa78`
- `0x14003ff0c`
- `0x140041ff0`
- `0x1400864a8`
- `0x140087550`
- `0x14008b1a8`
- `0x140093ee8`
- `0x140097360`
- `0x1400995ec`
- `0x14009b370`
- `0x14009d6dc`
- `0x1400af194`
- `0x1400b8da4`
- `0x1400bb3dc`
- `0x1400d3588`
- `0x1400d5c00`
- `0x1400da6e8`
- `0x1400da960`
- `0x1400f4eb8`
- `0x1400fe010`

## import_xrefs

- `IPHLPAPI!SetJobCompartmentId` at `0x14009b718`
- `IPHLPAPI!SetJobCompartmentId` at `0x14009b718`
- `wc_storage!WcDetachFilterEx` at `0x14009b770`
- `wc_storage!WcDetachFilterEx` at `0x14009b770`

## string_xrefs

- `0x14009b885`: `onecore\vm\compute\shared\net\NetworkUtilities.h`
- `0x14009b5d2`: `Compute system %ws exited unexpectedly`
- `0x14009b89d`: `onecore\vm\compute\management\computesystem\computesystem.h`
- `0x14009b8b5`: `onecore\vm\compute\management\computesystem\computesystem.h`
- `0x14009b5e8`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmhostedcontainerorchestrator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
char __fastcall ComputeService::Management::VmHostedContainerOrchestrator::Destruct(
        __int64 a1,
        _QWORD **a2,
        _DWORD *a3)
{
  void (__fastcall *v5)(__int64, __int128 *, __int128 *); // rcx
  __int64 v6; // r13
  __int64 v7; // rbx
  __int64 v8; // rax
  __int64 *v9; // rax
  __int64 v10; // rcx
  volatile signed __int32 *v11; // rdi
  unsigned __int64 v12; // rsi
  const char *v13; // rdx
  struct ComputeService::Management::BaseStateMachine *v14; // r8
  int v15; // eax
  ComputeService::Management::VmHostedContainer *v16; // rdi
  __int64 v17; // rcx
  __int64 v18; // rcx
  const char *v19; // r9
  ComputeService::ContainerUtilities *v20; // rsi
  __int64 v21; // r15
  _QWORD *v22; // rdx
  const unsigned __int16 *v23; // rdx
  struct ComputeService::Management::BaseContainerState *v24; // rdx
  const unsigned __int16 *v25; // rdx
  const WCHAR *v26; // rdx
  __int128 *p_Src; // rcx
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // rax
  int v32; // [rsp+20h] [rbp-E0h]
  void (__fastcall *v33)(__int64, __int128 *, __int128 *); // [rsp+40h] [rbp-C0h] BYREF
  __int64 v34; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v35; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v36; // [rsp+60h] [rbp-A0h]
  __int64 v37; // [rsp+68h] [rbp-98h]
  __int128 v38; // [rsp+70h] [rbp-90h] BYREF
  __int128 Src; // [rsp+80h] [rbp-80h] BYREF
  __int128 v40; // [rsp+90h] [rbp-70h]
  __int128 *v41; // [rsp+A8h] [rbp-58h]
  __int128 *v42; // [rsp+B0h] [rbp-50h]
  _QWORD v43[42]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v44[2]; // [rsp+210h] [rbp+110h] BYREF
  _QWORD v45[42]; // [rsp+220h] [rbp+120h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3B8h] [rbp+2B8h]

  memset_0(v45, 0, sizeof(v45));
  LODWORD(v34) = *a3;
  v5 = (void (__fastcall *)(__int64, __int128 *, __int128 *))(**a2 + 8LL);
  if ( *(_QWORD *)(**a2 + 32LL) > 7u )
    v5 = *(void (__fastcall **)(__int64, __int128 *, __int128 *))v5;
  v33 = v5;
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v45,
    "VmHostedContainer_Destruct");
  v45[0] = &ComputeService::Diagnostics::TraceProvider::VmHostedContainer_Destruct::`vftable';
  ComputeService::Diagnostics::TraceProvider::VmHostedContainer_Destruct::StartActivity<unsigned short const *,unsigned int,int const &>(
    v45,
    &v33,
    &v34,
    a3 + 2);
  v6 = _RTDynamicCast_0(
         **a2,
         0,
         &ComputeService::Management::ComputeSystemConfiguration `RTTI Type Descriptor',
         &ComputeService::Management::VmHostedContainerConfiguration `RTTI Type Descriptor');
  if ( !v6 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5D,
      (unsigned int)"onecore\\vm\\compute\\management\\computesystem\\computesystem.h",
      (const char *)0x80004001LL,
      0);
  v7 = _RTDynamicCast_0(
         (*a2)[1],
         0,
         &ComputeService::Management::ComputeSystemState `RTTI Type Descriptor',
         &ComputeService::Management::VmHostedComputeSystemState `RTTI Type Descriptor');
  if ( !v7 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5D,
      (unsigned int)"onecore\\vm\\compute\\management\\computesystem\\computesystem.h",
      (const char *)0x80004001LL,
      0);
  v44[0] = 0;
  v38 = 0;
  v41 = &v38;
  v8 = ComputeService::Diagnostics::TraceProvider::VmHostedContainer_Destruct::Split(v45, v43);
  v42 = &v35;
  v35 = 0;
  if ( *((_QWORD *)&v38 + 1) )
    _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v38 + 1) + 8LL));
  v35 = v38;
  v9 = (__int64 *)std::make_unique<ComputeService::Management::ActivityHolderImpl<ComputeService::Diagnostics::TraceProvider::VmHostedContainer_Destruct>,ComputeService::Diagnostics::TraceProvider::VmHostedContainer_Destruct,0>(
                    &v33,
                    v8);
  v10 = *v9;
  *v9 = 0;
  v34 = v10;
  ComputeService::Management::BeginOperation_DestructImpl(
    (unsigned int)v44,
    (_DWORD)a2,
    (_DWORD)a3,
    (unsigned int)&v34,
    (__int64)&v35,
    (__int64)lambda_a321f071fb85d275461122c97dc9cee8_::_lambda_invoker_cdecl_);
  if ( v33 )
    (**(void (__fastcall ***)(void (__fastcall *)(__int64, __int128 *, __int128 *), __int64))v33)(v33, 1);
  v11 = (volatile signed __int32 *)*((_QWORD *)&v38 + 1);
  v12 = -1;
  if ( *((_QWORD *)&v38 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v38 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
      if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
    }
  }
  v43[0] = &ComputeService::Diagnostics::TraceProvider::VmHostedContainer_Destruct::`vftable';
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v43);
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>(v43);
  if ( *(_DWORD *)(*(_QWORD *)v44[0] + 24LL) == 1 )
  {
    v13 = (const char *)(**a2 + 8LL);
    if ( *(_QWORD *)(**a2 + 32LL) > 7u )
      v13 = *(const char **)v13;
    LOBYTE(v32) = *(_BYTE *)a3 & 1;
    wil::details::in1diag3::Log_HrIfMsg(
      retaddr,
      (void *)0x1AA,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmhostedcontainerorchestrator.cpp",
      (const char *)0xC0370106LL,
      v32,
      (bool)"Compute system %ws exited unexpectedly",
      v13);
    v15 = *(_DWORD *)(*(_QWORD *)v44[0] + 16LL);
    if ( v15 == 9 )
    {
      ComputeService::ContainerUtilities::TerminateWindowsContainer(v7 + 128);
      *(_DWORD *)(*(_QWORD *)v44[0] + 24LL) = 0;
    }
    else if ( v15 == 10 )
    {
      ComputeService::Management::RundownOperationsForCleanup(
        (ComputeService::Management *)v44,
        (struct ComputeService::Management::ActiveStateOperation *)(v7 + 240),
        v14);
      v16 = (ComputeService::Management::VmHostedContainer *)(v7 + 144);
      ComputeService::ContainerUtilities::RemoveMappedDirectoryLinks(v17, v7 + 144, v6 + 400);
      if ( *(_QWORD *)(v6 + 672) )
      {
        v21 = ComputeService::Net::NetworkingInterface::m_interface;
        if ( !ComputeService::Net::NetworkingInterface::m_interface )
          wil::details::in1diag3::_Throw_NullAlloc(
            retaddr,
            (void *)0x8D,
            (unsigned int)"onecore\\vm\\compute\\shared\\net\\NetworkUtilities.h",
            v19);
        v33 = *(void (__fastcall **)(__int64, __int128 *, __int128 *))(*(_QWORD *)ComputeService::Net::NetworkingInterface::m_interface
                                                                     + 40LL);
        v22 = (_QWORD *)(**a2 + 8LL);
        if ( *(_QWORD *)(**a2 + 32LL) > 7u )
          v22 = (_QWORD *)*v22;
        Src = 0;
        v40 = 0;
        do
          ++v12;
        while ( *((_WORD *)v22 + v12) );
        std::wstring::_Construct<1,unsigned short const *>((__int64)&Src, v22, v12);
        v23 = (const unsigned __int16 *)(v6 + 656);
        if ( *(_QWORD *)(v6 + 680) > 7u )
          v23 = *(const unsigned __int16 **)v23;
        Vml::VmGuid::Assign((Vml::VmGuid *)&v35, v23);
        v33(v21, &v35, &Src);
        std::wstring::~wstring(&Src);
        v20 = (ComputeService::ContainerUtilities *)(v7 + 128);
        SetJobCompartmentId(*(HANDLE *)(v7 + 128), 0);
      }
      else
      {
        v20 = (ComputeService::ContainerUtilities *)(v7 + 128);
      }
      ComputeService::ContainerUtilities::RemoveMappedVirtualDiskLinks(v18, v7 + 144, v6 + 448);
      ComputeService::ContainerUtilities::CleanupWindowsContainer(v20, v24);
      if ( *(_BYTE *)(v7 + 176) )
      {
        if ( *(_QWORD *)(v7 + 168) <= 7u )
          v26 = (const WCHAR *)(v7 + 144);
        else
          v26 = *(const WCHAR **)v16;
        CommonUtilities::CombineFilePath(&Src, v26, L".\\");
        p_Src = &Src;
        if ( *((_QWORD *)&v40 + 1) > 7u )
          p_Src = (__int128 *)Src;
        WcDetachFilterEx(p_Src, 0);
        std::wstring::~wstring(&Src);
        *(_BYTE *)(v7 + 176) = 0;
      }
      if ( (*(_BYTE *)a3 & 2) == 0 && *(_QWORD *)(v7 + 160) )
      {
        if ( *(_QWORD *)(v7 + 168) > 7u )
          v16 = *(ComputeService::Management::VmHostedContainer **)v16;
        ComputeService::Management::VmHostedContainer::OfflineVolume(v16, v25);
      }
      *(_DWORD *)(*(_QWORD *)v44[0] + 136LL) = 0;
      *(_QWORD *)&v35 = *(_QWORD *)(v7 + 336);
      v28 = *(_QWORD *)(v7 + 360);
      *(_QWORD *)(v7 + 360) = 0;
      v29 = *(_QWORD *)(v7 + 352);
      *(_QWORD *)(v7 + 352) = 0;
      v30 = *(_QWORD *)(v7 + 344);
      *(_QWORD *)(v7 + 344) = 0;
      *((_QWORD *)&v35 + 1) = v30;
      v36 = v29;
      v37 = v28;
      ComputeService::Management::ActiveStateOperation::Complete(v44, &v35);
    }
  }
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v45,
    0);
  std::unique_ptr<ComputeService::Management::ActiveStateOperation::ActiveStateOperationContext>::~unique_ptr<ComputeService::Management::ActiveStateOperation::ActiveStateOperationContext>(v44);
  v45[0] = &ComputeService::Diagnostics::TraceProvider::VmHostedContainer_Destruct::`vftable';
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v45);
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>(v45);
  return 0;
}

```

## disassembly

```asm
0x14009b370  mov     [rsp-8+arg_0], rbx
0x14009b375  push    rbp
0x14009b376  push    rsi
0x14009b377  push    rdi
0x14009b378  push    r12
0x14009b37a  push    r13
0x14009b37c  push    r14
0x14009b37e  push    r15
0x14009b380  lea     rbp, [rsp-280h]
0x14009b388  sub     rsp, 380h
0x14009b38f  mov     rax, cs:__security_cookie
0x14009b396  xor     rax, rsp
0x14009b399  mov     [rbp+2B0h+var_40], rax
0x14009b3a0  mov     r12, r8
0x14009b3a3  mov     r14, rdx
0x14009b3a6  xor     r15d, r15d
0x14009b3a9  xor     edx, edx; Val
0x14009b3ab  mov     r8d, 150h; Size
0x14009b3b1  lea     rcx, [rbp+2B0h+var_190]; void *
0x14009b3b8  call    memset_0
0x14009b3bd  mov     eax, [r12]
0x14009b3c1  mov     dword ptr [rsp+3B0h+var_368], eax
0x14009b3c5  mov     rax, [r14]
0x14009b3c8  mov     rcx, [rax]
0x14009b3cb  add     rcx, 8
0x14009b3cf  cmp     qword ptr [rcx+18h], 7
0x14009b3d4  jbe     short loc_14009B3D9
0x14009b3d6  mov     rcx, [rcx]
0x14009b3d9  mov     [rsp+3B0h+var_370], rcx
0x14009b3de  lea     rdx, aVmhostedcontai; "VmHostedContainer_Destruct"
0x14009b3e5  lea     rcx, [rbp+2B0h+var_190]
0x14009b3ec  call    ??0?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x14009b3f1  lea     rax, ??_7VmHostedContainer_Destruct@TraceProvider@Diagnostics@ComputeService@@6B@; const ComputeService::Diagnostics::TraceProvider::VmHostedContainer_Destruct::`vftable'
0x14009b3f8  mov     [rbp+2B0h+var_190], rax
0x14009b3ff  lea     r9, [r12+8]
0x14009b404  lea     r8, [rsp+3B0h+var_368]
0x14009b409  lea     rdx, [rsp+3B0h+var_370]
0x14009b40e  lea     rcx, [rbp+2B0h+var_190]
0x14009b415  call    ??$StartActivity@PEBGIAEBH@VmHostedContainer_Destruct@TraceProvider@Diagnostics@ComputeService@@QEAAX$$QEAPEBG$$QEAIAEBH@Z; ComputeService::Diagnostics::TraceProvider::VmHostedContainer_Destruct::StartActivity<ushort const *,uint,int const &>(ushort const * &&,uint &&,int const &)
0x14009b41a  nop
0x14009b41b  mov     rcx, [r14]
0x14009b41e  mov     [rsp+3B0h+var_390], r15d; int
0x14009b423  lea     r9, ??_R0?AUVmHostedContainerConfiguration@Management@ComputeService@@@8; ComputeService::Management::VmHostedContainerConfiguration `RTTI Type Descriptor'
0x14009b42a  lea     r8, ??_R0?AUComputeSystemConfiguration@Management@ComputeService@@@8; ComputeService::Management::ComputeSystemConfiguration `RTTI Type Descriptor'
0x14009b431  xor     edx, edx
0x14009b433  mov     rcx, [rcx]
0x14009b436  call    __RTDynamicCast_0
0x14009b43b  mov     r13, rax
0x14009b43e  mov     rcx, [rbp+2B8h]; this
0x14009b445  test    rax, rax
0x14009b448  jz      loc_14009B897
0x14009b44e  mov     rcx, [r14]
0x14009b451  mov     [rsp+3B0h+var_390], r15d; int
0x14009b456  lea     r9, ??_R0?AUVmHostedComputeSystemState@Management@ComputeService@@@8; ComputeService::Management::VmHostedComputeSystemState `RTTI Type Descriptor'
0x14009b45d  lea     r8, ??_R0?AUComputeSystemState@Management@ComputeService@@@8; ComputeService::Management::ComputeSystemState `RTTI Type Descriptor'
0x14009b464  xor     edx, edx
0x14009b466  mov     rcx, [rcx+8]
0x14009b46a  call    __RTDynamicCast_0
0x14009b46f  mov     rbx, rax
0x14009b472  mov     rcx, [rbp+2B8h]; this
0x14009b479  test    rax, rax
0x14009b47c  jz      loc_14009B8AF
0x14009b482  mov     [rbp+2B0h+var_1A0], r15
0x14009b489  xorps   xmm0, xmm0
0x14009b48c  movdqa  [rsp+3B0h+var_340], xmm0
0x14009b492  lea     rax, [rsp+3B0h+var_340]
0x14009b497  mov     [rbp+2B0h+var_308], rax
0x14009b49b  lea     rdx, [rbp+2B0h+var_2F0]
0x14009b49f  lea     rcx, [rbp+2B0h+var_190]
0x14009b4a6  call    ?Split@VmHostedContainer_Destruct@TraceProvider@Diagnostics@ComputeService@@QEAA?AV1234@XZ; ComputeService::Diagnostics::TraceProvider::VmHostedContainer_Destruct::Split(void)
0x14009b4ab  nop
0x14009b4ac  lea     rcx, [rsp+3B0h+var_360]
0x14009b4b1  mov     [rbp+2B0h+var_300], rcx
0x14009b4b5  xorps   xmm0, xmm0
0x14009b4b8  movdqa  [rsp+3B0h+var_360], xmm0
0x14009b4be  mov     rcx, qword ptr [rsp+3B0h+var_340+8]
0x14009b4c3  test    rcx, rcx
0x14009b4c6  jz      short loc_14009B4CC
0x14009b4c8  lock inc dword ptr [rcx+8]
0x14009b4cc  movaps  xmm0, [rsp+3B0h+var_340]
0x14009b4d1  movdqa  [rsp+3B0h+var_360], xmm0
0x14009b4d7  mov     rdx, rax
0x14009b4da  lea     rcx, [rsp+3B0h+var_370]
0x14009b4df  call    ??$make_unique@V?$ActivityHolderImpl@VVmHostedContainer_Destruct@TraceProvider@Diagnostics@ComputeService@@@Management@ComputeService@@VVmHostedContainer_Destruct@TraceProvider@Diagnostics@3@$0A@@std@@YA?AV?$unique_ptr@V?$ActivityHolderImpl@VVmHostedContainer_Destruct@TraceProvider@Diagnostics@ComputeService@@@Management@ComputeService@@U?$default_delete@V?$ActivityHolderImpl@VVmHostedContainer_Destruct@TraceProvider@Diagnostics@ComputeService@@@Management@ComputeService@@@std@@@0@$$QEAVVmHostedContainer_Destruct@TraceProvider@Diagnostics@ComputeService@@@Z; std::make_unique<ComputeService::Management::ActivityHolderImpl<ComputeService::Diagnostics::TraceProvider::VmHostedContainer_Destruct>,ComputeService::Diagnostics::TraceProvider::VmHostedContainer_Destruct,0>(ComputeService::Diagnostics::TraceProvider::VmHostedContainer_Destruct &&)
0x14009b4e4  nop
0x14009b4e5  mov     rcx, [rax]
0x14009b4e8  mov     [rax], r15
0x14009b4eb  mov     [rsp+3B0h+var_368], rcx
0x14009b4f0  lea     rax, _lambda_a321f071fb85d275461122c97dc9cee8____lambda_invoker_cdecl_
0x14009b4f7  mov     qword ptr [rsp+3B0h+var_388], rax
0x14009b4fc  lea     rax, [rsp+3B0h+var_360]
0x14009b501  mov     qword ptr [rsp+3B0h+var_390], rax
0x14009b506  lea     r9, [rsp+3B0h+var_368]
0x14009b50b  mov     r8, r12
0x14009b50e  mov     rdx, r14
0x14009b511  lea     rcx, [rbp+2B0h+var_1A0]
0x14009b518  call    ?BeginOperation_DestructImpl@Management@ComputeService@@YA?AVActiveStateOperation@12@AEBV?$shared_ptr@VComputeSystem@Management@ComputeService@@@std@@AEBUDestructInfo@12@V?$unique_ptr@VActivityHolder@Management@ComputeService@@U?$default_delete@VActivityHolder@Management@ComputeService@@@std@@@5@V?$shared_ptr@UStateOperationContext@Management@ComputeService@@@5@P6AX0AEAVCompletedStateOperation@12@@Z@Z; ComputeService::Management::BeginOperation_DestructImpl(std::shared_ptr<ComputeService::Management::ComputeSystem> const &,ComputeService::Management::DestructInfo const &,std::unique_ptr<ComputeService::Management::ActivityHolder>,std::shared_ptr<ComputeService::Management::StateOperationContext>,void (*)(std::shared_ptr<ComputeService::Management::ComputeSystem> const &,ComputeService::Management::CompletedStateOperation &))
0x14009b51d  nop
0x14009b51e  mov     rcx, [rsp+3B0h+var_370]
0x14009b523  test    rcx, rcx
0x14009b526  jz      short loc_14009B539
0x14009b528  mov     rax, [rcx]
0x14009b52b  mov     edx, 1
0x14009b530  mov     rax, [rax]
0x14009b533  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009b538  nop
0x14009b539  mov     rdi, qword ptr [rsp+3B0h+var_340+8]
0x14009b53e  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14009b542  test    rdi, rdi
0x14009b545  jz      short loc_14009B57B
0x14009b547  mov     eax, esi
0x14009b549  lock xadd [rdi+8], eax
0x14009b54e  add     eax, esi
0x14009b550  jnz     short loc_14009B57B
0x14009b552  mov     rax, [rdi]
0x14009b555  mov     rcx, rdi
0x14009b558  mov     rax, [rax]
0x14009b55b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009b560  mov     eax, esi
0x14009b562  lock xadd [rdi+0Ch], eax
0x14009b567  add     eax, esi
0x14009b569  jnz     short loc_14009B57B
0x14009b56b  mov     rax, [rdi]
0x14009b56e  mov     rcx, rdi
0x14009b571  mov     rax, [rax+8]
0x14009b575  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009b57a  nop
0x14009b57b  lea     rax, ??_7VmHostedContainer_Destruct@TraceProvider@Diagnostics@ComputeService@@6B@; const ComputeService::Diagnostics::TraceProvider::VmHostedContainer_Destruct::`vftable'
0x14009b582  mov     [rbp+2B0h+var_2F0], rax
0x14009b586  lea     rcx, [rbp+2B0h+var_2F0]
0x14009b58a  call    ?Destroy@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x14009b58f  lea     rcx, [rbp+2B0h+var_2F0]
0x14009b593  call    ??1?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x14009b598  mov     rax, [rbp+2B0h+var_1A0]
0x14009b59f  mov     rcx, [rax]
0x14009b5a2  cmp     dword ptr [rcx+18h], 1
0x14009b5a6  jnz     loc_14009B817
0x14009b5ac  mov     rax, [r14]
0x14009b5af  mov     rdx, [rax]
0x14009b5b2  add     rdx, 8
0x14009b5b6  cmp     qword ptr [rdx+18h], 7
0x14009b5bb  jbe     short loc_14009B5C0
0x14009b5bd  mov     rdx, [rdx]
0x14009b5c0  mov     al, [r12]
0x14009b5c4  and     al, 1
0x14009b5c6  mov     rcx, [rbp+2B8h]; this
0x14009b5cd  mov     [rsp+3B0h+var_380], rdx; char *
0x14009b5d2  lea     rdx, aComputeSystemW; "Compute system %ws exited unexpectedly"
0x14009b5d9  mov     qword ptr [rsp+3B0h+var_388], rdx; bool
0x14009b5de  mov     byte ptr [rsp+3B0h+var_390], al; int
0x14009b5e2  mov     r9d, 0C0370106h; char *
0x14009b5e8  lea     r8, aOnecoreVmCompu_25; "onecore\\vm\\compute\\management\\orche"...
0x14009b5ef  mov     edx, 1AAh; void *
0x14009b5f4  call    ?Log_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Log_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x14009b5f9  mov     rax, [rbp+2B0h+var_1A0]
0x14009b600  mov     rcx, [rax]
0x14009b603  mov     eax, [rcx+10h]
0x14009b606  cmp     eax, 9
0x14009b609  jnz     short loc_14009B62A
0x14009b60b  lea     rcx, [rbx+80h]
0x14009b612  call    ?TerminateWindowsContainer@ContainerUtilities@ComputeService@@YAXAEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; ComputeService::ContainerUtilities::TerminateWindowsContainer(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &)
0x14009b617  mov     rax, [rbp+2B0h+var_1A0]
0x14009b61e  mov     rcx, [rax]
0x14009b621  mov     [rcx+18h], r15d
0x14009b625  jmp     loc_14009B817
0x14009b62a  cmp     eax, 0Ah
0x14009b62d  jnz     loc_14009B817
0x14009b633  lea     rdx, [rbx+0F0h]; struct ComputeService::Management::ActiveStateOperation *
0x14009b63a  lea     rcx, [rbp+2B0h+var_1A0]; this
0x14009b641  call    ?RundownOperationsForCleanup@Management@ComputeService@@YAXAEAVActiveStateOperation@12@PEAUBaseStateMachine@12@@Z; ComputeService::Management::RundownOperationsForCleanup(ComputeService::Management::ActiveStateOperation &,ComputeService::Management::BaseStateMachine *)
0x14009b646  lea     rdi, [rbx+90h]
0x14009b64d  lea     r8, [r13+190h]
0x14009b654  mov     rdx, rdi
0x14009b657  call    ?RemoveMappedDirectoryLinks@ContainerUtilities@ComputeService@@YAXPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$vector@UMappedDirectory@Containers@Config@@V?$allocator@UMappedDirectory@Containers@Config@@@std@@@4@@Z; ComputeService::ContainerUtilities::RemoveMappedDirectoryLinks(void *,std::wstring const &,std::vector<Config::Containers::MappedDirectory> const &)
0x14009b65c  cmp     [r13+2A0h], r15
0x14009b663  jnz     short loc_14009B671
0x14009b665  lea     rsi, [rbx+80h]
0x14009b66c  jmp     loc_14009B721
0x14009b671  mov     rcx, [rbp+2B8h]; this
0x14009b678  mov     r15, cs:?m_interface@NetworkingInterface@Net@ComputeService@@0V?$unique_ptr@VNetworkingInterface@Net@ComputeService@@U?$default_delete@VNetworkingInterface@Net@ComputeService@@@std@@@std@@A; std::unique_ptr<ComputeService::Net::NetworkingInterface> ComputeService::Net::NetworkingInterface::m_interface
0x14009b67f  xor     r8d, r8d
0x14009b682  test    r15, r15
0x14009b685  jz      loc_14009B885
0x14009b68b  mov     rax, [r15]
0x14009b68e  mov     rax, [rax+28h]
0x14009b692  mov     [rsp+3B0h+var_370], rax
0x14009b697  mov     rax, [r14]
0x14009b69a  mov     rdx, [rax]
0x14009b69d  add     rdx, 8
0x14009b6a1  cmp     qword ptr [rdx+18h], 7
0x14009b6a6  jbe     short loc_14009B6AB
0x14009b6a8  mov     rdx, [rdx]
0x14009b6ab  xorps   xmm0, xmm0
0x14009b6ae  movups  [rbp+2B0h+Src], xmm0
0x14009b6b2  xorps   xmm1, xmm1
0x14009b6b5  movdqu  [rbp+2B0h+var_320], xmm1
0x14009b6ba  inc     rsi
0x14009b6bd  cmp     [rdx+rsi*2], r8w
0x14009b6c2  jnz     short loc_14009B6BA
0x14009b6c4  mov     r8, rsi
0x14009b6c7  lea     rcx, [rbp+2B0h+Src]
0x14009b6cb  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14009b6d0  nop
0x14009b6d1  lea     rdx, [r13+290h]
0x14009b6d8  cmp     qword ptr [rdx+18h], 7
0x14009b6dd  jbe     short loc_14009B6E2
0x14009b6df  mov     rdx, [rdx]; unsigned __int16 *
0x14009b6e2  lea     rcx, [rsp+3B0h+var_360]; this
0x14009b6e7  call    ?Assign@VmGuid@Vml@@QEAAXQEBG@Z; Vml::VmGuid::Assign(ushort const * const)
0x14009b6ec  lea     r8, [rbp+2B0h+Src]
0x14009b6f0  lea     rdx, [rsp+3B0h+var_360]
0x14009b6f5  mov     rcx, r15
0x14009b6f8  mov     rax, [rsp+3B0h+var_370]
0x14009b6fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009b702  nop
0x14009b703  lea     rcx, [rbp+2B0h+Src]; void *
0x14009b707  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14009b70c  lea     rsi, [rbx+80h]
0x14009b713  xor     edx, edx; CompartmentId
0x14009b715  mov     rcx, [rsi]; JobHandle
0x14009b718  call    cs:__imp_SetJobCompartmentId
0x14009b71e  xor     r15d, r15d
0x14009b721  lea     r8, [r13+1C0h]
0x14009b728  mov     rdx, rdi
0x14009b72b  call    ?RemoveMappedVirtualDiskLinks@ContainerUtilities@ComputeService@@YAXPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$vector@UMappedVirtualDisk@Containers@Config@@V?$allocator@UMappedVirtualDisk@Containers@Config@@@std@@@4@@Z; ComputeService::ContainerUtilities::RemoveMappedVirtualDiskLinks(void *,std::wstring const &,std::vector<Config::Containers::MappedVirtualDisk> const &)
0x14009b730  mov     rcx, rsi; this
0x14009b733  call    ?CleanupWindowsContainer@ContainerUtilities@ComputeService@@YAXPEAUBaseContainerState@Management@2@@Z; ComputeService::ContainerUtilities::CleanupWindowsContainer(ComputeService::Management::BaseContainerState *)
0x14009b738  cmp     [rbx+0B0h], r15b
0x14009b73f  jz      short loc_14009B786
0x14009b741  cmp     qword ptr [rdi+18h], 7
0x14009b746  jbe     short loc_14009B74D
0x14009b748  mov     rdx, [rdi]
0x14009b74b  jmp     short loc_14009B750
0x14009b74d  mov     rdx, rdi; pszPathIn
0x14009b750  lea     r8, pszMore; ".\\"
0x14009b757  lea     rcx, [rbp+2B0h+Src]; Src
0x14009b75b  call    ?CombineFilePath@CommonUtilities@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; CommonUtilities::CombineFilePath(ushort const *,ushort const *)
0x14009b760  lea     rcx, [rbp+2B0h+Src]
0x14009b764  cmp     qword ptr [rbp+2B0h+var_320+8], 7
0x14009b769  cmova   rcx, qword ptr [rbp+2B0h+Src]
0x14009b76e  xor     edx, edx
0x14009b770  call    cs:__imp_WcDetachFilterEx
0x14009b776  lea     rcx, [rbp+2B0h+Src]; void *
0x14009b77a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14009b77f  mov     [rbx+0B0h], r15b
0x14009b786  test    byte ptr [r12], 2
0x14009b78b  jnz     short loc_14009B7A8
0x14009b78d  cmp     [rbx+0A0h], r15
0x14009b794  jz      short loc_14009B7A8
0x14009b796  cmp     qword ptr [rdi+18h], 7
0x14009b79b  jbe     short loc_14009B7A0
0x14009b79d  mov     rdi, [rdi]
0x14009b7a0  mov     rcx, rdi; this
0x14009b7a3  call    ?OfflineVolume@VmHostedContainer@Management@ComputeService@@YAXPEBG@Z; ComputeService::Management::VmHostedContainer::OfflineVolume(ushort const *)
0x14009b7a8  mov     rax, [rbp+2B0h+var_1A0]
0x14009b7af  mov     rcx, [rax]
0x14009b7b2  mov     [rcx+88h], r15d
0x14009b7b9  mov     eax, [rbx+150h]
0x14009b7bf  mov     dword ptr [rsp+3B0h+var_360], eax
0x14009b7c3  mov     eax, [rbx+154h]
0x14009b7c9  mov     dword ptr [rsp+3B0h+var_360+4], eax
0x14009b7cd  mov     rdx, [rbx+168h]
0x14009b7d4  mov     [rbx+168h], r15
0x14009b7db  mov     rcx, [rbx+160h]
0x14009b7e2  mov     [rbx+160h], r15
0x14009b7e9  mov     rax, [rbx+158h]
0x14009b7f0  mov     [rbx+158h], r15
0x14009b7f7  mov     qword ptr [rsp+3B0h+var_360+8], rax
0x14009b7fc  mov     [rsp+3B0h+var_350], rcx
0x14009b801  mov     [rsp+3B0h+var_348], rdx
0x14009b806  lea     rdx, [rsp+3B0h+var_360]
0x14009b80b  lea     rcx, [rbp+2B0h+var_1A0]
0x14009b812  call    ?Complete@ActiveStateOperation@Management@ComputeService@@QEAAXUSystemExitStatus@System@Responses@Schema@@@Z; ComputeService::Management::ActiveStateOperation::Complete(Schema::Responses::System::SystemExitStatus)
0x14009b817  xor     edx, edx
0x14009b819  lea     rcx, [rbp+2B0h+var_190]
0x14009b820  call    ?Stop@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x14009b825  nop
0x14009b826  lea     rcx, [rbp+2B0h+var_1A0]
0x14009b82d  call    ??1?$unique_ptr@UActiveStateOperationContext@ActiveStateOperation@Management@ComputeService@@U?$default_delete@UActiveStateOperationContext@ActiveStateOperation@Management@ComputeService@@@std@@@std@@QEAA@XZ; std::unique_ptr<ComputeService::Management::ActiveStateOperation::ActiveStateOperationContext>::~unique_ptr<ComputeService::Management::ActiveStateOperation::ActiveStateOperationContext>(void)
0x14009b832  nop
0x14009b833  lea     rax, ??_7VmHostedContainer_Destruct@TraceProvider@Diagnostics@ComputeService@@6B@; const ComputeService::Diagnostics::TraceProvider::VmHostedContainer_Destruct::`vftable'
0x14009b83a  mov     [rbp+2B0h+var_190], rax
0x14009b841  lea     rcx, [rbp+2B0h+var_190]
0x14009b848  call    ?Destroy@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x14009b84d  lea     rcx, [rbp+2B0h+var_190]
0x14009b854  call    ??1?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x14009b859  xor     al, al
0x14009b85b  mov     rcx, [rbp+2B0h+var_40]
0x14009b862  xor     rcx, rsp; StackCookie
0x14009b865  call    __security_check_cookie
0x14009b86a  mov     rbx, [rsp+3B0h+arg_0]
0x14009b872  add     rsp, 380h
0x14009b879  pop     r15
0x14009b87b  pop     r14
0x14009b87d  pop     r13
0x14009b87f  pop     r12
0x14009b881  pop     rdi
0x14009b882  pop     rsi
0x14009b883  pop     rbp
0x14009b884  retn
  ... truncated ...
```
