# STRING_HANDLE_bind

- ea: `0x1800ecb40`
- end: `0x1800ecd3f`
- name: `STRING_HANDLE_bind`
- size: `511`
- prototype: `__int64 __fastcall(RPC_WSTR NetworkAddr)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000a994`
- `0x1800c6774`
- `0x1800ecb40`
- `0x180106340`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x1800ecd04`
- `RPCRT4!RpcStringFreeW` at `0x1800ecd18`
- `RPCRT4!RpcStringFreeW` at `0x1800ecd04`
- `RPCRT4!RpcStringFreeW` at `0x1800ecd18`
- `RPCRT4!RpcBindingSetAuthInfoW` at `0x1800eccd4`
- `RPCRT4!RpcBindingSetAuthInfoW` at `0x1800eccd4`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800ecbed`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800ecbed`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800ecba5`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800ecba5`
- `RPCRT4!RpcMgmtInqServerPrincNameW` at `0x1800ecc7d`
- `RPCRT4!RpcMgmtInqServerPrincNameW` at `0x1800ecc7d`
- `RPCRT4!RpcBindingSetOption` at `0x1800ecc3d`
- `RPCRT4!RpcBindingSetOption` at `0x1800ecc3d`

## string_xrefs

- `0x1800ecb86`: `Security=Impersonation Dynamic False`
- `0x1800ecbba`: `onecore\net\netprofiles\service\src\l2manager\clientlib\rpcbinding.cpp`
- `0x1800ecc02`: `onecore\net\netprofiles\service\src\l2manager\clientlib\rpcbinding.cpp`
- `0x1800ecc52`: `onecore\net\netprofiles\service\src\l2manager\clientlib\rpcbinding.cpp`
- `0x1800ecc92`: `onecore\net\netprofiles\service\src\l2manager\clientlib\rpcbinding.cpp`
- `0x1800ecce9`: `onecore\net\netprofiles\service\src\l2manager\clientlib\rpcbinding.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
RPC_BINDING_HANDLE __fastcall STRING_HANDLE_bind(RPC_WSTR NetworkAddr, __int64 a2, __int64 a3)
{
  unsigned int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // eax
  RPC_BINDING_HANDLE v8; // rbx
  unsigned int Options; // [rsp+20h] [rbp-78h]
  unsigned int Optionsa; // [rsp+20h] [rbp-78h]
  RPC_BINDING_HANDLE Binding; // [rsp+68h] [rbp-30h] BYREF
  RPC_WSTR String; // [rsp+70h] [rbp-28h] BYREF
  RPC_WSTR ServerPrincName; // [rsp+78h] [rbp-20h] BYREF
  unsigned __int16 *v15; // [rsp+80h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v15 = NetworkAddr;
  if ( NetworkAddr )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(NetworkAddr, a2, a3);
    NetworkAddr = v15;
  }
  String = 0;
  v3 = RpcStringBindingComposeW(
         0,
         (RPC_WSTR)L"ncalrpc",
         NetworkAddr,
         (RPC_WSTR)L"nlaplg",
         (RPC_WSTR)L"Security=Impersonation Dynamic False",
         &String);
  if ( v3 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x15,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\l2manager\\clientlib\\rpcbinding.cpp",
      (const char *)v3,
      Options);
  Binding = 0;
  v4 = RpcBindingFromStringBindingW(String, &Binding);
  if ( v4 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x1F,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\l2manager\\clientlib\\rpcbinding.cpp",
      (const char *)v4,
      Options);
  v5 = RpcBindingSetOption(Binding, 0xBu, 1u);
  if ( v5 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x25,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\l2manager\\clientlib\\rpcbinding.cpp",
      (const char *)v5,
      Options);
  ServerPrincName = 0;
  v6 = RpcMgmtInqServerPrincNameW(Binding, 0xAu, &ServerPrincName);
  if ( v6 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x29,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\l2manager\\clientlib\\rpcbinding.cpp",
      (const char *)v6,
      Options);
  v7 = RpcBindingSetAuthInfoW(Binding, ServerPrincName, 6u, 0xAu, 0, 0);
  if ( v7 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x2F,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\l2manager\\clientlib\\rpcbinding.cpp",
      (const char *)v7,
      Optionsa);
  v8 = Binding;
  RpcStringFreeW(&ServerPrincName);
  if ( String )
    RpcStringFreeW(&String);
  return v8;
}

```

## disassembly

```asm
0x1800ecb40  mov     r11, rsp
0x1800ecb43  push    rbx
0x1800ecb44  sub     rsp, 90h
0x1800ecb4b  mov     rax, cs:__security_cookie
0x1800ecb52  xor     rax, rsp
0x1800ecb55  mov     [rsp+98h+var_10], rax
0x1800ecb5d  mov     [r11-18h], rcx
0x1800ecb61  test    rcx, rcx
0x1800ecb64  jz      short loc_1800ECB73
0x1800ecb66  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "!serverAddress")
0x1800ecb6b  mov     rcx, [rsp+98h+var_18]
0x1800ecb73  mov     [rsp+98h+String], 0
0x1800ecb7c  lea     rax, [rsp+98h+String]
0x1800ecb81  mov     [rsp+98h+StringBinding], rax; StringBinding
0x1800ecb86  lea     rax, Options; "Security=Impersonation Dynamic False"
0x1800ecb8d  mov     [rsp+98h+Options], rax; unsigned int
0x1800ecb92  lea     r9, Endpoint; "nlaplg"
0x1800ecb99  mov     r8, rcx; NetworkAddr
0x1800ecb9c  lea     rdx, aNcalrpc; "ncalrpc"
0x1800ecba3  xor     ecx, ecx; ObjUuid
0x1800ecba5  call    cs:__imp_RpcStringBindingComposeW
0x1800ecbab  mov     rcx, [rsp+98h]; this
0x1800ecbb3  test    eax, eax
0x1800ecbb5  jz      short loc_1800ECBCB
0x1800ecbb7  mov     r9d, eax; char *
0x1800ecbba  lea     r8, aOnecoreNetNetp_0; "onecore\\net\\netprofiles\\service\\src"...
0x1800ecbc1  mov     edx, 15h; void *
0x1800ecbc6  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800ecbcb  lea     rax, [rsp+98h+String]
0x1800ecbd0  mov     [rsp+98h+var_68], rax
0x1800ecbd5  mov     [rsp+98h+var_60], 1
0x1800ecbda  mov     [rsp+98h+Binding], 0
0x1800ecbe3  lea     rdx, [rsp+98h+Binding]; Binding
0x1800ecbe8  mov     rcx, [rsp+98h+String]; StringBinding
0x1800ecbed  call    cs:__imp_RpcBindingFromStringBindingW
0x1800ecbf3  mov     rcx, [rsp+98h]; this
0x1800ecbfb  test    eax, eax
0x1800ecbfd  jz      short loc_1800ECC13
0x1800ecbff  mov     r9d, eax; char *
0x1800ecc02  lea     r8, aOnecoreNetNetp_0; "onecore\\net\\netprofiles\\service\\src"...
0x1800ecc09  mov     edx, 1Fh; void *
0x1800ecc0e  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800ecc13  lea     rax, [rsp+98h+var_18]
0x1800ecc1b  mov     [rsp+98h+var_48], rax
0x1800ecc20  lea     rax, [rsp+98h+Binding]
0x1800ecc25  mov     [rsp+98h+var_40], rax
0x1800ecc2a  mov     [rsp+98h+var_38], 1
0x1800ecc2f  mov     edx, 0Bh; option
0x1800ecc34  lea     r8d, [rdx-0Ah]; optionValue
0x1800ecc38  mov     rcx, [rsp+98h+Binding]; hBinding
0x1800ecc3d  call    cs:__imp_RpcBindingSetOption
0x1800ecc43  mov     rcx, [rsp+98h]; this
0x1800ecc4b  test    eax, eax
0x1800ecc4d  jz      short loc_1800ECC63
0x1800ecc4f  mov     r9d, eax; char *
0x1800ecc52  lea     r8, aOnecoreNetNetp_0; "onecore\\net\\netprofiles\\service\\src"...
0x1800ecc59  mov     edx, 25h ; '%'; void *
0x1800ecc5e  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800ecc63  mov     [rsp+98h+ServerPrincName], 0
0x1800ecc6c  lea     r8, [rsp+98h+ServerPrincName]; ServerPrincName
0x1800ecc71  mov     ebx, 0Ah
0x1800ecc76  mov     edx, ebx; AuthnSvc
0x1800ecc78  mov     rcx, [rsp+98h+Binding]; Binding
0x1800ecc7d  call    cs:__imp_RpcMgmtInqServerPrincNameW
0x1800ecc83  mov     rcx, [rsp+98h]; this
0x1800ecc8b  test    eax, eax
0x1800ecc8d  jz      short loc_1800ECCA1
0x1800ecc8f  mov     r9d, eax; char *
0x1800ecc92  lea     r8, aOnecoreNetNetp_0; "onecore\\net\\netprofiles\\service\\src"...
0x1800ecc99  lea     edx, [rbx+1Fh]; void *
0x1800ecc9c  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800ecca1  lea     rax, [rsp+98h+ServerPrincName]
0x1800ecca6  mov     [rsp+98h+var_58], rax
0x1800eccab  mov     [rsp+98h+var_50], 1
0x1800eccb0  mov     dword ptr [rsp+98h+StringBinding], 0; AuthzSvc
0x1800eccb8  mov     [rsp+98h+Options], 0; unsigned int
0x1800eccc1  mov     r9d, ebx; AuthnSvc
0x1800eccc4  mov     r8d, 6; AuthnLevel
0x1800eccca  mov     rdx, [rsp+98h+ServerPrincName]; ServerPrincName
0x1800ecccf  mov     rcx, [rsp+98h+Binding]; Binding
0x1800eccd4  call    cs:__imp_RpcBindingSetAuthInfoW
0x1800eccda  mov     rcx, [rsp+98h]; this
0x1800ecce2  test    eax, eax
0x1800ecce4  jz      short loc_1800ECCFA
0x1800ecce6  mov     r9d, eax; char *
0x1800ecce9  lea     r8, aOnecoreNetNetp_0; "onecore\\net\\netprofiles\\service\\src"...
0x1800eccf0  mov     edx, 2Fh ; '/'; void *
0x1800eccf5  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800eccfa  mov     rbx, [rsp+98h+Binding]
0x1800eccff  lea     rcx, [rsp+98h+ServerPrincName]; String
0x1800ecd04  call    cs:__imp_RpcStringFreeW
0x1800ecd0a  nop
0x1800ecd0b  cmp     [rsp+98h+String], 0
0x1800ecd11  jz      short loc_1800ECD1E
0x1800ecd13  lea     rcx, [rsp+98h+String]; String
0x1800ecd18  call    cs:__imp_RpcStringFreeW
0x1800ecd1e  mov     rax, rbx
0x1800ecd21  jmp     short loc_1800ECD25
0x1800ecd23  xor     eax, eax
0x1800ecd25  mov     rcx, [rsp+98h+var_10]
0x1800ecd2d  xor     rcx, rsp; StackCookie
0x1800ecd30  call    __security_check_cookie
0x1800ecd35  add     rsp, 90h
0x1800ecd3c  pop     rbx
0x1800ecd3d  retn
```
