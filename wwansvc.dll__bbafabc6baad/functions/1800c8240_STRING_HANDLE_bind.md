# STRING_HANDLE_bind

- ea: `0x1800c8240`
- end: `0x1800c8457`
- name: `STRING_HANDLE_bind`
- size: `535`
- prototype: `__int64 __fastcall(RPC_WSTR NetworkAddr)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800085d0`
- `0x180059c18`
- `0x1800c5d28`
- `0x1800c8240`

## import_xrefs

- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800c82dd`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800c82dd`
- `RPCRT4!RpcStringFreeW` at `0x1800c83b6`
- `RPCRT4!RpcStringFreeW` at `0x1800c83ca`
- `RPCRT4!RpcStringFreeW` at `0x1800c83b6`
- `RPCRT4!RpcStringFreeW` at `0x1800c83ca`
- `RPCRT4!RpcBindingSetOption` at `0x1800c831d`
- `RPCRT4!RpcBindingSetOption` at `0x1800c831d`
- `RPCRT4!RpcMgmtInqServerPrincNameW` at `0x1800c834d`
- `RPCRT4!RpcMgmtInqServerPrincNameW` at `0x1800c834d`
- `RPCRT4!RpcBindingSetAuthInfoW` at `0x1800c8396`
- `RPCRT4!RpcBindingSetAuthInfoW` at `0x1800c8396`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800c82a5`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800c82a5`

## string_xrefs

- `0x1800c8286`: `Security=Impersonation Dynamic False`
- `0x1800c83f3`: `onecore\net\netprofiles\service\src\l2manager\clientlib\rpcbinding.cpp`
- `0x1800c8408`: `onecore\net\netprofiles\service\src\l2manager\clientlib\rpcbinding.cpp`
- `0x1800c841d`: `onecore\net\netprofiles\service\src\l2manager\clientlib\rpcbinding.cpp`
- `0x1800c8431`: `onecore\net\netprofiles\service\src\l2manager\clientlib\rpcbinding.cpp`
- `0x1800c8444`: `onecore\net\netprofiles\service\src\l2manager\clientlib\rpcbinding.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
RPC_BINDING_HANDLE __fastcall STRING_HANDLE_bind(RPC_WSTR NetworkAddr)
{
  unsigned int v1; // eax
  unsigned int v2; // eax
  unsigned int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // eax
  RPC_BINDING_HANDLE v6; // rbx
  const char *v7; // r9
  RPC_BINDING_HANDLE result; // rax
  unsigned int Options; // [rsp+20h] [rbp-78h]
  unsigned int Optionsa; // [rsp+20h] [rbp-78h]
  RPC_BINDING_HANDLE Binding; // [rsp+68h] [rbp-30h] BYREF
  RPC_WSTR String; // [rsp+70h] [rbp-28h] BYREF
  RPC_WSTR ServerPrincName; // [rsp+78h] [rbp-20h] BYREF
  unsigned __int16 *v14; // [rsp+80h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  try
  {
    v14 = NetworkAddr;
    if ( NetworkAddr )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      NetworkAddr = v14;
    }
    String = 0;
    v1 = RpcStringBindingComposeW(
           0,
           (RPC_WSTR)L"ncalrpc",
           NetworkAddr,
           (RPC_WSTR)L"nlaplg",
           (RPC_WSTR)L"Security=Impersonation Dynamic False",
           &String);
    if ( v1 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x15,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\l2manager\\clientlib\\rpcbinding.cpp",
        (const char *)v1,
        Options);
    Binding = 0;
    v2 = RpcBindingFromStringBindingW(String, &Binding);
    if ( v2 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x1F,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\l2manager\\clientlib\\rpcbinding.cpp",
        (const char *)v2,
        Options);
    v3 = RpcBindingSetOption(Binding, 0xBu, 1u);
    if ( v3 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x25,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\l2manager\\clientlib\\rpcbinding.cpp",
        (const char *)v3,
        Options);
    ServerPrincName = 0;
    v4 = RpcMgmtInqServerPrincNameW(Binding, 0xAu, &ServerPrincName);
    if ( v4 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x29,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\l2manager\\clientlib\\rpcbinding.cpp",
        (const char *)v4,
        Options);
    v5 = RpcBindingSetAuthInfoW(Binding, ServerPrincName, 6u, 0xAu, 0, 0);
    if ( v5 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x2F,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\l2manager\\clientlib\\rpcbinding.cpp",
        (const char *)v5,
        Optionsa);
    v6 = Binding;
    RpcStringFreeW(&ServerPrincName);
    if ( String )
      RpcStringFreeW(&String);
    result = v6;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x36,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\l2manager\\clientlib\\rpcbinding.cpp",
      v7);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800c8240  mov     r11, rsp
0x1800c8243  push    rbx
0x1800c8244  sub     rsp, 90h
0x1800c824b  mov     rax, cs:__security_cookie
0x1800c8252  xor     rax, rsp
0x1800c8255  mov     [rsp+98h+var_10], rax
0x1800c825d  mov     [r11-18h], rcx
0x1800c8261  test    rcx, rcx
0x1800c8264  jz      short loc_1800C8273
0x1800c8266  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800c826b  mov     rcx, [rsp+98h+var_18]
0x1800c8273  mov     [rsp+98h+String], 0
0x1800c827c  lea     rax, [rsp+98h+String]
0x1800c8281  mov     [rsp+98h+StringBinding], rax; StringBinding
0x1800c8286  lea     rax, Options; "Security=Impersonation Dynamic False"
0x1800c828d  mov     [rsp+98h+Options], rax; unsigned int
0x1800c8292  lea     r9, aNlaplg; "nlaplg"
0x1800c8299  mov     r8, rcx; NetworkAddr
0x1800c829c  lea     rdx, ProtSeq; "ncalrpc"
0x1800c82a3  xor     ecx, ecx; ObjUuid
0x1800c82a5  call    cs:__imp_RpcStringBindingComposeW
0x1800c82ab  mov     rcx, [rsp+98h]; this
0x1800c82b3  test    eax, eax
0x1800c82b5  jnz     loc_1800C83F0
0x1800c82bb  lea     rax, [rsp+98h+String]
0x1800c82c0  mov     [rsp+98h+var_68], rax
0x1800c82c5  mov     [rsp+98h+var_60], 1
0x1800c82ca  mov     [rsp+98h+Binding], 0
0x1800c82d3  lea     rdx, [rsp+98h+Binding]; Binding
0x1800c82d8  mov     rcx, [rsp+98h+String]; StringBinding
0x1800c82dd  call    cs:__imp_RpcBindingFromStringBindingW
0x1800c82e3  mov     rcx, [rsp+98h]; this
0x1800c82eb  test    eax, eax
0x1800c82ed  jnz     loc_1800C8405
0x1800c82f3  lea     rax, [rsp+98h+var_18]
0x1800c82fb  mov     [rsp+98h+var_48], rax
0x1800c8300  lea     rax, [rsp+98h+Binding]
0x1800c8305  mov     [rsp+98h+var_40], rax
0x1800c830a  mov     [rsp+98h+var_38], 1
0x1800c830f  mov     edx, 0Bh; option
0x1800c8314  lea     r8d, [rdx-0Ah]; optionValue
0x1800c8318  mov     rcx, [rsp+98h+Binding]; hBinding
0x1800c831d  call    cs:__imp_RpcBindingSetOption
0x1800c8323  mov     rcx, [rsp+98h]; this
0x1800c832b  test    eax, eax
0x1800c832d  jnz     loc_1800C841A
0x1800c8333  mov     [rsp+98h+ServerPrincName], 0
0x1800c833c  lea     r8, [rsp+98h+ServerPrincName]; ServerPrincName
0x1800c8341  mov     ebx, 0Ah
0x1800c8346  mov     edx, ebx; AuthnSvc
0x1800c8348  mov     rcx, [rsp+98h+Binding]; Binding
0x1800c834d  call    cs:__imp_RpcMgmtInqServerPrincNameW
0x1800c8353  mov     rcx, [rsp+98h]; this
0x1800c835b  test    eax, eax
0x1800c835d  jnz     loc_1800C842E
0x1800c8363  lea     rax, [rsp+98h+ServerPrincName]
0x1800c8368  mov     [rsp+98h+var_58], rax
0x1800c836d  mov     [rsp+98h+var_50], 1
0x1800c8372  mov     dword ptr [rsp+98h+StringBinding], 0; AuthzSvc
0x1800c837a  mov     [rsp+98h+Options], 0; unsigned int
0x1800c8383  mov     r9d, ebx; AuthnSvc
0x1800c8386  mov     r8d, 6; AuthnLevel
0x1800c838c  mov     rdx, [rsp+98h+ServerPrincName]; ServerPrincName
0x1800c8391  mov     rcx, [rsp+98h+Binding]; Binding
0x1800c8396  call    cs:__imp_RpcBindingSetAuthInfoW
0x1800c839c  mov     rcx, [rsp+98h]; this
0x1800c83a4  test    eax, eax
0x1800c83a6  jnz     loc_1800C8441
0x1800c83ac  mov     rbx, [rsp+98h+Binding]
0x1800c83b1  lea     rcx, [rsp+98h+ServerPrincName]; String
0x1800c83b6  call    cs:__imp_RpcStringFreeW
0x1800c83bc  nop
0x1800c83bd  cmp     [rsp+98h+String], 0
0x1800c83c3  jz      short loc_1800C83D0
0x1800c83c5  lea     rcx, [rsp+98h+String]; String
0x1800c83ca  call    cs:__imp_RpcStringFreeW
0x1800c83d0  mov     rax, rbx
0x1800c83d3  jmp     short loc_1800C83D7
0x1800c83d5  xor     eax, eax
0x1800c83d7  mov     rcx, [rsp+98h+var_10]
0x1800c83df  xor     rcx, rsp; StackCookie
0x1800c83e2  call    __security_check_cookie
0x1800c83e7  add     rsp, 90h
0x1800c83ee  pop     rbx
0x1800c83ef  retn
0x1800c83f0  mov     r9d, eax; char *
0x1800c83f3  lea     r8, aOnecoreNetNetp_0; "onecore\\net\\netprofiles\\service\\src"...
0x1800c83fa  mov     edx, 15h; void *
0x1800c83ff  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800c8405  mov     r9d, eax; char *
0x1800c8408  lea     r8, aOnecoreNetNetp_0; "onecore\\net\\netprofiles\\service\\src"...
0x1800c840f  mov     edx, 1Fh; void *
0x1800c8414  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800c841a  mov     r9d, eax; char *
0x1800c841d  lea     r8, aOnecoreNetNetp_0; "onecore\\net\\netprofiles\\service\\src"...
0x1800c8424  mov     edx, 25h ; '%'; void *
0x1800c8429  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800c842e  mov     r9d, eax; char *
0x1800c8431  lea     r8, aOnecoreNetNetp_0; "onecore\\net\\netprofiles\\service\\src"...
0x1800c8438  lea     edx, [rbx+1Fh]; void *
0x1800c843b  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800c8441  mov     r9d, eax; char *
0x1800c8444  lea     r8, aOnecoreNetNetp_0; "onecore\\net\\netprofiles\\service\\src"...
0x1800c844b  mov     edx, 2Fh ; '/'; void *
0x1800c8450  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
