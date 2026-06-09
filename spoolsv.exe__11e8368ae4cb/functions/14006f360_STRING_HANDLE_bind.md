# STRING_HANDLE_bind

- ea: `0x14006f360`
- end: `0x14006f556`
- name: `STRING_HANDLE_bind`
- size: `502`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000a620`
- `0x14000ad50`
- `0x14002abc0`
- `0x14002b3c0`
- `0x1400573bc`
- `0x140058898`
- `0x140058a9c`
- `0x140058dd4`
- `0x140058ec4`
- `0x1400592dc`
- `0x14006f360`

## import_xrefs

- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x14006f501`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x14006f501`
- `RPCRT4!RpcStringBindingComposeW` at `0x14006f45c`
- `RPCRT4!RpcStringBindingComposeW` at `0x14006f45c`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x14006f47e`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x14006f47e`
- `RPCRT4!RpcStringFreeW` at `0x14006f516`
- `RPCRT4!RpcStringFreeW` at `0x14006f516`

## string_xrefs

- `0x14006f437`: `Security=Impersonation Static True`

## pseudocode

```c
RPC_BINDING_HANDLE __fastcall STRING_HANDLE_bind(unsigned __int64 a1)
{
  const unsigned __int16 *v1; // r8
  unsigned __int64 v2; // rbx
  unsigned __int64 v3; // rbx
  unsigned __int16 *Options; // rbx
  unsigned __int16 *v5; // rsi
  unsigned __int16 *RpcOverTcpPortString; // rax
  unsigned __int16 *v7; // rdi
  RPC_STATUS v8; // ebx
  RPC_STATUS v9; // ebx
  int v10; // ebx
  unsigned __int16 *ServerPrincipalName; // rdi
  RPC_WSTR String; // [rsp+40h] [rbp-C0h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+48h] [rbp-B8h] BYREF
  RPC_SECURITY_QOS SecurityQOS[3]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 NetworkAddr[264]; // [rsp+80h] [rbp-80h] BYREF

  String = 0;
  Binding = 0;
  if ( !a1 || *(_WORD *)a1 != 92 || *(_WORD *)(a1 + 2) != 92 )
    return 0;
  v1 = (const unsigned __int16 *)(a1 + 4);
  LODWORD(a1) = 0;
  if ( *v1 )
  {
    do
    {
      if ( v1[(unsigned int)a1] == 92 )
        break;
      a1 = (unsigned int)(a1 + 1);
    }
    while ( v1[a1] );
    if ( (unsigned int)a1 >= 0x106 )
      return 0;
  }
  v2 = (unsigned int)a1;
  StringCchCopyNW(NetworkAddr, 0x106u, v1, (unsigned int)a1);
  v3 = v2;
  if ( v3 >= 262 )
    _report_rangecheckfailure();
  NetworkAddr[v3] = 0;
  if ( (unsigned int)UseNamedPipeProtocol() )
  {
    v5 = L"ncacn_np";
    RpcOverTcpPortString = (unsigned __int16 *)AllocSplStr(L"\\pipe\\spoolss");
    Options = L"Security=Impersonation Static True";
  }
  else
  {
    Options = 0;
    v5 = L"ncacn_ip_tcp";
    RpcOverTcpPortString = GetRpcOverTcpPortString();
  }
  v7 = RpcOverTcpPortString;
  v8 = RpcStringBindingComposeW(0, v5, NetworkAddr, RpcOverTcpPortString, Options, &String);
  DllFreeSplStr(v7);
  if ( v8 )
    return 0;
  v9 = RpcBindingFromStringBindingW(String, &Binding);
  if ( !v9 )
  {
    if ( (unsigned int)IsAuthenticationRequiredForRpc() )
    {
      SecurityQOS[0].Version = 3;
      memset(&SecurityQOS[1].Capabilities, 0, 20);
      *(_QWORD *)&SecurityQOS[0].ImpersonationType = 3;
      *(_QWORD *)&SecurityQOS[0].Capabilities = 1;
      v10 = ForceKerberosAuthentication();
      ServerPrincipalName = GetServerPrincipalName(NetworkAddr);
      v9 = RpcBindingSetAuthInfoExW(Binding, ServerPrincipalName, 6u, v10 != 0 ? 16 : 9, 0, -(v10 != 0), SecurityQOS);
      DllFreeSplStr(ServerPrincipalName);
    }
  }
  RpcStringFreeW(&String);
  if ( v9 )
    return 0;
  else
    return Binding;
}

```

## disassembly

```asm
0x14006f360  mov     [rsp-8+arg_8], rbx
0x14006f365  mov     [rsp-8+arg_10], rsi
0x14006f36a  push    rbp
0x14006f36b  push    rdi
0x14006f36c  push    r14
0x14006f36e  lea     rbp, [rsp-1A0h]
0x14006f376  sub     rsp, 2A0h
0x14006f37d  mov     rax, cs:__security_cookie
0x14006f384  xor     rax, rsp
0x14006f387  mov     [rbp+1B0h+var_20], rax
0x14006f38e  xor     r14d, r14d
0x14006f391  mov     [rsp+2B0h+String], r14
0x14006f396  mov     [rsp+2B0h+Binding], r14
0x14006f39b  test    rcx, rcx
0x14006f39e  jz      loc_14006F52D
0x14006f3a4  cmp     word ptr [rcx], 5Ch ; '\'
0x14006f3a8  jnz     loc_14006F52D
0x14006f3ae  cmp     word ptr [rcx+2], 5Ch ; '\'
0x14006f3b3  jnz     loc_14006F52D
0x14006f3b9  lea     r8, [rcx+4]; unsigned __int16 *
0x14006f3bd  mov     edx, 106h; unsigned __int64
0x14006f3c2  mov     ecx, r14d
0x14006f3c5  cmp     [r8], r14w
0x14006f3c9  jz      short loc_14006F3E6
0x14006f3cb  mov     eax, ecx
0x14006f3cd  cmp     word ptr [r8+rax*2], 5Ch ; '\'
0x14006f3d3  jz      short loc_14006F3DE
0x14006f3d5  inc     ecx
0x14006f3d7  cmp     [r8+rcx*2], r14w
0x14006f3dc  jnz     short loc_14006F3CB
0x14006f3de  cmp     ecx, edx
0x14006f3e0  jnb     loc_14006F52D
0x14006f3e6  mov     ebx, ecx
0x14006f3e8  mov     r9d, ecx; unsigned __int64
0x14006f3eb  lea     rcx, [rbp+1B0h+NetworkAddr]; unsigned __int16 *
0x14006f3ef  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x14006f3f4  add     rbx, rbx
0x14006f3f7  cmp     rbx, 20Ch
0x14006f3fe  jnb     loc_14006F527
0x14006f404  mov     [rbp+rbx+1B0h+NetworkAddr], r14w
0x14006f40a  call    ?UseNamedPipeProtocol@@YAHXZ; UseNamedPipeProtocol(void)
0x14006f40f  test    eax, eax
0x14006f411  jnz     short loc_14006F424
0x14006f413  mov     rbx, r14
0x14006f416  lea     rsi, ProtSeq; "ncacn_ip_tcp"
0x14006f41d  call    ?GetRpcOverTcpPortString@@YAPEAGXZ; GetRpcOverTcpPortString(void)
0x14006f422  jmp     short loc_14006F43E
0x14006f424  lea     rcx, aPipeSpoolss; "\\pipe\\spoolss"
0x14006f42b  lea     rsi, aNcacnNp; "ncacn_np"
0x14006f432  call    AllocSplStr
0x14006f437  lea     rbx, aSecurityImpers; "Security=Impersonation Static True"
0x14006f43e  mov     rdi, rax
0x14006f441  lea     r8, [rbp+1B0h+NetworkAddr]; NetworkAddr
0x14006f445  lea     rax, [rsp+2B0h+String]
0x14006f44a  mov     r9, rdi; Endpoint
0x14006f44d  mov     [rsp+2B0h+StringBinding], rax; StringBinding
0x14006f452  mov     rdx, rsi; ProtSeq
0x14006f455  xor     ecx, ecx; ObjUuid
0x14006f457  mov     [rsp+2B0h+Options], rbx; Options
0x14006f45c  call    cs:__imp_RpcStringBindingComposeW
0x14006f462  mov     rcx, rdi
0x14006f465  mov     ebx, eax
0x14006f467  call    DllFreeSplStr
0x14006f46c  test    ebx, ebx
0x14006f46e  jnz     loc_14006F52D
0x14006f474  mov     rcx, [rsp+2B0h+String]; StringBinding
0x14006f479  lea     rdx, [rsp+2B0h+Binding]; Binding
0x14006f47e  call    cs:__imp_RpcBindingFromStringBindingW
0x14006f484  mov     ebx, eax
0x14006f486  test    eax, eax
0x14006f488  jnz     loc_14006F511
0x14006f48e  call    ?IsAuthenticationRequiredForRpc@@YAHXZ; IsAuthenticationRequiredForRpc(void)
0x14006f493  test    eax, eax
0x14006f495  jz      short loc_14006F511
0x14006f497  lea     eax, [rbx+3]
0x14006f49a  mov     [rsp+2B0h+var_23C], r14d
0x14006f49f  xorps   xmm0, xmm0
0x14006f4a2  mov     dword ptr [rsp+2B0h+var_260], eax
0x14006f4a6  movdqu  [rsp+2B0h+var_24C], xmm0
0x14006f4ac  mov     qword ptr [rsp+2B0h+var_260+0Ch], rax
0x14006f4b1  mov     qword ptr [rsp+2B0h+var_260+4], 1
0x14006f4ba  call    ?ForceKerberosAuthentication@@YAHXZ; ForceKerberosAuthentication(void)
0x14006f4bf  lea     rcx, [rbp+1B0h+NetworkAddr]; unsigned __int16 *
0x14006f4c3  mov     ebx, eax
0x14006f4c5  call    ?GetServerPrincipalName@@YAPEAGPEAG@Z; GetServerPrincipalName(ushort *)
0x14006f4ca  mov     ecx, ebx
0x14006f4cc  mov     rdi, rax
0x14006f4cf  neg     ecx
0x14006f4d1  lea     rax, [rsp+2B0h+var_260]
0x14006f4d6  mov     rcx, [rsp+2B0h+Binding]; Binding
0x14006f4db  mov     r8d, 6; AuthnLevel
0x14006f4e1  sbb     edx, edx
0x14006f4e3  mov     [rsp+2B0h+SecurityQOS], rax; SecurityQOS
0x14006f4e8  mov     dword ptr [rsp+2B0h+StringBinding], edx; AuthzSvc
0x14006f4ec  neg     ebx
0x14006f4ee  mov     rdx, rdi; ServerPrincName
0x14006f4f1  mov     [rsp+2B0h+Options], r14; AuthIdentity
0x14006f4f6  sbb     r9d, r9d
0x14006f4f9  and     r9d, 7
0x14006f4fd  add     r9d, 9; AuthnSvc
0x14006f501  call    cs:__imp_RpcBindingSetAuthInfoExW
0x14006f507  mov     rcx, rdi
0x14006f50a  mov     ebx, eax
0x14006f50c  call    DllFreeSplStr
0x14006f511  lea     rcx, [rsp+2B0h+String]; String
0x14006f516  call    cs:__imp_RpcStringFreeW
0x14006f51c  test    ebx, ebx
0x14006f51e  jnz     short loc_14006F52D
0x14006f520  mov     rax, [rsp+2B0h+Binding]
0x14006f525  jmp     short loc_14006F52F
0x14006f527  call    __report_rangecheckfailure
0x14006f52d  xor     eax, eax
0x14006f52f  mov     rcx, [rbp+1B0h+var_20]
0x14006f536  xor     rcx, rsp; StackCookie
0x14006f539  call    __security_check_cookie
0x14006f53e  lea     r11, [rsp+2B0h+var_10]
0x14006f546  mov     rbx, [r11+28h]
0x14006f54a  mov     rsi, [r11+30h]
0x14006f54e  mov     rsp, r11
0x14006f551  pop     r14
0x14006f553  pop     rdi
0x14006f554  pop     rbp
0x14006f555  retn
```
