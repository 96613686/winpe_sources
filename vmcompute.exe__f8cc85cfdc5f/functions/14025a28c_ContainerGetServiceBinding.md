# ContainerGetServiceBinding

- ea: `0x14025a28c`
- end: `0x14025a3d6`
- name: `ContainerGetServiceBinding`
- size: `330`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140087548`

## callees

- `0x140017040`
- `0x140018d70`
- `0x1400877b4`
- `0x1400c4154`
- `0x1401332f0`
- `0x140177ddc`
- `0x14025a28c`

## import_xrefs

- `RPCRT4!RpcStringBindingComposeW` at `0x14025a308`
- `RPCRT4!RpcStringBindingComposeW` at `0x14025a308`
- `RPCRT4!RpcStringFreeW` at `0x14025a363`
- `RPCRT4!RpcStringFreeW` at `0x14025a363`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x14025a350`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x14025a350`

## string_xrefs

- `0x14025a320`: `onecore\vm\compute\service\cexec\client\cexeclib.cpp`
- `0x14025a37b`: `onecore\vm\compute\service\cexec\client\cexeclib.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall ContainerGetServiceBinding(const WCHAR *a1, _QWORD *a2)
{
  const WCHAR *v3; // r8
  unsigned __int16 *v4; // r9
  unsigned int v5; // eax
  unsigned int v6; // ebx
  RPC_BINDING_HANDLE v7; // rax
  unsigned int Options; // [rsp+20h] [rbp-58h]
  RPC_WSTR String; // [rsp+30h] [rbp-48h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+38h] [rbp-40h] BYREF
  RPC_WSTR Endpoint[4]; // [rsp+40h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v3 = &szPassword;
  if ( a1 )
    v3 = a1;
  Vml::FormatString(Endpoint, L"%s\\RPC Control\\%s", v3, L"cexecsvc");
  String = 0;
  v4 = (unsigned __int16 *)Endpoint;
  if ( Endpoint[3] > (RPC_WSTR)7 )
    v4 = Endpoint[0];
  v5 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, v4, 0, &String);
  if ( v5 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x81,
      (unsigned int)"onecore\\vm\\compute\\service\\cexec\\client\\cexeclib.cpp",
      (const char *)v5,
      Options);
  Binding = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &Binding,
    0);
  v6 = RpcBindingFromStringBindingW(String, &Binding);
  RpcStringFreeW(&String);
  if ( v6 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x89,
      (unsigned int)"onecore\\vm\\compute\\service\\cexec\\client\\cexeclib.cpp",
      (const char *)v6,
      Options);
  v7 = Binding;
  Binding = 0;
  *a2 = v7;
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Binding);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)Endpoint);
  return 0;
}

```

## disassembly

```asm
0x14025a28c  mov     [rsp+arg_10], rbx
0x14025a291  push    rdi
0x14025a292  sub     rsp, 70h
0x14025a296  mov     rax, cs:__security_cookie
0x14025a29d  xor     rax, rsp
0x14025a2a0  mov     [rsp+78h+var_18], rax
0x14025a2a5  mov     rdi, rdx
0x14025a2a8  lea     r8, szPassword
0x14025a2af  test    rcx, rcx
0x14025a2b2  cmovnz  r8, rcx
0x14025a2b6  lea     r9, aCexecsvc; "cexecsvc"
0x14025a2bd  lea     rdx, aSRpcControlS; "%s\\RPC Control\\%s"
0x14025a2c4  lea     rcx, [rsp+78h+Endpoint]
0x14025a2c9  call    ?FormatString@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; Vml::FormatString(ushort const *,...)
0x14025a2ce  nop
0x14025a2cf  mov     [rsp+78h+String], 0
0x14025a2d8  lea     r9, [rsp+78h+Endpoint]
0x14025a2dd  cmp     [rsp+78h+var_20], 7
0x14025a2e3  cmova   r9, [rsp+78h+Endpoint]; Endpoint
0x14025a2e9  lea     rax, [rsp+78h+String]
0x14025a2ee  mov     [rsp+78h+StringBinding], rax; StringBinding
0x14025a2f3  mov     [rsp+78h+Options], 0; unsigned int
0x14025a2fc  xor     r8d, r8d; NetworkAddr
0x14025a2ff  lea     rdx, ProtSeq; "ncalrpc"
0x14025a306  xor     ecx, ecx; ObjUuid
0x14025a308  call    cs:__imp_RpcStringBindingComposeW
0x14025a30f  nop     dword ptr [rax+rax+00h]
0x14025a314  test    eax, eax
0x14025a316  jz      short loc_14025A331
0x14025a318  mov     rcx, [rsp+78h]; this
0x14025a31d  mov     r9d, eax; char *
0x14025a320  lea     r8, aOnecoreVmCompu_22; "onecore\\vm\\compute\\service\\cexec\\c"...
0x14025a327  mov     edx, 81h; void *
0x14025a32c  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x14025a331  mov     [rsp+78h+Binding], 0
0x14025a33a  xor     edx, edx
0x14025a33c  lea     rcx, [rsp+78h+Binding]
0x14025a341  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x14025a346  lea     rdx, [rsp+78h+Binding]; Binding
0x14025a34b  mov     rcx, [rsp+78h+String]; StringBinding
0x14025a350  call    cs:__imp_RpcBindingFromStringBindingW
0x14025a357  nop     dword ptr [rax+rax+00h]
0x14025a35c  mov     ebx, eax
0x14025a35e  lea     rcx, [rsp+78h+String]; String
0x14025a363  call    cs:__imp_RpcStringFreeW
0x14025a36a  nop     dword ptr [rax+rax+00h]
0x14025a36f  test    ebx, ebx
0x14025a371  jz      short loc_14025A38C
0x14025a373  mov     rcx, [rsp+78h]; this
0x14025a378  mov     r9d, ebx; char *
0x14025a37b  lea     r8, aOnecoreVmCompu_22; "onecore\\vm\\compute\\service\\cexec\\c"...
0x14025a382  mov     edx, 89h; void *
0x14025a387  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x14025a38c  mov     rax, [rsp+78h+Binding]
0x14025a391  mov     [rsp+78h+Binding], 0
0x14025a39a  mov     [rdi], rax
0x14025a39d  lea     rcx, [rsp+78h+Binding]
0x14025a3a2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14025a3a7  nop
0x14025a3a8  lea     rcx, [rsp+78h+Endpoint]; this
0x14025a3ad  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x14025a3b2  xor     eax, eax
0x14025a3b4  jmp     short loc_14025A3BA
0x14025a3b6  mov     eax, dword ptr [rsp+78h+Binding]
0x14025a3ba  mov     rcx, [rsp+78h+var_18]
0x14025a3bf  xor     rcx, rsp; StackCookie
0x14025a3c2  call    __security_check_cookie
0x14025a3c7  mov     rbx, [rsp+78h+arg_10]
0x14025a3cf  add     rsp, 70h
0x14025a3d3  pop     rdi
0x14025a3d4  retn
```
