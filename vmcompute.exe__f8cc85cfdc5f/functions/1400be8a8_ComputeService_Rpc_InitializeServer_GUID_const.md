# ComputeService::Rpc::InitializeServer(_GUID const *)

- ea: `0x1400be8a8`
- end: `0x1400beaf9`
- name: `?InitializeServer@Rpc@ComputeService@@YAXPEBU_GUID@@@Z`
- size: `593`
- prototype: `void __fastcall(ComputeService::Rpc *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1400bd0b8`

## callees

- `0x140017040`
- `0x14001d490`
- `0x140031720`
- `0x140080180`
- `0x1400b1dd0`
- `0x1400be8a8`
- `0x1400beb00`
- `0x1400beb4c`
- `0x1400bebbc`
- `0x1400beca4`
- `0x1400becc4`
- `0x1400c4154`
- `0x1401332f0`
- `0x140133314`
- `0x140134048`
- `0x14025c474`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1400be97a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1400be97a`
- `RPCRT4!RpcServerInqBindings` at `0x1400be9f4`
- `RPCRT4!RpcServerInqBindings` at `0x1400be9f4`
- `RPCRT4!RpcEpRegisterW` at `0x1400bea44`
- `RPCRT4!RpcEpRegisterW` at `0x1400bea44`
- `RPCRT4!RpcServerUseProtseqW` at `0x1400be8f3`
- `RPCRT4!RpcServerUseProtseqW` at `0x1400be8f3`
- `WS2_32!__imp_WSAStartup` at `0x1400bea8c`
- `WS2_32!__imp_WSAStartup` at `0x1400bea8c`

## string_xrefs

- `0x1400be90d`: `onecore\vm\compute\rpc\server\rpcserver.cpp`
- `0x1400be991`: `onecore\vm\compute\rpc\server\rpcserver.cpp`
- `0x1400bea0e`: `onecore\vm\compute\rpc\server\rpcserver.cpp`
- `0x1400bea5e`: `onecore\vm\compute\rpc\server\rpcserver.cpp`
- `0x1400beaa6`: `onecore\vm\compute\rpc\server\rpcserver.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall ComputeService::Rpc::InitializeServer(ComputeService::Rpc *this, const struct _GUID *a2)
{
  unsigned int v2; // eax
  __int64 v3; // rdx
  PSID *v4; // rbx
  const char *v5; // r9
  __int64 v6; // rdx
  const unsigned __int16 *v7; // rdx
  const WCHAR *v8; // rcx
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // [rsp+20h] [rbp-E0h]
  RPC_BINDING_VECTOR *BindingVector; // [rsp+30h] [rbp-D0h] BYREF
  void *SecurityDescriptor; // [rsp+38h] [rbp-C8h] BYREF
  PSID *v15; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR StringSecurityDescriptor[5]; // [rsp+48h] [rbp-B8h] BYREF
  WSAData WSAData; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+128h]

  SecurityDescriptor = 0;
  ComputeService::Rpc::GetRpcEndpointQueryDescriptor(&SecurityDescriptor);
  v2 = RpcServerUseProtseqW((RPC_WSTR)L"ncalrpc", 0xAu, SecurityDescriptor);
  if ( v2 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x9D,
      (unsigned int)"onecore\\vm\\compute\\rpc\\server\\rpcserver.cpp",
      (const char *)v2,
      v12);
  std::wstring::wstring(StringSecurityDescriptor, L"O:BAG:BAD:(A;;GA;;;SY)(A;;GA;;;BA)(A;;GA;;;HA)");
  LOBYTE(v3) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_HcsRelaxRpcAccess>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_HcsRelaxRpcAccess>::GetImpl'::`2'::impl,
    v3);
  std::wstring::append(
    StringSecurityDescriptor,
    L"(A;;GA;;;S-1-5-80-2970612574-78537857-698502321-558674196-1451644582)");
  v4 = (PSID *)operator new(8u);
  *v4 = 0;
  v15 = v4;
  *v4 = 0;
  if ( !ConvertStringSidToSidW(L"S-1-5-80-2970612574-78537857-698502321-558674196-1451644582", v4) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xA9,
      (unsigned int)"onecore\\vm\\compute\\rpc\\server\\rpcserver.cpp",
      v5);
  v15 = 0;
  v6 = qword_1403DE908;
  qword_1403DE908 = (__int64)v4;
  if ( v6 )
    std::default_delete<ComputeService::Rpc::AccessCheckContext>::operator()(retaddr);
  std::unique_ptr<ComputeService::Rpc::AccessCheckContext>::~unique_ptr<ComputeService::Rpc::AccessCheckContext>(&v15);
  v8 = (const WCHAR *)StringSecurityDescriptor;
  if ( StringSecurityDescriptor[3] > (LPCWSTR)7 )
    v8 = StringSecurityDescriptor[0];
  ComputeService::Rpc::RegisterServerInterface(v8, v7);
  BindingVector = 0;
  v9 = RpcServerInqBindings(&BindingVector);
  if ( v9 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0xB2,
      (unsigned int)"onecore\\vm\\compute\\rpc\\server\\rpcserver.cpp",
      (const char *)v9,
      v12);
  v10 = RpcEpRegisterW(qword_1402C9E60, BindingVector, 0, 0);
  if ( v10 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0xBA,
      (unsigned int)"onecore\\vm\\compute\\rpc\\server\\rpcserver.cpp",
      (const char *)v10,
      1u);
  memset_0(&WSAData, 0, sizeof(WSAData));
  v11 = WSAStartup(0x202u, &WSAData);
  if ( v11 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0xBE,
      (unsigned int)"onecore\\vm\\compute\\rpc\\server\\rpcserver.cpp",
      (const char *)v11,
      1u);
  wil::details::unique_storage<wil::details::resource_policy<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR *),&void wil::details::WpRpcBindingVectorFree(_RPC_BINDING_VECTOR *),wistd::integral_constant<unsigned __int64,0>,_RPC_BINDING_VECTOR *,_RPC_BINDING_VECTOR *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR *),&void wil::details::WpRpcBindingVectorFree(_RPC_BINDING_VECTOR *),wistd::integral_constant<unsigned __int64,0>,_RPC_BINDING_VECTOR *,_RPC_BINDING_VECTOR *,0,std::nullptr_t>>(&BindingVector);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)StringSecurityDescriptor);
  Vml::VmLocalPtr<_TOKEN_PRIMARY_GROUP>::~VmLocalPtr<_TOKEN_PRIMARY_GROUP>(&SecurityDescriptor);
}

```

## disassembly

```asm
0x1400be8a8  mov     [rsp-8+arg_0], rbx
0x1400be8ad  push    rbp
0x1400be8ae  lea     rbp, [rsp-120h]
0x1400be8b6  sub     rsp, 220h
0x1400be8bd  mov     rax, cs:__security_cookie
0x1400be8c4  xor     rax, rsp
0x1400be8c7  mov     [rbp+120h+var_10], rax
0x1400be8ce  mov     [rsp+220h+SecurityDescriptor], 0
0x1400be8d7  lea     rcx, [rsp+220h+SecurityDescriptor]; SecurityDescriptor
0x1400be8dc  call    ?GetRpcEndpointQueryDescriptor@Rpc@ComputeService@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; ComputeService::Rpc::GetRpcEndpointQueryDescriptor(void)
0x1400be8e1  nop
0x1400be8e2  mov     r8, [rsp+220h+SecurityDescriptor]; SecurityDescriptor
0x1400be8e7  mov     edx, 0Ah; MaxCalls
0x1400be8ec  lea     rcx, ProtSeq; "ncalrpc"
0x1400be8f3  call    cs:__imp_RpcServerUseProtseqW
0x1400be8fa  nop     dword ptr [rax+rax+00h]
0x1400be8ff  mov     rcx, [rbp+128h]; this
0x1400be906  test    eax, eax
0x1400be908  jz      short loc_1400BE91F
0x1400be90a  mov     r9d, eax; char *
0x1400be90d  lea     r8, aOnecoreVmCompu_87; "onecore\\vm\\compute\\rpc\\server\\rpcs"...
0x1400be914  mov     edx, 9Dh; void *
0x1400be919  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400be91f  lea     rdx, aOBagBadAGaSyAG; "O:BAG:BAD:(A;;GA;;;SY)(A;;GA;;;BA)(A;;G"...
0x1400be926  lea     rcx, [rsp+220h+StringSecurityDescriptor]
0x1400be92b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1400be930  nop
0x1400be931  mov     dl, 1
0x1400be933  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_HcsRelaxRpcAccess@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_HcsRelaxRpcAccess@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HcsRelaxRpcAccess> `wil::Feature<__WilFeatureTraits_Feature_HcsRelaxRpcAccess>::GetImpl(void)'::`2'::impl
0x1400be93a  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_HcsRelaxRpcAccess@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HcsRelaxRpcAccess>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1400be93f  lea     rdx, aAGaS1580297061; "(A;;GA;;;S-1-5-80-2970612574-78537857-6"...
0x1400be946  lea     rcx, [rsp+220h+StringSecurityDescriptor]
0x1400be94b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1400be950  mov     ecx, 8; Size
0x1400be955  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400be95a  mov     rbx, rax
0x1400be95d  mov     qword ptr [rax], 0
0x1400be964  mov     [rsp+220h+var_1E0], rax
0x1400be969  mov     qword ptr [rax], 0
0x1400be970  mov     rdx, rax; Sid
0x1400be973  lea     rcx, aS1580297061257; "S-1-5-80-2970612574-78537857-698502321-"...
0x1400be97a  call    cs:__imp_ConvertStringSidToSidW
0x1400be981  nop     dword ptr [rax+rax+00h]
0x1400be986  mov     rcx, [rbp+128h]; this
0x1400be98d  test    eax, eax
0x1400be98f  jnz     short loc_1400BE9A3
0x1400be991  lea     r8, aOnecoreVmCompu_87; "onecore\\vm\\compute\\rpc\\server\\rpcs"...
0x1400be998  mov     edx, 0A9h; void *
0x1400be99d  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400be9a3  mov     [rsp+220h+var_1E0], 0
0x1400be9ac  mov     rdx, cs:qword_1403DE908
0x1400be9b3  mov     cs:qword_1403DE908, rbx
0x1400be9ba  test    rdx, rdx
0x1400be9bd  jz      short loc_1400BE9C5
0x1400be9bf  call    ??R?$default_delete@UAccessCheckContext@Rpc@ComputeService@@@std@@QEBAXPEAUAccessCheckContext@Rpc@ComputeService@@@Z; std::default_delete<ComputeService::Rpc::AccessCheckContext>::operator()(ComputeService::Rpc::AccessCheckContext *)
0x1400be9c4  nop
0x1400be9c5  lea     rcx, [rsp+220h+var_1E0]
0x1400be9ca  call    ??1?$unique_ptr@UAccessCheckContext@Rpc@ComputeService@@U?$default_delete@UAccessCheckContext@Rpc@ComputeService@@@std@@@std@@QEAA@XZ; std::unique_ptr<ComputeService::Rpc::AccessCheckContext>::~unique_ptr<ComputeService::Rpc::AccessCheckContext>(void)
0x1400be9cf  lea     rcx, [rsp+220h+StringSecurityDescriptor]
0x1400be9d4  cmp     [rsp+220h+var_1C0], 7
0x1400be9da  cmova   rcx, [rsp+220h+StringSecurityDescriptor]; StringSecurityDescriptor
0x1400be9e0  call    ?RegisterServerInterface@Rpc@ComputeService@@YAXPEBG@Z; ComputeService::Rpc::RegisterServerInterface(ushort const *)
0x1400be9e5  nop
0x1400be9e6  mov     [rsp+220h+BindingVector], 0
0x1400be9ef  lea     rcx, [rsp+220h+BindingVector]; BindingVector
0x1400be9f4  call    cs:__imp_RpcServerInqBindings
0x1400be9fb  nop     dword ptr [rax+rax+00h]
0x1400bea00  mov     rcx, [rbp+128h]; this
0x1400bea07  test    eax, eax
0x1400bea09  jz      short loc_1400BEA20
0x1400bea0b  mov     r9d, eax; char *
0x1400bea0e  lea     r8, aOnecoreVmCompu_87; "onecore\\vm\\compute\\rpc\\server\\rpcs"...
0x1400bea15  mov     edx, 0B2h; void *
0x1400bea1a  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400bea20  mov     qword ptr [rsp+220h+var_200], 1; unsigned int
0x1400bea29  mov     [rsp+220h+var_1F8], 0
0x1400bea32  xor     r9d, r9d; Annotation
0x1400bea35  xor     r8d, r8d; UuidVector
0x1400bea38  mov     rdx, [rsp+220h+BindingVector]; BindingVector
0x1400bea3d  lea     rcx, qword_1402C9E60; IfSpec
0x1400bea44  call    cs:__imp_RpcEpRegisterW
0x1400bea4b  nop     dword ptr [rax+rax+00h]
0x1400bea50  mov     rcx, [rbp+128h]; this
0x1400bea57  test    eax, eax
0x1400bea59  jz      short loc_1400BEA70
0x1400bea5b  mov     r9d, eax; char *
0x1400bea5e  lea     r8, aOnecoreVmCompu_87; "onecore\\vm\\compute\\rpc\\server\\rpcs"...
0x1400bea65  mov     edx, 0BAh; void *
0x1400bea6a  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400bea70  xor     edx, edx; Val
0x1400bea72  mov     r8d, 198h; Size
0x1400bea78  lea     rcx, [rsp+220h+WSAData]; void *
0x1400bea7d  call    memset_0
0x1400bea82  mov     ecx, 202h; wVersionRequested
0x1400bea87  lea     rdx, [rsp+220h+WSAData]; lpWSAData
0x1400bea8c  call    cs:__imp_WSAStartup
0x1400bea93  nop     dword ptr [rax+rax+00h]
0x1400bea98  mov     rcx, [rbp+128h]; this
0x1400bea9f  test    eax, eax
0x1400beaa1  jz      short loc_1400BEAB8
0x1400beaa3  mov     r9d, eax; char *
0x1400beaa6  lea     r8, aOnecoreVmCompu_87; "onecore\\vm\\compute\\rpc\\server\\rpcs"...
0x1400beaad  mov     edx, 0BEh; void *
0x1400beab2  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400beab8  lea     rcx, [rsp+220h+BindingVector]
0x1400beabd  call    ??1?$unique_storage@U?$resource_policy@PEAU_RPC_BINDING_VECTOR@@P6AXPEAU1@@Z$1?WpRpcBindingVectorFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR *),&wil::details::WpRpcBindingVectorFree(_RPC_BINDING_VECTOR *),wistd::integral_constant<unsigned __int64,0>,_RPC_BINDING_VECTOR *,_RPC_BINDING_VECTOR *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR *),&wil::details::WpRpcBindingVectorFree(_RPC_BINDING_VECTOR *),wistd::integral_constant<unsigned __int64,0>,_RPC_BINDING_VECTOR *,_RPC_BINDING_VECTOR *,0,std::nullptr_t>>(void)
0x1400beac2  nop
0x1400beac3  lea     rcx, [rsp+220h+StringSecurityDescriptor]; this
0x1400beac8  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400beacd  nop
0x1400beace  lea     rcx, [rsp+220h+SecurityDescriptor]
0x1400bead3  call    ??1?$VmLocalPtr@U_TOKEN_PRIMARY_GROUP@@@Vml@@QEAA@XZ; Vml::VmLocalPtr<_TOKEN_PRIMARY_GROUP>::~VmLocalPtr<_TOKEN_PRIMARY_GROUP>(void)
0x1400bead8  mov     rcx, [rbp+120h+var_10]
0x1400beadf  xor     rcx, rsp; StackCookie
0x1400beae2  call    __security_check_cookie
0x1400beae7  mov     rbx, [rsp+220h+arg_0]
0x1400beaef  add     rsp, 220h
0x1400beaf6  pop     rbp
0x1400beaf7  retn
```
