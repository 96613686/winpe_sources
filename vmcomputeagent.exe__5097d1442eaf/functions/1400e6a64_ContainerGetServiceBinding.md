# ContainerGetServiceBinding

- ea: `0x1400e6a64`
- end: `0x1400e6b8f`
- name: `ContainerGetServiceBinding`
- size: `299`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400a4860`
- `0x1400aa3b0`
- `0x1400d5d1c`

## callees

- `0x140005360`
- `0x140008760`
- `0x1400341ac`
- `0x14004346c`
- `0x14004fc5c`
- `0x1400e6a64`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x1400e6b12`
- `RPCRT4!RpcStringFreeW` at `0x1400e6b12`
- `RPCRT4!RpcStringBindingComposeW` at `0x1400e6ae0`
- `RPCRT4!RpcStringBindingComposeW` at `0x1400e6ae0`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1400e6b05`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1400e6b05`

## string_xrefs

- `0x1400e6b62`: `onecore\vm\compute\service\cexec\client\cexeclib.cpp`
- `0x1400e6b7c`: `onecore\vm\compute\service\cexec\client\cexeclib.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ContainerGetServiceBinding(__int64 a1, _QWORD *a2)
{
  unsigned __int16 *v3; // r9
  unsigned int v4; // eax
  RPC_BINDING_HANDLE *v5; // rax
  unsigned int v6; // ebx
  __int64 v7; // rax
  const char *v8; // r9
  __int64 result; // rax
  unsigned int Options; // [rsp+20h] [rbp-58h]
  RPC_WSTR String; // [rsp+30h] [rbp-48h] BYREF
  __int64 v12; // [rsp+38h] [rbp-40h] BYREF
  RPC_WSTR Endpoint[4]; // [rsp+40h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  try
  {
    Vml::FormatString(Endpoint, (wchar_t *)L"%s\\RPC Control\\%s");
    String = 0;
    v3 = (unsigned __int16 *)Endpoint;
    if ( Endpoint[3] > (RPC_WSTR)7 )
      v3 = Endpoint[0];
    v4 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, v3, 0, &String);
    if ( v4 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x81,
        (unsigned int)"onecore\\vm\\compute\\service\\cexec\\client\\cexeclib.cpp",
        (const char *)v4,
        Options);
    v12 = 0;
    v5 = (RPC_BINDING_HANDLE *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::operator&(&v12);
    v6 = RpcBindingFromStringBindingW(String, v5);
    RpcStringFreeW(&String);
    if ( v6 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x89,
        (unsigned int)"onecore\\vm\\compute\\service\\cexec\\client\\cexeclib.cpp",
        (const char *)v6,
        Options);
    v7 = v12;
    v12 = 0;
    *a2 = v7;
    std::wstring::~wstring(Endpoint);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x8F,
                           (unsigned int)"onecore\\vm\\compute\\service\\cexec\\client\\cexeclib.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x1400e6a64  mov     [rsp+arg_10], rbx
0x1400e6a69  push    rdi
0x1400e6a6a  sub     rsp, 70h
0x1400e6a6e  mov     rax, cs:__security_cookie
0x1400e6a75  xor     rax, rsp
0x1400e6a78  mov     [rsp+78h+var_18], rax
0x1400e6a7d  mov     rdi, rdx
0x1400e6a80  lea     r8, szPassword
0x1400e6a87  test    rcx, rcx
0x1400e6a8a  cmovnz  r8, rcx
0x1400e6a8e  lea     r9, aCexecsvc; "cexecsvc"
0x1400e6a95  lea     rdx, aSRpcControlS; "%s\\RPC Control\\%s"
0x1400e6a9c  lea     rcx, [rsp+78h+Endpoint]; Src
0x1400e6aa1  call    ?FormatString@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; Vml::FormatString(ushort const *,...)
0x1400e6aa6  nop
0x1400e6aa7  mov     [rsp+78h+String], 0
0x1400e6ab0  lea     r9, [rsp+78h+Endpoint]
0x1400e6ab5  cmp     [rsp+78h+var_20], 7
0x1400e6abb  cmova   r9, [rsp+78h+Endpoint]; Endpoint
0x1400e6ac1  lea     rax, [rsp+78h+String]
0x1400e6ac6  mov     [rsp+78h+StringBinding], rax; StringBinding
0x1400e6acb  mov     [rsp+78h+Options], 0; unsigned int
0x1400e6ad4  xor     r8d, r8d; NetworkAddr
0x1400e6ad7  lea     rdx, ProtSeq; "ncalrpc"
0x1400e6ade  xor     ecx, ecx; ObjUuid
0x1400e6ae0  call    cs:__imp_RpcStringBindingComposeW
0x1400e6ae6  test    eax, eax
0x1400e6ae8  jnz     short loc_1400E6B5A
0x1400e6aea  mov     [rsp+78h+var_40], 0
0x1400e6af3  lea     rcx, [rsp+78h+var_40]
0x1400e6af8  call    ??I?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::operator&(void)
0x1400e6afd  mov     rdx, rax; Binding
0x1400e6b00  mov     rcx, [rsp+78h+String]; StringBinding
0x1400e6b05  call    cs:__imp_RpcBindingFromStringBindingW
0x1400e6b0b  mov     ebx, eax
0x1400e6b0d  lea     rcx, [rsp+78h+String]; String
0x1400e6b12  call    cs:__imp_RpcStringFreeW
0x1400e6b18  test    ebx, ebx
0x1400e6b1a  jnz     short loc_1400E6B74
0x1400e6b1c  mov     rax, [rsp+78h+var_40]
0x1400e6b21  mov     [rsp+78h+var_40], 0
0x1400e6b2a  mov     [rdi], rax
0x1400e6b2d  lea     rcx, [rsp+78h+Endpoint]; void *
0x1400e6b32  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400e6b37  xor     eax, eax
0x1400e6b39  jmp     short loc_1400E6B3F
0x1400e6b3b  mov     eax, dword ptr [rsp+78h+String]
0x1400e6b3f  mov     rcx, [rsp+78h+var_18]
0x1400e6b44  xor     rcx, rsp; StackCookie
0x1400e6b47  call    __security_check_cookie
0x1400e6b4c  mov     rbx, [rsp+78h+arg_10]
0x1400e6b54  add     rsp, 70h
0x1400e6b58  pop     rdi
0x1400e6b59  retn
0x1400e6b5a  mov     rcx, [rsp+78h]; this
0x1400e6b5f  mov     r9d, eax; char *
0x1400e6b62  lea     r8, aOnecoreVmCompu_9; "onecore\\vm\\compute\\service\\cexec\\c"...
0x1400e6b69  mov     edx, 81h; void *
0x1400e6b6e  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400e6b74  mov     rcx, [rsp+78h]; this
0x1400e6b79  mov     r9d, ebx; char *
0x1400e6b7c  lea     r8, aOnecoreVmCompu_9; "onecore\\vm\\compute\\service\\cexec\\c"...
0x1400e6b83  mov     edx, 89h; void *
0x1400e6b88  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
