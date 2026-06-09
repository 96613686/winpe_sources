# ComputeService::Client::Details::MakeBinding(ushort const *)

- ea: `0x18003a43c`
- end: `0x18003a572`
- name: `?MakeBinding@Details@Client@ComputeService@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z`
- size: `310`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE *Binding)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18003a0f4`

## callees

- `0x180002f50`
- `0x180022d10`
- `0x18003a43c`

## import_xrefs

- `RPCRT4!RpcBindingBind` at `0x18003a50b`
- `RPCRT4!RpcBindingBind` at `0x18003a50b`
- `RPCRT4!RpcBindingCreateW` at `0x18003a4ef`
- `RPCRT4!RpcBindingCreateW` at `0x18003a4ef`

## string_xrefs

- `0x18003a547`: `onecore\vm\compute\dll\lib\core\rpcclient.cpp`
- `0x18003a560`: `onecore\vm\compute\dll\lib\core\rpcclient.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
RPC_BINDING_HANDLE *__fastcall ComputeService::Client::Details::MakeBinding(RPC_BINDING_HANDLE *Binding)
{
  unsigned int v2; // eax
  unsigned int v3; // eax
  __int64 v5; // [rsp+30h] [rbp-49h] BYREF
  int v6; // [rsp+38h] [rbp-41h]
  __int64 v7; // [rsp+3Ch] [rbp-3Dh]
  __int64 v8; // [rsp+44h] [rbp-35h]
  int v9; // [rsp+4Ch] [rbp-2Dh]
  __int64 v10; // [rsp+50h] [rbp-29h]
  int v11; // [rsp+58h] [rbp-21h]
  __int64 v12; // [rsp+5Ch] [rbp-1Dh]
  int v13; // [rsp+64h] [rbp-15h]
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+68h] [rbp-11h] BYREF
  RPC_BINDING_HANDLE_TEMPLATE_V1_W Template; // [rsp+90h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  memset(&Template.ProtocolSequence + 1, 0, 44);
  *(_QWORD *)&Security.Version = 1;
  Security.AuthIdentity = 0;
  v8 = 0;
  v9 = 0;
  v12 = 0;
  v13 = 0;
  *(_QWORD *)&Template.Version = 1;
  Template.ProtocolSequence = 3;
  Security.ServerPrincName = 0;
  Security.AuthnLevel = 5;
  Security.AuthnSvc = 10;
  Security.SecurityQos = (RPC_SECURITY_QOS *)&v5;
  v5 = 5;
  v6 = 1;
  v7 = 3;
  v10 = 0;
  v11 = 0;
  *Binding = 0;
  v2 = RpcBindingCreateW(&Template, &Security, 0, Binding);
  if ( v2 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x45,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\core\\rpcclient.cpp",
      (const char *)v2,
      1u);
  v3 = RpcBindingBind(0, *Binding, qword_18008BB10);
  if ( v3 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x47,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\core\\rpcclient.cpp",
      (const char *)v3,
      1u);
  return Binding;
}

```

## disassembly

```asm
0x18003a43c  mov     [rsp-8+arg_8], rbx
0x18003a441  mov     [rsp-8+arg_10], rdi
0x18003a446  push    rbp
0x18003a447  lea     rbp, [rsp-57h]
0x18003a44c  sub     rsp, 0D0h
0x18003a453  mov     rax, cs:__security_cookie
0x18003a45a  xor     rax, rsp
0x18003a45d  mov     [rbp+57h+var_8], rax
0x18003a461  mov     rbx, rcx
0x18003a464  mov     [rbp+57h+var_A8], rcx
0x18003a468  xor     edi, edi
0x18003a46a  mov     [rbp+57h+var_B0], edi
0x18003a46d  xorps   xmm0, xmm0
0x18003a470  xor     eax, eax
0x18003a472  movups  xmmword ptr [rbp+57h+Template.Version], xmm0
0x18003a476  movups  xmmword ptr [rbp+57h+Template.NetworkAddress], xmm0
0x18003a47a  movups  xmmword ptr [rbp+57h+Template.u1], xmm0
0x18003a47e  mov     qword ptr [rbp+57h+Template.ObjectUuid.Data4], rax
0x18003a482  mov     qword ptr [rbp+57h+Security.Version], 1
0x18003a48a  mov     [rbp+57h+Security.AuthIdentity], rdi
0x18003a48e  mov     [rbp+57h+var_8C], rdi
0x18003a492  mov     [rbp+57h+var_84], edi
0x18003a495  mov     [rbp+57h+var_74], rdi
0x18003a499  mov     [rbp+57h+var_6C], edi
0x18003a49c  lea     r8d, [rdi+1]
0x18003a4a0  mov     qword ptr [rbp+57h+Template.Version], r8
0x18003a4a4  lea     edx, [rdi+3]
0x18003a4a7  mov     [rbp+57h+Template.ProtocolSequence], edx
0x18003a4aa  mov     [rbp+57h+Template.StringEndpoint], rdi
0x18003a4ae  mov     [rbp+57h+Security.ServerPrincName], rdi
0x18003a4b2  lea     ecx, [rdi+5]
0x18003a4b5  mov     [rbp+57h+Security.AuthnLevel], ecx
0x18003a4b8  mov     [rbp+57h+Security.AuthnSvc], 0Ah
0x18003a4bf  lea     rax, [rbp+57h+var_A0]
0x18003a4c3  mov     [rbp+57h+Security.SecurityQos], rax
0x18003a4c7  mov     [rbp+57h+var_A0], rcx
0x18003a4cb  mov     [rbp+57h+var_98], r8d
0x18003a4cf  mov     [rbp+57h+var_94], rdx
0x18003a4d3  mov     [rbp+57h+var_80], rdi
0x18003a4d7  mov     [rbp+57h+var_78], edi
0x18003a4da  mov     [rbp+57h+var_B0], r8d
0x18003a4de  mov     [rbx], rdi
0x18003a4e1  mov     r9, rbx; Binding
0x18003a4e4  xor     r8d, r8d; Options
0x18003a4e7  lea     rdx, [rbp+57h+Security]; Security
0x18003a4eb  lea     rcx, [rbp+57h+Template]; Template
0x18003a4ef  call    cs:__imp_RpcBindingCreateW
0x18003a4f6  nop     dword ptr [rax+rax+00h]
0x18003a4fb  test    eax, eax
0x18003a4fd  jnz     short loc_18003A559
0x18003a4ff  lea     r8, qword_18008BB10; IfSpec
0x18003a506  mov     rdx, [rbx]; Binding
0x18003a509  xor     ecx, ecx; pAsync
0x18003a50b  call    cs:__imp_RpcBindingBind
0x18003a512  nop     dword ptr [rax+rax+00h]
0x18003a517  test    eax, eax
0x18003a519  jnz     short loc_18003A540
0x18003a51b  mov     rax, rbx
0x18003a51e  mov     rcx, [rbp+57h+var_8]
0x18003a522  xor     rcx, rsp; StackCookie
0x18003a525  call    __security_check_cookie
0x18003a52a  lea     r11, [rsp+0D0h+var_s0]
0x18003a532  mov     rbx, [r11+18h]
0x18003a536  mov     rdi, [r11+20h]
0x18003a53a  mov     rsp, r11
0x18003a53d  pop     rbp
0x18003a53e  retn
0x18003a540  mov     rcx, [rbp+5Fh]; this
0x18003a544  mov     r9d, eax; char *
0x18003a547  lea     r8, aOnecoreVmCompu_2; "onecore\\vm\\compute\\dll\\lib\\core\\r"...
0x18003a54e  mov     edx, 47h ; 'G'; void *
0x18003a553  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18003a559  mov     rcx, [rbp+5Fh]; this
0x18003a55d  mov     r9d, eax; char *
0x18003a560  lea     r8, aOnecoreVmCompu_2; "onecore\\vm\\compute\\dll\\lib\\core\\r"...
0x18003a567  mov     edx, 45h ; 'E'; void *
0x18003a56c  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
