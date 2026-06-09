# ComputeService::Management::SiloContainerOrchestrator::ModifySettings(std::shared_ptr<ComputeService::Management::ComputeSystem> const &,ComputeService::Management::OrchestratorCallContext,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,void *)

- ea: `0x14008b220`
- end: `0x14008b7de`
- name: `?ModifySettings@SiloContainerOrchestrator@Management@ComputeService@@UEAA_NAEBV?$shared_ptr@VComputeSystem@Management@ComputeService@@@std@@UOrchestratorCallContext@23@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@PEAX@Z`
- size: `1470`
- prototype: `__int64 __fastcall(int, int, int, int, HANDLE ExistingTokenHandle)`
- caller_count: `0`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x140005360`
- `0x1400056fc`
- `0x140006098`
- `0x1400083bc`
- `0x140008760`
- `0x14000ddac`
- `0x14000f93c`
- `0x140029594`
- `0x140034170`
- `0x1400393b8`
- `0x14003a9ac`
- `0x14003f374`
- `0x14003f698`
- `0x14003f850`
- `0x14003fa78`
- `0x14003ff0c`
- `0x14007df8c`
- `0x14007fb9c`
- `0x14008348c`
- `0x14008b220`
- `0x14008b7f0`
- `0x14008d87c`
- `0x1400b983c`
- `0x1400bd150`
- `0x1400dc6e8`
- `0x1400fe010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14008b449`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14008b449`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008b436`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008b436`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x14008b461`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x14008b461`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14008b441`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14008b441`

## string_xrefs

- `0x14008b781`: `onecore\vm\compute\management\orchestration\silocontainer\silocontainerorchestrator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
char __fastcall ComputeService::Management::SiloContainerOrchestrator::ModifySettings(
        __int64 a1,
        void (__fastcall ***a2)(_QWORD, __int64),
        __int128 *a3,
        _QWORD *a4,
        char *ExistingTokenHandle)
{
  __int64 v7; // r13
  __int64 *v8; // rcx
  __int128 v9; // rdi
  _QWORD *v10; // r14
  char *v11; // r13
  DWORD LastError; // ebx
  const char *v13; // r9
  __int64 v14; // rax
  __int64 **v15; // rax
  __int64 *v16; // rcx
  volatile signed __int32 *v17; // rbx
  volatile signed __int32 *v18; // rbx
  char v19; // di
  __int64 *v20; // rax
  char v21; // di
  volatile signed __int32 *v22; // rbx
  __int64 v24; // rax
  __int64 v25; // rax
  unsigned int v26; // eax
  const char *v27; // rdx
  __int64 *v28; // [rsp+30h] [rbp-D0h] BYREF
  void (__fastcall ***v29)(_QWORD, __int64); // [rsp+38h] [rbp-C8h] BYREF
  __int128 v30; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v31; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v32; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v33; // [rsp+70h] [rbp-90h]
  _OWORD *v34; // [rsp+80h] [rbp-80h]
  __int64 v35; // [rsp+88h] [rbp-78h]
  __int128 v36; // [rsp+90h] [rbp-70h]
  _OWORD v37[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 *v38; // [rsp+C0h] [rbp-40h]
  __int128 *v39; // [rsp+C8h] [rbp-38h]
  __int128 *v40; // [rsp+D0h] [rbp-30h]
  _QWORD v41[42]; // [rsp+E0h] [rbp-20h] BYREF
  PVOID v42[2]; // [rsp+230h] [rbp+130h] BYREF
  _OWORD v43[2]; // [rsp+240h] [rbp+140h] BYREF
  __int128 v44; // [rsp+260h] [rbp+160h] BYREF
  char v45[32]; // [rsp+280h] [rbp+180h] BYREF
  _QWORD v46[42]; // [rsp+2A0h] [rbp+1A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+438h] [rbp+338h]

  v7 = (__int64)a2;
  v29 = a2;
  v35 = a1;
  v38 = a3;
  memset_0(v46, 0, sizeof(v46));
  v8 = (__int64 *)(**(_QWORD **)v7 + 8LL);
  if ( *(_QWORD *)(**(_QWORD **)v7 + 32LL) > 7u )
    v8 = (__int64 *)*v8;
  v28 = v8;
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v46,
    "SiloContainer_ModifySettings");
  v46[0] = &ComputeService::Diagnostics::TraceProvider::SiloContainer_ModifySettings::`vftable';
  ComputeService::Diagnostics::TraceProvider::SiloContainer_ModifySettings::StartActivity<unsigned short const *>(
    v46,
    &v28);
  *((_QWORD *)&v9 + 1) = operator new(0xC8u);
  v28 = (__int64 *)*((_QWORD *)&v9 + 1);
  **((_OWORD **)&v9 + 1) = 0;
  *(_DWORD *)(*((_QWORD *)&v9 + 1) + 8LL) = 1;
  *(_DWORD *)(*((_QWORD *)&v9 + 1) + 12LL) = 1;
  **((_QWORD **)&v9 + 1) = &std::_Ref_count_obj2<ComputeService::Management::Details::ModifySiloContainerSettingsContext>::`vftable';
  *(_QWORD *)&v9 = *((_QWORD *)&v9 + 1) + 16LL;
  *(_QWORD *)(*((_QWORD *)&v9 + 1) + 56LL) = 0;
  *(_QWORD *)(*((_QWORD *)&v9 + 1) + 16LL) = &ComputeService::Management::Details::ModifySiloContainerSettingsContext::`vftable';
  *(_OWORD *)(*((_QWORD *)&v9 + 1) + 24LL) = 0;
  *(_QWORD *)(*((_QWORD *)&v9 + 1) + 40LL) = 0;
  *(_QWORD *)(*((_QWORD *)&v9 + 1) + 48LL) = 7;
  *(_WORD *)(*((_QWORD *)&v9 + 1) + 24LL) = 0;
  *(_QWORD *)(*((_QWORD *)&v9 + 1) + 120LL) = 0;
  *(_OWORD *)(*((_QWORD *)&v9 + 1) + 64LL) = 0u;
  *(_OWORD *)(*((_QWORD *)&v9 + 1) + 80LL) = 0u;
  *(_OWORD *)(*((_QWORD *)&v9 + 1) + 96LL) = 0u;
  *(_QWORD *)(*((_QWORD *)&v9 + 1) + 112LL) = 0;
  *(_QWORD *)(*((_QWORD *)&v9 + 1) + 184LL) = 0;
  *(_OWORD *)(*((_QWORD *)&v9 + 1) + 128LL) = 0u;
  *(_OWORD *)(*((_QWORD *)&v9 + 1) + 144LL) = 0u;
  *(_OWORD *)(*((_QWORD *)&v9 + 1) + 160LL) = 0u;
  *(_QWORD *)(*((_QWORD *)&v9 + 1) + 176LL) = 0;
  *(_QWORD *)(*((_QWORD *)&v9 + 1) + 192LL) = 0;
  v36 = v9;
  if ( a4[3] <= 7u )
    v10 = a4;
  else
    v10 = (_QWORD *)*a4;
  memset_0(v43, 0, 0x60u);
  *(_QWORD *)&v30 = v10;
  *((_QWORD *)&v30 + 1) = a4[2];
  Marshal::JsonParser::JsonParser(v43, &v30);
  Marshal::FromJson<Schema::Requests::System::ModifySettingRequest,>(
    (__int64)v37,
    (Marshal::JsonParser *)v43,
    *((_QWORD *)&v9 + 1) + 24LL,
    4);
  std::wstring::~wstring(v45);
  std::wstring::~wstring(&v44);
  if ( !LOBYTE(v37[0]) )
  {
    v24 = std::shared_ptr<ComputeService::Management::ComputeSystem>::operator-><ComputeService::Management::ComputeSystem,0>((__int64)v37 + 8);
    v25 = std::wstring::c_str(v24);
    v26 = wil::verify_hresult<long>(3224830221LL, v25);
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x1F,
      (unsigned int)"OneCore\\Internal\\VM\\inc\\MarshalUtilities.h",
      (const char *)v26,
      (int)"%ls",
      v27,
      v28);
  }
  std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy((char *)v37 + 8);
  if ( (unsigned __int64)(ExistingTokenHandle - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v11 = *(char **)(*((_QWORD *)&v9 + 1) + 192LL);
    if ( (unsigned __int64)(v11 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = GetLastError();
      CloseHandle(v11);
      SetLastError(LastError);
    }
    *(_QWORD *)(*((_QWORD *)&v9 + 1) + 192LL) = 0;
    if ( !DuplicateToken(ExistingTokenHandle, SecurityImpersonation, (PHANDLE)(*((_QWORD *)&v9 + 1) + 192LL)) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x6B2,
        (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\silocontainer\\silocontainerorchestrator.cpp",
        v13);
    v7 = (__int64)v29;
  }
  v42[0] = 0;
  v30 = v9;
  v36 = 0;
  v39 = &v30;
  v14 = ComputeService::Diagnostics::TraceProvider::SiloContainer_ModifySettings::Split(v46, v41);
  v31 = *a3;
  *(_QWORD *)a3 = 0;
  *((_QWORD *)a3 + 1) = 0;
  v32 = a3[1];
  *((_QWORD *)a3 + 2) = 0;
  *((_QWORD *)a3 + 3) = 0;
  v33 = a3[2];
  *((_QWORD *)a3 + 4) = 0;
  *((_QWORD *)a3 + 5) = 0;
  v40 = &v31;
  v34 = v37;
  v37[0] = v30;
  v30 = 0;
  v15 = (__int64 **)std::make_unique<ComputeService::Management::ActivityHolderImpl<ComputeService::Diagnostics::TraceProvider::SiloContainer_ModifySettings>,ComputeService::Diagnostics::TraceProvider::SiloContainer_ModifySettings,0>(
                      &v29,
                      v14);
  v16 = *v15;
  *v15 = 0;
  v28 = v16;
  v43[0] = v31;
  v31 = 0;
  v43[1] = v32;
  v32 = 0;
  v44 = v33;
  v33 = 0;
  ComputeService::Management::BeginOperation_ModifySettingsImpl(
    (unsigned int)v42,
    v7,
    (unsigned int)v43,
    (unsigned int)&v28,
    (__int64)v37);
  if ( v29 )
    (**v29)(v29, 1);
  ComputeService::Management::RetireServerOperation::~RetireServerOperation((ComputeService::Management::RetireServerOperation *)&v32);
  v17 = (volatile signed __int32 *)*((_QWORD *)&v31 + 1);
  if ( *((_QWORD *)&v31 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v31 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
      if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
    }
  }
  v18 = (volatile signed __int32 *)*((_QWORD *)&v30 + 1);
  if ( *((_QWORD *)&v30 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v30 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
      if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
    }
  }
  v41[0] = &ComputeService::Diagnostics::TraceProvider::SiloContainer_ModifySettings::`vftable';
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v41);
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>(v41);
  if ( (*(_BYTE *)(v35 + 8) & 4) != 0 )
  {
    v19 = 1;
    ComputeService::Management::ActiveStateOperation::ContinueOnWorkerThread(
      v42,
      (__int64)ComputeService::Management::Details::ModifySiloContainerSettingsWorker);
  }
  else
  {
    v19 = 0;
    v20 = (__int64 *)v42[0];
    v42[0] = 0;
    v28 = v20;
    ComputeService::Management::Details::ModifySiloContainerSettingsWorker(v7, &v28);
  }
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v46,
    0);
  v21 = v19 ^ 1;
  std::unique_ptr<ComputeService::Management::ActiveStateOperation::ActiveStateOperationContext>::~unique_ptr<ComputeService::Management::ActiveStateOperation::ActiveStateOperationContext>(v42);
  v46[0] = &ComputeService::Diagnostics::TraceProvider::SiloContainer_ModifySettings::`vftable';
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v46);
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>(v46);
  ComputeService::Management::RetireServerOperation::~RetireServerOperation((ComputeService::Management::RetireServerOperation *)(a3 + 1));
  v22 = (volatile signed __int32 *)*((_QWORD *)a3 + 1);
  if ( v22 )
  {
    if ( !_InterlockedDecrement(v22 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v22)(v22);
      if ( _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
    }
  }
  return v21;
}

```

## disassembly

```asm
0x14008b220  mov     [rsp-8+arg_0], rbx
0x14008b225  push    rbp
0x14008b226  push    rsi
0x14008b227  push    rdi
0x14008b228  push    r12
0x14008b22a  push    r13
0x14008b22c  push    r14
0x14008b22e  push    r15
0x14008b230  lea     rbp, [rsp-300h]
0x14008b238  sub     rsp, 400h
0x14008b23f  mov     rax, cs:__security_cookie
0x14008b246  xor     rax, rsp
0x14008b249  mov     [rbp+330h+var_40], rax
0x14008b250  mov     rbx, r9
0x14008b253  mov     r15, r8
0x14008b256  mov     r13, rdx
0x14008b259  mov     [rsp+430h+var_3F8], rdx
0x14008b25e  mov     [rbp+330h+var_3A8], rcx
0x14008b262  mov     [rbp+330h+var_370], r8
0x14008b266  mov     r12, [rbp+330h+ExistingTokenHandle]
0x14008b26d  xor     r14d, r14d
0x14008b270  xor     edx, edx; Val
0x14008b272  mov     r8d, 150h; Size
0x14008b278  lea     rcx, [rbp+330h+var_190]; void *
0x14008b27f  call    memset_0
0x14008b284  mov     rax, [r13+0]
0x14008b288  mov     rcx, [rax]
0x14008b28b  add     rcx, 8
0x14008b28f  cmp     qword ptr [rcx+18h], 7
0x14008b294  jbe     short loc_14008B299
0x14008b296  mov     rcx, [rcx]
0x14008b299  mov     [rsp+430h+var_400], rcx
0x14008b29e  lea     rdx, aSilocontainerM; "SiloContainer_ModifySettings"
0x14008b2a5  lea     rcx, [rbp+330h+var_190]
0x14008b2ac  call    ??0?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x14008b2b1  lea     rax, ??_7SiloContainer_ModifySettings@TraceProvider@Diagnostics@ComputeService@@6B@; const ComputeService::Diagnostics::TraceProvider::SiloContainer_ModifySettings::`vftable'
0x14008b2b8  mov     [rbp+330h+var_190], rax
0x14008b2bf  lea     rdx, [rsp+430h+var_400]
0x14008b2c4  lea     rcx, [rbp+330h+var_190]
0x14008b2cb  call    ??$StartActivity@PEBG@SiloContainer_ModifySettings@TraceProvider@Diagnostics@ComputeService@@QEAAX$$QEAPEBG@Z; ComputeService::Diagnostics::TraceProvider::SiloContainer_ModifySettings::StartActivity<ushort const *>(ushort const * &&)
0x14008b2d0  nop
0x14008b2d1  mov     ecx, 0C8h; Size
0x14008b2d6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14008b2db  mov     rsi, rax
0x14008b2de  mov     [rsp+430h+var_400], rax
0x14008b2e3  xorps   xmm0, xmm0
0x14008b2e6  movups  xmmword ptr [rax], xmm0
0x14008b2e9  mov     eax, 1
0x14008b2ee  mov     [rsi+8], eax
0x14008b2f1  mov     [rsi+0Ch], eax
0x14008b2f4  lea     rax, ??_7?$_Ref_count_obj2@UModifySiloContainerSettingsContext@Details@Management@ComputeService@@@std@@6B@; const std::_Ref_count_obj2<ComputeService::Management::Details::ModifySiloContainerSettingsContext>::`vftable'
0x14008b2fb  mov     [rsi], rax
0x14008b2fe  lea     rdi, [rsi+10h]
0x14008b302  xor     eax, eax
0x14008b304  mov     [rdi+28h], rax
0x14008b308  lea     rax, ??_7ModifySiloContainerSettingsContext@Details@Management@ComputeService@@6B@; const ComputeService::Management::Details::ModifySiloContainerSettingsContext::`vftable'
0x14008b30f  mov     [rdi], rax
0x14008b312  movups  xmmword ptr [rdi+8], xmm0
0x14008b316  mov     [rdi+18h], r14
0x14008b31a  mov     qword ptr [rdi+20h], 7
0x14008b322  mov     [rdi+8], r14w
0x14008b327  mov     [rdi+68h], r14
0x14008b32b  mov     [rdi+30h], r14
0x14008b32f  mov     [rdi+38h], r14
0x14008b333  mov     [rdi+40h], r14
0x14008b337  mov     [rdi+48h], r14
0x14008b33b  mov     [rdi+50h], r14
0x14008b33f  mov     [rdi+58h], r14
0x14008b343  mov     [rdi+60h], r14
0x14008b347  mov     [rdi+0A8h], r14
0x14008b34e  mov     [rdi+70h], r14
0x14008b352  mov     [rdi+78h], r14
0x14008b356  mov     [rdi+80h], r14
0x14008b35d  mov     [rdi+88h], r14
0x14008b364  mov     [rdi+90h], r14
0x14008b36b  mov     [rdi+98h], r14
0x14008b372  mov     [rdi+0A0h], r14
0x14008b379  mov     [rdi+0B0h], r14
0x14008b380  movups  [rbp+330h+var_3A0], xmm0
0x14008b384  mov     qword ptr [rbp+330h+var_3A0], rdi
0x14008b388  mov     qword ptr [rbp+330h+var_3A0+8], rsi
0x14008b38c  cmp     qword ptr [rbx+18h], 7
0x14008b391  jbe     short loc_14008B398
0x14008b393  mov     r14, [rbx]
0x14008b396  jmp     short loc_14008B39B
0x14008b398  mov     r14, rbx
0x14008b39b  xor     edx, edx; Val
0x14008b39d  lea     r8d, [rdx+60h]; Size
0x14008b3a1  lea     rcx, [rbp+330h+var_1F0]; void *
0x14008b3a8  call    memset_0
0x14008b3ad  mov     qword ptr [rsp+430h+var_3F0], r14
0x14008b3b2  mov     rax, [rbx+10h]
0x14008b3b6  mov     qword ptr [rsp+430h+var_3F0+8], rax
0x14008b3bb  lea     rdx, [rsp+430h+var_3F0]
0x14008b3c0  lea     rcx, [rbp+330h+var_1F0]
0x14008b3c7  call    ??0JsonParser@Marshal@@QEAA@V?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; Marshal::JsonParser::JsonParser(std::basic_string_view<ushort>)
0x14008b3cc  nop
0x14008b3cd  mov     r9d, 4
0x14008b3d3  lea     r8, [rdi+8]
0x14008b3d7  lea     rdx, [rbp+330h+var_1F0]
0x14008b3de  lea     rcx, [rbp+330h+var_390]
0x14008b3e2  call    ??$FromJson@UModifySettingRequest@System@Requests@Schema@@$$V@Marshal@@YA?AU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@AEAVJsonParser@0@PEAUModifySettingRequest@System@Requests@Schema@@W4UnmarshalFlags@0@@Z; Marshal::FromJson<Schema::Requests::System::ModifySettingRequest,>(Marshal::JsonParser &,Schema::Requests::System::ModifySettingRequest *,Marshal::UnmarshalFlags)
0x14008b3e7  nop
0x14008b3e8  lea     rcx, [rbp+330h+var_1B0]; void *
0x14008b3ef  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14008b3f4  lea     rcx, [rbp+330h+var_1D0]; void *
0x14008b3fb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14008b400  nop
0x14008b401  xor     r14d, r14d
0x14008b404  cmp     byte ptr [rbp+330h+var_390], r14b
0x14008b408  jz      loc_14008B793
0x14008b40e  lea     rcx, [rbp+330h+var_390+8]
0x14008b412  call    ?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::_Tidy(void)
0x14008b417  lea     rax, [r12-1]
0x14008b41c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14008b420  ja      short loc_14008B47E
0x14008b422  lea     r14, [rdi+0B0h]
0x14008b429  mov     r13, [r14]
0x14008b42c  lea     rax, [r13-1]
0x14008b430  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14008b434  ja      short loc_14008B44F
0x14008b436  call    cs:__imp_GetLastError
0x14008b43c  mov     ebx, eax
0x14008b43e  mov     rcx, r13; hObject
0x14008b441  call    cs:__imp_CloseHandle
0x14008b447  mov     ecx, ebx; dwErrCode
0x14008b449  call    cs:__imp_SetLastError
0x14008b44f  mov     qword ptr [r14], 0
0x14008b456  mov     r8, r14; DuplicateTokenHandle
0x14008b459  mov     edx, 2; ImpersonationLevel
0x14008b45e  mov     rcx, r12; ExistingTokenHandle
0x14008b461  call    cs:__imp_DuplicateToken
0x14008b467  mov     rcx, [rbp+338h]; this
0x14008b46e  xor     r14d, r14d
0x14008b471  test    eax, eax
0x14008b473  jz      loc_14008B781
0x14008b479  mov     r13, [rsp+430h+var_3F8]
0x14008b47e  mov     [rbp+330h+var_200], r14
0x14008b485  mov     qword ptr [rsp+430h+var_3F0], rdi
0x14008b48a  mov     qword ptr [rsp+430h+var_3F0+8], rsi
0x14008b48f  xorps   xmm0, xmm0
0x14008b492  movdqu  [rbp+330h+var_3A0], xmm0
0x14008b497  lea     rax, [rsp+430h+var_3F0]
0x14008b49c  mov     [rbp+330h+var_368], rax
0x14008b4a0  lea     rdx, [rbp+330h+var_350]
0x14008b4a4  lea     rcx, [rbp+330h+var_190]
0x14008b4ab  call    ?Split@SiloContainer_ModifySettings@TraceProvider@Diagnostics@ComputeService@@QEAA?AV1234@XZ; ComputeService::Diagnostics::TraceProvider::SiloContainer_ModifySettings::Split(void)
0x14008b4b0  mov     rdx, rax
0x14008b4b3  mov     rcx, [r15]
0x14008b4b6  mov     qword ptr [rsp+430h+var_3E0], rcx
0x14008b4bb  mov     rcx, [r15+8]
0x14008b4bf  mov     qword ptr [rsp+430h+var_3E0+8], rcx
0x14008b4c4  mov     [r15], r14
0x14008b4c7  mov     [r15+8], r14
0x14008b4cb  lea     rsi, [r15+10h]
0x14008b4cf  mov     rcx, [rsi]
0x14008b4d2  mov     qword ptr [rsp+430h+var_3D0], rcx
0x14008b4d7  mov     rax, [rsi+8]
0x14008b4db  mov     qword ptr [rsp+430h+var_3D0+8], rax
0x14008b4e0  mov     [rsi], r14
0x14008b4e3  mov     [rsi+8], r14
0x14008b4e7  mov     rax, [rsi+10h]
0x14008b4eb  mov     qword ptr [rsp+430h+var_3C0], rax
0x14008b4f0  mov     rax, [rsi+18h]
0x14008b4f4  mov     qword ptr [rsp+430h+var_3C0+8], rax
0x14008b4f9  mov     [rsi+10h], r14
0x14008b4fd  mov     [rsi+18h], r14
0x14008b501  lea     rax, [rsp+430h+var_3E0]
0x14008b506  mov     [rbp+330h+var_360], rax
0x14008b50a  lea     rax, [rbp+330h+var_390]
0x14008b50e  mov     [rbp+330h+var_3B0], rax
0x14008b512  movaps  xmm0, [rsp+430h+var_3F0]
0x14008b517  movdqa  [rbp+330h+var_390], xmm0
0x14008b51c  xorps   xmm1, xmm1
0x14008b51f  movdqa  [rsp+430h+var_3F0], xmm1
0x14008b525  lea     rcx, [rsp+430h+var_3F8]
0x14008b52a  call    ??$make_unique@V?$ActivityHolderImpl@VSiloContainer_ModifySettings@TraceProvider@Diagnostics@ComputeService@@@Management@ComputeService@@VSiloContainer_ModifySettings@TraceProvider@Diagnostics@3@$0A@@std@@YA?AV?$unique_ptr@V?$ActivityHolderImpl@VSiloContainer_ModifySettings@TraceProvider@Diagnostics@ComputeService@@@Management@ComputeService@@U?$default_delete@V?$ActivityHolderImpl@VSiloContainer_ModifySettings@TraceProvider@Diagnostics@ComputeService@@@Management@ComputeService@@@std@@@0@$$QEAVSiloContainer_ModifySettings@TraceProvider@Diagnostics@ComputeService@@@Z; std::make_unique<ComputeService::Management::ActivityHolderImpl<ComputeService::Diagnostics::TraceProvider::SiloContainer_ModifySettings>,ComputeService::Diagnostics::TraceProvider::SiloContainer_ModifySettings,0>(ComputeService::Diagnostics::TraceProvider::SiloContainer_ModifySettings &&)
0x14008b52f  nop
0x14008b530  mov     rcx, [rax]
0x14008b533  mov     [rax], r14
0x14008b536  mov     [rsp+430h+var_400], rcx
0x14008b53b  mov     rax, qword ptr [rsp+430h+var_3E0]
0x14008b540  mov     qword ptr [rbp+330h+var_1F0], rax
0x14008b547  mov     rax, qword ptr [rsp+430h+var_3E0+8]
0x14008b54c  mov     qword ptr [rbp+330h+var_1F0+8], rax
0x14008b553  xorps   xmm0, xmm0
0x14008b556  movdqu  [rsp+430h+var_3E0], xmm0
0x14008b55c  mov     rax, qword ptr [rsp+430h+var_3D0]
0x14008b561  mov     qword ptr [rbp+330h+var_1E0], rax
0x14008b568  mov     rax, qword ptr [rsp+430h+var_3D0+8]
0x14008b56d  mov     qword ptr [rbp+330h+var_1E0+8], rax
0x14008b574  movdqu  [rsp+430h+var_3D0], xmm0
0x14008b57a  mov     rax, qword ptr [rsp+430h+var_3C0]
0x14008b57f  mov     qword ptr [rbp+330h+var_1D0], rax
0x14008b586  mov     rax, qword ptr [rsp+430h+var_3C0+8]
0x14008b58b  mov     qword ptr [rbp+330h+var_1D0+8], rax
0x14008b592  movdqu  [rsp+430h+var_3C0], xmm0
0x14008b598  lea     rax, [rbp+330h+var_390]
0x14008b59c  mov     qword ptr [rsp+430h+var_410], rax
0x14008b5a1  lea     r9, [rsp+430h+var_400]
0x14008b5a6  lea     r8, [rbp+330h+var_1F0]
0x14008b5ad  mov     rdx, r13
0x14008b5b0  lea     rcx, [rbp+330h+var_200]
0x14008b5b7  call    ?BeginOperation_ModifySettingsImpl@Management@ComputeService@@YA?AVActiveStateOperation@12@AEBV?$shared_ptr@VComputeSystem@Management@ComputeService@@@std@@VActiveServerOperation@12@V?$unique_ptr@VActivityHolder@Management@ComputeService@@U?$default_delete@VActivityHolder@Management@ComputeService@@@std@@@5@V?$shared_ptr@UStateOperationContext@Management@ComputeService@@@5@@Z; ComputeService::Management::BeginOperation_ModifySettingsImpl(std::shared_ptr<ComputeService::Management::ComputeSystem> const &,ComputeService::Management::ActiveServerOperation,std::unique_ptr<ComputeService::Management::ActivityHolder>,std::shared_ptr<ComputeService::Management::StateOperationContext>)
0x14008b5bc  nop
0x14008b5bd  mov     rcx, [rsp+430h+var_3F8]
0x14008b5c2  test    rcx, rcx
0x14008b5c5  jz      short loc_14008B5D8
0x14008b5c7  mov     rax, [rcx]
0x14008b5ca  mov     edx, 1
0x14008b5cf  mov     rax, [rax]
0x14008b5d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008b5d7  nop
0x14008b5d8  lea     rcx, [rsp+430h+var_3D0]; this
0x14008b5dd  call    ??1RetireServerOperation@Management@ComputeService@@QEAA@XZ; ComputeService::Management::RetireServerOperation::~RetireServerOperation(void)
0x14008b5e2  mov     rbx, qword ptr [rsp+430h+var_3E0+8]
0x14008b5e7  or      r12d, 0FFFFFFFFh
0x14008b5eb  test    rbx, rbx
0x14008b5ee  jz      short loc_14008B628
0x14008b5f0  mov     eax, r12d
0x14008b5f3  lock xadd [rbx+8], eax
0x14008b5f8  add     eax, r12d
0x14008b5fb  jnz     short loc_14008B628
0x14008b5fd  mov     rax, [rbx]
0x14008b600  mov     rcx, rbx
0x14008b603  mov     rax, [rax]
0x14008b606  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008b60b  mov     eax, r12d
0x14008b60e  lock xadd [rbx+0Ch], eax
0x14008b613  add     eax, r12d
0x14008b616  jnz     short loc_14008B628
0x14008b618  mov     rax, [rbx]
0x14008b61b  mov     rcx, rbx
0x14008b61e  mov     rax, [rax+8]
0x14008b622  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008b627  nop
0x14008b628  mov     rbx, qword ptr [rsp+430h+var_3F0+8]
0x14008b62d  test    rbx, rbx
0x14008b630  jz      short loc_14008B66A
0x14008b632  mov     eax, r12d
0x14008b635  lock xadd [rbx+8], eax
0x14008b63a  add     eax, r12d
0x14008b63d  jnz     short loc_14008B66A
0x14008b63f  mov     rax, [rbx]
0x14008b642  mov     rcx, rbx
0x14008b645  mov     rax, [rax]
0x14008b648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008b64d  mov     eax, r12d
0x14008b650  lock xadd [rbx+0Ch], eax
0x14008b655  add     eax, r12d
0x14008b658  jnz     short loc_14008B66A
0x14008b65a  mov     rax, [rbx]
0x14008b65d  mov     rcx, rbx
0x14008b660  mov     rax, [rax+8]
0x14008b664  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008b669  nop
0x14008b66a  lea     rbx, ??_7SiloContainer_ModifySettings@TraceProvider@Diagnostics@ComputeService@@6B@; const ComputeService::Diagnostics::TraceProvider::SiloContainer_ModifySettings::`vftable'
0x14008b671  mov     [rbp+330h+var_350], rbx
0x14008b675  lea     rcx, [rbp+330h+var_350]
0x14008b679  call    ?Destroy@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x14008b67e  lea     rcx, [rbp+330h+var_350]
0x14008b682  call    ??1?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x14008b687  mov     rax, [rbp+330h+var_3A8]
0x14008b68b  test    byte ptr [rax+8], 4
0x14008b68f  jz      short loc_14008B6A9
0x14008b691  mov     dil, 1
0x14008b694  lea     rdx, ?ModifySiloContainerSettingsWorker@Details@Management@ComputeService@@YAXAEBV?$shared_ptr@VComputeSystem@Management@ComputeService@@@std@@VActiveStateOperation@23@@Z; ComputeService::Management::Details::ModifySiloContainerSettingsWorker(std::shared_ptr<ComputeService::Management::ComputeSystem> const &,ComputeService::Management::ActiveStateOperation)
0x14008b69b  lea     rcx, [rbp+330h+var_200]
0x14008b6a2  call    ?ContinueOnWorkerThread@ActiveStateOperation@Management@ComputeService@@QEAAXP6AXAEBV?$shared_ptr@VComputeSystem@Management@ComputeService@@@std@@V123@@Z@Z; ComputeService::Management::ActiveStateOperation::ContinueOnWorkerThread(void (*)(std::shared_ptr<ComputeService::Management::ComputeSystem> const &,ComputeService::Management::ActiveStateOperation))
0x14008b6a7  jmp     short loc_14008B6CC
0x14008b6a9  mov     dil, r14b
0x14008b6ac  mov     rax, [rbp+330h+var_200]
0x14008b6b3  mov     [rbp+330h+var_200], r14
0x14008b6ba  mov     [rsp+430h+var_400], rax
0x14008b6bf  lea     rdx, [rsp+430h+var_400]
0x14008b6c4  mov     rcx, r13
0x14008b6c7  call    ?ModifySiloContainerSettingsWorker@Details@Management@ComputeService@@YAXAEBV?$shared_ptr@VComputeSystem@Management@ComputeService@@@std@@VActiveStateOperation@23@@Z; ComputeService::Management::Details::ModifySiloContainerSettingsWorker(std::shared_ptr<ComputeService::Management::ComputeSystem> const &,ComputeService::Management::ActiveStateOperation)
0x14008b6cc  xor     edx, edx
0x14008b6ce  lea     rcx, [rbp+330h+var_190]
0x14008b6d5  call    ?Stop@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x14008b6da  nop
0x14008b6db  xor     dil, 1
0x14008b6df  lea     rcx, [rbp+330h+var_200]
0x14008b6e6  call    ??1?$unique_ptr@UActiveStateOperationContext@ActiveStateOperation@Management@ComputeService@@U?$default_delete@UActiveStateOperationContext@ActiveStateOperation@Management@ComputeService@@@std@@@std@@QEAA@XZ; std::unique_ptr<ComputeService::Management::ActiveStateOperation::ActiveStateOperationContext>::~unique_ptr<ComputeService::Management::ActiveStateOperation::ActiveStateOperationContext>(void)
0x14008b6eb  nop
0x14008b6ec  mov     [rbp+330h+var_190], rbx
0x14008b6f3  lea     rcx, [rbp+330h+var_190]
0x14008b6fa  call    ?Destroy@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x14008b6ff  lea     rcx, [rbp+330h+var_190]
0x14008b706  call    ??1?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x14008b70b  nop
0x14008b70c  mov     rcx, rsi; this
0x14008b70f  call    ??1RetireServerOperation@Management@ComputeService@@QEAA@XZ; ComputeService::Management::RetireServerOperation::~RetireServerOperation(void)
0x14008b714  mov     rbx, [r15+8]
0x14008b718  test    rbx, rbx
0x14008b71b  jz      short loc_14008B754
0x14008b71d  mov     eax, r12d
0x14008b720  lock xadd [rbx+8], eax
0x14008b725  add     eax, r12d
0x14008b728  jnz     short loc_14008B754
  ... truncated ...
```
