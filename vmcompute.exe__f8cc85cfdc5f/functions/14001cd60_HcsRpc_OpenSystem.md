# HcsRpc_OpenSystem

- ea: `0x14001cd60`
- end: `0x14001d47f`
- name: `HcsRpc_OpenSystem`
- size: `1823`
- prototype: ``
- caller_count: `0`
- callee_count: `28`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x14001629c`
- `0x140017040`
- `0x14001cd60`
- `0x14001d4d0`
- `0x14001d570`
- `0x14001d6bc`
- `0x14001d7ec`
- `0x14001d8f4`
- `0x14001d9ec`
- `0x14001e6a0`
- `0x140020890`
- `0x140025f98`
- `0x14004ee20`
- `0x14005ad04`
- `0x14005de00`
- `0x140061258`
- `0x140087500`
- `0x140091e20`
- `0x1400a6578`
- `0x1400a65a0`
- `0x1400bc830`
- `0x1400c40e0`
- `0x1400d2e2c`
- `0x1400f9a24`
- `0x1401332f0`
- `0x1401336bc`
- `0x140134048`
- `0x1402c4010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x14001d2db`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x14001cdcd`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x14001cdcd`
- `RPCRT4!UuidFromStringW` at `0x14001cea9`
- `RPCRT4!UuidFromStringW` at `0x14001cea9`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x14001cf1a`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x14001cf1a`
- `RPCRT4!RpcRevertToSelfEx` at `0x14001ce07`
- `RPCRT4!RpcRevertToSelfEx` at `0x14001ce16`

## string_xrefs

- `0x14001cf5f`: `HcsRpc_OpenSystem`
- `0x14001cde9`: `onecore\vm\compute\rpc\server\rpcserver.cpp`
- `0x14001d373`: `onecore\vm\compute\rpc\server\rpcserver.cpp`
- `0x14001d3c0`: `onecore\vm\compute\rpc\server\rpcserver.cpp`
- `0x14001d397`: `onecore\vm\compute\rpc\server\computesystemrpc.cpp`
- `0x14001d3ae`: `onecore\vm\compute\rpc\server\computesystemrpc.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall HcsRpc_OpenSystem(__int64 a1, unsigned __int16 *a2, __int64 a3, UUID **a4)
{
  const char *v5; // r9
  int LastError; // ebx
  __int64 v7; // r8
  __int64 v8; // rcx
  RPC_WSTR v9; // rbx
  WINBOOL v10; // ebx
  UUID *v11; // rbx
  const char *v12; // r9
  char v13; // di
  __int64 v14; // rbx
  __int64 v15; // r8
  unsigned int v16; // ebx
  const struct std::nothrow_t *v17; // rdx
  void *v18; // rcx
  __int64 v19; // r8
  UUID *v20; // rdx
  __int64 v21; // rax
  __int64 v22; // rcx
  volatile signed __int32 *v23; // rcx
  const char *v24; // r9
  __int64 result; // rax
  __int64 v26; // r8
  unsigned __int64 v27; // rcx
  struct _GUID *v28; // rax
  struct _GUID **v29; // rdi
  struct _GUID **v30; // rdx
  int v31; // r9d
  struct _GUID **v32; // r14
  struct _GUID **v33; // rbx
  struct _GUID **v34; // r8
  char v35; // di
  int v36; // r8d
  __int64 v37; // rdx
  void *v38[2]; // [rsp+20h] [rbp-2A8h] BYREF
  UUID Uuid; // [rsp+30h] [rbp-298h] BYREF
  void *v40[2]; // [rsp+40h] [rbp-288h] BYREF
  __m128i si128; // [rsp+50h] [rbp-278h]
  _QWORD v42[2]; // [rsp+60h] [rbp-268h] BYREF
  char v43; // [rsp+70h] [rbp-258h]
  RPC_WSTR StringUuid; // [rsp+78h] [rbp-250h] BYREF
  UUID *Context; // [rsp+80h] [rbp-248h] BYREF
  _DWORD RpcCallAttributes[2]; // [rsp+90h] [rbp-238h] BYREF
  _BYTE v47[56]; // [rsp+98h] [rbp-230h] BYREF
  WINBOOL v48; // [rsp+D0h] [rbp-1F8h]
  WINBOOL IsMember[2]; // [rsp+110h] [rbp-1B8h] BYREF
  struct _GUID *v50[2]; // [rsp+118h] [rbp-1B0h] BYREF
  __int128 v51; // [rsp+128h] [rbp-1A0h]
  void **v52; // [rsp+140h] [rbp-188h] BYREF
  int v53; // [rsp+148h] [rbp-180h] BYREF
  char v54; // [rsp+14Ch] [rbp-17Ch]
  int v55; // [rsp+170h] [rbp-158h] BYREF
  const char *v56; // [rsp+178h] [rbp-150h]
  __int64 v57; // [rsp+180h] [rbp-148h]
  char v58; // [rsp+188h] [rbp-140h]
  int v59; // [rsp+190h] [rbp-138h]
  _BYTE v60[152]; // [rsp+198h] [rbp-130h] BYREF
  __int128 v61; // [rsp+230h] [rbp-98h]
  int v62; // [rsp+240h] [rbp-88h]
  __int64 v63; // [rsp+248h] [rbp-80h]
  int *v64; // [rsp+250h] [rbp-78h]
  _QWORD v65[4]; // [rsp+258h] [rbp-70h] BYREF
  int v66; // [rsp+278h] [rbp-50h]
  int *v67; // [rsp+280h] [rbp-48h]
  char v68; // [rsp+288h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+0h]

  try
  {
    StringUuid = a2;
    if ( qword_1403DE908 )
    {
      v38[0] = 0;
      ComputeService::Rpc::HcsRpcImpersonateClient(v38, a1);
      IsMember[0] = 0;
      if ( !CheckTokenMembership(0, *(PSID *)qword_1403DE908, IsMember) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x16C,
                      (unsigned int)"onecore\\vm\\compute\\rpc\\server\\rpcserver.cpp",
                      v5);
        if ( v38[0] != (void *)-1LL )
          RpcRevertToSelfEx(v38[0]);
        goto LABEL_8;
      }
      if ( IsMember[0] )
      {
        LastError = -2143878885;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x16F,
          (unsigned int)"onecore\\vm\\compute\\rpc\\server\\rpcserver.cpp",
          (const char *)0x8037011BLL,
          (int)v38[0]);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long RpcRevertToSelfEx(void *),wistd::integral_constant<unsigned __int64,2>,void *,void *,-1,void *>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long RpcRevertToSelfEx(void *),wistd::integral_constant<unsigned __int64,2>,void *,void *,-1,void *>>>(v38);
        goto LABEL_8;
      }
      if ( v38[0] != (void *)-1LL )
        ((void (*)(void))RpcRevertToSelfEx)();
    }
    LastError = 0;
LABEL_8:
    if ( LastError < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1C9,
        (unsigned int)"onecore\\vm\\compute\\rpc\\server\\computesystemrpc.cpp",
        (const char *)(unsigned int)LastError,
        (int)v38[0]);
    if ( !a4 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1CB,
        (unsigned int)"onecore\\vm\\compute\\rpc\\server\\computesystemrpc.cpp",
        (const char *)0x80004003LL,
        (int)v38[0]);
    *a4 = 0;
    *(_OWORD *)v40 = 0;
    si128 = 0u;
    v7 = -1;
    do
      ++v7;
    while ( StringUuid[v7] );
    std::wstring::_Construct<1,unsigned short const *>(v40, StringUuid);
    Context = (UUID *)ComputeService::Rpc::RpcContextMap<std::wstring,ComputeService::Rpc::SystemContext,Vml::CaseInsensitiveLess>::CreateContext(
                        v8,
                        v40);
    v9 = StringUuid;
    Uuid = 0;
    if ( !StringUuid || UuidFromStringW(StringUuid, &Uuid) )
    {
      *(_OWORD *)v50 = 0;
      v51 = 0;
      v26 = -1;
      do
        ++v26;
      while ( v9[v26] );
      std::wstring::_Construct<1,unsigned short const *>(v50, v9);
      v27 = *((_QWORD *)&v51 + 1);
      v28 = v50[0];
      if ( *((_QWORD *)&v51 + 1) > 7u )
      {
        v29 = (struct _GUID **)v50[0];
        v30 = (struct _GUID **)v50[0];
      }
      else
      {
        v29 = v50;
        v30 = v50;
      }
      v31 = v51;
      v32 = (struct _GUID **)((char *)v30 + 2 * v51);
      v33 = v50;
      if ( *((_QWORD *)&v51 + 1) > 7u )
        v33 = (struct _GUID **)v50[0];
      while ( v33 != v32 )
      {
        *(_WORD *)v29 = ((__int64 (__fastcall *)(_QWORD))towupper)(*(unsigned __int16 *)v33);
        v33 = (struct _GUID **)((char *)v33 + 2);
        v29 = (struct _GUID **)((char *)v29 + 2);
        v27 = *((_QWORD *)&v51 + 1);
        v31 = v51;
        v28 = v50[0];
      }
      v34 = v50;
      if ( v27 > 7 )
        v34 = (struct _GUID **)v28;
      Uuid = *Vml::CreateType5Guid(
                (Vml *)v38,
                &`ComputeService::Management::GetComputeSystemGuid'::`2'::c_ComputeSystemSeedId,
                (UCHAR *)v34,
                (const void *)(unsigned int)(2 * v31));
      Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v50);
    }
    Context[2] = Uuid;
    memset_0(&v52, 0, 0x150u);
    v10 = -1;
    memset_0(v47, 0, 0x70u);
    RpcCallAttributes[1] = 16;
    RpcCallAttributes[0] = 3;
    if ( !RpcServerInqCallAttributesW(0, RpcCallAttributes) )
      v10 = v48;
    IsMember[0] = v10;
    v11 = Context;
    v53 = 0;
    v54 = 0;
    v58 = 0;
    v55 = 0;
    v56 = "HcsRpc_OpenSystem";
    v57 = 0;
    v59 = 0;
    v61 = 0;
    memset_0(v60, 0, sizeof(v60));
    v62 = 1;
    v63 = 0;
    v64 = &v53;
    v65[0] = 0;
    v65[1] = 0;
    v65[2] = &v52;
    v65[3] = 0;
    v66 = 0;
    v67 = &v55;
    v68 = 0;
    v52 = &ComputeService::Diagnostics::TraceProvider::HcsRpc_OpenSystem::`vftable';
    ComputeService::Diagnostics::TraceProvider::HcsRpc_OpenSystem::StartActivity<_GUID &,unsigned short const * &,unsigned long>(
      &v52,
      &v11[2],
      &StringUuid,
      IsMember);
    v42[0] = &StringUuid;
    v42[1] = &Context;
    v13 = 1;
    v43 = 1;
    Uuid = 0;
    v14 = qword_1403DE910;
    if ( !qword_1403DE910 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x10C,
        (unsigned int)"onecore\\vm\\compute\\rpc\\server\\rpcserver.cpp",
        v12);
    *(_OWORD *)v40 = 0;
    si128 = 0;
    v15 = -1;
    do
      ++v15;
    while ( StringUuid[v15] );
    std::wstring::_Construct<1,unsigned short const *>(v40, StringUuid);
    ComputeService::Management::ComputeSystemManager::FindComputeSystem(v14, &Uuid, v40);
    v16 = -1070137074;
    if ( si128.m128i_i64[1] > 7uLL )
    {
      v17 = (const struct std::nothrow_t *)(2 * si128.m128i_i64[1] + 2);
      *(_QWORD *)IsMember = v17;
      v18 = v40[0];
      v38[0] = v40[0];
      if ( (unsigned __int64)v17 >= 0x1000 )
      {
        std::_Adjust_manually_vector_aligned(v38, (unsigned __int64 *)IsMember);
        v18 = v38[0];
        v17 = *(const struct std::nothrow_t **)IsMember;
      }
      operator delete(v18, v17);
    }
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v40[0]) = 0;
    if ( *(_QWORD *)&Uuid.Data1 )
    {
      v19 = -1;
      do
        ++v19;
      while ( StringUuid[v19] );
      std::wstring::_Assign<unsigned short>(Context);
      v20 = Context;
      v21 = *(_QWORD *)Uuid.Data4;
      if ( *(_QWORD *)Uuid.Data4 )
      {
        v22 = *(_QWORD *)&Uuid.Data1;
        _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)Uuid.Data4 + 12LL), 1u);
      }
      else
      {
        v21 = 0;
        v22 = 0;
      }
      *(_QWORD *)v20[7].Data4 = v22;
      v23 = *(volatile signed __int32 **)&v20[8].Data1;
      *(_QWORD *)&v20[8].Data1 = v21;
      if ( v23 && _InterlockedExchangeAdd(v23 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
      *a4 = Context;
      v13 = 0;
      v16 = 0;
    }
    if ( *(_QWORD *)Uuid.Data4 )
      std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)Uuid.Data4);
    wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
      &v52,
      v16);
    if ( v13 )
    {
      v43 = 0;
      lambda_8a9c26a4b897a382f3d965e8f7daa3d8_::operator()(v42);
    }
    v52 = &ComputeService::Diagnostics::TraceProvider::HcsRpc_OpenSystem::`vftable';
    if ( !v65[0] )
      goto LABEL_37;
    v38[0] = 0;
    wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,70368744185856,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      &v52,
      v38);
    if ( v65[0] && *(_DWORD *)v65[0] == 1 )
    {
      v35 = 1;
    }
    else
    {
      v35 = 0;
      wil::details::shared_object<wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ComputeService::Diagnostics::TraceProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(v65);
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(v38);
    if ( v35 )
    {
LABEL_37:
      if ( *v64 == 1 )
      {
        v36 = v64[22];
        IsMember[0] = v36;
        v37 = 2147942974LL;
        if ( v36 < 0 )
          v37 = (unsigned int)v36;
        wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ComputeService::Diagnostics::TraceProvider,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
          v64,
          v37,
          IsMember);
        wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(&v52);
      }
    }
    wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeService::Diagnostics::TraceProvider,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>(&v52);
    result = v16;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1ED,
                           (unsigned int)"onecore\\vm\\compute\\rpc\\server\\computesystemrpc.cpp",
                           v24);
  }
  return result;
}

```

## disassembly

```asm
0x14001cd60  mov     [rsp+arg_10], rbx
0x14001cd65  push    rsi
0x14001cd66  push    rdi
0x14001cd67  push    r12
0x14001cd69  push    r14
0x14001cd6b  push    r15
0x14001cd6d  sub     rsp, 2A0h
0x14001cd74  mov     rax, cs:__security_cookie
0x14001cd7b  xor     rax, rsp
0x14001cd7e  mov     [rsp+2C8h+var_38], rax
0x14001cd86  mov     rsi, r9
0x14001cd89  mov     [rsp+2C8h+StringUuid], rdx
0x14001cd8e  xor     r15d, r15d
0x14001cd91  cmp     cs:qword_1403DE908, r15
0x14001cd98  jz      loc_14001CE23
0x14001cd9e  mov     [rsp+2C8h+var_2A8], r15; int
0x14001cda3  mov     rdx, rcx
0x14001cda6  lea     rcx, [rsp+2C8h+var_2A8]
0x14001cdab  call    ?HcsRpcImpersonateClient@Rpc@ComputeService@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?RpcRevertToSelfEx@@YAJ0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0?0PEAX@details@wil@@@details@wil@@@wil@@PEAX@Z; ComputeService::Rpc::HcsRpcImpersonateClient(void *)
0x14001cdb0  nop
0x14001cdb1  mov     [rsp+2C8h+IsMember], r15d
0x14001cdb9  lea     r8, [rsp+2C8h+IsMember]; IsMember
0x14001cdc1  mov     rdx, cs:qword_1403DE908
0x14001cdc8  mov     rdx, [rdx]; SidToCheck
0x14001cdcb  xor     ecx, ecx; TokenHandle
0x14001cdcd  call    cs:__imp_CheckTokenMembership
0x14001cdd4  nop     dword ptr [rax+rax+00h]
0x14001cdd9  test    eax, eax
0x14001cddb  jnz     loc_14001D293
0x14001cde1  mov     rcx, [rsp+2C8h]; this
0x14001cde9  lea     r8, aOnecoreVmCompu_87; "onecore\\vm\\compute\\rpc\\server\\rpcs"...
0x14001cdf0  mov     edx, 16Ch; void *
0x14001cdf5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14001cdfa  mov     ebx, eax
0x14001cdfc  mov     rcx, [rsp+2C8h+var_2A8]
0x14001ce01  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14001ce05  jz      short loc_14001CE26
0x14001ce07  mov     rax, cs:__imp_RpcRevertToSelfEx
0x14001ce0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ce13  nop
0x14001ce14  jmp     short loc_14001CE26
0x14001ce16  mov     rax, cs:__imp_RpcRevertToSelfEx
0x14001ce1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ce22  nop
0x14001ce23  mov     ebx, r15d
0x14001ce26  mov     rcx, [rsp+2C8h]; this
0x14001ce2e  test    ebx, ebx
0x14001ce30  js      loc_14001D394
0x14001ce36  mov     rcx, [rsp+2C8h]; this
0x14001ce3e  test    rsi, rsi
0x14001ce41  jz      loc_14001D3A8
0x14001ce47  mov     [rsi], r15
0x14001ce4a  mov     rdx, [rsp+2C8h+StringUuid]
0x14001ce4f  xorps   xmm0, xmm0
0x14001ce52  movups  xmmword ptr [rsp+2C8h+var_288], xmm0
0x14001ce57  mov     qword ptr [rsp+2C8h+var_278], r15
0x14001ce5c  mov     qword ptr [rsp+2C8h+var_278+8], r15
0x14001ce61  or      r8, 0FFFFFFFFFFFFFFFFh
0x14001ce65  inc     r8
0x14001ce68  cmp     [rdx+r8*2], r15w
0x14001ce6d  jnz     short loc_14001CE65
0x14001ce6f  lea     rcx, [rsp+2C8h+var_288]
0x14001ce74  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14001ce79  lea     rdx, [rsp+2C8h+var_288]
0x14001ce7e  call    ?CreateContext@?$RpcContextMap@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@USystemContext@Rpc@ComputeService@@UCaseInsensitiveLess@Vml@@@Rpc@ComputeService@@QEAAPEAUSystemContext@23@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ComputeService::Rpc::RpcContextMap<std::wstring,ComputeService::Rpc::SystemContext,Vml::CaseInsensitiveLess>::CreateContext(std::wstring)
0x14001ce83  mov     [rsp+2C8h+var_248], rax
0x14001ce8b  mov     rbx, [rsp+2C8h+StringUuid]
0x14001ce90  xorps   xmm0, xmm0
0x14001ce93  movups  xmmword ptr [rsp+2C8h+Uuid.Data1], xmm0
0x14001ce98  test    rbx, rbx
0x14001ce9b  jz      loc_14001D235
0x14001cea1  lea     rdx, [rsp+2C8h+Uuid]; Uuid
0x14001cea6  mov     rcx, rbx; StringUuid
0x14001cea9  call    cs:__imp_UuidFromStringW
0x14001ceb0  nop     dword ptr [rax+rax+00h]
0x14001ceb5  test    eax, eax
0x14001ceb7  jnz     loc_14001D235
0x14001cebd  movaps  xmm0, xmmword ptr [rsp+2C8h+Uuid.Data1]
0x14001cec2  mov     rax, [rsp+2C8h+var_248]
0x14001ceca  movdqu  xmmword ptr [rax+20h], xmm0
0x14001cecf  xor     edx, edx; Val
0x14001ced1  mov     r8d, 150h; Size
0x14001ced7  lea     rcx, [rsp+2C8h+var_188]; void *
0x14001cedf  call    memset_0
0x14001cee4  or      ebx, 0FFFFFFFFh
0x14001cee7  xor     edx, edx; Val
0x14001cee9  lea     r8d, [rdx+70h]; Size
0x14001ceed  lea     rcx, [rsp+2C8h+var_230]; void *
0x14001cef5  call    memset_0
0x14001cefa  mov     [rsp+2C8h+var_234], 10h
0x14001cf05  mov     [rsp+2C8h+RpcCallAttributes], 3
0x14001cf10  lea     rdx, [rsp+2C8h+RpcCallAttributes]; RpcCallAttributes
0x14001cf18  xor     ecx, ecx; ClientBinding
0x14001cf1a  call    cs:__imp_RpcServerInqCallAttributesW
0x14001cf21  nop     dword ptr [rax+rax+00h]
0x14001cf26  test    eax, eax
0x14001cf28  cmovz   ebx, [rsp+2C8h+var_1F8]
0x14001cf30  mov     [rsp+2C8h+IsMember], ebx
0x14001cf37  mov     rbx, [rsp+2C8h+var_248]
0x14001cf3f  mov     [rsp+2C8h+var_180], r15d
0x14001cf47  mov     [rsp+2C8h+var_17C], r15b
0x14001cf4f  mov     [rsp+2C8h+var_140], r15b
0x14001cf57  mov     [rsp+2C8h+var_158], r15d
0x14001cf5f  lea     rax, aHcsrpcOpensyst; "HcsRpc_OpenSystem"
0x14001cf66  mov     [rsp+2C8h+var_150], rax
0x14001cf6e  mov     [rsp+2C8h+var_148], r15
0x14001cf76  mov     [rsp+2C8h+var_138], r15d
0x14001cf7e  xorps   xmm0, xmm0
0x14001cf81  movdqa  [rsp+2C8h+var_98], xmm0
0x14001cf8a  xor     edx, edx; Val
0x14001cf8c  mov     r8d, 98h; Size
0x14001cf92  lea     rcx, [rsp+2C8h+var_130]; void *
0x14001cf9a  call    memset_0
0x14001cf9f  mov     r14d, 1
0x14001cfa5  mov     [rsp+2C8h+var_88], r14d
0x14001cfad  xor     eax, eax
0x14001cfaf  mov     [rsp+2C8h+var_80], rax
0x14001cfb7  lea     rax, [rsp+2C8h+var_180]
0x14001cfbf  mov     [rsp+2C8h+var_78], rax
0x14001cfc7  mov     [rsp+2C8h+var_70], r15
0x14001cfcf  mov     [rsp+2C8h+var_68], r15
0x14001cfd7  lea     rax, [rsp+2C8h+var_188]
0x14001cfdf  mov     [rsp+2C8h+var_60], rax
0x14001cfe7  mov     [rsp+2C8h+var_58], r15
0x14001cfef  mov     [rsp+2C8h+var_50], r15d
0x14001cff7  lea     rax, [rsp+2C8h+var_158]
0x14001cfff  mov     [rsp+2C8h+var_48], rax
0x14001d007  mov     [rsp+2C8h+var_40], r15b
0x14001d00f  lea     r12, ??_7HcsRpc_OpenSystem@TraceProvider@Diagnostics@ComputeService@@6B@; const ComputeService::Diagnostics::TraceProvider::HcsRpc_OpenSystem::`vftable'
0x14001d016  mov     [rsp+2C8h+var_188], r12
0x14001d01e  lea     r9, [rsp+2C8h+IsMember]
0x14001d026  lea     r8, [rsp+2C8h+StringUuid]
0x14001d02b  lea     rdx, [rbx+20h]
0x14001d02f  lea     rcx, [rsp+2C8h+var_188]
0x14001d037  call    ??$StartActivity@AEAU_GUID@@AEAPEBGK@HcsRpc_OpenSystem@TraceProvider@Diagnostics@ComputeService@@QEAAXAEAU_GUID@@AEAPEBG$$QEAK@Z; ComputeService::Diagnostics::TraceProvider::HcsRpc_OpenSystem::StartActivity<_GUID &,ushort const * &,ulong>(_GUID &,ushort const * &,ulong &&)
0x14001d03c  nop
0x14001d03d  lea     rax, [rsp+2C8h+StringUuid]
0x14001d042  mov     [rsp+2C8h+var_268], rax
0x14001d047  lea     rax, [rsp+2C8h+var_248]
0x14001d04f  mov     [rsp+2C8h+var_260], rax
0x14001d054  mov     dil, r14b
0x14001d057  mov     [rsp+2C8h+var_258], r14b
0x14001d05c  xorps   xmm0, xmm0
0x14001d05f  movups  xmmword ptr [rsp+2C8h+Uuid.Data1], xmm0
0x14001d064  mov     rcx, [rsp+2C8h]; this
0x14001d06c  mov     rbx, cs:qword_1403DE910
0x14001d073  test    rbx, rbx
0x14001d076  jz      loc_14001D3C0
0x14001d07c  mov     rdx, [rsp+2C8h+StringUuid]
0x14001d081  movups  xmmword ptr [rsp+2C8h+var_288], xmm0
0x14001d086  xorps   xmm1, xmm1
0x14001d089  movdqu  [rsp+2C8h+var_278], xmm1
0x14001d08f  or      r8, 0FFFFFFFFFFFFFFFFh
0x14001d093  inc     r8
0x14001d096  cmp     [rdx+r8*2], r15w
0x14001d09b  jnz     short loc_14001D093
0x14001d09d  lea     rcx, [rsp+2C8h+var_288]
0x14001d0a2  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14001d0a7  nop
0x14001d0a8  lea     r8, [rsp+2C8h+var_288]
0x14001d0ad  lea     rdx, [rsp+2C8h+Uuid]
0x14001d0b2  mov     rcx, rbx
0x14001d0b5  call    ?FindComputeSystem@ComputeSystemManager@Management@ComputeService@@QEBA?AV?$shared_ptr@VComputeSystem@Management@ComputeService@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@@Z; ComputeService::Management::ComputeSystemManager::FindComputeSystem(std::wstring const &)
0x14001d0ba  nop
0x14001d0bb  mov     rdx, qword ptr [rsp+2C8h+var_278+8]
0x14001d0c0  mov     ebx, 0C037010Eh
0x14001d0c5  cmp     rdx, 7
0x14001d0c9  jbe     short loc_14001D0F7
0x14001d0cb  lea     rdx, ds:2[rdx*2]; struct std::nothrow_t *
0x14001d0d3  mov     qword ptr [rsp+2C8h+IsMember], rdx
0x14001d0db  mov     rcx, [rsp+2C8h+var_288]; void *
0x14001d0e0  mov     [rsp+2C8h+var_2A8], rcx
0x14001d0e5  cmp     rdx, 1000h
0x14001d0ec  jnb     loc_14001D3D2
0x14001d0f2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001d0f7  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x14001d0ff  movdqu  [rsp+2C8h+var_278], xmm0
0x14001d105  mov     word ptr [rsp+2C8h+var_288], r15w
0x14001d10b  cmp     qword ptr [rsp+2C8h+Uuid.Data1], r15
0x14001d110  jz      loc_14001D197
0x14001d116  mov     rdx, [rsp+2C8h+StringUuid]
0x14001d11b  or      r8, 0FFFFFFFFFFFFFFFFh
0x14001d11f  inc     r8
0x14001d122  cmp     [rdx+r8*2], r15w
0x14001d127  jnz     short loc_14001D11F
0x14001d129  mov     rcx, [rsp+2C8h+var_248]
0x14001d131  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x14001d136  mov     rdx, [rsp+2C8h+var_248]
0x14001d13e  mov     rax, qword ptr [rsp+2C8h+Uuid.Data4]
0x14001d143  test    rax, rax
0x14001d146  jz      loc_14001D22A
0x14001d14c  mov     rcx, qword ptr [rsp+2C8h+Uuid.Data1]
0x14001d151  lock add [rax+0Ch], r14d
0x14001d156  mov     [rdx+78h], rcx
0x14001d15a  mov     rcx, [rdx+80h]
0x14001d161  mov     [rdx+80h], rax
0x14001d168  test    rcx, rcx
0x14001d16b  jz      short loc_14001D186
0x14001d16d  or      eax, 0FFFFFFFFh
0x14001d170  lock xadd [rcx+0Ch], eax
0x14001d175  cmp     eax, 1
0x14001d178  jnz     short loc_14001D186
0x14001d17a  mov     rax, [rcx]
0x14001d17d  mov     rax, [rax+8]
0x14001d181  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d186  mov     rax, [rsp+2C8h+var_248]
0x14001d18e  mov     [rsi], rax
0x14001d191  mov     dil, r15b
0x14001d194  mov     ebx, r15d
0x14001d197  mov     rcx, qword ptr [rsp+2C8h+Uuid.Data4]; this
0x14001d19c  test    rcx, rcx
0x14001d19f  jz      short loc_14001D1A6
0x14001d1a1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14001d1a6  mov     edx, ebx
0x14001d1a8  lea     rcx, [rsp+2C8h+var_188]
0x14001d1b0  call    ?Stop@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0CA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x14001d1b5  nop
0x14001d1b6  test    dil, dil
0x14001d1b9  jz      short loc_14001D1CB
0x14001d1bb  mov     [rsp+2C8h+var_258], r15b
0x14001d1c0  lea     rcx, [rsp+2C8h+var_268]
0x14001d1c5  call    _lambda_8a9c26a4b897a382f3d965e8f7daa3d8___operator__
0x14001d1ca  nop
0x14001d1cb  mov     [rsp+2C8h+var_188], r12
0x14001d1d3  cmp     [rsp+2C8h+var_70], r15
0x14001d1db  jnz     loc_14001D3F6
0x14001d1e1  mov     rcx, [rsp+2C8h+var_78]
0x14001d1e9  cmp     [rcx], r14d
0x14001d1ec  jz      loc_14001D43C
0x14001d1f2  lea     rcx, [rsp+2C8h+var_188]
0x14001d1fa  call    ??1?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0CA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeService::Diagnostics::TraceProvider,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x14001d1ff  mov     eax, ebx
0x14001d201  mov     rcx, [rsp+2C8h+var_38]
0x14001d209  xor     rcx, rsp; StackCookie
0x14001d20c  call    __security_check_cookie
0x14001d211  mov     rbx, [rsp+2C8h+arg_10]
0x14001d219  add     rsp, 2A0h
0x14001d220  pop     r15
0x14001d222  pop     r14
0x14001d224  pop     r12
0x14001d226  pop     rdi
0x14001d227  pop     rsi
0x14001d228  retn
0x14001d22a  mov     rax, r15
0x14001d22d  mov     rcx, r15
0x14001d230  jmp     loc_14001D156
0x14001d235  xorps   xmm0, xmm0
0x14001d238  movups  xmmword ptr [rsp+2C8h+var_1B0], xmm0
0x14001d240  xorps   xmm1, xmm1
0x14001d243  movdqu  [rsp+2C8h+var_1A0], xmm1
0x14001d24c  or      r8, 0FFFFFFFFFFFFFFFFh
0x14001d250  inc     r8
0x14001d253  cmp     [rbx+r8*2], r15w
0x14001d258  jnz     short loc_14001D250
0x14001d25a  mov     rdx, rbx
0x14001d25d  lea     rcx, [rsp+2C8h+var_1B0]
0x14001d265  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14001d26a  nop
0x14001d26b  mov     rcx, qword ptr [rsp+2C8h+var_1A0+8]
0x14001d273  mov     rax, [rsp+2C8h+var_1B0]
0x14001d27b  cmp     rcx, 7
0x14001d27f  ja      short loc_14001D2B5
0x14001d281  lea     rdi, [rsp+2C8h+var_1B0]
0x14001d289  lea     rdx, [rsp+2C8h+var_1B0]
0x14001d291  jmp     short loc_14001D2BB
0x14001d293  cmp     [rsp+2C8h+IsMember], r15d
0x14001d29b  jnz     loc_14001D363
0x14001d2a1  mov     rcx, [rsp+2C8h+var_2A8]
0x14001d2a6  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14001d2aa  jnz     loc_14001CE16
0x14001d2b0  jmp     loc_14001CE23
0x14001d2b5  mov     rdi, rax
0x14001d2b8  mov     rdx, rax
0x14001d2bb  mov     r9, qword ptr [rsp+2C8h+var_1A0]
0x14001d2c3  lea     r14, [rdx+r9*2]
0x14001d2c7  lea     rbx, [rsp+2C8h+var_1B0]
0x14001d2cf  cmova   rbx, rax
0x14001d2d3  cmp     rbx, r14
0x14001d2d6  jz      short loc_14001D30C
0x14001d2d8  movzx   ecx, word ptr [rbx]
0x14001d2db  mov     rax, cs:__imp_towupper
0x14001d2e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d2e7  mov     [rdi], ax
0x14001d2ea  add     rbx, 2
0x14001d2ee  add     rdi, 2
0x14001d2f2  mov     rcx, qword ptr [rsp+2C8h+var_1A0+8]
0x14001d2fa  mov     r9, qword ptr [rsp+2C8h+var_1A0]
0x14001d302  mov     rax, [rsp+2C8h+var_1B0]
0x14001d30a  jmp     short loc_14001D2D3
0x14001d30c  lea     r8, [rsp+2C8h+var_1B0]
0x14001d314  cmp     rcx, 7
0x14001d318  cmova   r8, rax; struct _GUID *
0x14001d31c  add     r9d, r9d; void *
0x14001d31f  lea     rdx, ?c_ComputeSystemSeedId@?1??GetComputeSystemGuid@Management@ComputeService@@YA?AU_GUID@@PEBG@Z@4U4@B; retstr
0x14001d326  lea     rcx, [rsp+2C8h+var_2A8]; this
0x14001d32b  call    ?CreateType5Guid@Vml@@YA?AU_GUID@@AEBU2@PEBXK@Z; Vml::CreateType5Guid(_GUID const &,void const *,ulong)
0x14001d330  movups  xmm0, xmmword ptr [rax]
0x14001d333  movdqu  xmmword ptr [rsp+2C8h+Uuid.Data1], xmm0
0x14001d339  lea     rcx, [rsp+2C8h+var_1B0]; this
0x14001d341  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
  ... truncated ...
```
