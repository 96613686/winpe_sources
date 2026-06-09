# ComputeService::Communication::LoggingServiceManager::SendModificationRequest(Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits> const &)

- ea: `0x1400557a4`
- end: `0x140055942`
- name: `?SendModificationRequest@LoggingServiceManager@Communication@ComputeService@@YAXAEBV?$DelayedBase@XUDelayedJsonTraits@Details@Marshal@@@Marshal@@@Z`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140054f80`

## callees

- `0x140005360`
- `0x1400083bc`
- `0x140008760`
- `0x14000f93c`
- `0x140034170`
- `0x1400393b8`
- `0x14003a9ac`
- `0x140049f74`
- `0x14004b7d8`
- `0x14004b848`
- `0x14004fc5c`
- `0x1400557a4`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x1400558d5`
- `RPCRT4!RpcStringFreeW` at `0x1400558d5`
- `RPCRT4!RpcStringBindingComposeW` at `0x14005582e`
- `RPCRT4!RpcStringBindingComposeW` at `0x14005582e`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x14005584c`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x14005584c`
- `RPCRT4!RpcBindingFree` at `0x1400558be`
- `RPCRT4!RpcBindingFree` at `0x1400558be`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ComputeService::Communication::LoggingServiceManager::SendModificationRequest(__int64 a1)
{
  _BYTE *v1; // rax
  RPC_BINDING_HANDLE *v2; // rax
  __int64 (__fastcall *v3)(); // rcx
  __int128 *v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  unsigned int v7; // eax
  const char *v8; // rdx
  __int128 *v9; // [rsp+30h] [rbp-19h] BYREF
  char v10[8]; // [rsp+38h] [rbp-11h] BYREF
  char v11[24]; // [rsp+40h] [rbp-9h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+58h] [rbp+Fh] BYREF
  __int128 *v13; // [rsp+60h] [rbp+17h] BYREF
  RPC_WSTR StringBinding; // [rsp+68h] [rbp+1Fh] BYREF
  unsigned int v15; // [rsp+70h] [rbp+27h] BYREF
  __int128 v16; // [rsp+78h] [rbp+2Fh] BYREF
  __m128i si128; // [rsp+88h] [rbp+3Fh]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v15 = 0;
  v16 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v16) = 0;
  v1 = (_BYTE *)Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<Compute::Containers::BridgeMessage::LogForwardServiceRpcRequest>(
                  a1,
                  v10,
                  &v15);
  if ( !*v1 )
  {
    v5 = std::shared_ptr<ComputeService::Management::ComputeSystem>::operator-><ComputeService::Management::ComputeSystem,0>((__int64)(v1 + 8));
    v6 = std::wstring::c_str(v5);
    v7 = wil::verify_hresult<long>(2147942413LL, v6);
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x1F,
      (unsigned int)"OneCore\\Internal\\VM\\inc\\MarshalUtilities.h",
      (const char *)v7,
      (int)"%ls",
      v8);
  }
  std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(v11);
  StringBinding = 0;
  RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, (RPC_WSTR)L"ncalrpc:[ms_logfwdsvc]", 0, &StringBinding);
  v13 = 0;
  v2 = (RPC_BINDING_HANDLE *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::operator&(&v13);
  RpcBindingFromStringBindingW(StringBinding, v2);
  if ( v15 )
  {
    if ( v15 == 1 )
    {
      v3 = LogForwardServiceRpc_StartLogForwarding;
    }
    else
    {
      if ( v15 != 2 )
        goto LABEL_11;
      v3 = LogForwardServiceRpc_StopLogForwarding;
    }
    v9 = v13;
    wil::invoke_rpc_nothrow<long (&)(void *),void *>(v3, &v9);
  }
  else
  {
    v4 = &v16;
    if ( si128.m128i_i64[1] > 7uLL )
      v4 = (__int128 *)v16;
    v9 = v4;
    Binding = v13;
    wil::invoke_rpc_nothrow<long (&)(void *,unsigned short const *),void *,unsigned short const *>(v15, &Binding, &v9);
  }
LABEL_11:
  if ( v13 )
  {
    Binding = v13;
    RpcBindingFree(&Binding);
  }
  if ( StringBinding )
  {
    Binding = StringBinding;
    RpcStringFreeW((RPC_WSTR *)&Binding);
  }
  std::wstring::~wstring(&v16);
}

```

## disassembly

```asm
0x1400557a4  push    rbp
0x1400557a6  lea     rbp, [rsp-57h]
0x1400557ab  sub     rsp, 0A0h
0x1400557b2  mov     rax, cs:__security_cookie
0x1400557b9  xor     rax, rsp
0x1400557bc  mov     [rbp+57h+var_8], rax
0x1400557c0  mov     [rbp+57h+var_30], 0
0x1400557c7  xorps   xmm0, xmm0
0x1400557ca  movups  [rbp+57h+var_28], xmm0
0x1400557ce  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1400557d6  movdqu  [rbp+57h+var_18], xmm1
0x1400557db  xor     eax, eax
0x1400557dd  mov     word ptr [rbp+57h+var_28], ax
0x1400557e1  lea     r8, [rbp+57h+var_30]
0x1400557e5  lea     rdx, [rbp+57h+var_68]
0x1400557e9  call    ??$Unmarshal@ULogForwardServiceRpcRequest@BridgeMessage@Containers@Compute@@@?$DelayedBase@XUDelayedJsonTraits@Details@Marshal@@@Marshal@@QEBA?AU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@PEAULogForwardServiceRpcRequest@BridgeMessage@Containers@Compute@@@Z; Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<Compute::Containers::BridgeMessage::LogForwardServiceRpcRequest>(Compute::Containers::BridgeMessage::LogForwardServiceRpcRequest *)
0x1400557ee  nop
0x1400557ef  cmp     byte ptr [rax], 0
0x1400557f2  jz      loc_1400558FA
0x1400557f8  lea     rcx, [rbp+57h+var_60]
0x1400557fc  call    ?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::_Tidy(void)
0x140055801  mov     [rbp+57h+var_38], 0
0x140055809  lea     rax, [rbp+57h+var_38]
0x14005580d  mov     [rsp+0A0h+StringBinding], rax; StringBinding
0x140055812  mov     [rsp+0A0h+Options], 0; Options
0x14005581b  lea     r9, Endpoint; "ncalrpc:[ms_logfwdsvc]"
0x140055822  xor     r8d, r8d; NetworkAddr
0x140055825  lea     rdx, ProtSeq; "ncalrpc"
0x14005582c  xor     ecx, ecx; ObjUuid
0x14005582e  call    cs:__imp_RpcStringBindingComposeW
0x140055834  mov     [rbp+57h+var_40], 0
0x14005583c  lea     rcx, [rbp+57h+var_40]
0x140055840  call    ??I?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::operator&(void)
0x140055845  mov     rdx, rax; Binding
0x140055848  mov     rcx, [rbp+57h+var_38]; StringBinding
0x14005584c  call    cs:__imp_RpcBindingFromStringBindingW
0x140055852  mov     ecx, [rbp+57h+var_30]
0x140055855  test    ecx, ecx
0x140055857  jz      short loc_140055886
0x140055859  sub     ecx, 1
0x14005585c  jz      short loc_14005586C
0x14005585e  cmp     ecx, 1
0x140055861  jnz     short loc_1400558AD
0x140055863  lea     rcx, LogForwardServiceRpc_StopLogForwarding
0x14005586a  jmp     short loc_140055873
0x14005586c  lea     rcx, LogForwardServiceRpc_StartLogForwarding
0x140055873  mov     rax, [rbp+57h+var_40]
0x140055877  lea     rdx, [rbp+57h+var_70]
0x14005587b  mov     [rbp+57h+var_70], rax
0x14005587f  call    ??$invoke_rpc_nothrow@A6AJPEAX@ZPEAX@wil@@YAJA6AJPEAX@Z$$QEAPEAX@Z; wil::invoke_rpc_nothrow<long (&)(void *),void *>(long (&)(void *),void * &&)
0x140055884  jmp     short loc_1400558AD
0x140055886  lea     rax, [rbp+57h+var_28]
0x14005588a  cmp     qword ptr [rbp+57h+var_18+8], 7
0x14005588f  cmova   rax, qword ptr [rbp+57h+var_28]
0x140055894  mov     [rbp+57h+var_70], rax
0x140055898  mov     rax, [rbp+57h+var_40]
0x14005589c  mov     [rbp+57h+Binding], rax
0x1400558a0  lea     r8, [rbp+57h+var_70]
0x1400558a4  lea     rdx, [rbp+57h+Binding]
0x1400558a8  call    ??$invoke_rpc_nothrow@A6AJPEAXPEBG@ZPEAXPEBG@wil@@YAJA6AJPEAXPEBG@Z$$QEAPEAX$$QEAPEBG@Z; wil::invoke_rpc_nothrow<long (&)(void *,ushort const *),void *,ushort const *>(long (&)(void *,ushort const *),void * &&,ushort const * &&)
0x1400558ad  mov     rax, [rbp+57h+var_40]
0x1400558b1  test    rax, rax
0x1400558b4  jz      short loc_1400558C4
0x1400558b6  mov     [rbp+57h+Binding], rax
0x1400558ba  lea     rcx, [rbp+57h+Binding]; Binding
0x1400558be  call    cs:__imp_RpcBindingFree
0x1400558c4  mov     rax, [rbp+57h+var_38]
0x1400558c8  test    rax, rax
0x1400558cb  jz      short loc_1400558DC
0x1400558cd  mov     [rbp+57h+Binding], rax
0x1400558d1  lea     rcx, [rbp+57h+Binding]; String
0x1400558d5  call    cs:__imp_RpcStringFreeW
0x1400558db  nop
0x1400558dc  lea     rcx, [rbp+57h+var_28]; void *
0x1400558e0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400558e5  mov     rcx, [rbp+57h+var_8]
0x1400558e9  xor     rcx, rsp; StackCookie
0x1400558ec  call    __security_check_cookie
0x1400558f1  add     rsp, 0A0h
0x1400558f8  pop     rbp
0x1400558f9  retn
0x1400558fa  lea     rcx, [rax+8]
0x1400558fe  call    ??$?CVComputeSystem@Management@ComputeService@@$0A@@?$shared_ptr@VComputeSystem@Management@ComputeService@@@std@@QEBAPEAVComputeSystem@Management@ComputeService@@XZ; std::shared_ptr<ComputeService::Management::ComputeSystem>::operator-><ComputeService::Management::ComputeSystem,0>(void)
0x140055903  mov     rcx, rax
0x140055906  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x14005590b  mov     rdx, rax
0x14005590e  mov     ecx, 8007000Dh
0x140055913  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x140055918  mov     r9d, eax; char *
0x14005591b  mov     rcx, [rbp+5Fh]; this
0x14005591f  mov     [rsp+0A0h+StringBinding], rdx; char *
0x140055924  lea     rax, aLs; "%ls"
0x14005592b  mov     [rsp+0A0h+Options], rax; int
0x140055930  lea     r8, aOnecoreInterna; "OneCore\\Internal\\VM\\inc\\MarshalUtil"...
0x140055937  mov     edx, 1Fh; void *
0x14005593c  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
